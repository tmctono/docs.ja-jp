---
title: 入れ子になった Entity SQL クエリの作成
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: 4d6892e96cfbc9c5ba9d389aa03588c5133c7943
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606226"
---
# <a name="composing-nested-entity-sql-queries"></a><span data-ttu-id="e6455-102">入れ子になった Entity SQL クエリの作成</span><span class="sxs-lookup"><span data-stu-id="e6455-102">Composing Nested Entity SQL Queries</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e6455-103">は、機能の豊富な関数言語です。</span><span class="sxs-lookup"><span data-stu-id="e6455-103">is a rich functional language.</span></span> <span data-ttu-id="e6455-104">ビルド ブロック[!INCLUDE[esql](../../../../../../includes/esql-md.md)]式を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6455-104">The building block of [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is an expression.</span></span> <span data-ttu-id="e6455-105">従来の SQL とは異なり[!INCLUDE[esql](../../../../../../includes/esql-md.md)]は表形式の結果セットに限定されません。[!INCLUDE[esql](../../../../../../includes/esql-md.md)]リテラル、パラメーター、または入れ子になった式が複雑な式の作成をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e6455-105">Unlike conventional SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not limited to a tabular result set: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports composing complex expressions that can have literals, parameters, or nested expressions.</span></span> <span data-ttu-id="e6455-106">式の値をパラメーター化されたまたはその他の式で構成できます。</span><span class="sxs-lookup"><span data-stu-id="e6455-106">A value in the expression can be parameterized or composed of some other expression.</span></span>  
  
## <a name="nested-expressions"></a><span data-ttu-id="e6455-107">入れ子になった式</span><span class="sxs-lookup"><span data-stu-id="e6455-107">Nested Expressions</span></span>  
 <span data-ttu-id="e6455-108">入れ子になった式は、その式によって返される型の値が受け入れられる場所であればどこにでも配置できます。</span><span class="sxs-lookup"><span data-stu-id="e6455-108">A nested expression can be placed anywhere a value of the type it returns is accepted.</span></span> <span data-ttu-id="e6455-109">例:</span><span class="sxs-lookup"><span data-stu-id="e6455-109">For example:</span></span>  
  
```  
-- Returns a hierarchical collection of three elements at top-level.   
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 <span data-ttu-id="e6455-110">入れ子になったクエリは、projection 句に配置できます。</span><span class="sxs-lookup"><span data-stu-id="e6455-110">A nested query can be placed in a projection clause.</span></span> <span data-ttu-id="e6455-111">例:</span><span class="sxs-lookup"><span data-stu-id="e6455-111">For example:</span></span>  
  
```  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)   
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)   
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 <span data-ttu-id="e6455-112">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] では、入れ子になったクエリを次のようにかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6455-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], nested queries must always be enclosed in parentheses:</span></span>  
  
```  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 <span data-ttu-id="e6455-113">次の例は、内の式を正しく入れ子にする方法を示します[!INCLUDE[esql](../../../../../../includes/esql-md.md)]:[方法:2 つのクエリの結合を並べ替える](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="e6455-113">The following example demonstrates how to properly nest expressions in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [How to: Order the Union of Two Queries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100)).</span></span>  
  
## <a name="nested-queries-in-projection"></a><span data-ttu-id="e6455-114">投影内の入れ子になったクエリ</span><span class="sxs-lookup"><span data-stu-id="e6455-114">Nested Queries in Projection</span></span>  
 <span data-ttu-id="e6455-115">project 句内の入れ子になったクエリは、サーバーでデカルト積に変換されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="e6455-115">Nested queries in the project clause might get translated into Cartesian product queries on the server.</span></span> <span data-ttu-id="e6455-116">SLQ Server などの一部のバックエンド サーバーでは、これによって TempDB テーブルのサイズが非常に大きくなり、サーバーのパフォーマンスに悪影響を及ぼす場合があります。</span><span class="sxs-lookup"><span data-stu-id="e6455-116">In some backend servers, including SLQ Server, this can cause the TempDB table to get very large, which can adversely affect server performance.</span></span>  
  
 <span data-ttu-id="e6455-117">以下は、このようなクエリの例です。</span><span class="sxs-lookup"><span data-stu-id="e6455-117">The following is an example of such a query:</span></span>  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="e6455-118">入れ子になったクエリの順序</span><span class="sxs-lookup"><span data-stu-id="e6455-118">Ordering Nested Queries</span></span>  
 <span data-ttu-id="e6455-119">Entity Framework では、入れ子になった式をクエリ内の任意の場所に配置できます。</span><span class="sxs-lookup"><span data-stu-id="e6455-119">In the Entity Framework, a nested expression can be placed anywhere in the query.</span></span> <span data-ttu-id="e6455-120">Entity SQL ではクエリを柔軟に作成できるので、入れ子になったクエリの順序を含むクエリを記述できます。</span><span class="sxs-lookup"><span data-stu-id="e6455-120">Because Entity SQL allows great flexibility in writing queries, it is possible to write a query that contains an ordering of nested queries.</span></span> <span data-ttu-id="e6455-121">ただし、入れ子になったクエリの順序は維持されません。</span><span class="sxs-lookup"><span data-stu-id="e6455-121">However, the order of a nested query is not preserved.</span></span>  
  
```  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6455-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6455-122">See also</span></span>

- [<span data-ttu-id="e6455-123">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="e6455-123">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
