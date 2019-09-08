---
title: アソシエーション End
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 33cc2e10d9b72ef7f5f024905938c41fcc4a9755
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785049"
---
# <a name="association-end"></a><span data-ttu-id="e2309-102">アソシエーション End</span><span class="sxs-lookup"><span data-stu-id="e2309-102">association end</span></span>
<span data-ttu-id="e2309-103">アソシエーション*end*は、アソシエーションの一方の end の[エンティティ型](entity-type.md)と、アソシエーションのその end に存在できるエンティティ型のインスタンスの[数を識別](association-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="e2309-103">An *association end* identifies the [entity type](entity-type.md) on one end of an [association](association-type.md) and the number of entity type instances that can exist at that end of an association.</span></span> <span data-ttu-id="e2309-104">アソシエーション End はアソシエーションの一部として定義され、アソシエーションには必ず 2 つのアソシエーション End が必要です。</span><span class="sxs-lookup"><span data-stu-id="e2309-104">Association ends are defined as part of an association; an association must have exactly two association ends.</span></span> <span data-ttu-id="e2309-105">[ナビゲーションプロパティ](navigation-property.md)を使用すると、1つのアソシエーションエンドからもう一方のアソシエーション end へのナビゲーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e2309-105">[Navigation properties](navigation-property.md) allow for navigation from one association end to the other.</span></span>  
  
 <span data-ttu-id="e2309-106">アソシエーション End の定義には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2309-106">An association end definition contains the following information:</span></span>  
  
- <span data-ttu-id="e2309-107">アソシエーションに含まれるエンティティ型の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="e2309-107">One of the entity types involved in the association.</span></span> <span data-ttu-id="e2309-108">(必須)</span><span class="sxs-lookup"><span data-stu-id="e2309-108">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e2309-109">アソシエーションでは、各アソシエーション End に同じエンティティ型を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e2309-109">For a given association, the entity type specified for each association end can be the same.</span></span> <span data-ttu-id="e2309-110">これにより、自己アソシエーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e2309-110">This creates a self-association.</span></span>  
  
- <span data-ttu-id="e2309-111">アソシエーションの1つの end に存在できるエンティティ型インスタンスの数を示す[アソシエーション end の多重度](association-end-multiplicity.md)。</span><span class="sxs-lookup"><span data-stu-id="e2309-111">An [association end multiplicity](association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="e2309-112">アソシエーション end の多重度には、1 (1)、0または 1 (0 ..1)、または many (\*) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e2309-112">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span>  
  
- <span data-ttu-id="e2309-113">アソシエーション End の名前。</span><span class="sxs-lookup"><span data-stu-id="e2309-113">A name for the association end.</span></span> <span data-ttu-id="e2309-114">(オプション)</span><span class="sxs-lookup"><span data-stu-id="e2309-114">(Optional)</span></span>  
  
- <span data-ttu-id="e2309-115">アソシエーション End に実行する CASCADE ON DELETE などの操作の情報。</span><span class="sxs-lookup"><span data-stu-id="e2309-115">Information about operations that are performed on the association end, such as cascade on delete.</span></span> <span data-ttu-id="e2309-116">(オプション)</span><span class="sxs-lookup"><span data-stu-id="e2309-116">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2309-117">例</span><span class="sxs-lookup"><span data-stu-id="e2309-117">Example</span></span>  
 <span data-ttu-id="e2309-118">下のダイアグラムは、`PublishedBy` および `WrittenBy` という 2 つのアソシエーションの概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="e2309-118">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="e2309-119">`PublishedBy` アソシエーションのアソシエーション End は `Book` および `Publisher` のエンティティ型です。</span><span class="sxs-lookup"><span data-stu-id="e2309-119">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="e2309-120">`Publisher` End の多重度は 1 (1) で、 `Book` end の多重度は多数 (\*) であり、出版社が多数の書籍を出版し、書籍が1つの出版社によって発行されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="e2309-120">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 ![3種類のエンティティを持つモデルの例](./media/association-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="e2309-122">ADO.NET Entity Framework は、概念スキーマ定義言語 ([CSDL](./ef/language-reference/csdl-specification.md)) と呼ばれるドメイン固有言語 (DSL) を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="e2309-122">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="e2309-123">次の CSDL は、上のダイアグラムに示された `PublishedBy` アソシエーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="e2309-123">The CSDL below defines the `PublishedBy` association shown in the diagram above.</span></span> <span data-ttu-id="e2309-124">各アソシエーション End の型、名前、および多重度は、XML 属性 (それぞれ `Type` 属性、`Role` 属性、および `Multiplicity` 属性) で指定されます。</span><span class="sxs-lookup"><span data-stu-id="e2309-124">Note that the type, name, and multiplicity of each association end are specified by XML attributes (the `Type`, `Role`, and `Multiplicity` attributes, respectively).</span></span> <span data-ttu-id="e2309-125">アソシエーション End に実行する操作に関するオプション情報は、XML 要素 (`OnDelete` 要素) に指定します。</span><span class="sxs-lookup"><span data-stu-id="e2309-125">Optional information about operations performed on an end is specified in an XML element (the `OnDelete` element).</span></span> <span data-ttu-id="e2309-126">この場合、出版社を削除すると、関連付けられたすべての書籍も削除されます。</span><span class="sxs-lookup"><span data-stu-id="e2309-126">In this case, if a publisher is deleted, so are all associated books.</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a><span data-ttu-id="e2309-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2309-127">See also</span></span>

- [<span data-ttu-id="e2309-128">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="e2309-128">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="e2309-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="e2309-129">Entity Data Model</span></span>](entity-data-model.md)
