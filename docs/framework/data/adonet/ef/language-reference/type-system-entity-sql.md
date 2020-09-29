---
title: 型システム (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: d4c8ba7a9d9b58220455b50ff99960fa132c00c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200993"
---
# <a name="type-system-entity-sql"></a><span data-ttu-id="64322-102">型システム (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="64322-102">Type System (Entity SQL)</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="64322-103">では、次に示すように多数の型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="64322-103">supports a number of types:</span></span>  
  
- <span data-ttu-id="64322-104">`Int32` や `String.` などのプリミティブ型 (単純型)。</span><span class="sxs-lookup"><span data-stu-id="64322-104">Primitive (simple) types such as `Int32` and `String.`</span></span>  
  
- <span data-ttu-id="64322-105"><xref:System.Data.Metadata.Edm.EntityType>、<xref:System.Data.Metadata.Edm.ComplexType>、<xref:System.Data.Metadata.Edm.RelationshipType> など、スキーマで定義される標準型。</span><span class="sxs-lookup"><span data-stu-id="64322-105">Nominal types that are defined in the schema, such as <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, and <xref:System.Data.Metadata.Edm.RelationshipType>.</span></span>  
  
- <span data-ttu-id="64322-106"><xref:System.Data.Metadata.Edm.CollectionType>、<xref:System.Data.Metadata.Edm.RowType>、<xref:System.Data.Metadata.Edm.RefType> など、明示的にはスキーマで定義されない匿名型。</span><span class="sxs-lookup"><span data-stu-id="64322-106">Anonymous types that are not defined in the schema explicitly: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, and <xref:System.Data.Metadata.Edm.RefType>.</span></span>  
  
 <span data-ttu-id="64322-107">ここでは、明示的にはスキーマで定義されていなくても Entity SQL でサポートされている匿名型について説明します。</span><span class="sxs-lookup"><span data-stu-id="64322-107">This section discusses the anonymous types that are not defined in the schema explicitly but are supported by Entity SQL.</span></span> <span data-ttu-id="64322-108">プリミティブ型および標準型については、「[概念モデルの型 (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64322-108">For information on primitive and nominal types, see [Conceptual Model Types (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span></span>  
  
## <a name="rows"></a><span data-ttu-id="64322-109">行</span><span class="sxs-lookup"><span data-stu-id="64322-109">Rows</span></span>  

 <span data-ttu-id="64322-110">行の構造は、行を構成する型指定された名前付きのメンバーの配列に依存します。</span><span class="sxs-lookup"><span data-stu-id="64322-110">The structure of a row depends on the sequence of typed and named members that the row consists of.</span></span> <span data-ttu-id="64322-111">行型には ID がなく、派生元にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="64322-111">A row type has no identity and cannot be inherited from.</span></span> <span data-ttu-id="64322-112">同じ行型のインスタンスは、メンバーがそれぞれ同等である場合は同等になります。</span><span class="sxs-lookup"><span data-stu-id="64322-112">Instances of the same row type are equivalent if the members are respectively equivalent.</span></span> <span data-ttu-id="64322-113">行には構造同値以外の動作はなく、共通言語ランタイムに同等のものはありません。</span><span class="sxs-lookup"><span data-stu-id="64322-113">Rows have no behavior beyond their structural equivalence and have no equivalent in the common language runtime.</span></span> <span data-ttu-id="64322-114">クエリの結果は、行または行のコレクションを含む構造になります。</span><span class="sxs-lookup"><span data-stu-id="64322-114">Queries can result in structures that contain rows or collections of rows.</span></span> <span data-ttu-id="64322-115">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] クエリとホスト言語の間の API バインドは、結果を生成したクエリでどのように行が構成されるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="64322-115">The API binding between the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries and the host language defines how rows are realized in the query that produced the result.</span></span> <span data-ttu-id="64322-116">行インスタンスの作成方法については、「[コンストラクター](constructing-types-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64322-116">For information on how to construct a row instance, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="64322-117">コレクション</span><span class="sxs-lookup"><span data-stu-id="64322-117">Collections</span></span>  

 <span data-ttu-id="64322-118">コレクション型は、他のオブジェクトの 0 個以上のインスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="64322-118">Collection types represent zero or more instances of other objects.</span></span> <span data-ttu-id="64322-119">コレクションの作成方法については、「[コンストラクター](constructing-types-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64322-119">For information on how to construct collection, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="64322-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="64322-120">References</span></span>  

 <span data-ttu-id="64322-121">参照とは、特定のエンティティ セットにある特定のエンティティへの論理ポインターです。</span><span class="sxs-lookup"><span data-stu-id="64322-121">A reference is a logical pointer to a specific entity in a specific entity set.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="64322-122">では、参照の構築、分解、およびナビゲートを行うための次の演算子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="64322-122">supports the following operators to construct, deconstruct, and navigate through references:</span></span>  
  
- [<span data-ttu-id="64322-123">REF</span><span class="sxs-lookup"><span data-stu-id="64322-123">REF</span></span>](ref-entity-sql.md)  
  
- [<span data-ttu-id="64322-124">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="64322-124">CREATEREF</span></span>](createref-entity-sql.md)  
  
- [<span data-ttu-id="64322-125">KEY</span><span class="sxs-lookup"><span data-stu-id="64322-125">KEY</span></span>](key-entity-sql.md)  
  
- [<span data-ttu-id="64322-126">DEREF</span><span class="sxs-lookup"><span data-stu-id="64322-126">DEREF</span></span>](deref-entity-sql.md)  
  
 <span data-ttu-id="64322-127">メンバー アクセス (ドット) 演算子 (`.`) を使用して参照によるナビゲーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="64322-127">You can navigate through a reference by using the member access (dot) operator(`.`).</span></span> <span data-ttu-id="64322-128">次のコード例では、r (参照) プロパティによるナビゲーションで Order の Id プロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="64322-128">The following snippet extracts the Id property (of Order) by navigating through the r (reference) property.</span></span>  
  
```sql  
select o2.r.Id
from (select ref(o) as r from LOB.Orders as o) as o2
```  
  
 <span data-ttu-id="64322-129">参照値が null であるか、参照先が存在しない場合、結果は null になります。</span><span class="sxs-lookup"><span data-stu-id="64322-129">If the reference value is null, or if the target of the reference does not exist, the result is null.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64322-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="64322-130">See also</span></span>

- [<span data-ttu-id="64322-131">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="64322-131">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="64322-132">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="64322-132">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="64322-133">CAST</span><span class="sxs-lookup"><span data-stu-id="64322-133">CAST</span></span>](cast-entity-sql.md)
- [<span data-ttu-id="64322-134">CSDL、SSDL、および MSL 仕様</span><span class="sxs-lookup"><span data-stu-id="64322-134">CSDL, SSDL, and MSL Specifications</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
