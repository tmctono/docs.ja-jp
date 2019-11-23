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
ms.openlocfilehash: fe6ee470698504bc0434930cc9aa6de712e04254
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004674"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="152c4-102">Take While 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="152c4-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="152c4-103">指定された条件が `true` である限り、コレクションの要素を含むようにし、残りの要素をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="152c4-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="152c4-104">構文</span><span class="sxs-lookup"><span data-stu-id="152c4-104">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="152c4-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="152c4-105">Parts</span></span>  
  
|<span data-ttu-id="152c4-106">用語</span><span class="sxs-lookup"><span data-stu-id="152c4-106">Term</span></span>|<span data-ttu-id="152c4-107">Definition</span><span class="sxs-lookup"><span data-stu-id="152c4-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="152c4-108">必須。</span><span class="sxs-lookup"><span data-stu-id="152c4-108">Required.</span></span> <span data-ttu-id="152c4-109">テスト要素の条件を表す式。</span><span class="sxs-lookup"><span data-stu-id="152c4-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="152c4-110">式は、`Boolean` 値または同等の機能 (`Boolean`として評価される `Integer` など) を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="152c4-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="152c4-111">コメント</span><span class="sxs-lookup"><span data-stu-id="152c4-111">Remarks</span></span>  
 <span data-ttu-id="152c4-112">`Take While` 句には、指定された `expression` が `false`を返すまで、クエリ結果の先頭からの要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="152c4-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="152c4-113">`expression` が `false`を返した後、クエリは残りのすべての要素をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="152c4-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="152c4-114">残りの結果については、`expression` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="152c4-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="152c4-115">`Take While` 句は、特定の条件を満たすクエリのすべての要素を含めるために `Where` 句を使用できるという点で、`Where` 句とは異なります。</span><span class="sxs-lookup"><span data-stu-id="152c4-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="152c4-116">`Take While` 句には、最初に条件が満たされない限り、要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="152c4-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="152c4-117">`Take While` 句は、順序付けられたクエリ結果を操作する場合に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="152c4-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="152c4-118">例</span><span class="sxs-lookup"><span data-stu-id="152c4-118">Example</span></span>  
 <span data-ttu-id="152c4-119">次のコード例では、`Take While` 句を使用して、注文のない最初の顧客が見つかるまで結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="152c4-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="152c4-120">参照</span><span class="sxs-lookup"><span data-stu-id="152c4-120">See also</span></span>

- [<span data-ttu-id="152c4-121">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="152c4-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="152c4-122">クエリ</span><span class="sxs-lookup"><span data-stu-id="152c4-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="152c4-123">Select 句</span><span class="sxs-lookup"><span data-stu-id="152c4-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="152c4-124">From 句</span><span class="sxs-lookup"><span data-stu-id="152c4-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="152c4-125">Take 句</span><span class="sxs-lookup"><span data-stu-id="152c4-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="152c4-126">Skip While 句</span><span class="sxs-lookup"><span data-stu-id="152c4-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="152c4-127">WHERE 句</span><span class="sxs-lookup"><span data-stu-id="152c4-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
