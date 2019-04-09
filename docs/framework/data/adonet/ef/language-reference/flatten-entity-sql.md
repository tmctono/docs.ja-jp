---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 76fba91f27479df19bbc4ac6e120d615a16f1d42
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115116"
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="aac3d-102">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="aac3d-102">FLATTEN (Entity SQL)</span></span>
<span data-ttu-id="aac3d-103">コレクションのコレクションをフラット化して単一のコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="aac3d-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="aac3d-104">変換後のコレクションは、入れ子構造が失われるだけで、変換前のコレクションとまったく同じ要素を格納します。</span><span class="sxs-lookup"><span data-stu-id="aac3d-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aac3d-105">構文</span><span class="sxs-lookup"><span data-stu-id="aac3d-105">Syntax</span></span>  
  
```  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="aac3d-106">引数</span><span class="sxs-lookup"><span data-stu-id="aac3d-106">Arguments</span></span>  
 `collection`  
 <span data-ttu-id="aac3d-107">値のコレクションのコレクションをフラット化して単一のコレクションとして返す有効な任意の式。</span><span class="sxs-lookup"><span data-stu-id="aac3d-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aac3d-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="aac3d-108">Remarks</span></span>  
 `FLATTEN` <span data-ttu-id="aac3d-109">1 つ、[!INCLUDE[esql](../../../../../../includes/esql-md.md)]演算子を設定します。</span><span class="sxs-lookup"><span data-stu-id="aac3d-109">is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="aac3d-110">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] のすべての集合演算子は左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="aac3d-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="aac3d-111">参照してください[EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)の優先順位は、[!INCLUDE[esql](../../../../../../includes/esql-md.md)]演算子を設定します。</span><span class="sxs-lookup"><span data-stu-id="aac3d-111">See [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aac3d-112">例</span><span class="sxs-lookup"><span data-stu-id="aac3d-112">Example</span></span>  
 <span data-ttu-id="aac3d-113">次の Entity SQL クエリでは、 `FLATTEN` 演算子を使用して、コレクションのコレクションをフラット化されたコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="aac3d-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="aac3d-114">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="aac3d-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="aac3d-115">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="aac3d-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="aac3d-116">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="aac3d-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FLATTEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="aac3d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="aac3d-117">See also</span></span>

- [<span data-ttu-id="aac3d-118">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="aac3d-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
