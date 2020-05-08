---
title: アソシエーション End
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 489802ca18708e076c0cd5dd380ad1361916ad5f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732357"
---
# <a name="association-end"></a><span data-ttu-id="fe774-102">アソシエーション End</span><span class="sxs-lookup"><span data-stu-id="fe774-102">association end</span></span>
<span data-ttu-id="fe774-103">"*アソシエーション End*" では、[アソシエーション](association-type.md)の一方の End にある[エンティティ型](entity-type.md)と、アソシエーションのその End に存在できるエンティティ型のインスタンス数が示されます。</span><span class="sxs-lookup"><span data-stu-id="fe774-103">An *association end* identifies the [entity type](entity-type.md) on one end of an [association](association-type.md) and the number of entity type instances that can exist at that end of an association.</span></span> <span data-ttu-id="fe774-104">アソシエーション End はアソシエーションの一部として定義され、アソシエーションには必ず 2 つのアソシエーション End が必要です。</span><span class="sxs-lookup"><span data-stu-id="fe774-104">Association ends are defined as part of an association; an association must have exactly two association ends.</span></span> <span data-ttu-id="fe774-105">[ナビゲーション プロパティ](navigation-property.md)により、一方のアソシエーション End から他方のアソシエーション End へのナビゲーションが可能になります。</span><span class="sxs-lookup"><span data-stu-id="fe774-105">[Navigation properties](navigation-property.md) allow for navigation from one association end to the other.</span></span>  
  
 <span data-ttu-id="fe774-106">アソシエーション End の定義には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe774-106">An association end definition contains the following information:</span></span>  
  
- <span data-ttu-id="fe774-107">アソシエーションに含まれるエンティティ型の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="fe774-107">One of the entity types involved in the association.</span></span> <span data-ttu-id="fe774-108">(必須)</span><span class="sxs-lookup"><span data-stu-id="fe774-108">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fe774-109">アソシエーションでは、各アソシエーション End に同じエンティティ型を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="fe774-109">For a given association, the entity type specified for each association end can be the same.</span></span> <span data-ttu-id="fe774-110">これにより、自己アソシエーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fe774-110">This creates a self-association.</span></span>  
  
- <span data-ttu-id="fe774-111">アソシエーションの 1 つの End に存在できるエンティティ型のインスタンス数を示す[アソシエーション End の多重度](association-end-multiplicity.md)。</span><span class="sxs-lookup"><span data-stu-id="fe774-111">An [association end multiplicity](association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="fe774-112">アソシエーション End の多重度には、1 、ゼロか 1 (0..1)、または多数 (\*) の値を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="fe774-112">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span>  
  
- <span data-ttu-id="fe774-113">アソシエーション End の名前。</span><span class="sxs-lookup"><span data-stu-id="fe774-113">A name for the association end.</span></span> <span data-ttu-id="fe774-114">(オプション)。</span><span class="sxs-lookup"><span data-stu-id="fe774-114">(Optional)</span></span>  
  
- <span data-ttu-id="fe774-115">アソシエーション End に実行する CASCADE ON DELETE などの操作の情報。</span><span class="sxs-lookup"><span data-stu-id="fe774-115">Information about operations that are performed on the association end, such as cascade on delete.</span></span> <span data-ttu-id="fe774-116">(オプション)。</span><span class="sxs-lookup"><span data-stu-id="fe774-116">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe774-117">例</span><span class="sxs-lookup"><span data-stu-id="fe774-117">Example</span></span>  
 <span data-ttu-id="fe774-118">下のダイアグラムは、`PublishedBy` および `WrittenBy` という 2 つのアソシエーションの概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="fe774-118">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="fe774-119">`PublishedBy` アソシエーションのアソシエーション End は `Book` および `Publisher` のエンティティ型です。</span><span class="sxs-lookup"><span data-stu-id="fe774-119">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="fe774-120">`Publisher` End の多重度は 1 で、`Book` End の多重度は多数 (\*) です。これは、出版社が多くの書籍を出版し、書籍は 1 社の出版社により出版されることを示します。</span><span class="sxs-lookup"><span data-stu-id="fe774-120">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 ![3 種類のエンティティを持つモデルの例](./media/association-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="fe774-122">ADO.NET Entity Framework では、概念スキーマ定義言語 ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) と呼ばれるドメイン固有言語 (DSL) を使用して、概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="fe774-122">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="fe774-123">次の CSDL は、上のダイアグラムに示された `PublishedBy` アソシエーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="fe774-123">The CSDL below defines the `PublishedBy` association shown in the diagram above.</span></span> <span data-ttu-id="fe774-124">各アソシエーション End の型、名前、および多重度は、XML 属性 (それぞれ `Type` 属性、`Role` 属性、および `Multiplicity` 属性) で指定されます。</span><span class="sxs-lookup"><span data-stu-id="fe774-124">Note that the type, name, and multiplicity of each association end are specified by XML attributes (the `Type`, `Role`, and `Multiplicity` attributes, respectively).</span></span> <span data-ttu-id="fe774-125">アソシエーション End に実行する操作に関するオプション情報は、XML 要素 (`OnDelete` 要素) に指定します。</span><span class="sxs-lookup"><span data-stu-id="fe774-125">Optional information about operations performed on an end is specified in an XML element (the `OnDelete` element).</span></span> <span data-ttu-id="fe774-126">この場合、出版社を削除すると、関連付けられたすべての書籍も削除されます。</span><span class="sxs-lookup"><span data-stu-id="fe774-126">In this case, if a publisher is deleted, so are all associated books.</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a><span data-ttu-id="fe774-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe774-127">See also</span></span>

- [<span data-ttu-id="fe774-128">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="fe774-128">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="fe774-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="fe774-129">Entity Data Model</span></span>](entity-data-model.md)
