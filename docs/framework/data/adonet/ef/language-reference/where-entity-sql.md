---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 02eeaeb8cfa335e5545b26d3d52b91c4e1614629
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879438"
---
# <a name="where-entity-sql"></a><span data-ttu-id="0c8f6-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0c8f6-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="0c8f6-103">WHERE 句は、直後に適用、 [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md)句。</span><span class="sxs-lookup"><span data-stu-id="0c8f6-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c8f6-104">構文</span><span class="sxs-lookup"><span data-stu-id="0c8f6-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0c8f6-105">引数</span><span class="sxs-lookup"><span data-stu-id="0c8f6-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="0c8f6-106">ブール型です。</span><span class="sxs-lookup"><span data-stu-id="0c8f6-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c8f6-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0c8f6-107">Remarks</span></span>  
 <span data-ttu-id="0c8f6-108">WHERE 句は、[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] で設定された場合と同じセマンティクスを持ちます。</span><span class="sxs-lookup"><span data-stu-id="0c8f6-108">The WHERE clause has the same semantics as described for [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0c8f6-109">ソース コレクションの要素を条件を満たすものに制限することで、クエリ式によって生成されるオブジェクトを制限します。</span><span class="sxs-lookup"><span data-stu-id="0c8f6-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="0c8f6-110">式 `e` には Boolean 型が含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c8f6-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="0c8f6-111">WHERE 句は、FROM 句の直後、およびグループ化、順序付け、または投影が実行される前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0c8f6-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="0c8f6-112">FROM 句で定義されたすべての要素名は、WHERE 句の式に対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c8f6-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c8f6-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c8f6-113">See also</span></span>

- [<span data-ttu-id="0c8f6-114">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="0c8f6-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="0c8f6-115">クエリ式</span><span class="sxs-lookup"><span data-stu-id="0c8f6-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
