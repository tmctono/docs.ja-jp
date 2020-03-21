---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 40a5afd7eb99dba7cae8fe14ed0a45213fda94a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149948"
---
# <a name="ref-entity-sql"></a><span data-ttu-id="672da-102">REF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="672da-102">REF (Entity SQL)</span></span>
<span data-ttu-id="672da-103">エンティティ インスタンスへの参照を返します。</span><span class="sxs-lookup"><span data-stu-id="672da-103">Returns a reference to an entity instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="672da-104">構文</span><span class="sxs-lookup"><span data-stu-id="672da-104">Syntax</span></span>  
  
```sql  
REF( expression )
```  
  
## <a name="arguments"></a><span data-ttu-id="672da-105">引数</span><span class="sxs-lookup"><span data-stu-id="672da-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="672da-106">エンティティ型のインスタンスを生成する任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="672da-106">Any valid expression that yields an instance of an entity type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="672da-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="672da-107">Return Value</span></span>  
 <span data-ttu-id="672da-108">指定されたエンティティ インスタンスへの参照。</span><span class="sxs-lookup"><span data-stu-id="672da-108">A reference to the specified entity instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="672da-109">解説</span><span class="sxs-lookup"><span data-stu-id="672da-109">Remarks</span></span>  
 <span data-ttu-id="672da-110">エンティティ参照は、エンティティ キーとエンティティ セット名で構成されます。</span><span class="sxs-lookup"><span data-stu-id="672da-110">An entity reference consists of the entity key and an entity set name.</span></span> <span data-ttu-id="672da-111">異なるエンティティ セットが同じエンティティ型に基づくことができるので、特定のエンティティ キーが複数のエンティティ セットで使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="672da-111">Because different entity sets can be based on the same entity type, a particular entity key can appear in multiple entity sets.</span></span> <span data-ttu-id="672da-112">ただし、エンティティ参照は常に一意です。</span><span class="sxs-lookup"><span data-stu-id="672da-112">However, an entity reference is always unique.</span></span> <span data-ttu-id="672da-113">入力式が永続エンティティを表す場合、このエンティティへの参照が返されます。</span><span class="sxs-lookup"><span data-stu-id="672da-113">If the input expression represents a persisted entity, a reference to this entity will be returned.</span></span> <span data-ttu-id="672da-114">入力式が永続エンティティではない場合は、NULL 参照が返されます。</span><span class="sxs-lookup"><span data-stu-id="672da-114">If the input expression is not a persisted entity, a null reference will be returned.</span></span>  
  
 <span data-ttu-id="672da-115">プロパティ抽出演算子 (.) を使用してエンティティのプロパティにアクセスすると、参照は自動的に逆参照されます。</span><span class="sxs-lookup"><span data-stu-id="672da-115">If the property extraction operator (.) is used to access a property of an entity, the reference is automatically dereferenced.</span></span>  
  
## <a name="example"></a><span data-ttu-id="672da-116">例</span><span class="sxs-lookup"><span data-stu-id="672da-116">Example</span></span>  
 <span data-ttu-id="672da-117">次の Entity SQL クエリは、REF 演算子を使用して入力エンティティ引数の参照を返します。</span><span class="sxs-lookup"><span data-stu-id="672da-117">The following Entity SQL query uses the REF operator to return the reference for an input entity argument.</span></span> <span data-ttu-id="672da-118">プロパティ抽出演算子 (.) を使用して Product エンティティのプロパティにアクセスすることにより、同じクエリでこの参照が逆参照されます。</span><span class="sxs-lookup"><span data-stu-id="672da-118">The same query dereferences the reference because we are using a property extraction operation (.) to access a property of the Product entity.</span></span> <span data-ttu-id="672da-119">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="672da-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="672da-120">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="672da-120">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="672da-121">[「方法: プリミティブ型の結果を返すクエリを実行する](../how-to-execute-a-query-that-returns-primitivetype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="672da-121">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="672da-122">次のクエリを引数として `ExecutePrimitiveTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="672da-122">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#REF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref)]  
  
## <a name="see-also"></a><span data-ttu-id="672da-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="672da-123">See also</span></span>

- [<span data-ttu-id="672da-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="672da-124">DEREF</span></span>](deref-entity-sql.md)
- [<span data-ttu-id="672da-125">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="672da-125">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="672da-126">キー</span><span class="sxs-lookup"><span data-stu-id="672da-126">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="672da-127">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="672da-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="672da-128">型定義</span><span class="sxs-lookup"><span data-stu-id="672da-128">Type Definitions</span></span>](type-definitions-entity-sql.md)
