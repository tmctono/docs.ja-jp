---
title: Skip 句
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: c582b014bad4fa8fa3165d2b756f4bc955840cfc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349654"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="44804-102">Skip 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44804-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="44804-103">コレクション内の指定された数の要素をバイパスし、残りの要素を返します。</span><span class="sxs-lookup"><span data-stu-id="44804-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44804-104">構文</span><span class="sxs-lookup"><span data-stu-id="44804-104">Syntax</span></span>  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="44804-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="44804-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="44804-106">必須。</span><span class="sxs-lookup"><span data-stu-id="44804-106">Required.</span></span> <span data-ttu-id="44804-107">スキップするシーケンスの要素数に評価される値または式。</span><span class="sxs-lookup"><span data-stu-id="44804-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44804-108">コメント</span><span class="sxs-lookup"><span data-stu-id="44804-108">Remarks</span></span>  
 <span data-ttu-id="44804-109">`Skip` 句を使用すると、クエリは結果リストの先頭の要素をバイパスし、残りの要素を返します。</span><span class="sxs-lookup"><span data-stu-id="44804-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="44804-110">スキップする要素の数は、`count` パラメーターによって識別されます。</span><span class="sxs-lookup"><span data-stu-id="44804-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="44804-111">`Take` 句と共に `Skip` 句を使用すると、クエリの任意のセグメントからデータの範囲を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="44804-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="44804-112">これを行うには、範囲の最初の要素のインデックスを `Skip` 句に渡し、範囲のサイズを `Take` 句に渡します。</span><span class="sxs-lookup"><span data-stu-id="44804-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="44804-113">クエリで `Skip` 句を使用する場合は、`Skip` の句が意図した結果をバイパスできるように、結果が返される順序になるようにする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="44804-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="44804-114">クエリ結果の順序付けの詳細については、「 [Order By 句](../../../visual-basic/language-reference/queries/order-by-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44804-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="44804-115">指定した条件に応じて、特定の要素のみを無視するように指定するには、`SkipWhile` 句を使用します。</span><span class="sxs-lookup"><span data-stu-id="44804-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44804-116">例</span><span class="sxs-lookup"><span data-stu-id="44804-116">Example</span></span>  
 <span data-ttu-id="44804-117">次のコード例では、`Take` 句と共に `Skip` 句を使用して、ページ内のクエリからデータを返します。</span><span class="sxs-lookup"><span data-stu-id="44804-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="44804-118">`GetCustomers` 関数は、`Skip` 句を使用して、指定された開始インデックス値までリスト内の顧客をバイパスし、`Take` 句を使用して、そのインデックス値から始まる顧客のページを返します。</span><span class="sxs-lookup"><span data-stu-id="44804-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="44804-119">参照</span><span class="sxs-lookup"><span data-stu-id="44804-119">See also</span></span>

- [<span data-ttu-id="44804-120">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="44804-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="44804-121">クエリ</span><span class="sxs-lookup"><span data-stu-id="44804-121">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="44804-122">Select 句</span><span class="sxs-lookup"><span data-stu-id="44804-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="44804-123">From 句</span><span class="sxs-lookup"><span data-stu-id="44804-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="44804-124">Order By 句</span><span class="sxs-lookup"><span data-stu-id="44804-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="44804-125">Skip While 句</span><span class="sxs-lookup"><span data-stu-id="44804-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="44804-126">Take 句</span><span class="sxs-lookup"><span data-stu-id="44804-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
