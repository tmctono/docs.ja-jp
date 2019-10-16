---
title: < (より小さい) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: fb3f4a1c6bc0df6af3c27836f7b53b2701776366
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319693"
---
# <a name="-less-than-entity-sql"></a><span data-ttu-id="0e57d-102">\< (より小さい) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0e57d-102">\< (Less Than) (Entity SQL)</span></span>
<span data-ttu-id="0e57d-103">2 つの式を比較して、左の式の値が右の式の値よりも小さいかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="0e57d-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e57d-104">構文</span><span class="sxs-lookup"><span data-stu-id="0e57d-104">Syntax</span></span>  
  
```sql  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="0e57d-105">引数</span><span class="sxs-lookup"><span data-stu-id="0e57d-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="0e57d-106">任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="0e57d-106">Any valid expression.</span></span> <span data-ttu-id="0e57d-107">両方の式とも、暗黙的に変換可能なデータ型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="0e57d-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0e57d-108">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="0e57d-108">Result Types</span></span>  
 <span data-ttu-id="0e57d-109">左の式の値が右の式の値よりも小さい場合は`true` 、そうでない場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="0e57d-109">`true` if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e57d-110">例</span><span class="sxs-lookup"><span data-stu-id="0e57d-110">Example</span></span>  
 <span data-ttu-id="0e57d-111">次の Entity SQL クエリは、「<」比較演算子を使用して 2 つの式を比較し、左の式の値が右の式の値よりも小さいかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="0e57d-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="0e57d-112">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="0e57d-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0e57d-113">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0e57d-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="0e57d-114">「 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0e57d-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="0e57d-115">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="0e57d-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a><span data-ttu-id="0e57d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e57d-116">See also</span></span>

- [<span data-ttu-id="0e57d-117">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="0e57d-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
