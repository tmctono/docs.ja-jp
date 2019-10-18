---
title: orderby 句 - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: b62634c0f61e17c046cd474670fddf437287ab7a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634104"
---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="d4584-102">orderby 句 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d4584-102">orderby clause (C# Reference)</span></span>

<span data-ttu-id="d4584-103">クエリ式では、`orderby` 句によって返されるシーケンスまたはサブシーケンス (グループ) が昇順または降順で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="d4584-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="d4584-104">2 番目の並べ替え操作を 1 つ以上実行するために、複数のキーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d4584-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="d4584-105">並べ替えは、要素の型の既定の比較演算子によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="d4584-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="d4584-106">既定の並べ替え順序は昇順です。</span><span class="sxs-lookup"><span data-stu-id="d4584-106">The default sort order is ascending.</span></span> <span data-ttu-id="d4584-107">カスタムの比較演算子を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4584-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="d4584-108">ただしこれは、メソッド ベースの構文を使用する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4584-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="d4584-109">詳細については、[データの並べ替え](../../programming-guide/concepts/linq/sorting-data.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4584-109">For more information, see [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md).</span></span>

## <a name="example"></a><span data-ttu-id="d4584-110">例</span><span class="sxs-lookup"><span data-stu-id="d4584-110">Example</span></span>

<span data-ttu-id="d4584-111">次の例では、最初のクエリが A から始まるアルファベット順で単語を並べ替え、2 番目のクエリが同じ単語を降順で並べ替えます</span><span class="sxs-lookup"><span data-stu-id="d4584-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="d4584-112">(`ascending` キーワードは、既定の並べ替え値で、省略可能です)。</span><span class="sxs-lookup"><span data-stu-id="d4584-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a><span data-ttu-id="d4584-113">例</span><span class="sxs-lookup"><span data-stu-id="d4584-113">Example</span></span>

<span data-ttu-id="d4584-114">次の例では、学生の姓で最初の並べ替えを実行し、学生の名で 2 番目の並べ替えを実行します。</span><span class="sxs-lookup"><span data-stu-id="d4584-114">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a><span data-ttu-id="d4584-115">解説</span><span class="sxs-lookup"><span data-stu-id="d4584-115">Remarks</span></span>

<span data-ttu-id="d4584-116">コンパイル時に、`orderby` 句は <xref:System.Linq.Enumerable.OrderBy%2A> メソッドの呼び出しに変換されます。</span><span class="sxs-lookup"><span data-stu-id="d4584-116">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="d4584-117">`orderby` 句内の複数のキーは、<xref:System.Linq.Enumerable.ThenBy%2A> メソッドの呼び出しに変換されます。</span><span class="sxs-lookup"><span data-stu-id="d4584-117">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4584-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4584-118">See also</span></span>

- [<span data-ttu-id="d4584-119">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d4584-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d4584-120">クエリ キーワード (LINQ)</span><span class="sxs-lookup"><span data-stu-id="d4584-120">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="d4584-121">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="d4584-121">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)
- [<span data-ttu-id="d4584-122">group 句</span><span class="sxs-lookup"><span data-stu-id="d4584-122">group clause</span></span>](group-clause.md)
- [<span data-ttu-id="d4584-123">C# の LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="d4584-123">Getting Started with LINQ in C#</span></span>](../../programming-guide/concepts/linq/getting-started-with-linq.md)
