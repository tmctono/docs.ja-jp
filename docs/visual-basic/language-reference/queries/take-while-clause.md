---
title: Take While 句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 080a106fc1deeb54165511ed03d7c7c5d2060f21
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818750"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="f5416-102">Take While 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5416-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="f5416-103">指定された条件が `true` である限り、コレクションの要素を含むようにし、残りの要素をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="f5416-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5416-104">構文</span><span class="sxs-lookup"><span data-stu-id="f5416-104">Syntax</span></span>  
  
```  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="f5416-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="f5416-105">Parts</span></span>  
  
|<span data-ttu-id="f5416-106">用語</span><span class="sxs-lookup"><span data-stu-id="f5416-106">Term</span></span>|<span data-ttu-id="f5416-107">定義</span><span class="sxs-lookup"><span data-stu-id="f5416-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="f5416-108">必須。</span><span class="sxs-lookup"><span data-stu-id="f5416-108">Required.</span></span> <span data-ttu-id="f5416-109">要素をテストするための条件を表す式。</span><span class="sxs-lookup"><span data-stu-id="f5416-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="f5416-110">式を返す必要があります、`Boolean`値またはそれと同等の機能など、`Integer`として評価される、`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="f5416-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5416-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="f5416-111">Remarks</span></span>  
 <span data-ttu-id="f5416-112">`Take While`句にはまで、指定されたクエリ結果の先頭から要素が含まれます`expression`返します`false`します。</span><span class="sxs-lookup"><span data-stu-id="f5416-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="f5416-113">後に、`expression`返します`false`クエリでは、残りのすべての要素をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="f5416-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="f5416-114">`expression`残りの結果は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f5416-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="f5416-115">`Take While`句とは異なります、`Where`句を`Where`を特定の条件を満たすクエリからのすべての要素を含める句を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5416-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="f5416-116">`Take While`句には、条件が満たされていませんが、初めてまでのみの要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f5416-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="f5416-117">`Take While`句は、順序付けられたクエリ結果を使用しているときに最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f5416-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5416-118">例</span><span class="sxs-lookup"><span data-stu-id="f5416-118">Example</span></span>  
 <span data-ttu-id="f5416-119">次のコード例では、`Take While`句を任意の注文数が、最初の顧客が見つかるまで結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="f5416-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f5416-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5416-120">See also</span></span>

- [<span data-ttu-id="f5416-121">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="f5416-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f5416-122">クエリ</span><span class="sxs-lookup"><span data-stu-id="f5416-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="f5416-123">Select 句</span><span class="sxs-lookup"><span data-stu-id="f5416-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="f5416-124">From 句</span><span class="sxs-lookup"><span data-stu-id="f5416-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="f5416-125">Take 句</span><span class="sxs-lookup"><span data-stu-id="f5416-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="f5416-126">Skip While 句</span><span class="sxs-lookup"><span data-stu-id="f5416-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="f5416-127">Where 句</span><span class="sxs-lookup"><span data-stu-id="f5416-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
