---
title: let 句 - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: e9e10957e7ebe93a6dea9bbb6233ca7733f68e20
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633462"
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="48c46-102">let 句 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="48c46-102">let clause (C# Reference)</span></span>

<span data-ttu-id="48c46-103">クエリ式では、後続の句で使用するために、サブ式の結果を保存すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="48c46-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="48c46-104">`let` キーワードを使用してこれを行うことができます。これにより新しい範囲変数を作成し、指定した式の結果でそれを初期化します。</span><span class="sxs-lookup"><span data-stu-id="48c46-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="48c46-105">値で初期化されると、範囲変数を使用して別の値を格納することはできません。</span><span class="sxs-lookup"><span data-stu-id="48c46-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="48c46-106">ただし、範囲変数がクエリ可能型を保持している場合、クエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="48c46-106">However, if the range variable holds a queryable type, it can be queried.</span></span>

## <a name="example"></a><span data-ttu-id="48c46-107">例</span><span class="sxs-lookup"><span data-stu-id="48c46-107">Example</span></span>

<span data-ttu-id="48c46-108">次の例で、`let` は 2 つの方法で使用されます。</span><span class="sxs-lookup"><span data-stu-id="48c46-108">In the following example `let` is used in two ways:</span></span>

1. <span data-ttu-id="48c46-109">それ自体を照会できる列挙可能な型を作成します。</span><span class="sxs-lookup"><span data-stu-id="48c46-109">To create an enumerable type that can itself be queried.</span></span>

2. <span data-ttu-id="48c46-110">クエリが値変数 `word` に対して `ToLower` を 1 回のみ呼び出すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="48c46-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="48c46-111">`let` を使用しない場合、`where` 句の各述語内で、`ToLower` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="48c46-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a><span data-ttu-id="48c46-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="48c46-112">See also</span></span>

- [<span data-ttu-id="48c46-113">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="48c46-113">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="48c46-114">クエリ キーワード (LINQ)</span><span class="sxs-lookup"><span data-stu-id="48c46-114">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="48c46-115">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="48c46-115">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)
- [<span data-ttu-id="48c46-116">C# の LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="48c46-116">Getting Started with LINQ in C#</span></span>](../../programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="48c46-117">クエリ式の例外の処理</span><span class="sxs-lookup"><span data-stu-id="48c46-117">Handle exceptions in query expressions</span></span>](../../linq/handle-exceptions-in-query-expressions.md)
