---
title: '- (減算) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: 17841f336ed186dcbc50b84254048546b15297e7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181038"
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="858d0-102">- (減算) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="858d0-102">- (Subtract) (Entity SQL)</span></span>

<span data-ttu-id="858d0-103">2 つの値の間で減算をします。</span><span class="sxs-lookup"><span data-stu-id="858d0-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="858d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="858d0-104">Syntax</span></span>  
  
```sql  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="858d0-105">引数</span><span class="sxs-lookup"><span data-stu-id="858d0-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="858d0-106">任意の数値データ型の有効な式。</span><span class="sxs-lookup"><span data-stu-id="858d0-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="858d0-107">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="858d0-107">Result Types</span></span>  

 <span data-ttu-id="858d0-108">2 つの引数の暗黙の型の昇格の結果であるデータ型。</span><span class="sxs-lookup"><span data-stu-id="858d0-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="858d0-109">暗黙の型の昇格について詳しくは、「[型システム](type-system-entity-sql.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="858d0-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="858d0-110">例</span><span class="sxs-lookup"><span data-stu-id="858d0-110">Example</span></span>  

 <span data-ttu-id="858d0-111">次の Entity SQL クエリでは、- 算術演算子を使用して 2 つの数値の間で減算をします。</span><span class="sxs-lookup"><span data-stu-id="858d0-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="858d0-112">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="858d0-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="858d0-113">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="858d0-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="858d0-114">「[方法: StructuralType 結果を返すクエリを実行する](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="858d0-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="858d0-115">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="858d0-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#SUBTRACT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="858d0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="858d0-116">See also</span></span>

- [<span data-ttu-id="858d0-117">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="858d0-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
