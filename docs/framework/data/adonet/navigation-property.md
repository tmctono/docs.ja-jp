---
title: ナビゲーションプロパティ-ADO.NET
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: afb2043abf70fa92ea7cdf8d1e8246d5cdfdba74
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738385"
---
# <a name="navigation-property"></a><span data-ttu-id="b09cd-102">ナビゲーション プロパティ</span><span class="sxs-lookup"><span data-stu-id="b09cd-102">Navigation property</span></span>

<span data-ttu-id="b09cd-103">*ナビゲーションプロパティ*は、[アソシエーション](association-type.md)の一方の[端](association-end.md)からもう一方の端へのナビゲーションを可能にする[エンティティ型](entity-type.md)の省略可能なプロパティです。</span><span class="sxs-lookup"><span data-stu-id="b09cd-103">A *navigation property* is an optional property on an [entity type](entity-type.md) that allows for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="b09cd-104">他の[プロパティ](property.md)とは異なり、ナビゲーションプロパティはデータを保持しません。</span><span class="sxs-lookup"><span data-stu-id="b09cd-104">Unlike other [properties](property.md), navigation properties do not carry data.</span></span>

<span data-ttu-id="b09cd-105">ナビゲーション プロパティの定義には、以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b09cd-105">A navigation property definition includes the following:</span></span>

- <span data-ttu-id="b09cd-106">名前。</span><span class="sxs-lookup"><span data-stu-id="b09cd-106">A name.</span></span> <span data-ttu-id="b09cd-107">(必須)</span><span class="sxs-lookup"><span data-stu-id="b09cd-107">(Required)</span></span>

- <span data-ttu-id="b09cd-108">移動対象のアソシエーション。</span><span class="sxs-lookup"><span data-stu-id="b09cd-108">The association that it navigates.</span></span> <span data-ttu-id="b09cd-109">(必須)</span><span class="sxs-lookup"><span data-stu-id="b09cd-109">(Required)</span></span>

- <span data-ttu-id="b09cd-110">移動対象のアソシエーションの End。</span><span class="sxs-lookup"><span data-stu-id="b09cd-110">The ends of the association that it navigates.</span></span> <span data-ttu-id="b09cd-111">(必須)</span><span class="sxs-lookup"><span data-stu-id="b09cd-111">(Required)</span></span>

<span data-ttu-id="b09cd-112">ナビゲーション プロパティは、アソシエーション End の両方のエンティティ型で省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b09cd-112">Note that navigation properties are optional on both entity types at the ends of an association.</span></span> <span data-ttu-id="b09cd-113">1 つのアソシエーション End のエンティティ型にナビゲーション プロパティを定義した場合に、そのアソシエーションの他方の End でもエンティティ型にナビゲーション プロパティを定義する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b09cd-113">If you define a navigation property on one entity type at the end of an association, you do not have to define a navigation property on the entity type at the other end of the association.</span></span>

<span data-ttu-id="b09cd-114">ナビゲーションプロパティのデータ型は、リモートの[アソシエーション end](association-end.md)の[複数要素](association-end-multiplicity.md)の接続性によって決まります。</span><span class="sxs-lookup"><span data-stu-id="b09cd-114">The data type of a navigation property is determined by the [multiplicity](association-end-multiplicity.md) of its remote [association end](association-end.md).</span></span> <span data-ttu-id="b09cd-115">たとえば、ナビゲーション プロパティ `OrdersNavProp` が `Customer` エンティティ型に存在し、`Customer` と `Order` の間の一対多のアソシエーションで移動するとします。</span><span class="sxs-lookup"><span data-stu-id="b09cd-115">For example, suppose a navigation property, `OrdersNavProp`, exists on a `Customer` entity type and navigates a one-to-many association between `Customer` and `Order`.</span></span> <span data-ttu-id="b09cd-116">ナビゲーションプロパティのリモートアソシエーション end の多重度は多く (\*) であるため、そのデータ型はコレクション (`Order`) です。</span><span class="sxs-lookup"><span data-stu-id="b09cd-116">Because the remote association end for the navigation property has multiplicity of many (\*), its data type is a collection (of `Order`).</span></span> <span data-ttu-id="b09cd-117">同様に、`CustomerNavProp` エンティティ型にナビゲーション プロパティ、`Order` が存在する場合、リモート End の多重度が (1) であるため、データ型は `Customer` になります。</span><span class="sxs-lookup"><span data-stu-id="b09cd-117">Similarly, if a navigation property, `CustomerNavProp`, exists on the `Order` entity type, its data type would be `Customer`, because the multiplicity of the remote end is one (1).</span></span>

## <a name="example"></a><span data-ttu-id="b09cd-118">例</span><span class="sxs-lookup"><span data-stu-id="b09cd-118">Example</span></span>

<span data-ttu-id="b09cd-119">下のダイアグラムは、`Book`、`Publisher`、および `Author` という 3 つのエンティティ型の概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="b09cd-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="b09cd-120">Book エンティティ型には、ナビゲーション プロパティ、`Publisher` および `Authors` が定義されています。</span><span class="sxs-lookup"><span data-stu-id="b09cd-120">Navigation properties, `Publisher` and `Authors`, are defined on the Book entity type.</span></span> <span data-ttu-id="b09cd-121">Publisher エンティティ型と `Books` エンティティ型には、ナビゲーション プロパティ、`Author` が定義されています。</span><span class="sxs-lookup"><span data-stu-id="b09cd-121">Navigation property `Books` is defined on both the Publisher entity type and the `Author` entity type.</span></span>

 ![3種類のエンティティを持つ概念モデルを示す図](./media/navigation-property/conceptual-model-entity-types-associations.gif)  

<span data-ttu-id="b09cd-123">[ADO.NET Entity Framework](./ef/index.md)は、概念スキーマ定義言語 ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) と呼ばれるドメイン固有言語 (DSL) を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="b09cd-123">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="b09cd-124">次の CSDL は、上のダイアグラムに示された `Book` エンティティ型を定義しています。</span><span class="sxs-lookup"><span data-stu-id="b09cd-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>

[!code-xml[EDM_Example_Model#EntityExample](~/samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]

<span data-ttu-id="b09cd-125">ナビゲーション プロパティの定義に必要な情報を伝達するために、XML 属性が使用されています。属性 `Name` にはプロパティ名が含まれ、`Relationship` には移動対象のアソシエーション名が含まれ、`FromRole` および `ToRole` にはアソシエーション End が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b09cd-125">Note that XML attributes are used to communicate the information necessary to define a navigation property: The attribute `Name` contains the name of the property, `Relationship` contains the name of the association it navigates, and `FromRole` and `ToRole` contain the ends of the association.</span></span>

## <a name="see-also"></a><span data-ttu-id="b09cd-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="b09cd-126">See also</span></span>

- [<span data-ttu-id="b09cd-127">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="b09cd-127">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="b09cd-128">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="b09cd-128">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="b09cd-129">リレーションシップ、ナビゲーションプロパティ、外部キー</span><span class="sxs-lookup"><span data-stu-id="b09cd-129">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)
