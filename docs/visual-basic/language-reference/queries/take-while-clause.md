---
title: Take While 句
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 23b7c84a9f896161a66059fcb1f30753d3b863d5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347111"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="20ba5-102">Take While 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20ba5-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="20ba5-103">指定された条件が `true` である限り、コレクションの要素を含むようにし、残りの要素をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="20ba5-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20ba5-104">構文</span><span class="sxs-lookup"><span data-stu-id="20ba5-104">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="20ba5-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="20ba5-105">Parts</span></span>  
  
|<span data-ttu-id="20ba5-106">用語</span><span class="sxs-lookup"><span data-stu-id="20ba5-106">Term</span></span>|<span data-ttu-id="20ba5-107">定義</span><span class="sxs-lookup"><span data-stu-id="20ba5-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="20ba5-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="20ba5-108">Required.</span></span> <span data-ttu-id="20ba5-109">An expression that represents a condition to test elements for.</span><span class="sxs-lookup"><span data-stu-id="20ba5-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="20ba5-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="20ba5-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20ba5-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="20ba5-111">Remarks</span></span>  
 <span data-ttu-id="20ba5-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span><span class="sxs-lookup"><span data-stu-id="20ba5-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="20ba5-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span><span class="sxs-lookup"><span data-stu-id="20ba5-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="20ba5-114">The `expression` is ignored for the remaining results.</span><span class="sxs-lookup"><span data-stu-id="20ba5-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="20ba5-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span><span class="sxs-lookup"><span data-stu-id="20ba5-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="20ba5-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span><span class="sxs-lookup"><span data-stu-id="20ba5-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="20ba5-117">The `Take While` clause is most useful when you are working with an ordered query result.</span><span class="sxs-lookup"><span data-stu-id="20ba5-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20ba5-118">例</span><span class="sxs-lookup"><span data-stu-id="20ba5-118">Example</span></span>  
 <span data-ttu-id="20ba5-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span><span class="sxs-lookup"><span data-stu-id="20ba5-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="20ba5-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="20ba5-120">See also</span></span>

- [<span data-ttu-id="20ba5-121">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="20ba5-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="20ba5-122">クエリ</span><span class="sxs-lookup"><span data-stu-id="20ba5-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="20ba5-123">Select 句</span><span class="sxs-lookup"><span data-stu-id="20ba5-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="20ba5-124">From 句</span><span class="sxs-lookup"><span data-stu-id="20ba5-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="20ba5-125">Take 句</span><span class="sxs-lookup"><span data-stu-id="20ba5-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="20ba5-126">Skip While 句</span><span class="sxs-lookup"><span data-stu-id="20ba5-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="20ba5-127">WHERE 句</span><span class="sxs-lookup"><span data-stu-id="20ba5-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
