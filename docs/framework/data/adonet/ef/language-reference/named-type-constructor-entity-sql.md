---
title: 名前付きの型コンストラクター (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: f40adce1a9e031ed0b7cd5d03d9c63db255aa610
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319574"
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="28273-102">名前付きの型コンストラクター (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="28273-102">Named Type Constructor (Entity SQL)</span></span>
<span data-ttu-id="28273-103">エンティティ型や複合型など、概念モデル標準型のインスタンスの作成に使用します。</span><span class="sxs-lookup"><span data-stu-id="28273-103">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28273-104">構文</span><span class="sxs-lookup"><span data-stu-id="28273-104">Syntax</span></span>  
  
```sql  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="28273-105">引数</span><span class="sxs-lookup"><span data-stu-id="28273-105">Arguments</span></span>  
 `identifier`  
 <span data-ttu-id="28273-106">単純な識別子および引用符で囲まれた識別子の値。</span><span class="sxs-lookup"><span data-stu-id="28273-106">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="28273-107">詳細については、「[識別子](identifiers-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28273-107">For more information see, [Identifiers](identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="28273-108">型の宣言に表示される順序と同じ順序であると見なされる型の属性。</span><span class="sxs-lookup"><span data-stu-id="28273-108">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28273-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="28273-109">Return Value</span></span>  
 <span data-ttu-id="28273-110">名前付きの複合型とエンティティ型のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="28273-110">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28273-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="28273-111">Remarks</span></span>  
 <span data-ttu-id="28273-112">次の例は、標準型と複合型を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="28273-112">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="28273-113">次の式は、 `Person` 型のインスタンスを作成する式です。</span><span class="sxs-lookup"><span data-stu-id="28273-113">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="28273-114">次の式は、複合型のインスタンスを作成する式です。</span><span class="sxs-lookup"><span data-stu-id="28273-114">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="28273-115">次の式は、入れ子になった複合型のインスタンスを作成する式です。</span><span class="sxs-lookup"><span data-stu-id="28273-115">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="28273-116">次の式は、入れ子になった複合型を持つエンティティのインスタンスを作成する式です。</span><span class="sxs-lookup"><span data-stu-id="28273-116">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="28273-117">次の例は、複合型のプロパティを null に初期化する方法を示しています。`MyModel.ZipCode(‘98118’, null)`</span><span class="sxs-lookup"><span data-stu-id="28273-117">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="28273-118">例</span><span class="sxs-lookup"><span data-stu-id="28273-118">Example</span></span>  
 <span data-ttu-id="28273-119">次の Entity SQL クエリでは、名前付きの型コンストラクターを使用して、概念モデル型のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="28273-119">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="28273-120">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="28273-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="28273-121">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="28273-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="28273-122">「 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="28273-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="28273-123">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="28273-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NAMED_TYPE_CONSTRUCTOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="28273-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="28273-124">See also</span></span>

- [<span data-ttu-id="28273-125">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="28273-125">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="28273-126">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="28273-126">Entity SQL Reference</span></span>](entity-sql-reference.md)
