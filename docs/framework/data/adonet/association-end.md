---
title: アソシエーション End
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 489802ca18708e076c0cd5dd380ad1361916ad5f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732357"
---
# <a name="association-end"></a><span data-ttu-id="cc110-102">アソシエーション End</span><span class="sxs-lookup"><span data-stu-id="cc110-102">association end</span></span>
<span data-ttu-id="cc110-103">アソシエーション*end*は、アソシエーションの一方の end の[エンティティ型](entity-type.md)と、アソシエーションのその end に存在できるエンティティ型のインスタンスの[数を識別](association-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc110-103">An *association end* identifies the [entity type](entity-type.md) on one end of an [association](association-type.md) and the number of entity type instances that can exist at that end of an association.</span></span> <span data-ttu-id="cc110-104">アソシエーション End はアソシエーションの一部として定義され、アソシエーションには必ず 2 つのアソシエーション End が必要です。</span><span class="sxs-lookup"><span data-stu-id="cc110-104">Association ends are defined as part of an association; an association must have exactly two association ends.</span></span> <span data-ttu-id="cc110-105">[ナビゲーションプロパティ](navigation-property.md)を使用すると、1つのアソシエーションエンドからもう一方のアソシエーション end へのナビゲーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cc110-105">[Navigation properties](navigation-property.md) allow for navigation from one association end to the other.</span></span>  
  
 <span data-ttu-id="cc110-106">アソシエーション End の定義には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc110-106">An association end definition contains the following information:</span></span>  
  
- <span data-ttu-id="cc110-107">アソシエーションに含まれるエンティティ型の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="cc110-107">One of the entity types involved in the association.</span></span> <span data-ttu-id="cc110-108">(必須)</span><span class="sxs-lookup"><span data-stu-id="cc110-108">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="cc110-109">アソシエーションでは、各アソシエーション End に同じエンティティ型を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="cc110-109">For a given association, the entity type specified for each association end can be the same.</span></span> <span data-ttu-id="cc110-110">これにより、自己アソシエーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cc110-110">This creates a self-association.</span></span>  
  
- <span data-ttu-id="cc110-111">アソシエーションの1つの end に存在できるエンティティ型インスタンスの数を示す[アソシエーション end の多重度](association-end-multiplicity.md)。</span><span class="sxs-lookup"><span data-stu-id="cc110-111">An [association end multiplicity](association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="cc110-112">アソシエーション end の多重度には、1 (1)、0または 1 (0 ..1)、または多数 (\*) の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cc110-112">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span>  
  
- <span data-ttu-id="cc110-113">アソシエーション End の名前。</span><span class="sxs-lookup"><span data-stu-id="cc110-113">A name for the association end.</span></span> <span data-ttu-id="cc110-114">(オプション)。</span><span class="sxs-lookup"><span data-stu-id="cc110-114">(Optional)</span></span>  
  
- <span data-ttu-id="cc110-115">アソシエーション End に実行する CASCADE ON DELETE などの操作の情報。</span><span class="sxs-lookup"><span data-stu-id="cc110-115">Information about operations that are performed on the association end, such as cascade on delete.</span></span> <span data-ttu-id="cc110-116">(オプション)。</span><span class="sxs-lookup"><span data-stu-id="cc110-116">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc110-117">例</span><span class="sxs-lookup"><span data-stu-id="cc110-117">Example</span></span>  
 <span data-ttu-id="cc110-118">下のダイアグラムは、`PublishedBy` および `WrittenBy` という 2 つのアソシエーションの概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="cc110-118">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="cc110-119">`PublishedBy` アソシエーションのアソシエーション End は `Book` および `Publisher` のエンティティ型です。</span><span class="sxs-lookup"><span data-stu-id="cc110-119">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="cc110-120">`Publisher` end の多重度は 1 (1) で、`Book` end の多重度は多数 (\*) であり、パブリッシャーが多数のブックを発行し、1つの出版社によって書籍が発行されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="cc110-120">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 ![3種類のエンティティを持つモデルの例](./media/association-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="cc110-122">ADO.NET Entity Framework は、概念スキーマ定義言語 ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) と呼ばれるドメイン固有言語 (DSL) を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="cc110-122">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="cc110-123">次の CSDL は、上のダイアグラムに示された `PublishedBy` アソシエーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="cc110-123">The CSDL below defines the `PublishedBy` association shown in the diagram above.</span></span> <span data-ttu-id="cc110-124">各アソシエーション End の型、名前、および多重度は、XML 属性 (それぞれ `Type` 属性、`Role` 属性、および `Multiplicity` 属性) で指定されます。</span><span class="sxs-lookup"><span data-stu-id="cc110-124">Note that the type, name, and multiplicity of each association end are specified by XML attributes (the `Type`, `Role`, and `Multiplicity` attributes, respectively).</span></span> <span data-ttu-id="cc110-125">アソシエーション End に実行する操作に関するオプション情報は、XML 要素 (`OnDelete` 要素) に指定します。</span><span class="sxs-lookup"><span data-stu-id="cc110-125">Optional information about operations performed on an end is specified in an XML element (the `OnDelete` element).</span></span> <span data-ttu-id="cc110-126">この場合、出版社を削除すると、関連付けられたすべての書籍も削除されます。</span><span class="sxs-lookup"><span data-stu-id="cc110-126">In this case, if a publisher is deleted, so are all associated books.</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a><span data-ttu-id="cc110-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc110-127">See also</span></span>

- [<span data-ttu-id="cc110-128">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="cc110-128">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="cc110-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="cc110-129">Entity Data Model</span></span>](entity-data-model.md)
