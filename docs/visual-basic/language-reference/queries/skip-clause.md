---
title: Skip 句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: e52de186e1475bfabd02821a0cd2384d8350eed3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004768"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="99cdb-102">Skip 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99cdb-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="99cdb-103">コレクション内の指定された数の要素をバイパスし、残りの要素を返します。</span><span class="sxs-lookup"><span data-stu-id="99cdb-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99cdb-104">構文</span><span class="sxs-lookup"><span data-stu-id="99cdb-104">Syntax</span></span>  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="99cdb-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="99cdb-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="99cdb-106">必須。</span><span class="sxs-lookup"><span data-stu-id="99cdb-106">Required.</span></span> <span data-ttu-id="99cdb-107">スキップするシーケンスの要素数に評価される値または式。</span><span class="sxs-lookup"><span data-stu-id="99cdb-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99cdb-108">コメント</span><span class="sxs-lookup"><span data-stu-id="99cdb-108">Remarks</span></span>  
 <span data-ttu-id="99cdb-109">@No__t-0 句を使用すると、クエリは結果リストの先頭にある要素をバイパスし、残りの要素を返します。</span><span class="sxs-lookup"><span data-stu-id="99cdb-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="99cdb-110">スキップする要素の数は、`count` パラメーターによって識別されます。</span><span class="sxs-lookup"><span data-stu-id="99cdb-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="99cdb-111">@No__t-1 句を指定した `Skip` 句を使用すると、クエリの任意のセグメントからデータの範囲を取得できます。</span><span class="sxs-lookup"><span data-stu-id="99cdb-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="99cdb-112">これを行うには、範囲の最初の要素のインデックスを `Skip` 句に、範囲のサイズを `Take` 句に渡します。</span><span class="sxs-lookup"><span data-stu-id="99cdb-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="99cdb-113">クエリで `Skip` 句を使用する場合は、`Skip` の句で意図した結果をバイパスできる順序で結果が返されるようにすることも必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="99cdb-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="99cdb-114">クエリ結果の順序付けの詳細については、「 [Order By 句](../../../visual-basic/language-reference/queries/order-by-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99cdb-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="99cdb-115">指定された条件に応じて、特定の要素のみを無視するように指定するには、`SkipWhile` 句を使用します。</span><span class="sxs-lookup"><span data-stu-id="99cdb-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99cdb-116">例</span><span class="sxs-lookup"><span data-stu-id="99cdb-116">Example</span></span>  
 <span data-ttu-id="99cdb-117">次のコード例では、`Take` 句と共に `Skip` 句を使用して、ページ内のクエリからデータを返します。</span><span class="sxs-lookup"><span data-stu-id="99cdb-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="99cdb-118">@No__t-0 関数は、`Skip` 句を使用して、指定された開始インデックス値までリスト内の顧客をバイパスし、`Take` 句を使用して、そのインデックス値から始まる顧客のページを返します。</span><span class="sxs-lookup"><span data-stu-id="99cdb-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="99cdb-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="99cdb-119">See also</span></span>

- [<span data-ttu-id="99cdb-120">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="99cdb-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="99cdb-121">クエリ</span><span class="sxs-lookup"><span data-stu-id="99cdb-121">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="99cdb-122">Select 句</span><span class="sxs-lookup"><span data-stu-id="99cdb-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="99cdb-123">From 句</span><span class="sxs-lookup"><span data-stu-id="99cdb-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="99cdb-124">Order By 句</span><span class="sxs-lookup"><span data-stu-id="99cdb-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="99cdb-125">Skip While 句</span><span class="sxs-lookup"><span data-stu-id="99cdb-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="99cdb-126">Take 句</span><span class="sxs-lookup"><span data-stu-id="99cdb-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
