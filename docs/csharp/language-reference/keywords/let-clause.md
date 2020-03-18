---
title: let 句 - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: 3ce2b663e5678de6b53db610b489f85ab1427b9d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173589"
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="10d81-102">let 句 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="10d81-102">let clause (C# Reference)</span></span>

<span data-ttu-id="10d81-103">クエリ式では、後続の句で使用するために、サブ式の結果を保存すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="10d81-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="10d81-104">`let` キーワードを使用してこれを行うことができます。これにより新しい範囲変数を作成し、指定した式の結果でそれを初期化します。</span><span class="sxs-lookup"><span data-stu-id="10d81-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="10d81-105">値で初期化されると、範囲変数を使用して別の値を格納することはできません。</span><span class="sxs-lookup"><span data-stu-id="10d81-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="10d81-106">ただし、範囲変数がクエリ可能型を保持している場合、クエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="10d81-106">However, if the range variable holds a queryable type, it can be queried.</span></span>

## <a name="example"></a><span data-ttu-id="10d81-107">例</span><span class="sxs-lookup"><span data-stu-id="10d81-107">Example</span></span>

<span data-ttu-id="10d81-108">次の例で、`let` は 2 つの方法で使用されます。</span><span class="sxs-lookup"><span data-stu-id="10d81-108">In the following example `let` is used in two ways:</span></span>

1. <span data-ttu-id="10d81-109">それ自体を照会できる列挙可能な型を作成します。</span><span class="sxs-lookup"><span data-stu-id="10d81-109">To create an enumerable type that can itself be queried.</span></span>

2. <span data-ttu-id="10d81-110">クエリが値変数 `ToLower` に対して `word` を 1 回のみ呼び出すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="10d81-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="10d81-111">`let` を使用しない場合、`ToLower` 句の各述語内で、`where` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="10d81-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a><span data-ttu-id="10d81-112">参照</span><span class="sxs-lookup"><span data-stu-id="10d81-112">See also</span></span>

- [<span data-ttu-id="10d81-113">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="10d81-113">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="10d81-114">クエリ キーワード (LINQ)</span><span class="sxs-lookup"><span data-stu-id="10d81-114">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="10d81-115">C# での LINQ</span><span class="sxs-lookup"><span data-stu-id="10d81-115">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="10d81-116">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="10d81-116">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="10d81-117">クエリ式の例外の処理</span><span class="sxs-lookup"><span data-stu-id="10d81-117">Handle exceptions in query expressions</span></span>](../../linq/handle-exceptions-in-query-expressions.md)
