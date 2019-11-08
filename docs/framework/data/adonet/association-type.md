---
title: アソシエーション型
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: e1430e6255dce2bae6d82411db5d2a9f11f46e1a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738556"
---
# <a name="association-type"></a><span data-ttu-id="5ff2a-102">アソシエーション型</span><span class="sxs-lookup"><span data-stu-id="5ff2a-102">association type</span></span>
<span data-ttu-id="5ff2a-103">*アソシエーション型*(アソシエーションとも呼ばれます) は、ENTITY DATA MODEL (EDM) でリレーションシップを記述するための基本的な構成要素です。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-103">An *association type* (also called an association) is the fundamental building block for describing relationships in the Entity Data Model (EDM).</span></span> <span data-ttu-id="5ff2a-104">概念モデルでは、アソシエーションは2つの[エンティティ型](entity-type.md)(`Customer` や `Order`など) 間のリレーションシップを表します。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-104">In a conceptual model, an association represents a relationship between two [entity types](entity-type.md) (such as `Customer` and `Order`).</span></span> <span data-ttu-id="5ff2a-105">アプリケーションでは、アソシエーションのインスタンスが特定のアソシエーション (`Customer` のインスタンスと `Order` のインスタンスの間のアソシエーションなど) を表します。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-105">In an application, an instance of an association represents a specific association (such as an association between an instance of `Customer` and an instance of `Order`).</span></span> <span data-ttu-id="5ff2a-106">アソシエーションインスタンスは、[アソシエーションセット](association-set.md)に論理的にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-106">Association instances are logically grouped in an [association set](association-set.md).</span></span>  
  
 <span data-ttu-id="5ff2a-107">アソシエーションの定義には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-107">An association definition contains the following information:</span></span>  
  
- <span data-ttu-id="5ff2a-108">一意の名前</span><span class="sxs-lookup"><span data-stu-id="5ff2a-108">A unique name.</span></span> <span data-ttu-id="5ff2a-109">(必須)</span><span class="sxs-lookup"><span data-stu-id="5ff2a-109">(Required)</span></span>  
  
- <span data-ttu-id="5ff2a-110">リレーションシップのエンティティ型ごとに1つずつ、2つの[アソシエーションが終了](association-end.md)します。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-110">Two [association ends](association-end.md), one for each entity type in the relationship.</span></span> <span data-ttu-id="5ff2a-111">(必須)</span><span class="sxs-lookup"><span data-stu-id="5ff2a-111">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="5ff2a-112">アソシエーションは、2 つ以上のエンティティ型のリレーションシップを表すことができません。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-112">An association cannot represent a relationship among more than two entity types.</span></span> <span data-ttu-id="5ff2a-113">しかし、各アソシエーション End に同じエンティティ型を指定することによって、アソシエーションで自己リレーションシップを定義できます。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-113">An association can, however, define a self-relationship by specifying the same entity type for each of its association ends.</span></span>  
  
- <span data-ttu-id="5ff2a-114">[参照整合性制約](referential-integrity-constraint.md)。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-114">A [referential integrity constraint](referential-integrity-constraint.md).</span></span> <span data-ttu-id="5ff2a-115">(オプション)。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-115">(Optional)</span></span>  
  
 <span data-ttu-id="5ff2a-116">各アソシエーション end には、アソシエーションの1つの end に存在できるエンティティ型インスタンスの数を示す[アソシエーション end の多重度](association-end-multiplicity.md)を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-116">Each association end must specify an [association end multiplicity](association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="5ff2a-117">アソシエーション end の多重度には、1 (1)、0または 1 (0 ..1)、または多数 (\*) の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-117">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span> <span data-ttu-id="5ff2a-118">アソシエーションの1つの end にあるエンティティ型のインスタンスは、エンティティ型で公開されている場合、[ナビゲーションプロパティ](navigation-property.md)または外部キーを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-118">Entity type instances at one end of an association can be accessed through [navigation properties](navigation-property.md) or foreign keys if they are exposed on an entity type.</span></span> <span data-ttu-id="5ff2a-119">詳細については、「 [Entity Data Model: 外部キー](foreign-key-property.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-119">For more information, see [Entity Data Model: Foreign Keys](foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ff2a-120">例</span><span class="sxs-lookup"><span data-stu-id="5ff2a-120">Example</span></span>  
 <span data-ttu-id="5ff2a-121">下のダイアグラムは、`PublishedBy` および `WrittenBy` という 2 つのアソシエーションの概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-121">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="5ff2a-122">`PublishedBy` アソシエーションのアソシエーション End は `Book` および `Publisher` のエンティティ型です。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-122">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="5ff2a-123">`Publisher` end の多重度は 1 (1) で、`Book` end の多重度は多数 (\*) であり、パブリッシャーが多数のブックを発行し、1つの出版社によって書籍が発行されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-123">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 ![3種類のエンティティを持つモデルの例](./media/association-type/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="5ff2a-125">[ADO.NET Entity Framework](./ef/index.md)は、概念スキーマ定義言語 ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) と呼ばれるドメイン固有言語 (DSL) を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-125">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="5ff2a-126">次の CSDL は、上のダイアグラムに示された `PublishedBy` アソシエーションを定義しています。</span><span class="sxs-lookup"><span data-stu-id="5ff2a-126">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="5ff2a-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ff2a-127">See also</span></span>

- [<span data-ttu-id="5ff2a-128">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="5ff2a-128">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="5ff2a-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="5ff2a-129">Entity Data Model</span></span>](entity-data-model.md)
