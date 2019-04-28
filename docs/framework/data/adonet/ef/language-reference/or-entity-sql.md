---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: d089bcec56ff13ddcd5250a63aee6a00d0c3ef11
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760312"
---
# <a name="-or-entity-sql"></a><span data-ttu-id="4d6cf-102">|| (OR) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4d6cf-102">|| (OR) (Entity SQL)</span></span>
<span data-ttu-id="4d6cf-103">2 つの `Boolean` 式を結合します。</span><span class="sxs-lookup"><span data-stu-id="4d6cf-103">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d6cf-104">構文</span><span class="sxs-lookup"><span data-stu-id="4d6cf-104">Syntax</span></span>  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="4d6cf-105">引数</span><span class="sxs-lookup"><span data-stu-id="4d6cf-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="4d6cf-106">`Boolean`値を返す任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="4d6cf-106">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d6cf-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="4d6cf-107">Return Value</span></span>  
 <span data-ttu-id="4d6cf-108">いずれかの条件が`true` の場合は `true`、それ以外の場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="4d6cf-108">`true` when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d6cf-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="4d6cf-109">Remarks</span></span>  
 <span data-ttu-id="4d6cf-110">OR は [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の論理演算子です。</span><span class="sxs-lookup"><span data-stu-id="4d6cf-110">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="4d6cf-111">2 つの条件を結合する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="4d6cf-111">It is used to combine two conditions.</span></span> <span data-ttu-id="4d6cf-112">1 つのステートメント内に複数の論理演算子が使われている場合、OR 演算子は AND 演算子の次に評価されます。</span><span class="sxs-lookup"><span data-stu-id="4d6cf-112">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="4d6cf-113">ただし、かっこを使うと、演算の順序を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4d6cf-113">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="4d6cf-114">二重の縦棒 (&#124;&#124;)、OR 演算子と同じ機能があります。</span><span class="sxs-lookup"><span data-stu-id="4d6cf-114">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="4d6cf-115">使用可能な入力値と戻り値の型を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="4d6cf-115">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="4d6cf-116">true</span><span class="sxs-lookup"><span data-stu-id="4d6cf-116">TRUE</span></span>|<span data-ttu-id="4d6cf-117">true</span><span class="sxs-lookup"><span data-stu-id="4d6cf-117">TRUE</span></span>|<span data-ttu-id="4d6cf-118">true</span><span class="sxs-lookup"><span data-stu-id="4d6cf-118">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="4d6cf-119">true</span><span class="sxs-lookup"><span data-stu-id="4d6cf-119">TRUE</span></span>|<span data-ttu-id="4d6cf-120">false</span><span class="sxs-lookup"><span data-stu-id="4d6cf-120">FALSE</span></span>|<span data-ttu-id="4d6cf-121">NULL</span><span class="sxs-lookup"><span data-stu-id="4d6cf-121">NULL</span></span>|  
|`NULL`|<span data-ttu-id="4d6cf-122">true</span><span class="sxs-lookup"><span data-stu-id="4d6cf-122">TRUE</span></span>|<span data-ttu-id="4d6cf-123">NULL</span><span class="sxs-lookup"><span data-stu-id="4d6cf-123">NULL</span></span>|<span data-ttu-id="4d6cf-124">NULL</span><span class="sxs-lookup"><span data-stu-id="4d6cf-124">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4d6cf-125">例</span><span class="sxs-lookup"><span data-stu-id="4d6cf-125">Example</span></span>  
 <span data-ttu-id="4d6cf-126">次の Entity SQL クエリでは、OR 演算子を使用して 2 つの `Boolean` 式を結合します。</span><span class="sxs-lookup"><span data-stu-id="4d6cf-126">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="4d6cf-127">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="4d6cf-127">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4d6cf-128">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4d6cf-128">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="4d6cf-129">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d6cf-129">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="4d6cf-130">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="4d6cf-130">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a><span data-ttu-id="4d6cf-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d6cf-131">See also</span></span>

- [<span data-ttu-id="4d6cf-132">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="4d6cf-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
