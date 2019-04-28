---
title: + (文字列連結)(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 5f2c031218a9e533889c696bc592e73a27b51d06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797671"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="2693f-102">+ (文字列連結) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2693f-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="2693f-103">2 つの文字列を連結します。</span><span class="sxs-lookup"><span data-stu-id="2693f-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2693f-104">構文</span><span class="sxs-lookup"><span data-stu-id="2693f-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="2693f-105">引数</span><span class="sxs-lookup"><span data-stu-id="2693f-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2693f-106">EDM.String データ型の任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="2693f-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="2693f-107">両方の式は、同じデータ型でなければなりません。または、一方の式をもう一方の式のデータ型に暗黙的に変換できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2693f-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2693f-108">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="2693f-108">Result Types</span></span>  
 <span data-ttu-id="2693f-109">2 つの引数の暗黙の型の昇格の結果であるデータ型。</span><span class="sxs-lookup"><span data-stu-id="2693f-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="2693f-110">暗黙的な型の上位変換の詳細については、次を参照してください。[型システム](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="2693f-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2693f-111">例</span><span class="sxs-lookup"><span data-stu-id="2693f-111">Example</span></span>  
 <span data-ttu-id="2693f-112">次の Entity SQL クエリでは、+ 演算子を使用して、2 つの文字列を連結します。</span><span class="sxs-lookup"><span data-stu-id="2693f-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="2693f-113">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="2693f-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2693f-114">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2693f-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2693f-115">」の手順に従って[方法。PrimitiveType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="2693f-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="2693f-116">次のクエリを引数として `ExecutePrimitiveTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="2693f-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="2693f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2693f-117">See also</span></span>

- [<span data-ttu-id="2693f-118">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="2693f-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="2693f-119">概念モデルの型 (CSDL)</span><span class="sxs-lookup"><span data-stu-id="2693f-119">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
