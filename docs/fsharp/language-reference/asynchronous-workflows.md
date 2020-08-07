---
title: 非同期ワークフロー
description: 'F # プログラミング言語でのサポートについて説明します。これは、他の作業の実行をブロックすることなく実行される計算を非同期に実行します。'
ms.date: 05/16/2016
ms.openlocfilehash: 3bc24639b329401a8f944488e974f0739d4680df
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855466"
---
# <a name="asynchronous-workflows"></a>非同期ワークフロー

この記事では、計算を非同期的に実行する F # のサポートについて説明します。つまり、他の作業の実行をブロックすることはありません。 たとえば、非同期計算を使用して、アプリケーションが他の作業を実行するときにユーザーに応答し続ける Ui を持つアプリケーションを作成できます。

> [!NOTE]
> F # の docs.microsoft.com API リファレンスが完全ではありません。 壊れたリンクが見つかった場合は、代わりに[F # コアライブラリのドキュメント](https://fsharp.github.io/fsharp-core-docs/)を参照してください。

## <a name="syntax"></a>構文

```fsharp
async { expression }
```

## <a name="remarks"></a>Remarks

前の構文では、によって表される計算 `expression` が非同期的に実行されるように設定されています。つまり、非同期スリープ操作、i/o、およびその他の非同期操作が実行されるときに、現在の計算スレッドをブロックしません。 非同期計算は、多くの場合、現在のスレッドで実行を継続しながらバックグラウンドスレッドで開始されます。 式の型はです `Async<'T>` 。ここで、 `'T` は、 `return` キーワードが使用されている場合に、式によって返される型です。 このような式のコードは、*非同期ブロック*または非同期*ブロック*と呼ばれます。

非同期プログラミングにはさまざまな方法があり、クラスには [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7) いくつかのシナリオをサポートするメソッドが用意されています。 一般的な方法では、 `Async` 非同期的に実行する計算または計算を表すオブジェクトを作成し、トリガー関数のいずれかを使用して、これらの計算を開始します。 さまざまなトリガー関数は、非同期計算を実行するさまざまな方法を提供します。どちらを使用するかは、現在のスレッド、バックグラウンドスレッド、.NET Framework タスクオブジェクトを使用するかどうか、および計算が終了したときに実行する必要のある継続関数があるかどうかによって異なります。 たとえば、現在のスレッドで非同期計算を開始するには、を使用し [`Async.StartImmediate`](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3) ます。 UI スレッドから非同期計算を開始する場合は、キーストロークやマウスアクティビティなどのユーザー操作を処理するメインイベントループをブロックしないため、アプリケーションの応答性が維持されます。

## <a name="asynchronous-binding-by-using-let"></a>Let を使用した非同期バインド

非同期ワークフローでは、一部の式と操作は同期的であり、一部の式と操作は、非同期的に結果を返すように設計された、より長い計算です。 通常のバインディングではなく、メソッドを非同期的に呼び出す場合は、を `let` 使用し `let!` ます。 の効果は、 `let!` 計算の実行中に、他の計算やスレッドで実行を継続できるようにすることです。 バインディングの右側から制御が戻った後、 `let!` 非同期ワークフローの残りの部分は実行を再開します。

次のコードは、との違いを示して `let` `let!` います。 を使用するコード行で `let` は、またはなどを使用して後で実行できるオブジェクトとして非同期計算を作成し `Async.StartImmediate` [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) ます。 を使用するコード行によって計算が開始され、その `let!` 後、結果が使用可能になるまでスレッドが中断されます。

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

に加えて `let!` 、を使用して非同期バインディングを実行することもでき `use!` ます。 との違い `let!` は、との違い `use!` と同じです `let` `use` 。 の場合 `use!` 、オブジェクトは現在のスコープの終了時に破棄されます。 現在のリリースの F # 言語では、がの場合でも、値を null に初期化することはできないことに注意して `use!` `use` ください。

## <a name="asynchronous-primitives"></a>非同期プリミティブ

1つの非同期タスクを実行し、その結果を返すメソッドは、*非同期プリミティブ*と呼ばれ、専用に設計されてい `let!` ます。 いくつかの非同期プリミティブは、F # コアライブラリで定義されています。 このような Web アプリケーションの2つのメソッドは、モジュールで定義されて [`Microsoft.FSharp.Control.WebExtensions`](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003) [`WebRequest.AsyncGetResponse`](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c) [`WebClient.AsyncDownloadString`](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a) います。 どちらのプリミティブも、URL を指定して Web ページからデータをダウンロードします。 `AsyncGetResponse`オブジェクトを生成 `System.Net.WebResponse` し、 `AsyncDownloadString` Web ページの HTML を表す文字列を生成します。

非同期 i/o 操作のためのいくつかのプリミティブは、モジュールに含まれてい [`Microsoft.FSharp.Control.CommonExtensions`](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396) ます。 クラスの拡張メソッド `System.IO.Stream` は [`Stream.AsyncRead`](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e) 、と [`Stream.AsyncWrite`](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618) です。

また、完全な本文が非同期ブロックで囲まれた関数を定義することで、独自の非同期プリミティブを作成することもできます。

F # の非同期プログラミングモデルを使用して他の非同期モデル用にデザインされた .NET Framework で非同期メソッドを使用するには、F # オブジェクトを返す関数を作成し `Async` ます。 F # ライブラリには、これを簡単に実行できる関数が用意されています。

非同期ワークフローの使用例を次に示します。[非同期クラス](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)のメソッドに関するドキュメントには、他にも多くのものがあります。

この例では、非同期ワークフローを使用して並列で計算を実行する方法を示します。

次のコード例では、関数は `fetchAsync` Web 要求から返された HTML テキストを取得します。 関数には、 `fetchAsync` 非同期のコードブロックが含まれています。 非同期プリミティブの結果にバインドする場合は、次のようにし [`AsyncDownloadString`](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a) ます。 let ではなくを使用します。

関数を使用し [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) て非同期操作を実行し、その結果を待機します。 例として、関数を関数と共に使用することで、複数の非同期操作を並列で実行でき [`Async.Parallel`](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4) `Async.RunSynchronously` ます。 関数は、 `Async.Parallel` オブジェクトの一覧を取得し `Async` 、各タスクオブジェクトのコードを `Async` 並列で実行するように設定し、 `Async` 並列計算を表すオブジェクトを返します。 1回の操作と同じように、を呼び出して `Async.RunSynchronously` 実行を開始します。

関数は、 `runAll` 3 つの非同期ワークフローを並列で起動し、すべてが完了するまで待機します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>関連項目

- [F# 言語リファレンス](index.md)
- [コンピュテーション式](computation-expressions.md)
- [Control. Async クラス](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
