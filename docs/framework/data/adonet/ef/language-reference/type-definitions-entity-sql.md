---
title: 型定義 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 306b204a-ade5-47ef-95b5-c785d2da4a7e
ms.openlocfilehash: 471964266c290d5eba95804dbe1c2bc5225e3f83
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248946"
---
# <a name="type-definitions-entity-sql"></a><span data-ttu-id="b4317-102">型定義 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b4317-102">Type Definitions (Entity SQL)</span></span>
<span data-ttu-id="b4317-103">型定義は、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] Inline 関数の宣言ステートメントで使用されます。</span><span class="sxs-lookup"><span data-stu-id="b4317-103">A type definition is used in the declaration statement of an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Inline function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4317-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="b4317-104">Remarks</span></span>  
 <span data-ttu-id="b4317-105">インライン関数の宣言ステートメントは[、関数の](function-entity-sql.md)名前を表す識別子 (たとえば、"myavg") の後に、かっこ内のパラメーター定義リスト (たとえば、"待機中のコレクション (10進数) ")。</span><span class="sxs-lookup"><span data-stu-id="b4317-105">The declaration statement for an inline function consists of the [FUNCTION](function-entity-sql.md) keyword followed by the identifier representing the function name (for example, "MyAvg") followed by a parameter definition list in parenthesis (for example, "dues Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="b4317-106">パラメーター定義リストは、0 個以上のパラメーター定義で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b4317-106">The parameter definition list consists of zero or more parameter definitions.</span></span> <span data-ttu-id="b4317-107">各パラメーター定義は、識別子 (関数のパラメーターの名前。例 : "dues") とそれに続く型定義 (例 : "Collection(Decimal)") で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b4317-107">Each parameter definition consists of an identifier (the name of the parameter to the function, for example, "dues") followed by a type definition (for example, "Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="b4317-108">型定義は、次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="b4317-108">The type definitions can be either:</span></span>  
  
- <span data-ttu-id="b4317-109">識別子の型 ("Int32" や "AdventureWorks.Order" など)。</span><span class="sxs-lookup"><span data-stu-id="b4317-109">The type of the identifier (for example, "Int32" or "AdventureWorks.Order").</span></span>  
  
- <span data-ttu-id="b4317-110">キーワード `COLLECTION` とそれに続くかっこに囲まれた別の型定義 (例 : "Collection(AdventureWorks.Order)")。</span><span class="sxs-lookup"><span data-stu-id="b4317-110">The keyword `COLLECTION` followed by another type definition in parenthesis (for example, "Collection(AdventureWorks.Order)").</span></span>  
  
- <span data-ttu-id="b4317-111">キーワード ROW とそれに続くかっこに囲まれたプロパティ定義リスト (例 : "Row(x AdventureWorks.Order)")。</span><span class="sxs-lookup"><span data-stu-id="b4317-111">The keyword ROW followed by a list of property definitions in parenthesis (for example, "Row(x AdventureWorks.Order)").</span></span> <span data-ttu-id="b4317-112">プロパティ定義の形式は、"`identifier type_definition`, `identifier type_definition`,..." です。</span><span class="sxs-lookup"><span data-stu-id="b4317-112">Property definitions have a format such as "`identifier type_definition`, `identifier type_definition`, ...".</span></span>  
  
- <span data-ttu-id="b4317-113">キーワード REF とそれに続くかっこに囲まれた識別子の型 (例 : "Ref(AdventureWorks.Order)")。</span><span class="sxs-lookup"><span data-stu-id="b4317-113">The keyword REF followed by the type of the identifier in parenthesis (for example, "Ref(AdventureWorks.Order)").</span></span> <span data-ttu-id="b4317-114">REF 型定義演算子は、引数としてエンティティ型を必要とします。</span><span class="sxs-lookup"><span data-stu-id="b4317-114">The REF type definition operator requires an entity type as the argument.</span></span> <span data-ttu-id="b4317-115">引数としてプリミティブ型を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4317-115">You cannot specify a primitive type as the argument.</span></span>  
  
 <span data-ttu-id="b4317-116">型定義を入れ子にできます (例 : "Collection(Row(x Ref(AdventureWorks.Order)))")。</span><span class="sxs-lookup"><span data-stu-id="b4317-116">You can also nest type definitions (for example, "Collection(Row(x Ref(AdventureWorks.Order)))").</span></span>  
  
 <span data-ttu-id="b4317-117">型定義のオプションは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b4317-117">The type definition options are:</span></span>  
  
- <span data-ttu-id="b4317-118">`IdentifierName supported_type`、、または</span><span class="sxs-lookup"><span data-stu-id="b4317-118">`IdentifierName supported_type`, or</span></span>  
  
- <span data-ttu-id="b4317-119">`IdentifierName` COLLECTION(`type_definition`)、または</span><span class="sxs-lookup"><span data-stu-id="b4317-119">`IdentifierName` COLLECTION(`type_definition`), or</span></span>  
  
- <span data-ttu-id="b4317-120">`IdentifierName` ROW(`property_definition`)、または</span><span class="sxs-lookup"><span data-stu-id="b4317-120">`IdentifierName` ROW(`property_definition`), or</span></span>  
  
- <span data-ttu-id="b4317-121">`IdentifierName` REF(`supported_entity_type`)</span><span class="sxs-lookup"><span data-stu-id="b4317-121">`IdentifierName` REF(`supported_entity_type`)</span></span>  
  
 <span data-ttu-id="b4317-122">プロパティ定義オプションは、`IdentifierName type_definition` です。</span><span class="sxs-lookup"><span data-stu-id="b4317-122">The property definition option is `IdentifierName type_definition`.</span></span>  
  
 <span data-ttu-id="b4317-123">現在の名前空間で使用されている型であれば、いずれもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b4317-123">Supported types are any types in the current namespace.</span></span> <span data-ttu-id="b4317-124">これには、プリミティブ型とエンティティ型の両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b4317-124">These include both primitive and entity types.</span></span>  
  
 <span data-ttu-id="b4317-125">サポートされるエンティティ型は、現在の名前空間で使用されているエンティティ型だけを参照します。</span><span class="sxs-lookup"><span data-stu-id="b4317-125">Supported entity types refer to only entity types in the current namespace.</span></span> <span data-ttu-id="b4317-126">これには、プリミティブ型は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b4317-126">They do not include primitive types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b4317-127">使用例</span><span class="sxs-lookup"><span data-stu-id="b4317-127">Examples</span></span>  
 <span data-ttu-id="b4317-128">簡単な型定義の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b4317-128">The following is an example of a simple type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 EDM.Decimal) AS (  
   Round(p1)  
)  
MyRound(CAST(1.7 as EDM.Decimal))  
```  
  
 <span data-ttu-id="b4317-129">COLLECTION 型定義の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b4317-129">The following is an example of a COLLECTION type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Collection(EDM.Decimal)) AS (  
   Select Round(p1) from p1  
)  
MyRound({CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)})  
```  
  
 <span data-ttu-id="b4317-130">ROW 型定義の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b4317-130">The following is an example of a ROW type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Row(x EDM.Decimal)) AS (  
   Round(p1.x)  
)  
select MyRound(row(a as x)) from {CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)} as a  
```  
  
 <span data-ttu-id="b4317-131">REF 型定義の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b4317-131">The following is an example of a REF type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function UnReference(p1 Ref(AdventureWorks.Order)) AS (  
   Deref(p1)  
)  
select Ref(x) from AdventureWorksEntities.SalesOrderHeaders as x  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4317-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4317-132">See also</span></span>

- [<span data-ttu-id="b4317-133">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="b4317-133">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="b4317-134">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="b4317-134">Entity SQL Reference</span></span>](entity-sql-reference.md)
