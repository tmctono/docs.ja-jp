---
title: < = (に等しいまたはそれよりも小さい) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: 9e5a61cb68895982344eadec083a697bdaff54e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193955"
---
# <a name="-less-than-or-equal-to-entity-sql"></a><span data-ttu-id="a5a83-102">\<= (以下) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a5a83-102">\<= (Less Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="a5a83-103">2 つの式を比較して、左の式の値が右の式の値以下であるかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="a5a83-103">Compares two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5a83-104">構文</span><span class="sxs-lookup"><span data-stu-id="a5a83-104">Syntax</span></span>  
  
```  
expression <= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a5a83-105">引数</span><span class="sxs-lookup"><span data-stu-id="a5a83-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="a5a83-106">任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="a5a83-106">Any valid expression.</span></span> <span data-ttu-id="a5a83-107">両方の式とも、暗黙的に変換可能なデータ型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a5a83-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a5a83-108">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="a5a83-108">Result Types</span></span>  
 `true` <span data-ttu-id="a5a83-109">左の式がある右の式以下の値を場合それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="a5a83-109">if the left expression has a value less than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5a83-110">例</span><span class="sxs-lookup"><span data-stu-id="a5a83-110">Example</span></span>  
 <span data-ttu-id="a5a83-111">次の Entity SQL クエリは「<=」比較演算子を使用して 2 つの式を比較し、左の式の値が右の式の値以下であるかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="a5a83-111">The following Entity SQL query uses <= comparison operator to compare two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span> <span data-ttu-id="a5a83-112">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="a5a83-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a5a83-113">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5a83-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a5a83-114">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="a5a83-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="a5a83-115">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="a5a83-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="a5a83-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5a83-116">See also</span></span>

- [<span data-ttu-id="a5a83-117">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="a5a83-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
