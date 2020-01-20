---
title: 量指定子操作 (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 5c931e0971a2ae7970415905be8772a64a82ee39
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635484"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="d0f71-102">量指定子操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="d0f71-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="d0f71-103">量指定子操作は、シーケンス内の要素の一部またはすべてが条件を満たしているかどうかを示す <xref:System.Boolean> 値を返します。</span><span class="sxs-lookup"><span data-stu-id="d0f71-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="d0f71-104">次の図は、2 つの異なるソース シーケンスに対する、2 つの異なる量指定子操作を示しています。</span><span class="sxs-lookup"><span data-stu-id="d0f71-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="d0f71-105">最初の操作では、1 つ以上の要素が文字 'A' であるかどうかを尋ねていて、その結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="d0f71-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="d0f71-106">2 番目の操作では、すべての要素が文字 'A' であるかどうかを尋ねていて、その結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="d0f71-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![LINQ 量指定子操作](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="d0f71-108">次のセクションでは、量指定子操作を実行する標準クエリ演算子のメソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d0f71-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d0f71-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="d0f71-109">Methods</span></span>  
  
|<span data-ttu-id="d0f71-110">メソッド名</span><span class="sxs-lookup"><span data-stu-id="d0f71-110">Method Name</span></span>|<span data-ttu-id="d0f71-111">説明</span><span class="sxs-lookup"><span data-stu-id="d0f71-111">Description</span></span>|<span data-ttu-id="d0f71-112">C# のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="d0f71-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="d0f71-113">説明</span><span class="sxs-lookup"><span data-stu-id="d0f71-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="d0f71-114">すべて</span><span class="sxs-lookup"><span data-stu-id="d0f71-114">All</span></span>|<span data-ttu-id="d0f71-115">シーケンス内のすべての要素が条件を満たしているかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="d0f71-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="d0f71-116">該当なし。</span><span class="sxs-lookup"><span data-stu-id="d0f71-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d0f71-117">どれでも可</span><span class="sxs-lookup"><span data-stu-id="d0f71-117">Any</span></span>|<span data-ttu-id="d0f71-118">シーケンス内のいずれかの要素が条件を満たしているかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="d0f71-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="d0f71-119">該当なし。</span><span class="sxs-lookup"><span data-stu-id="d0f71-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d0f71-120">内容</span><span class="sxs-lookup"><span data-stu-id="d0f71-120">Contains</span></span>|<span data-ttu-id="d0f71-121">指定した要素がシーケンスに格納されているかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="d0f71-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="d0f71-122">該当なし。</span><span class="sxs-lookup"><span data-stu-id="d0f71-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="d0f71-123">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="d0f71-123">Query Expression Syntax Examples</span></span>  
  
### <a name="all"></a><span data-ttu-id="d0f71-124">すべて</span><span class="sxs-lookup"><span data-stu-id="d0f71-124">All</span></span>  
<span data-ttu-id="d0f71-125">次の例では、`All` を使用して、すべての文字列が特定の長さであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0f71-125">The following example uses the `All` to check that all strings are of a specific length.</span></span>
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a><span data-ttu-id="d0f71-126">どれでも可</span><span class="sxs-lookup"><span data-stu-id="d0f71-126">Any</span></span>  
<span data-ttu-id="d0f71-127">次の例では、`Any` を使用して、任意の文字列が "o" で開始されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0f71-127">The following example uses the `Any` to check that any strings are start with 'o'.</span></span>  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a><span data-ttu-id="d0f71-128">内容</span><span class="sxs-lookup"><span data-stu-id="d0f71-128">Contains</span></span>  
<span data-ttu-id="d0f71-129">次の例では、`Contains` を使用して、配列に特定の要素が含まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0f71-129">The following example uses the `Contains` to check an array have a specific element.</span></span>  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a><span data-ttu-id="d0f71-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0f71-130">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="d0f71-131">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="d0f71-131">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="d0f71-132">実行時における述語フィルターの動的指定</span><span class="sxs-lookup"><span data-stu-id="d0f71-132">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="d0f71-133">指定されたワードのセットを含む文章を照会する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="d0f71-133">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
