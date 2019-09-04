---
title: '- 8060(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: d4e4c1449b665e6dea22bfcc0ee2277478b4da1a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251054"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="0609e-102">/ (除算) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0609e-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="0609e-103">1 つの値を別の値で除算します。</span><span class="sxs-lookup"><span data-stu-id="0609e-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0609e-104">構文</span><span class="sxs-lookup"><span data-stu-id="0609e-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="0609e-105">引数</span><span class="sxs-lookup"><span data-stu-id="0609e-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="0609e-106">除算する数値式。</span><span class="sxs-lookup"><span data-stu-id="0609e-106">The numeric expression to divide.</span></span> <span data-ttu-id="0609e-107">`dividend` は、任意の数値データ型の有効な式です。</span><span class="sxs-lookup"><span data-stu-id="0609e-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="0609e-108">被除数を除算する数値式。</span><span class="sxs-lookup"><span data-stu-id="0609e-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="0609e-109">`divisor` は、任意の数値データ型の有効な式です。</span><span class="sxs-lookup"><span data-stu-id="0609e-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0609e-110">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="0609e-110">Result Types</span></span>  
 <span data-ttu-id="0609e-111">2 つの引数の暗黙の型の昇格の結果であるデータ型。</span><span class="sxs-lookup"><span data-stu-id="0609e-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="0609e-112">暗黙の型の昇格の詳細については、「[型システム](type-system-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0609e-112">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0609e-113">例</span><span class="sxs-lookup"><span data-stu-id="0609e-113">Example</span></span>  
 <span data-ttu-id="0609e-114">次の Entity SQL クエリでは、/算術演算子を使用して、1つの数値を別の数値で除算します。</span><span class="sxs-lookup"><span data-stu-id="0609e-114">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="0609e-115">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="0609e-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0609e-116">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0609e-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="0609e-117">[「方法:StructuralType の結果](../how-to-execute-a-query-that-returns-structuraltype-results.md)を返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="0609e-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="0609e-118">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="0609e-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="0609e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0609e-119">See also</span></span>

- [<span data-ttu-id="0609e-120">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="0609e-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
