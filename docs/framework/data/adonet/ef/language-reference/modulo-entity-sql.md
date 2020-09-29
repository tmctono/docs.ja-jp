---
title: (剰余) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: 25bd34db3a627fa708e1ab9a3f0e237426487bcb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175708"
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="fc606-102">(剰余) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="fc606-102">(Modulo) (Entity SQL)</span></span>

<span data-ttu-id="fc606-103">ある式を別の式で除算した結果の余りを返します。</span><span class="sxs-lookup"><span data-stu-id="fc606-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc606-104">構文</span><span class="sxs-lookup"><span data-stu-id="fc606-104">Syntax</span></span>  
  
```sql  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="fc606-105">引数</span><span class="sxs-lookup"><span data-stu-id="fc606-105">Arguments</span></span>  

 `dividend`  
 <span data-ttu-id="fc606-106">除算する数値式。</span><span class="sxs-lookup"><span data-stu-id="fc606-106">The numeric expression to divide.</span></span> <span data-ttu-id="fc606-107">`dividend` は、任意の数値データ型の有効な式です。</span><span class="sxs-lookup"><span data-stu-id="fc606-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="fc606-108">被除数を除算する数値式。</span><span class="sxs-lookup"><span data-stu-id="fc606-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="fc606-109">`divisor` は、任意の数値データ型の有効な式です。</span><span class="sxs-lookup"><span data-stu-id="fc606-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="fc606-110">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="fc606-110">Result Types</span></span>  

 <span data-ttu-id="fc606-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="fc606-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc606-112">例</span><span class="sxs-lookup"><span data-stu-id="fc606-112">Example</span></span>  

 <span data-ttu-id="fc606-113">次の Entity SQL クエリでは、% 算術演算子を使用して、特定の式を別の式で除算した結果の余りを返します。</span><span class="sxs-lookup"><span data-stu-id="fc606-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="fc606-114">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="fc606-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="fc606-115">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fc606-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="fc606-116">「[方法: StructuralType 結果を返すクエリを実行する](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fc606-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="fc606-117">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="fc606-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#MODULO](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="fc606-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc606-118">See also</span></span>

- [<span data-ttu-id="fc606-119">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="fc606-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
