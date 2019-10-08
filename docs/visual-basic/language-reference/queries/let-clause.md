---
title: Let 句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 88166a040823cfefe623f672e556c364d652a7fc
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004732"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="8fb20-102">Let 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fb20-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="8fb20-103">値を計算し、クエリ内の新しい変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="8fb20-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fb20-104">構文</span><span class="sxs-lookup"><span data-stu-id="8fb20-104">Syntax</span></span>  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="8fb20-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="8fb20-105">Parts</span></span>  
  
|<span data-ttu-id="8fb20-106">項目</span><span class="sxs-lookup"><span data-stu-id="8fb20-106">Term</span></span>|<span data-ttu-id="8fb20-107">定義</span><span class="sxs-lookup"><span data-stu-id="8fb20-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="8fb20-108">必須。</span><span class="sxs-lookup"><span data-stu-id="8fb20-108">Required.</span></span> <span data-ttu-id="8fb20-109">指定された式の結果を参照するために使用できるエイリアス。</span><span class="sxs-lookup"><span data-stu-id="8fb20-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="8fb20-110">必須。</span><span class="sxs-lookup"><span data-stu-id="8fb20-110">Required.</span></span> <span data-ttu-id="8fb20-111">評価され、指定された変数に割り当てられる式。</span><span class="sxs-lookup"><span data-stu-id="8fb20-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fb20-112">コメント</span><span class="sxs-lookup"><span data-stu-id="8fb20-112">Remarks</span></span>  
 <span data-ttu-id="8fb20-113">@No__t-0 句を使用すると、各クエリ結果の値を計算し、別名を使用してその値を参照できます。</span><span class="sxs-lookup"><span data-stu-id="8fb20-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="8fb20-114">別名は、`Where` 句などの他の句で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8fb20-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="8fb20-115">@No__t-0 句を使用すると、クエリに含まれる式の句の別名を指定し、expression 句が使用されるたびに別名を置き換えることができるので、読みやすいクエリステートメントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8fb20-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="8fb20-116">@No__t-2 句には、任意の数の @no__t 0 と @no__t の割り当てを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8fb20-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="8fb20-117">各割り当てはコンマ (,) で区切ります。</span><span class="sxs-lookup"><span data-stu-id="8fb20-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fb20-118">例</span><span class="sxs-lookup"><span data-stu-id="8fb20-118">Example</span></span>  
 <span data-ttu-id="8fb20-119">次のコード例では、`Let` 句を使用して、製品に対して 10% の割引を計算します。</span><span class="sxs-lookup"><span data-stu-id="8fb20-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="8fb20-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fb20-120">See also</span></span>

- [<span data-ttu-id="8fb20-121">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="8fb20-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="8fb20-122">クエリ</span><span class="sxs-lookup"><span data-stu-id="8fb20-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="8fb20-123">Select 句</span><span class="sxs-lookup"><span data-stu-id="8fb20-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="8fb20-124">From 句</span><span class="sxs-lookup"><span data-stu-id="8fb20-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="8fb20-125">Where 句</span><span class="sxs-lookup"><span data-stu-id="8fb20-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
