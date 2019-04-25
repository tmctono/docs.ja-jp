---
title: '> (より大きい)(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: e1d13fa863eb79982d239f4e2dc298f7fcd1346f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879490"
---
# <a name="-greater-than-entity-sql"></a><span data-ttu-id="0d77f-102">> (より大きい) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0d77f-102">> (Greater Than) (Entity SQL)</span></span>
<span data-ttu-id="0d77f-103">2 つの式を比較して、左の式の値が右の式の値よりも大きいかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="0d77f-103">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d77f-104">構文</span><span class="sxs-lookup"><span data-stu-id="0d77f-104">Syntax</span></span>  
  
```  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="0d77f-105">引数</span><span class="sxs-lookup"><span data-stu-id="0d77f-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="0d77f-106">任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="0d77f-106">Any valid expression.</span></span> <span data-ttu-id="0d77f-107">両方の式とも、暗黙的に変換可能なデータ型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="0d77f-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0d77f-108">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="0d77f-108">Result Types</span></span>  
 <span data-ttu-id="0d77f-109">左の式の値が右の式の値よりも大きい場合は`true` 、そうでない場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="0d77f-109">`true` if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d77f-110">例</span><span class="sxs-lookup"><span data-stu-id="0d77f-110">Example</span></span>  
 <span data-ttu-id="0d77f-111">次の Entity SQL クエリは「>」比較演算子を使用して 2 つの式を比較し、左の式の値が右の式の値よりも大きいかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="0d77f-111">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="0d77f-112">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="0d77f-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0d77f-113">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d77f-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="0d77f-114">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="0d77f-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="0d77f-115">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="0d77f-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="0d77f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d77f-116">See also</span></span>

- [<span data-ttu-id="0d77f-117">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="0d77f-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
