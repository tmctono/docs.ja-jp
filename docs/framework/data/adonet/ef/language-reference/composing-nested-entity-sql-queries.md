---
title: 入れ子になった Entity SQL クエリの作成
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: 0ab92c1e41c89f141c3cbd37be3e1e18e64d9666
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833914"
---
# <a name="composing-nested-entity-sql-queries"></a><span data-ttu-id="53a14-102">入れ子になった Entity SQL クエリの作成</span><span class="sxs-lookup"><span data-stu-id="53a14-102">Composing Nested Entity SQL Queries</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="53a14-103">は、機能の豊富な関数言語です。</span><span class="sxs-lookup"><span data-stu-id="53a14-103">is a rich functional language.</span></span> <span data-ttu-id="53a14-104">@No__t-0 のビルディングブロックは式です。</span><span class="sxs-lookup"><span data-stu-id="53a14-104">The building block of [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is an expression.</span></span> <span data-ttu-id="53a14-105">従来の SQL とは異なり、@no__t 0 は表形式の結果セットに限定されません。 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] は、リテラル、パラメーター、または入れ子になった式を含む複雑な式の作成をサポートします。</span><span class="sxs-lookup"><span data-stu-id="53a14-105">Unlike conventional SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not limited to a tabular result set: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports composing complex expressions that can have literals, parameters, or nested expressions.</span></span> <span data-ttu-id="53a14-106">式の値は、パラメーター化することも、他の式で構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="53a14-106">A value in the expression can be parameterized or composed of some other expression.</span></span>  
  
## <a name="nested-expressions"></a><span data-ttu-id="53a14-107">入れ子になった式</span><span class="sxs-lookup"><span data-stu-id="53a14-107">Nested Expressions</span></span>  
 <span data-ttu-id="53a14-108">入れ子になった式は、その式によって返される型の値が受け入れられる場所であればどこにでも配置できます。</span><span class="sxs-lookup"><span data-stu-id="53a14-108">A nested expression can be placed anywhere a value of the type it returns is accepted.</span></span> <span data-ttu-id="53a14-109">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="53a14-109">For example:</span></span>  
  
```sql  
-- Returns a hierarchical collection of three elements at top-level.   
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 <span data-ttu-id="53a14-110">入れ子になったクエリは、projection 句に配置できます。</span><span class="sxs-lookup"><span data-stu-id="53a14-110">A nested query can be placed in a projection clause.</span></span> <span data-ttu-id="53a14-111">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="53a14-111">For example:</span></span>  
  
```sql  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)   
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)   
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 <span data-ttu-id="53a14-112">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] では、入れ子になったクエリを次のようにかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="53a14-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], nested queries must always be enclosed in parentheses:</span></span>  
  
```sql  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 <span data-ttu-id="53a14-113">次の例は @no__t 0 で式を適切に入れ子にする方法を示しています。[方法:2つのクエリの和集合を @ no__t-0 として並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="53a14-113">The following example demonstrates how to properly nest expressions in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [How to: Order the Union of Two Queries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100)).</span></span>  
  
## <a name="nested-queries-in-projection"></a><span data-ttu-id="53a14-114">投影内の入れ子になったクエリ</span><span class="sxs-lookup"><span data-stu-id="53a14-114">Nested Queries in Projection</span></span>  
 <span data-ttu-id="53a14-115">project 句内の入れ子になったクエリは、サーバーでデカルト積に変換されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="53a14-115">Nested queries in the project clause might get translated into Cartesian product queries on the server.</span></span> <span data-ttu-id="53a14-116">SLQ Server などの一部のバックエンド サーバーでは、これによって TempDB テーブルのサイズが非常に大きくなり、サーバーのパフォーマンスに悪影響を及ぼす場合があります。</span><span class="sxs-lookup"><span data-stu-id="53a14-116">In some backend servers, including SLQ Server, this can cause the TempDB table to get very large, which can adversely affect server performance.</span></span>  
  
 <span data-ttu-id="53a14-117">以下は、このようなクエリの例です。</span><span class="sxs-lookup"><span data-stu-id="53a14-117">The following is an example of such a query:</span></span>  
  
```sql  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="53a14-118">入れ子になったクエリの順序</span><span class="sxs-lookup"><span data-stu-id="53a14-118">Ordering Nested Queries</span></span>  
 <span data-ttu-id="53a14-119">Entity Framework では、入れ子になった式をクエリ内の任意の場所に配置できます。</span><span class="sxs-lookup"><span data-stu-id="53a14-119">In the Entity Framework, a nested expression can be placed anywhere in the query.</span></span> <span data-ttu-id="53a14-120">Entity SQL ではクエリを柔軟に作成できるので、入れ子になったクエリの順序を含むクエリを記述できます。</span><span class="sxs-lookup"><span data-stu-id="53a14-120">Because Entity SQL allows great flexibility in writing queries, it is possible to write a query that contains an ordering of nested queries.</span></span> <span data-ttu-id="53a14-121">ただし、入れ子になったクエリの順序は維持されません。</span><span class="sxs-lookup"><span data-stu-id="53a14-121">However, the order of a nested query is not preserved.</span></span>  
  
```sql  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="see-also"></a><span data-ttu-id="53a14-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="53a14-122">See also</span></span>

- [<span data-ttu-id="53a14-123">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="53a14-123">Entity SQL Overview</span></span>](entity-sql-overview.md)
