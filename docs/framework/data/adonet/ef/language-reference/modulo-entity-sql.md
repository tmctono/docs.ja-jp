---
title: (剰余) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: e2d2c4cd6fd62cf5785d6b69aa399a74f8d04d30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59326737"
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="e7a74-102">(剰余) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e7a74-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="e7a74-103">ある式を別の式で除算した結果の余りを返します。</span><span class="sxs-lookup"><span data-stu-id="e7a74-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7a74-104">構文</span><span class="sxs-lookup"><span data-stu-id="e7a74-104">Syntax</span></span>  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="e7a74-105">引数</span><span class="sxs-lookup"><span data-stu-id="e7a74-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="e7a74-106">除算する数値式。</span><span class="sxs-lookup"><span data-stu-id="e7a74-106">The numeric expression to divide.</span></span> <span data-ttu-id="e7a74-107">`dividend` は、任意の数値データ型の有効な式です。</span><span class="sxs-lookup"><span data-stu-id="e7a74-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="e7a74-108">被除数を除算する数値式。</span><span class="sxs-lookup"><span data-stu-id="e7a74-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="e7a74-109">`divisor` は、任意の数値データ型の有効な式です。</span><span class="sxs-lookup"><span data-stu-id="e7a74-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e7a74-110">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="e7a74-110">Result Types</span></span>  
 <span data-ttu-id="e7a74-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="e7a74-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7a74-112">例</span><span class="sxs-lookup"><span data-stu-id="e7a74-112">Example</span></span>  
 <span data-ttu-id="e7a74-113">次の Entity SQL クエリでは、% 算術演算子を使用して、特定の式を別の式で除算した結果の余りを返します。</span><span class="sxs-lookup"><span data-stu-id="e7a74-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="e7a74-114">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e7a74-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e7a74-115">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7a74-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="e7a74-116">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="e7a74-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="e7a74-117">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="e7a74-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="e7a74-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7a74-118">See also</span></span>

- [<span data-ttu-id="e7a74-119">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="e7a74-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
