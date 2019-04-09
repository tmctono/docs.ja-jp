---
title: (剰余) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: b08689b6f5b17950738c557e02f995fa85aeb35e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160486"
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="cf8d8-102">(剰余) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cf8d8-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="cf8d8-103">ある式を別の式で除算した結果の余りを返します。</span><span class="sxs-lookup"><span data-stu-id="cf8d8-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf8d8-104">構文</span><span class="sxs-lookup"><span data-stu-id="cf8d8-104">Syntax</span></span>  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="cf8d8-105">引数</span><span class="sxs-lookup"><span data-stu-id="cf8d8-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="cf8d8-106">除算する数値式。</span><span class="sxs-lookup"><span data-stu-id="cf8d8-106">The numeric expression to divide.</span></span> `dividend` <span data-ttu-id="cf8d8-107">数値データ型のいずれかの任意の有効な式です。</span><span class="sxs-lookup"><span data-stu-id="cf8d8-107">is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="cf8d8-108">被除数を除算する数値式。</span><span class="sxs-lookup"><span data-stu-id="cf8d8-108">The numeric expression to divide the dividend by.</span></span> `divisor` <span data-ttu-id="cf8d8-109">数値データ型のいずれかの任意の有効な式です。</span><span class="sxs-lookup"><span data-stu-id="cf8d8-109">is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="cf8d8-110">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="cf8d8-110">Result Types</span></span>  
 <span data-ttu-id="cf8d8-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="cf8d8-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf8d8-112">例</span><span class="sxs-lookup"><span data-stu-id="cf8d8-112">Example</span></span>  
 <span data-ttu-id="cf8d8-113">次の Entity SQL クエリでは、% 算術演算子を使用して、特定の式を別の式で除算した結果の余りを返します。</span><span class="sxs-lookup"><span data-stu-id="cf8d8-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="cf8d8-114">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="cf8d8-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cf8d8-115">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf8d8-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="cf8d8-116">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf8d8-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="cf8d8-117">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="cf8d8-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="cf8d8-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf8d8-118">See also</span></span>

- [<span data-ttu-id="cf8d8-119">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="cf8d8-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
