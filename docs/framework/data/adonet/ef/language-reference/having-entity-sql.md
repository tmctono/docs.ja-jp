---
title: HAVING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
ms.openlocfilehash: 76a63140668fb1f41cf9e6f901d9a43240a1d098
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936085"
---
# <a name="having-entity-sql"></a><span data-ttu-id="2097c-102">HAVING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2097c-102">HAVING (Entity SQL)</span></span>
<span data-ttu-id="2097c-103">グループまたは集計の検索条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="2097c-103">Specifies a search condition for a group or an aggregate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2097c-104">構文</span><span class="sxs-lookup"><span data-stu-id="2097c-104">Syntax</span></span>  
  
```  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2097c-105">引数</span><span class="sxs-lookup"><span data-stu-id="2097c-105">Arguments</span></span>  
 `search_condition`  
 <span data-ttu-id="2097c-106">グループまたは集計の検索条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="2097c-106">Specifies the search condition for the group or the aggregate to meet.</span></span> <span data-ttu-id="2097c-107">HAVING 句を GROUP BY ALL と共に使用した場合、HAVING 句により ALL はオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="2097c-107">When HAVING is used with GROUP BY ALL, the HAVING clause overrides ALL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2097c-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="2097c-108">Remarks</span></span>  
 <span data-ttu-id="2097c-109">HAVING 句は、グループ化の結果について追加的なフィルター処理条件を指定する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="2097c-109">The HAVING clause is used to specify an additional filtering condition on the result of a grouping.</span></span> <span data-ttu-id="2097c-110">クエリ式で GROUP BY 句が指定されていないと、暗黙的な単独セットのグループになります。</span><span class="sxs-lookup"><span data-stu-id="2097c-110">If no GROUP BY clause is specified in the query expression, an implicit single-set group is assumed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2097c-111">HAVING は、 [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)ステートメントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2097c-111">HAVING can be used only with the [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) statement.</span></span> <span data-ttu-id="2097c-112">[GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md)を使用しない場合、HAVING は WHERE 句と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="2097c-112">When [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) is not used, HAVING behaves like a WHERE clause.</span></span>  
  
 <span data-ttu-id="2097c-113">GROUP BY 操作後に適用される場合を除いて、HAVING 句は WHERE 句と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="2097c-113">The HAVING clause works like the WHERE clause except that it is applied after the GROUP BY operation.</span></span> <span data-ttu-id="2097c-114">つまり、次の例のように、HAVING 句は別名および集計のグループ化のみを参照できます。</span><span class="sxs-lookup"><span data-stu-id="2097c-114">This means that the HAVING clause can only make references to grouping aliases and aggregates, as illustrated in the following example.</span></span>  
  
```  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 <span data-ttu-id="2097c-115">前述のグループは、複数の製品を含むグループのみに制限されています。</span><span class="sxs-lookup"><span data-stu-id="2097c-115">The previous restricts the groups to only those that include more than one product.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2097c-116">例</span><span class="sxs-lookup"><span data-stu-id="2097c-116">Example</span></span>  
 <span data-ttu-id="2097c-117">次の Entity SQL のクエリでは、HAVING および GROUP BY 操作を使用して、グループまたは集計の検索条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="2097c-117">The following Entity SQL query uses the HAVING and GROUP BY operators to specify a search condition for a group or an aggregate.</span></span> <span data-ttu-id="2097c-118">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="2097c-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2097c-119">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2097c-119">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2097c-120">[「方法:PrimitiveType の結果](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)を返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="2097c-120">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="2097c-121">次のクエリを引数として `ExecutePrimitiveTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="2097c-121">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#HAVING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#having)]  
  
## <a name="see-also"></a><span data-ttu-id="2097c-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2097c-122">See also</span></span>

- [<span data-ttu-id="2097c-123">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="2097c-123">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="2097c-124">クエリ式</span><span class="sxs-lookup"><span data-stu-id="2097c-124">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
