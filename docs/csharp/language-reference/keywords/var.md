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
# <a name="var-c-reference"></a><span data-ttu-id="18940-103">var (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="18940-103">var (C# Reference)</span></span>

<span data-ttu-id="18940-104">Visual C# 3.0 以降、メソッド スコープで宣言された変数には暗黙的な "型" `var` を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="18940-104">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="18940-105">暗黙的に型指定されたローカル変数では、型を自分で宣言した場合と同様に厳密に型指定されますが、コンパイラが型を決定します。</span><span class="sxs-lookup"><span data-stu-id="18940-105">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="18940-106">次の 2 つの `i` の宣言は機能的に等しくなります。</span><span class="sxs-lookup"><span data-stu-id="18940-106">The following two declarations of `i` are functionally equivalent:</span></span>

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

<span data-ttu-id="18940-107">詳しくは、「[暗黙的に型指定されるローカル変数](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)」および「[LINQ クエリ操作での型の関係](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="18940-107">For more information, see [Implicitly Typed Local Variables](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18940-108">`var` を null 許容参照型を有効にして使用すると、式の型で null 値が許容されない場合でも、常に null 値を許容する参照型を表します。</span><span class="sxs-lookup"><span data-stu-id="18940-108">When `var` is used with nullable reference types enabled, it always implies a nullable reference type even if the expression type isn't nullable.</span></span>

## <a name="example"></a><span data-ttu-id="18940-109">例</span><span class="sxs-lookup"><span data-stu-id="18940-109">Example</span></span>

<span data-ttu-id="18940-110">次の例は、2 つのクエリ式を示しています。</span><span class="sxs-lookup"><span data-stu-id="18940-110">The following example shows two query expressions.</span></span> <span data-ttu-id="18940-111">最初の式では、`var` の使用が許可されますが、必須ではありません。クエリ結果の型を `IEnumerable<string>` として明示的に指定できるためです。</span><span class="sxs-lookup"><span data-stu-id="18940-111">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="18940-112">一方、2 つ目の式の `var` では、匿名型のコレクションとしての結果が許され、その型の名前にはコンパイラ自体以外はアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="18940-112">However, in the second expression, `var` allows the result to be a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="18940-113">`var` を使うと、結果のために新しいクラスを作成する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="18940-113">Use of `var` eliminates the requirement to create a new class for the result.</span></span> <span data-ttu-id="18940-114">例 #2 では、`foreach` 繰り返し変数 `item` も暗黙的に型指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18940-114">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a><span data-ttu-id="18940-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="18940-115">See also</span></span>

- [<span data-ttu-id="18940-116">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="18940-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="18940-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="18940-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="18940-118">暗黙的に型指定されるローカル変数</span><span class="sxs-lookup"><span data-stu-id="18940-118">Implicitly Typed Local Variables</span></span>](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
