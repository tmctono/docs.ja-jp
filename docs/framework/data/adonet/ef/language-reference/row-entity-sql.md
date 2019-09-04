---
title: ROW (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
ms.openlocfilehash: dfd0031f49cbdf41797cecf21c149fafde4d7a8c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249246"
---
# <a name="row-entity-sql"></a><span data-ttu-id="8e84d-102">ROW (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8e84d-102">ROW (Entity SQL)</span></span>
<span data-ttu-id="8e84d-103">1 つまたは複数の値から構造的に型付けされた匿名レコードを構築します。</span><span class="sxs-lookup"><span data-stu-id="8e84d-103">Constructs anonymous, structurally typed records from one or more values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e84d-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e84d-104">Syntax</span></span>  
  
```  
ROW ( expression [ AS alias ] [,...] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="8e84d-105">引数</span><span class="sxs-lookup"><span data-stu-id="8e84d-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="8e84d-106">行型で構築する値を返す任意の有効なクエリ式。</span><span class="sxs-lookup"><span data-stu-id="8e84d-106">Any valid query expression that returns a value to construct in a row type.</span></span>  
  
 `alias`  
 <span data-ttu-id="8e84d-107">行型で指定された値の別名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e84d-107">Specifies an alias for the value specified in a row type.</span></span> <span data-ttu-id="8e84d-108">別名を指定しないと、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] は [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 別名生成規則に基づいて別名の生成を試みます。</span><span class="sxs-lookup"><span data-stu-id="8e84d-108">If an alias is not provided, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to generate an alias based on the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alias generation rules.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e84d-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="8e84d-109">Return Value</span></span>  
 <span data-ttu-id="8e84d-110">行型。</span><span class="sxs-lookup"><span data-stu-id="8e84d-110">A row type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e84d-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e84d-111">Remarks</span></span>  
 <span data-ttu-id="8e84d-112">1 つまたは複数の値から構造的に型付けされた匿名レコードを構築するには、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の行コンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e84d-112">You use row constructors in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="8e84d-113">行コンストラクターの結果の型は、行の構築に使用された値の型に対応するフィールド型を持つ行型です。</span><span class="sxs-lookup"><span data-stu-id="8e84d-113">The result type of a row constructor is a row type whose field types correspond to the types of the values that were used to construct the row.</span></span> <span data-ttu-id="8e84d-114">たとえば、次の式は `Record(a int, b string, c int)`型の値を構築します。</span><span class="sxs-lookup"><span data-stu-id="8e84d-114">For example, the following expression constructs a value of type `Record(a int, b string, c int)`.</span></span>  
  
```  
ROW(1 AS a, "abc" AS b, a+34 AS c)  
```  
  
 <span data-ttu-id="8e84d-115">行コンストラクターで式の別名が指定されていなければ、Entity Framework は別名の生成を試みます。</span><span class="sxs-lookup"><span data-stu-id="8e84d-115">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="8e84d-116">詳細については、「 [識別子](identifiers-entity-sql.md) 」トピックの「別名規則」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e84d-116">For more information, see the "Aliasing Rules" section of the [Identifiers](identifiers-entity-sql.md) topic.</span></span>  
  
 <span data-ttu-id="8e84d-117">次の規則は、行コンストラクターで別名を定義する式に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8e84d-117">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
- <span data-ttu-id="8e84d-118">行コンストラクターの式で同じコンストラクターの他の別名を参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="8e84d-118">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
- <span data-ttu-id="8e84d-119">同じ行コンストラクター内の 2 つの式に同じ別名を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8e84d-119">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="8e84d-120">クエリコンストラクターの詳細については、「[型の構築](constructing-types-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e84d-120">For more information about query constructors, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e84d-121">例</span><span class="sxs-lookup"><span data-stu-id="8e84d-121">Example</span></span>  
 <span data-ttu-id="8e84d-122">次の Entity SQL クエリは ROW 演算子を使用して、構造的に型付けされた匿名レコードを構築します。</span><span class="sxs-lookup"><span data-stu-id="8e84d-122">The following Entity SQL query uses the ROW operator to construct anonymous, structurally typed records.</span></span> <span data-ttu-id="8e84d-123">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="8e84d-123">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8e84d-124">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8e84d-124">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="8e84d-125">[「方法:StructuralType の結果](../how-to-execute-a-query-that-returns-structuraltype-results.md)を返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="8e84d-125">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="8e84d-126">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="8e84d-126">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ROW](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#row)]  
  
## <a name="see-also"></a><span data-ttu-id="8e84d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e84d-127">See also</span></span>

- [<span data-ttu-id="8e84d-128">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="8e84d-128">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="8e84d-129">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="8e84d-129">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="8e84d-130">型定義</span><span class="sxs-lookup"><span data-stu-id="8e84d-130">Type Definitions</span></span>](type-definitions-entity-sql.md)
