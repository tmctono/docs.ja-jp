---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 8c93e68095a0e0ff63532f53152f166d6c3d047c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150094"
---
# <a name="-or-entity-sql"></a><span data-ttu-id="a87eb-102">|| (OR) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a87eb-102">|| (OR) (Entity SQL)</span></span>
<span data-ttu-id="a87eb-103">2 つの `Boolean` 式を結合します。</span><span class="sxs-lookup"><span data-stu-id="a87eb-103">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a87eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="a87eb-104">Syntax</span></span>  
  
```sql  
boolean_expression OR boolean_expression  
-- or
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a87eb-105">引数</span><span class="sxs-lookup"><span data-stu-id="a87eb-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="a87eb-106">`Boolean`値を返す任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="a87eb-106">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a87eb-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="a87eb-107">Return Value</span></span>  
 <span data-ttu-id="a87eb-108">いずれかの条件が`true` の場合は `true`、それ以外の場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="a87eb-108">`true` when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a87eb-109">解説</span><span class="sxs-lookup"><span data-stu-id="a87eb-109">Remarks</span></span>  
 <span data-ttu-id="a87eb-110">OR は [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の論理演算子です。</span><span class="sxs-lookup"><span data-stu-id="a87eb-110">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="a87eb-111">2 つの条件を結合する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="a87eb-111">It is used to combine two conditions.</span></span> <span data-ttu-id="a87eb-112">1 つのステートメント内に複数の論理演算子が使われている場合、OR 演算子は AND 演算子の次に評価されます。</span><span class="sxs-lookup"><span data-stu-id="a87eb-112">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="a87eb-113">ただし、かっこを使うと、演算の順序を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a87eb-113">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="a87eb-114">二重縦棒 (&#124;&#124;) は OR 演算子と同じ機能を持ちます。</span><span class="sxs-lookup"><span data-stu-id="a87eb-114">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="a87eb-115">使用可能な入力値と戻り値の型を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="a87eb-115">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="a87eb-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="a87eb-116">TRUE</span></span>|<span data-ttu-id="a87eb-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="a87eb-117">TRUE</span></span>|<span data-ttu-id="a87eb-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="a87eb-118">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="a87eb-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="a87eb-119">TRUE</span></span>|<span data-ttu-id="a87eb-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="a87eb-120">FALSE</span></span>|<span data-ttu-id="a87eb-121">NULL</span><span class="sxs-lookup"><span data-stu-id="a87eb-121">NULL</span></span>|  
|`NULL`|<span data-ttu-id="a87eb-122">TRUE</span><span class="sxs-lookup"><span data-stu-id="a87eb-122">TRUE</span></span>|<span data-ttu-id="a87eb-123">NULL</span><span class="sxs-lookup"><span data-stu-id="a87eb-123">NULL</span></span>|<span data-ttu-id="a87eb-124">NULL</span><span class="sxs-lookup"><span data-stu-id="a87eb-124">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a87eb-125">例</span><span class="sxs-lookup"><span data-stu-id="a87eb-125">Example</span></span>  
 <span data-ttu-id="a87eb-126">次の Entity SQL クエリでは、OR 演算子を使用して 2 つの `Boolean` 式を結合します。</span><span class="sxs-lookup"><span data-stu-id="a87eb-126">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="a87eb-127">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="a87eb-127">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a87eb-128">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a87eb-128">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="a87eb-129">「 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a87eb-129">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="a87eb-130">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="a87eb-130">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts 2#OR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#or)]  
  
## <a name="see-also"></a><span data-ttu-id="a87eb-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="a87eb-131">See also</span></span>

- [<span data-ttu-id="a87eb-132">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="a87eb-132">Entity SQL Reference</span></span>](entity-sql-reference.md)
