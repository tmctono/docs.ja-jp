---
description: var - C# リファレンス
title: var - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: 303a880a54a79e50515060e0ea28e8d021fa1b76
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141713"
---
# <a name="var-c-reference"></a>var (C# リファレンス)

Visual C# 3.0 以降、メソッド スコープで宣言された変数には暗黙的な "型" `var` を与えることができます。 暗黙的に型指定されたローカル変数では、型を自分で宣言した場合と同様に厳密に型指定されますが、コンパイラが型を決定します。 次の 2 つの `i` の宣言は機能的に等しくなります。

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

詳しくは、「[暗黙的に型指定されるローカル変数](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)」および「[LINQ クエリ操作での型の関係](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)」をご覧ください。

> [!IMPORTANT]
> `var` を null 許容参照型を有効にして使用すると、式の型で null 値が許容されない場合でも、常に null 値を許容する参照型を表します。

## <a name="example"></a>例

次の例は、2 つのクエリ式を示しています。 最初の式では、`var` の使用が許可されますが、必須ではありません。クエリ結果の型を `IEnumerable<string>` として明示的に指定できるためです。 一方、2 つ目の式の `var` では、匿名型のコレクションとしての結果が許され、その型の名前にはコンパイラ自体以外はアクセスできません。 `var` を使うと、結果のために新しいクラスを作成する必要がなくなります。 例 #2 では、`foreach` 繰り返し変数 `item` も暗黙的に型指定する必要があります。

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [C# プログラミング ガイド](../../programming-guide/index.md)
- [暗黙的に型指定されるローカル変数](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
