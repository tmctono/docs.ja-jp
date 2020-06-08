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
ms.openlocfilehash: 427d14453260a54bd3f2ab9a8ac75dedacd291f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359659"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="8e960-102">Skip 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e960-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="8e960-103">コレクション内の指定された数の要素をバイパスし、残りの要素を返します。</span><span class="sxs-lookup"><span data-stu-id="8e960-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e960-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e960-104">Syntax</span></span>  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="8e960-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="8e960-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="8e960-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="8e960-106">Required.</span></span> <span data-ttu-id="8e960-107">スキップするシーケンスの要素数に評価される値または式。</span><span class="sxs-lookup"><span data-stu-id="8e960-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e960-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e960-108">Remarks</span></span>  
 <span data-ttu-id="8e960-109">`Skip` 句を使用すると、クエリは結果リストの先頭の要素をバイパスし、残りの要素を返します。</span><span class="sxs-lookup"><span data-stu-id="8e960-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="8e960-110">スキップする要素の数は `count` パラメーターによって識別されます。</span><span class="sxs-lookup"><span data-stu-id="8e960-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="8e960-111">`Take` 句と共に `Skip` 句を使用すると、クエリの任意のセグメントからのデータの範囲を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8e960-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="8e960-112">これを行うには、範囲の最初の要素のインデックスを `Skip` 句に渡し、範囲のサイズを `Take` 句に渡します。</span><span class="sxs-lookup"><span data-stu-id="8e960-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="8e960-113">クエリで `Skip` 句を使用する場合は、`Skip` 句で目的の結果がバイパスされるような順番で、結果が返されるようにする必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8e960-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="8e960-114">クエリ結果の順序付けの詳細については、「[Order By 句](order-by-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e960-114">For more information about ordering query results, see [Order By Clause](order-by-clause.md).</span></span>  
  
 <span data-ttu-id="8e960-115">指定した条件に応じて、特定の要素のみが無視されるように指定するには、`SkipWhile` 句を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8e960-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e960-116">例</span><span class="sxs-lookup"><span data-stu-id="8e960-116">Example</span></span>  
 <span data-ttu-id="8e960-117">次のコード例では、`Take` 句と共に `Skip` 句を使用して、ページ内のクエリからのデータを返しています。</span><span class="sxs-lookup"><span data-stu-id="8e960-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="8e960-118">`GetCustomers` 関数は、`Skip` 句を使用して、指定した開始インデックス値までリスト内の顧客をバイパスし、`Take` 句を使用して、そのインデックス値から始まる顧客のページを返します。</span><span class="sxs-lookup"><span data-stu-id="8e960-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8e960-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e960-119">See also</span></span>

- [<span data-ttu-id="8e960-120">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="8e960-120">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="8e960-121">クエリ</span><span class="sxs-lookup"><span data-stu-id="8e960-121">Queries</span></span>](index.md)
- [<span data-ttu-id="8e960-122">Select 句</span><span class="sxs-lookup"><span data-stu-id="8e960-122">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="8e960-123">From 句</span><span class="sxs-lookup"><span data-stu-id="8e960-123">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="8e960-124">Order By 句</span><span class="sxs-lookup"><span data-stu-id="8e960-124">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="8e960-125">Skip While 句</span><span class="sxs-lookup"><span data-stu-id="8e960-125">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="8e960-126">Take 句</span><span class="sxs-lookup"><span data-stu-id="8e960-126">Take Clause</span></span>](take-clause.md)
