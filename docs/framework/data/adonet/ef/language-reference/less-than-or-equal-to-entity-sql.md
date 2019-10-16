---
title: < = (以下) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: b3c8fef47b06b9fdd0a1619a9e56d3d916d9dd2d
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319634"
---
# <a name="-less-than-or-equal-to-entity-sql"></a><span data-ttu-id="94ff6-102">\<= (以下) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="94ff6-102">\<= (Less Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="94ff6-103">2 つの式を比較して、左の式の値が右の式の値以下であるかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="94ff6-103">Compares two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94ff6-104">構文</span><span class="sxs-lookup"><span data-stu-id="94ff6-104">Syntax</span></span>  
  
```sql  
expression <= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="94ff6-105">引数</span><span class="sxs-lookup"><span data-stu-id="94ff6-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="94ff6-106">任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="94ff6-106">Any valid expression.</span></span> <span data-ttu-id="94ff6-107">両方の式とも、暗黙的に変換可能なデータ型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="94ff6-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="94ff6-108">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="94ff6-108">Result Types</span></span>  
 <span data-ttu-id="94ff6-109">左の式の値が右の式の値以下である場合は`true` 、そうでない場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="94ff6-109">`true` if the left expression has a value less than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94ff6-110">例</span><span class="sxs-lookup"><span data-stu-id="94ff6-110">Example</span></span>  
 <span data-ttu-id="94ff6-111">次の Entity SQL クエリは「<=」比較演算子を使用して 2 つの式を比較し、左の式の値が右の式の値以下であるかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="94ff6-111">The following Entity SQL query uses <= comparison operator to compare two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span> <span data-ttu-id="94ff6-112">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="94ff6-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="94ff6-113">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="94ff6-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="94ff6-114">「 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="94ff6-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="94ff6-115">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="94ff6-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS_OR_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="94ff6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="94ff6-116">See also</span></span>

- [<span data-ttu-id="94ff6-117">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="94ff6-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
