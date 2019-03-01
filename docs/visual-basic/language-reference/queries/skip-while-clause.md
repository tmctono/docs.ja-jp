---
title: Skip While 句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 380372d6aaf8df3050e0ba8606b74eb3834dec67
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972600"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="b16ae-102">Skip While 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b16ae-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="b16ae-103">指定された条件が `true` である限り、コレクションの要素をバイパスし、残りの要素を返します。</span><span class="sxs-lookup"><span data-stu-id="b16ae-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b16ae-104">構文</span><span class="sxs-lookup"><span data-stu-id="b16ae-104">Syntax</span></span>  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b16ae-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="b16ae-105">Parts</span></span>  
  
|<span data-ttu-id="b16ae-106">用語</span><span class="sxs-lookup"><span data-stu-id="b16ae-106">Term</span></span>|<span data-ttu-id="b16ae-107">定義</span><span class="sxs-lookup"><span data-stu-id="b16ae-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="b16ae-108">必須。</span><span class="sxs-lookup"><span data-stu-id="b16ae-108">Required.</span></span> <span data-ttu-id="b16ae-109">要素をテストするための条件を表す式。</span><span class="sxs-lookup"><span data-stu-id="b16ae-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="b16ae-110">式を返す必要があります、`Boolean`値またはそれと同等の機能など、`Integer`として評価される、`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="b16ae-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b16ae-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="b16ae-111">Remarks</span></span>  
 <span data-ttu-id="b16ae-112">`Skip While`句まで、指定されたクエリ結果の先頭から要素をバイパスする`expression`返します`false`します。</span><span class="sxs-lookup"><span data-stu-id="b16ae-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="b16ae-113">後`expression`返します`false`クエリは、残りのすべての要素を返します。</span><span class="sxs-lookup"><span data-stu-id="b16ae-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="b16ae-114">`expression`残りの結果は無視されます。</span><span class="sxs-lookup"><span data-stu-id="b16ae-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="b16ae-115">`Skip While`句とは異なります、`Where`句を`Where`を特定の条件を満たさないクエリからすべての要素を除外する句を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b16ae-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="b16ae-116">`Skip While`句は、条件が満たされていませんが、初めてまでのみ要素を除外します。</span><span class="sxs-lookup"><span data-stu-id="b16ae-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="b16ae-117">`Skip While`句は、順序付けられたクエリ結果を使用しているときに最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b16ae-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="b16ae-118">使用してクエリ結果の先頭からの結果の特定の数をバイパスできる、`Skip`句。</span><span class="sxs-lookup"><span data-stu-id="b16ae-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b16ae-119">例</span><span class="sxs-lookup"><span data-stu-id="b16ae-119">Example</span></span>  
 <span data-ttu-id="b16ae-120">次のコード例では、`Skip While`米国から最初の顧客が見つかるまで、結果をバイパスする句。</span><span class="sxs-lookup"><span data-stu-id="b16ae-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="b16ae-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="b16ae-121">See also</span></span>
- [<span data-ttu-id="b16ae-122">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="b16ae-122">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="b16ae-123">クエリ</span><span class="sxs-lookup"><span data-stu-id="b16ae-123">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="b16ae-124">Select 句</span><span class="sxs-lookup"><span data-stu-id="b16ae-124">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="b16ae-125">From 句</span><span class="sxs-lookup"><span data-stu-id="b16ae-125">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="b16ae-126">Skip 句</span><span class="sxs-lookup"><span data-stu-id="b16ae-126">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="b16ae-127">Take While 句</span><span class="sxs-lookup"><span data-stu-id="b16ae-127">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="b16ae-128">Where 句</span><span class="sxs-lookup"><span data-stu-id="b16ae-128">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
