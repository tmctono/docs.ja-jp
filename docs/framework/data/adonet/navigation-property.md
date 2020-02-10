---
title: ナビゲーション プロパティ
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: eaf22ad4dd24b4bf046f14ccabd435a9ecd1776f
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094385"
---
# <a name="navigation-property"></a><span data-ttu-id="bf46e-102">ナビゲーション プロパティ</span><span class="sxs-lookup"><span data-stu-id="bf46e-102">Navigation property</span></span>

<span data-ttu-id="bf46e-103">*ナビゲーションプロパティ*は、[アソシエーション](association-type.md)の一方の[端](association-end.md)からもう一方の端へのナビゲーションを可能にする[エンティティ型](entity-type.md)の省略可能なプロパティです。</span><span class="sxs-lookup"><span data-stu-id="bf46e-103">A *navigation property* is an optional property on an [entity type](entity-type.md) that allows for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="bf46e-104">他の[プロパティ](property.md)とは異なり、ナビゲーションプロパティはデータを保持しません。</span><span class="sxs-lookup"><span data-stu-id="bf46e-104">Unlike other [properties](property.md), navigation properties do not carry data.</span></span>

<span data-ttu-id="bf46e-105">ナビゲーション プロパティの定義には、以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bf46e-105">A navigation property definition includes the following:</span></span>

- <span data-ttu-id="bf46e-106">名前。</span><span class="sxs-lookup"><span data-stu-id="bf46e-106">A name.</span></span> <span data-ttu-id="bf46e-107">(必須)</span><span class="sxs-lookup"><span data-stu-id="bf46e-107">(Required)</span></span>

- <span data-ttu-id="bf46e-108">移動対象のアソシエーション。</span><span class="sxs-lookup"><span data-stu-id="bf46e-108">The association that it navigates.</span></span> <span data-ttu-id="bf46e-109">(必須)</span><span class="sxs-lookup"><span data-stu-id="bf46e-109">(Required)</span></span>

- <span data-ttu-id="bf46e-110">移動対象のアソシエーションの End。</span><span class="sxs-lookup"><span data-stu-id="bf46e-110">The ends of the association that it navigates.</span></span> <span data-ttu-id="bf46e-111">(必須)</span><span class="sxs-lookup"><span data-stu-id="bf46e-111">(Required)</span></span>

<span data-ttu-id="bf46e-112">ナビゲーションプロパティは、アソシエーションの end の両方のエンティティ型でオプションです。</span><span class="sxs-lookup"><span data-stu-id="bf46e-112">Navigation properties are optional on both entity types at the ends of an association.</span></span> <span data-ttu-id="bf46e-113">1 つのアソシエーション End のエンティティ型にナビゲーション プロパティを定義した場合に、そのアソシエーションの他方の End でもエンティティ型にナビゲーション プロパティを定義する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bf46e-113">If you define a navigation property on one entity type at the end of an association, you do not have to define a navigation property on the entity type at the other end of the association.</span></span>

<span data-ttu-id="bf46e-114">ナビゲーションプロパティのデータ型は、リモートの[アソシエーション end](association-end.md)の[複数要素](association-end-multiplicity.md)の接続性によって決まります。</span><span class="sxs-lookup"><span data-stu-id="bf46e-114">The data type of a navigation property is determined by the [multiplicity](association-end-multiplicity.md) of its remote [association end](association-end.md).</span></span> <span data-ttu-id="bf46e-115">たとえば、ナビゲーション プロパティ `OrdersNavProp` が `Customer` エンティティ型に存在し、`Customer` と `Order` の間の一対多のアソシエーションで移動するとします。</span><span class="sxs-lookup"><span data-stu-id="bf46e-115">For example, suppose a navigation property, `OrdersNavProp`, exists on a `Customer` entity type and navigates a one-to-many association between `Customer` and `Order`.</span></span> <span data-ttu-id="bf46e-116">ナビゲーションプロパティのリモートアソシエーション end の多重度は多く (\*) であるため、そのデータ型はコレクション (`Order`) です。</span><span class="sxs-lookup"><span data-stu-id="bf46e-116">Because the remote association end for the navigation property has multiplicity of many (\*), its data type is a collection (of `Order`).</span></span> <span data-ttu-id="bf46e-117">同様に、`CustomerNavProp` エンティティ型にナビゲーション プロパティ、`Order` が存在する場合、リモート End の多重度が (1) であるため、データ型は `Customer` になります。</span><span class="sxs-lookup"><span data-stu-id="bf46e-117">Similarly, if a navigation property, `CustomerNavProp`, exists on the `Order` entity type, its data type would be `Customer`, because the multiplicity of the remote end is one (1).</span></span>

## <a name="example"></a><span data-ttu-id="bf46e-118">例</span><span class="sxs-lookup"><span data-stu-id="bf46e-118">Example</span></span>

<span data-ttu-id="bf46e-119">下のダイアグラムは、`Book`、`Publisher`、および `Author` という 3 つのエンティティ型の概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="bf46e-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="bf46e-120">`Publisher` および `Authors` のナビゲーションプロパティは、Book エンティティ型で定義されています。</span><span class="sxs-lookup"><span data-stu-id="bf46e-120">The navigation properties `Publisher` and `Authors` are defined on the Book entity type.</span></span> <span data-ttu-id="bf46e-121">Publisher エンティティ型と `Books` エンティティ型には、ナビゲーション プロパティ、`Author` が定義されています。</span><span class="sxs-lookup"><span data-stu-id="bf46e-121">Navigation property `Books` is defined on both the Publisher entity type and the `Author` entity type.</span></span>

![3種類のエンティティを持つ概念モデルを示す図](./media/navigation-property/conceptual-model-entity-types-associations.gif)  

<span data-ttu-id="bf46e-123">[ADO.NET Entity Framework](./ef/index.md)は、概念スキーマ定義言語 ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) と呼ばれるドメイン固有言語 (DSL) を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="bf46e-123">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="bf46e-124">次の CSDL は、上のダイアグラムに示された `Book` エンティティ型を定義しています。</span><span class="sxs-lookup"><span data-stu-id="bf46e-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>

[!code-xml[EDM_Example_Model#EntityExample](~/samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]

<span data-ttu-id="bf46e-125">XML 属性は、ナビゲーションプロパティを定義するために必要な情報を伝達するために使用されます。属性 `Name` には、プロパティの名前が含まれています。また、`Relationship` 移動するアソシエーションの名前が含まれており、`FromRole` と `ToRole` アソシエーションの end を格納しています。</span><span class="sxs-lookup"><span data-stu-id="bf46e-125">XML attributes are used to communicate the information necessary to define a navigation property: The attribute `Name` contains the name of the property, `Relationship` contains the name of the association it navigates, and `FromRole` and `ToRole` contain the ends of the association.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf46e-126">参照</span><span class="sxs-lookup"><span data-stu-id="bf46e-126">See also</span></span>

- [<span data-ttu-id="bf46e-127">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="bf46e-127">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="bf46e-128">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="bf46e-128">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="bf46e-129">リレーションシップ、ナビゲーションプロパティ、および外部キー</span><span class="sxs-lookup"><span data-stu-id="bf46e-129">Relationships, navigation properties, and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)
