---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 1907b8786622d3c8019c75916f997c830cc07cfb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180960"
---
# <a name="where-entity-sql"></a><span data-ttu-id="73dda-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="73dda-102">WHERE (Entity SQL)</span></span>

<span data-ttu-id="73dda-103">WHERE 句は、[FROM](from-entity-sql.md) 句の直後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="73dda-103">The WHERE clause is applied directly after the [FROM](from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73dda-104">構文</span><span class="sxs-lookup"><span data-stu-id="73dda-104">Syntax</span></span>  
  
```sql  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="73dda-105">引数</span><span class="sxs-lookup"><span data-stu-id="73dda-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="73dda-106">ブール型です。</span><span class="sxs-lookup"><span data-stu-id="73dda-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73dda-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="73dda-107">Remarks</span></span>  

 <span data-ttu-id="73dda-108">WHERE 句のセマンティクスは、Transact-SQL で記述する場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="73dda-108">The WHERE clause has the same semantics as described for Transact-SQL.</span></span> <span data-ttu-id="73dda-109">ソース コレクションの要素を条件を満たすものに制限することで、クエリ式によって生成されるオブジェクトを制限します。</span><span class="sxs-lookup"><span data-stu-id="73dda-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```sql  
select c from cs as c where e  
```  
  
 <span data-ttu-id="73dda-110">式 `e` には Boolean 型が含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="73dda-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="73dda-111">WHERE 句は、FROM 句の直後、およびグループ化、順序付け、または投影が実行される前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="73dda-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="73dda-112">FROM 句で定義されたすべての要素名は、WHERE 句の式に対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="73dda-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73dda-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="73dda-113">See also</span></span>

- [<span data-ttu-id="73dda-114">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="73dda-114">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="73dda-115">クエリ式</span><span class="sxs-lookup"><span data-stu-id="73dda-115">Query Expressions</span></span>](query-expressions-entity-sql.md)
