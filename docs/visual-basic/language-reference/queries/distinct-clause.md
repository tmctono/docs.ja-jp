---
title: Distinct 句
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 94471898807ef4552564c3e01465f2b2f6211d0c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335372"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="416cb-102">Distinct 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="416cb-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="416cb-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span><span class="sxs-lookup"><span data-stu-id="416cb-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="416cb-104">構文</span><span class="sxs-lookup"><span data-stu-id="416cb-104">Syntax</span></span>  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="416cb-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="416cb-105">Remarks</span></span>  
 <span data-ttu-id="416cb-106">You can use the `Distinct` clause to return a list of unique items.</span><span class="sxs-lookup"><span data-stu-id="416cb-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="416cb-107">The `Distinct` clause causes the query to ignore duplicate query results.</span><span class="sxs-lookup"><span data-stu-id="416cb-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="416cb-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span><span class="sxs-lookup"><span data-stu-id="416cb-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="416cb-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span><span class="sxs-lookup"><span data-stu-id="416cb-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="416cb-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span><span class="sxs-lookup"><span data-stu-id="416cb-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="416cb-111">例</span><span class="sxs-lookup"><span data-stu-id="416cb-111">Example</span></span>  
 <span data-ttu-id="416cb-112">The following query expression joins a list of customers and a list of customer orders.</span><span class="sxs-lookup"><span data-stu-id="416cb-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="416cb-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span><span class="sxs-lookup"><span data-stu-id="416cb-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="416cb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="416cb-114">See also</span></span>

- [<span data-ttu-id="416cb-115">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="416cb-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="416cb-116">クエリ</span><span class="sxs-lookup"><span data-stu-id="416cb-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="416cb-117">From 句</span><span class="sxs-lookup"><span data-stu-id="416cb-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="416cb-118">Select 句</span><span class="sxs-lookup"><span data-stu-id="416cb-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="416cb-119">WHERE 句</span><span class="sxs-lookup"><span data-stu-id="416cb-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
