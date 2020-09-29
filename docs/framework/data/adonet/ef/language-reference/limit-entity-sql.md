---
title: LIMIT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: 81d135785e567d46a105adcafbf083f48cb4868e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161764"
---
# <a name="limit-entity-sql"></a><span data-ttu-id="406bc-102">LIMIT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="406bc-102">LIMIT (Entity SQL)</span></span>

<span data-ttu-id="406bc-103">物理的なページングは、ORDER BY 句の LIMIT サブ句を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="406bc-103">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="406bc-104">LIMIT は ORDER BY 句と切り離して使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="406bc-104">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="406bc-105">構文</span><span class="sxs-lookup"><span data-stu-id="406bc-105">Syntax</span></span>  
  
```sql  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="406bc-106">引数</span><span class="sxs-lookup"><span data-stu-id="406bc-106">Arguments</span></span>  

 `n`  
 <span data-ttu-id="406bc-107">選択する項目の数。</span><span class="sxs-lookup"><span data-stu-id="406bc-107">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="406bc-108">LIMIT 式のサブ句が ORDER BY 句に存在する場合、クエリは並べ替え順序に従って並べ替えられ、結果の行数は LIMIT 式によって制限されます。</span><span class="sxs-lookup"><span data-stu-id="406bc-108">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="406bc-109">たとえば、LIMIT 5 は、結果セットを 5 つのインスタンスまたは行に制限します。</span><span class="sxs-lookup"><span data-stu-id="406bc-109">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="406bc-110">LIMIT は機能的に TOP と等価ですが、LIMIT では ORDER BY 句が存在する必要がある点が異なります。</span><span class="sxs-lookup"><span data-stu-id="406bc-110">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="406bc-111">SKIP および LIMIT は ORDER BY 句と共に別々に使用できます。</span><span class="sxs-lookup"><span data-stu-id="406bc-111">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="406bc-112">TOP 修飾子と SKIP サブ句が同じクエリ式内に存在する場合には、Entity Sql クエリは無効と見なされます。</span><span class="sxs-lookup"><span data-stu-id="406bc-112">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="406bc-113">TOP 式を LIMIT 式に変更してクエリを記述し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="406bc-113">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="406bc-114">例</span><span class="sxs-lookup"><span data-stu-id="406bc-114">Example</span></span>  

 <span data-ttu-id="406bc-115">次の Entity SQL クエリでは、SELECT ステートメントで返されたオブジェクトの並べ替え順序の指定に ORDER BY 演算子を LIMIT と共に使用します。</span><span class="sxs-lookup"><span data-stu-id="406bc-115">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="406bc-116">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="406bc-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="406bc-117">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="406bc-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="406bc-118">「[方法: StructuralType 結果を返すクエリを実行する](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="406bc-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="406bc-119">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="406bc-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LIMIT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="406bc-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="406bc-120">See also</span></span>

- [<span data-ttu-id="406bc-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="406bc-121">ORDER BY</span></span>](order-by-entity-sql.md)
- <span data-ttu-id="406bc-122">[方法: クエリの結果をページングする](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="406bc-122">[How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="406bc-123">ページング</span><span class="sxs-lookup"><span data-stu-id="406bc-123">Paging</span></span>](paging-entity-sql.md)
- [<span data-ttu-id="406bc-124">TOP</span><span class="sxs-lookup"><span data-stu-id="406bc-124">TOP</span></span>](top-entity-sql.md)
