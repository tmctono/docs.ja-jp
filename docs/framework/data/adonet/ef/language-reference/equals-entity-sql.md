---
title: = (等しい) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: ad9eda5a3544ea157d06c57876b1b0454a25dba1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215681"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="35184-102">= (等しい) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="35184-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="35184-103">2 つの式の等価性を比較します。</span><span class="sxs-lookup"><span data-stu-id="35184-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35184-104">構文</span><span class="sxs-lookup"><span data-stu-id="35184-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="35184-105">引数</span><span class="sxs-lookup"><span data-stu-id="35184-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="35184-106">任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="35184-106">Any valid expression.</span></span> <span data-ttu-id="35184-107">両方の式とも、暗黙的に変換可能なデータ型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="35184-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="35184-108">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="35184-108">Result Types</span></span>  
 `true` <span data-ttu-id="35184-109">左の式が右の式に等しい場合それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="35184-109">if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35184-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="35184-110">Remarks</span></span>  
 <span data-ttu-id="35184-111">== 演算子は = 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="35184-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35184-112">例</span><span class="sxs-lookup"><span data-stu-id="35184-112">Example</span></span>  
 <span data-ttu-id="35184-113">次の Entity SQL クエリでは、= 比較演算子を使用して 2 つの式の等価性を比較します。</span><span class="sxs-lookup"><span data-stu-id="35184-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="35184-114">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="35184-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="35184-115">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="35184-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="35184-116">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="35184-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="35184-117">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="35184-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="35184-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="35184-118">See also</span></span>

- [<span data-ttu-id="35184-119">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="35184-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
