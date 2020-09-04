---
title: ファイルへの非同期アクセス (C#)
description: C# で非同期機能を使用してファイルにアクセスする方法について説明します。 コールバックを使用したり、複数のメソッドでコードを分割したりせずに、非同期メソッドを呼び出すことができます。
ms.date: 08/19/2020
ms.assetid: bb018fea-5313-4c80-ab3f-7c24b2145bd9
ms.openlocfilehash: 9a8db6004e8fff2cb39f0c350b403b56ea619e54
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812043"
---
# <a name="asynchronous-file-access-c"></a>ファイルへの非同期アクセス (C#)

ファイルにアクセスする際に非同期機能を使用できます。 非同期機能を使用すると、コールバックの使用や複数のメソッドまたはラムダ式へのコードの分割を行わずに、非同期メソッドを呼び出すことができます。 同期コードを非同期コードにするには、同期メソッドの代わりに非同期メソッドを呼び出して、コードにいくつかのキーワードを追加するだけで済みます。

ファイル アクセスの呼び出しに非同期性を適用する利点には、次のようなものがあります。

> [!div class="checklist"]
>
> - 非同期性により、UI アプリケーションの応答性が向上します。非同期処理を開始した UI スレッドが他の処理を実行できるためです。 UI スレッドが、時間のかかるコード、たとえば 50 ミリ秒を超えるコードを実行する必要がある場合、I/O が完了して、UI スレッドがキーボードやマウス入力などのイベントを再度処理できるようになるまで、UI が停止することがあります。
> - 非同期性を適用すると、スレッドの必要性が軽減され、ASP.NET などのサーバー ベースのアプリケーションのスケーラビリティが向上します。 アプリケーションが応答ごとに専用スレッドを使用している場合、1,000 個の要求を同時に処理するには、1,000 個のスレッドが必要です。 非同期操作では、待機中にスレッドを使用する必要はほとんどありません。 既存の I/O 完了スレッドが最後に少しだけ使用されます。
> - 現状ではファイル アクセス操作の待機時間が非常に短くても、将来に大幅に長くなる可能性があります。 たとえば、地球の裏側にあるサーバーにファイルが移動される場合があります。
> - 非同期機能の使用に伴うオーバーヘッドはわずかです。
> - 非同期タスクは簡単に並列実行できます。

## <a name="use-appropriate-classes"></a>適切なクラスを使用する

このトピックの簡単な例では、<xref:System.IO.File.WriteAllTextAsync%2A?displayProperty=nameWithType> と <xref:System.IO.File.ReadAllTextAsync%2A?displayProperty=nameWithType> について説明します。 ファイル I/O 操作を有限制御するには、<xref:System.IO.FileStream> クラスを使用します。これには、オペレーティング システムのレベルで非同期 I/O を発生させるオプションがあります。 このオプションを使用することにより、多くの場合、スレッド プール スレッドがブロックされるのを回避できます。 このオプションを有効にするには、コンストラクター呼び出しで `useAsync=true` または `options=FileOptions.Asynchronous` 引数を指定します。

ファイル パスを指定して <xref:System.IO.StreamReader> と <xref:System.IO.StreamWriter> を直接開いた場合、それらでこのオプションを使用することはできません。 一方、<xref:System.IO.FileStream> クラスによって開かれた <xref:System.IO.Stream> を使用する場合は、このオプションを使用できます。 UI アプリでは、スレッド プール スレッドがブロックされても、非同期呼び出しは高速になります。これは、UI スレッドは待機中にブロックされないためです。

## <a name="write-text"></a>テキストを書き込む

次の例では、ファイルにテキストを書き込みます。 各 await ステートメントに達すると、メソッドは直ちに終了します。 ファイル I/O が完了すると、メソッドは await ステートメントの後のステートメントから再開します。 async 修飾子は、await ステートメントを使用するメソッドの定義に含まれます。

### <a name="simple-example"></a>簡単な例

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleWrite":::

### <a name="finite-control-example"></a>有限制御の例

:::code language="csharp" source="snippets/file-access/Program.cs" id="WriteText":::

元の例には `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);` ステートメントがあります。これは、次の 2 つのステートメントの省略形です。

```csharp
Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);
await theTask;
```

最初のステートメントはタスクを返し、ファイル処理を開始します。 await が含まれた 2 番目のステートメントによって、メソッドが直ちに終了し、別のタスクを返します。 ファイル処理が完了すると、await の後のステートメントに実行が戻ります。

## <a name="read-text"></a>テキストを読み取る

次の例では、ファイルからテキストを読み取ります。

### <a name="simple-example"></a>簡単な例

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleRead":::

### <a name="finite-control-example"></a>有限制御の例

テキストはバッファーに格納されます。この例では <xref:System.Text.StringBuilder> に配置されます。 前の例と異なり、await の評価で値が生成されます。 <xref:System.IO.Stream.ReadAsync%2A> メソッドによって <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>> が返されます。処理の完了後、await の評価によって `Int32` 値 `numRead` が生成されます。 詳しくは、「[非同期の戻り値の型 (C#)](async-return-types.md)」をご覧ください。

:::code language="csharp" source="snippets/file-access/Program.cs" id="ReadText":::

## <a name="parallel-asynchronous-io"></a>並列非同期 I/O

次の例では、10 個のテキスト ファイルを記述する並列処理を示します。

### <a name="simple-example"></a>簡単な例

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleParallelWrite":::

### <a name="finite-control-example"></a>有限制御の例

<xref:System.IO.Stream.WriteAsync%2A> メソッドは、ファイルごとにタスクを返します。タスクはタスクの一覧に追加されます。 `await Task.WhenAll(tasks);` ステートメントはメソッドを終了し、すべてのタスクのファイル処理が完了すると、メソッド内で再開します。

この例では、タスクの完了後、`finally` ブロックのすべての <xref:System.IO.FileStream> インスタンスを閉じます。 `using` ステートメントで `FileStream` が作成された場合は、タスクが完了する前に `FileStream` が破棄されることがあります。

パフォーマンスの向上の多くは、非同期処理ではなく並列処理によって実現されます。 非同期性の利点は、複数のスレッドやユーザー インターフェイス スレッドが拘束されない点にあります。

:::code language="csharp" source="snippets/file-access/Program.cs" id="ParallelWriteText":::

<xref:System.IO.Stream.WriteAsync%2A> メソッドと <xref:System.IO.Stream.ReadAsync%2A> メソッドを使用すると、<xref:System.Threading.CancellationToken> を指定して、途中で処理をキャンセルすることができます。 詳細については、「[マネージド スレッドのキャンセル](../../../../standard/threading/cancellation-in-managed-threads.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [Async および Await を使用した非同期プログラミング (C#)](index.md)
- [非同期の戻り値の型 (C#)](async-return-types.md)
