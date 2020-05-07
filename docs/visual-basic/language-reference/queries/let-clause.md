---
title: Let 句
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 63eaf97016db259870eb77199651ecbdc5f809c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350435"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="5b9d2-102">Let 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b9d2-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="5b9d2-103">値を計算し、その値をクエリ内の新しい変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b9d2-104">構文</span><span class="sxs-lookup"><span data-stu-id="5b9d2-104">Syntax</span></span>  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="5b9d2-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="5b9d2-105">Parts</span></span>  
  
|<span data-ttu-id="5b9d2-106">用語</span><span class="sxs-lookup"><span data-stu-id="5b9d2-106">Term</span></span>|<span data-ttu-id="5b9d2-107">定義</span><span class="sxs-lookup"><span data-stu-id="5b9d2-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="5b9d2-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-108">Required.</span></span> <span data-ttu-id="5b9d2-109">指定された式の結果を参照するために使用できる別名。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="5b9d2-110">必須です。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-110">Required.</span></span> <span data-ttu-id="5b9d2-111">評価され、指定された変数に割り当てられる式。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b9d2-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="5b9d2-112">Remarks</span></span>  
 <span data-ttu-id="5b9d2-113">`Let` 句を使用すると、各クエリ結果の値を計算し、別名を使用してその値を参照できます。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="5b9d2-114">別名は、`Where` 句などの他の句で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="5b9d2-115">`Let` 句を使用すると、クエリに含まれる式の句の別名を指定し、その式の句が使用されるたびに別名を置き換えることができるため、読みやすいクエリ ステートメントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="5b9d2-116">`Let` 句には、任意の数の `variable` と `expression` の代入を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="5b9d2-117">各代入はコンマ (,) で区切ります。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b9d2-118">例</span><span class="sxs-lookup"><span data-stu-id="5b9d2-118">Example</span></span>  
 <span data-ttu-id="5b9d2-119">次のコード例では、`Let` 句を使用して、製品に対して 10% の割引を計算します。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="5b9d2-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b9d2-120">See also</span></span>

- [<span data-ttu-id="5b9d2-121">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="5b9d2-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="5b9d2-122">クエリ</span><span class="sxs-lookup"><span data-stu-id="5b9d2-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="5b9d2-123">Select 句</span><span class="sxs-lookup"><span data-stu-id="5b9d2-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="5b9d2-124">From 句</span><span class="sxs-lookup"><span data-stu-id="5b9d2-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="5b9d2-125">WHERE 句</span><span class="sxs-lookup"><span data-stu-id="5b9d2-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
