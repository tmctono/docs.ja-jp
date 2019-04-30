---
title: Distinct 句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: fbca9fa8aa227d8d5b6488bef179f4bda08bb38c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945354"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="0ce38-102">Distinct 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ce38-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="0ce38-103">次のクエリ句で、重複を排除する現在の範囲変数の値を制限します。</span><span class="sxs-lookup"><span data-stu-id="0ce38-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ce38-104">構文</span><span class="sxs-lookup"><span data-stu-id="0ce38-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="0ce38-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="0ce38-105">Remarks</span></span>  
 <span data-ttu-id="0ce38-106">使用することができます、`Distinct`句を一意の項目の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="0ce38-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="0ce38-107">`Distinct`句によって重複するクエリの結果を無視するクエリ。</span><span class="sxs-lookup"><span data-stu-id="0ce38-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="0ce38-108">`Distinct`句は、すべての戻り値で指定されたフィールドの重複する値を適用、`Select`句。</span><span class="sxs-lookup"><span data-stu-id="0ce38-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="0ce38-109">ない場合は`Select`句が指定されて、`Distinct`で特定されたクエリの範囲変数に句が適用される、`From`句。</span><span class="sxs-lookup"><span data-stu-id="0ce38-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="0ce38-110">クエリは、範囲変数が変更不可の型でない場合、既存のクエリ結果に一致する型のすべてのメンバーである場合は、クエリ結果を無視してはのみです。</span><span class="sxs-lookup"><span data-stu-id="0ce38-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ce38-111">例</span><span class="sxs-lookup"><span data-stu-id="0ce38-111">Example</span></span>  
 <span data-ttu-id="0ce38-112">次のクエリ式では、顧客の一覧と顧客の注文のリストを結合します。</span><span class="sxs-lookup"><span data-stu-id="0ce38-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="0ce38-113">`Distinct`句は、一意の顧客名のリストを返し、注文日に含まれています。</span><span class="sxs-lookup"><span data-stu-id="0ce38-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="0ce38-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ce38-114">See also</span></span>

- [<span data-ttu-id="0ce38-115">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="0ce38-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="0ce38-116">クエリ</span><span class="sxs-lookup"><span data-stu-id="0ce38-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="0ce38-117">From 句</span><span class="sxs-lookup"><span data-stu-id="0ce38-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="0ce38-118">Select 句</span><span class="sxs-lookup"><span data-stu-id="0ce38-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="0ce38-119">Where 句</span><span class="sxs-lookup"><span data-stu-id="0ce38-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
