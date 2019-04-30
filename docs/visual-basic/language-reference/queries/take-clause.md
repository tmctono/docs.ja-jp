---
title: Take 句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: cb109eaf43fee19b77ac690492b85919c9d78301
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054394"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="5b865-102">Take 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b865-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="5b865-103">コレクションの先頭から、指定された数の連続する要素を返します。</span><span class="sxs-lookup"><span data-stu-id="5b865-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b865-104">構文</span><span class="sxs-lookup"><span data-stu-id="5b865-104">Syntax</span></span>  
  
```  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="5b865-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="5b865-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="5b865-106">必須。</span><span class="sxs-lookup"><span data-stu-id="5b865-106">Required.</span></span> <span data-ttu-id="5b865-107">返すシーケンスの要素の数に評価される式または値。</span><span class="sxs-lookup"><span data-stu-id="5b865-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b865-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="5b865-108">Remarks</span></span>  
 <span data-ttu-id="5b865-109">`Take`句によってクエリを指定された数結果一覧の先頭からの連続する要素にはが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5b865-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="5b865-110">含まれる要素の数がで指定された、`count`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="5b865-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="5b865-111">使用することができます、`Take`句、`Skip`句をクエリの任意のセグメントからのデータの範囲を返します。</span><span class="sxs-lookup"><span data-stu-id="5b865-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="5b865-112">これを行うには、範囲の最初の要素のインデックスを渡す、`Skip`句とする範囲のサイズ、`Take`句。</span><span class="sxs-lookup"><span data-stu-id="5b865-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="5b865-113">ここで、`Take`後句を指定する必要があります、`Skip`句。</span><span class="sxs-lookup"><span data-stu-id="5b865-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="5b865-114">使用すると、`Take`クエリ句、する必要がありますも結果が可能にする順序で返されるように、`Take`に目的の結果に含める句。</span><span class="sxs-lookup"><span data-stu-id="5b865-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="5b865-115">クエリの結果を順序付けの詳細については、次を参照してください。 [Order By 句](../../../visual-basic/language-reference/queries/order-by-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="5b865-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="5b865-116">使用することができます、`TakeWhile`句を指定した条件に応じて特定の要素のみを返すことを指定します。</span><span class="sxs-lookup"><span data-stu-id="5b865-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b865-117">例</span><span class="sxs-lookup"><span data-stu-id="5b865-117">Example</span></span>  
 <span data-ttu-id="5b865-118">次のコード例では、`Take`句と組み合わせて、`Skip`句をページ内のクエリからデータを返します。</span><span class="sxs-lookup"><span data-stu-id="5b865-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="5b865-119">GetCustomers 関数は、`Skip`値、および使用して、指定された開始インデックスを作成するまで、リスト内の顧客をバイパスする句、`Take`句にそのインデックス値から開始のページが返されます。</span><span class="sxs-lookup"><span data-stu-id="5b865-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5b865-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b865-120">See also</span></span>

- [<span data-ttu-id="5b865-121">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="5b865-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="5b865-122">クエリ</span><span class="sxs-lookup"><span data-stu-id="5b865-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="5b865-123">Select 句</span><span class="sxs-lookup"><span data-stu-id="5b865-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="5b865-124">From 句</span><span class="sxs-lookup"><span data-stu-id="5b865-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="5b865-125">Order By 句</span><span class="sxs-lookup"><span data-stu-id="5b865-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="5b865-126">Take While 句</span><span class="sxs-lookup"><span data-stu-id="5b865-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="5b865-127">Skip 句</span><span class="sxs-lookup"><span data-stu-id="5b865-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
