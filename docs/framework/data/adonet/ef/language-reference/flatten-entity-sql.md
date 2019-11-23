---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 84b846e3db86c664bc42363f3d983a1001f5c318
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833804"
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="7379d-102">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7379d-102">FLATTEN (Entity SQL)</span></span>
<span data-ttu-id="7379d-103">コレクションのコレクションをフラット化して単一のコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="7379d-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="7379d-104">変換後のコレクションは、入れ子構造が失われるだけで、変換前のコレクションとまったく同じ要素を格納します。</span><span class="sxs-lookup"><span data-stu-id="7379d-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7379d-105">構文</span><span class="sxs-lookup"><span data-stu-id="7379d-105">Syntax</span></span>  
  
```sql  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="7379d-106">引数</span><span class="sxs-lookup"><span data-stu-id="7379d-106">Arguments</span></span>  
 `collection`  
 <span data-ttu-id="7379d-107">値のコレクションのコレクションをフラット化して単一のコレクションとして返す有効な任意の式。</span><span class="sxs-lookup"><span data-stu-id="7379d-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7379d-108">コメント</span><span class="sxs-lookup"><span data-stu-id="7379d-108">Remarks</span></span>  
 <span data-ttu-id="7379d-109">`FLATTEN` は、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の集合演算子の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="7379d-109">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="7379d-110">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] のすべての集合演算子は左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="7379d-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="7379d-111">Set 演算子の優先順位につい[ては、「](except-entity-sql.md)EXCEPT[!INCLUDE[esql](../../../../../../includes/esql-md.md)]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7379d-111">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7379d-112">例</span><span class="sxs-lookup"><span data-stu-id="7379d-112">Example</span></span>  
 <span data-ttu-id="7379d-113">次の Entity SQL クエリでは、 `FLATTEN` 演算子を使用して、コレクションのコレクションをフラット化されたコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="7379d-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="7379d-114">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7379d-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="7379d-115">「 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7379d-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="7379d-116">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="7379d-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FLATTEN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="7379d-117">参照</span><span class="sxs-lookup"><span data-stu-id="7379d-117">See also</span></span>

- [<span data-ttu-id="7379d-118">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="7379d-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
