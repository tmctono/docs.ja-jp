---
title: '- 引く(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: 8b5cfee4c82757e55babdf1ad14f6cf3c743a5a2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249015"
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="685be-102">- (減算) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="685be-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="685be-103">2 つの値の間で減算をします。</span><span class="sxs-lookup"><span data-stu-id="685be-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="685be-104">構文</span><span class="sxs-lookup"><span data-stu-id="685be-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="685be-105">引数</span><span class="sxs-lookup"><span data-stu-id="685be-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="685be-106">任意の数値データ型の有効な式。</span><span class="sxs-lookup"><span data-stu-id="685be-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="685be-107">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="685be-107">Result Types</span></span>  
 <span data-ttu-id="685be-108">2 つの引数の暗黙の型の昇格の結果であるデータ型。</span><span class="sxs-lookup"><span data-stu-id="685be-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="685be-109">暗黙の型の昇格の詳細については、「[型システム](type-system-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="685be-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="685be-110">例</span><span class="sxs-lookup"><span data-stu-id="685be-110">Example</span></span>  
 <span data-ttu-id="685be-111">次の Entity SQL クエリでは、- 算術演算子を使用して 2 つの数値の間で減算をします。</span><span class="sxs-lookup"><span data-stu-id="685be-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="685be-112">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="685be-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="685be-113">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="685be-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="685be-114">[「方法:StructuralType の結果](../how-to-execute-a-query-that-returns-structuraltype-results.md)を返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="685be-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="685be-115">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="685be-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="685be-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="685be-116">See also</span></span>

- [<span data-ttu-id="685be-117">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="685be-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
