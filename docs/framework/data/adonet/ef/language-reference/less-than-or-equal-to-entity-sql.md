---
title: < = (に等しいまたはそれよりも小さい) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: 7a65984da22d125bdbdd5cfadb5a2051fa3dafdc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304767"
---
# <a name="-less-than-or-equal-to-entity-sql"></a><span data-ttu-id="231e4-102">\<= (以下) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="231e4-102">\<= (Less Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="231e4-103">2 つの式を比較して、左の式の値が右の式の値以下であるかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="231e4-103">Compares two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="231e4-104">構文</span><span class="sxs-lookup"><span data-stu-id="231e4-104">Syntax</span></span>  
  
```  
expression <= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="231e4-105">引数</span><span class="sxs-lookup"><span data-stu-id="231e4-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="231e4-106">任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="231e4-106">Any valid expression.</span></span> <span data-ttu-id="231e4-107">両方の式とも、暗黙的に変換可能なデータ型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="231e4-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="231e4-108">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="231e4-108">Result Types</span></span>  
 <span data-ttu-id="231e4-109">左の式の値が右の式の値以下である場合は`true` 、そうでない場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="231e4-109">`true` if the left expression has a value less than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="231e4-110">例</span><span class="sxs-lookup"><span data-stu-id="231e4-110">Example</span></span>  
 <span data-ttu-id="231e4-111">次の Entity SQL クエリは「<=」比較演算子を使用して 2 つの式を比較し、左の式の値が右の式の値以下であるかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="231e4-111">The following Entity SQL query uses <= comparison operator to compare two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span> <span data-ttu-id="231e4-112">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="231e4-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="231e4-113">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="231e4-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="231e4-114">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="231e4-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="231e4-115">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="231e4-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="231e4-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="231e4-116">See also</span></span>

- [<span data-ttu-id="231e4-117">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="231e4-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
