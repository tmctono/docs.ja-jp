---
title: Take 句
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 3082954ef84560ccb70f7a47cd3532f622829392
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349645"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="31b0e-102">Take 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31b0e-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="31b0e-103">コレクションの先頭から、指定された数の連続する要素を返します。</span><span class="sxs-lookup"><span data-stu-id="31b0e-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31b0e-104">構文</span><span class="sxs-lookup"><span data-stu-id="31b0e-104">Syntax</span></span>  
  
```vb  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="31b0e-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="31b0e-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="31b0e-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="31b0e-106">Required.</span></span> <span data-ttu-id="31b0e-107">返されるシーケンスの要素数に評価される値または式。</span><span class="sxs-lookup"><span data-stu-id="31b0e-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31b0e-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="31b0e-108">Remarks</span></span>  
 <span data-ttu-id="31b0e-109">`Take` 句を指定すると、結果リストの先頭から指定した数の連続した要素がクエリに含まれます。</span><span class="sxs-lookup"><span data-stu-id="31b0e-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="31b0e-110">含まれる要素の数は `count` パラメーターによって指定します。</span><span class="sxs-lookup"><span data-stu-id="31b0e-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="31b0e-111">`Skip` 句と共に `Take` 句を使用すると、クエリの任意のセグメントからのデータの範囲を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="31b0e-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="31b0e-112">これを行うには、範囲の最初の要素のインデックスを `Skip` 句に渡し、範囲のサイズを `Take` 句に渡します。</span><span class="sxs-lookup"><span data-stu-id="31b0e-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="31b0e-113">この場合、`Take` 句を `Skip` 句の後に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31b0e-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="31b0e-114">クエリで `Take` 句を使用する場合は、`Take` 句に目的の結果が含まれるようにする順番で、結果が返されるようにする必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="31b0e-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="31b0e-115">クエリ結果の順序付けの詳細については、「[Order By 句](../../../visual-basic/language-reference/queries/order-by-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b0e-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="31b0e-116">指定した条件に応じて、特定の要素のみが返されるように指定するには、`TakeWhile` 句を使用できます。</span><span class="sxs-lookup"><span data-stu-id="31b0e-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31b0e-117">例</span><span class="sxs-lookup"><span data-stu-id="31b0e-117">Example</span></span>  
 <span data-ttu-id="31b0e-118">次のコード例では、`Skip` 句と共に `Take` 句を使用して、ページ内のクエリからのデータを返しています。</span><span class="sxs-lookup"><span data-stu-id="31b0e-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="31b0e-119">GetCustomers 関数では、`Skip` 句を使用して、指定した開始インデックス値までリスト内の顧客をバイパスし、`Take` 句を使用して、そのインデックス値から始まる顧客のページを返します。</span><span class="sxs-lookup"><span data-stu-id="31b0e-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="31b0e-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="31b0e-120">See also</span></span>

- [<span data-ttu-id="31b0e-121">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="31b0e-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="31b0e-122">クエリ</span><span class="sxs-lookup"><span data-stu-id="31b0e-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="31b0e-123">Select 句</span><span class="sxs-lookup"><span data-stu-id="31b0e-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="31b0e-124">From 句</span><span class="sxs-lookup"><span data-stu-id="31b0e-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="31b0e-125">Order By 句</span><span class="sxs-lookup"><span data-stu-id="31b0e-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="31b0e-126">Take While 句</span><span class="sxs-lookup"><span data-stu-id="31b0e-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="31b0e-127">Skip 句</span><span class="sxs-lookup"><span data-stu-id="31b0e-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
