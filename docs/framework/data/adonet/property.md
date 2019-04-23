---
title: property
ms.date: 03/30/2017
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
ms.openlocfilehash: 71a04f334ec465b0f11cc8f18f2680df651081eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181650"
---
# <a name="property"></a><span data-ttu-id="6aa6a-102">property</span><span class="sxs-lookup"><span data-stu-id="6aa6a-102">property</span></span>
<span data-ttu-id="6aa6a-103">*プロパティ*の基本的な構成要素を[エンティティ型](../../../../docs/framework/data/adonet/entity-type.md)と[複合型](../../../../docs/framework/data/adonet/complex-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-103">*Properties* are the fundamental building blocks of [entity types](../../../../docs/framework/data/adonet/entity-type.md) and [complex types](../../../../docs/framework/data/adonet/complex-type.md).</span></span> <span data-ttu-id="6aa6a-104">プロパティは、エンティティ型または複合型のインスタンスに含まれるデータの形と特性を定義します。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-104">Properties define the shape and characteristics of data that an entity type instance or complex type instance will contain.</span></span> <span data-ttu-id="6aa6a-105">概念モデルのプロパティは、クラスに定義されるプロパティに似ています。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-105">Properties in a conceptual model are analogous to properties defined on a class.</span></span> <span data-ttu-id="6aa6a-106">クラスのプロパティがクラスの構造を定義し、オブジェクトに関する情報を伝達するのと同様に、概念モデルのプロパティはエンティティ型の構造を定義し、エンティティ型のインスタンスに関する情報を伝達します。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-106">In the same way that properties on a class define the shape of the class and carry information about objects, properties in a conceptual model define the shape of an entity type and carry information about entity type instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6aa6a-107">このトピックで説明するプロパティは、ナビゲーション プロパティとは異なります。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-107">Properties, as described in this topic, are different from navigation properties.</span></span> <span data-ttu-id="6aa6a-108">詳細については、次を参照してください。[ナビゲーション プロパティ](../../../../docs/framework/data/adonet/navigation-property.md)します。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-108">For more information, see [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md).</span></span>  
  
 <span data-ttu-id="6aa6a-109">プロパティの定義には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-109">A property definition contains the following information:</span></span>  
  
-   <span data-ttu-id="6aa6a-110">プロパティ名。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-110">A property name.</span></span> <span data-ttu-id="6aa6a-111">(必須)</span><span class="sxs-lookup"><span data-stu-id="6aa6a-111">(Required)</span></span>  
  
-   <span data-ttu-id="6aa6a-112">プロパティの型。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-112">A property type.</span></span> <span data-ttu-id="6aa6a-113">(必須)</span><span class="sxs-lookup"><span data-stu-id="6aa6a-113">(Required)</span></span>  
  
-   <span data-ttu-id="6aa6a-114">一連の[ファセット](../../../../docs/framework/data/adonet/facet.md)します。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-114">A set of [facets](../../../../docs/framework/data/adonet/facet.md).</span></span> <span data-ttu-id="6aa6a-115">(オプション)。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-115">(Optional)</span></span>  
  
 <span data-ttu-id="6aa6a-116">プロパティには、プリミティブ データ (文字列、整数、ブール値など) または構造化データ (複合型) を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-116">A property can contain primitive data (such as a string, an integer, or a Boolean value), or structured data (such as a complex type).</span></span> <span data-ttu-id="6aa6a-117">プリミティブ型のプロパティは、スカラー プロパティとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-117">Properties that are of primitive type are also called scalar properties.</span></span> <span data-ttu-id="6aa6a-118">詳細については、次を参照してください[Entity Data Model:。プリミティブ データ型](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-118">For more information, see [Entity Data Model: Primitive Data Types](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6aa6a-119">複合型自体に、複合型のプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-119">A complex type can, itself, have properties that are complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6aa6a-120">例</span><span class="sxs-lookup"><span data-stu-id="6aa6a-120">Example</span></span>  
 <span data-ttu-id="6aa6a-121">下のダイアグラムは、`Book`、`Publisher`、および `Author` という 3 つのエンティティ型の概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-121">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="6aa6a-122">各エンティティ型には、いくつかのプロパティがありますが、ダイアグラムには各プロパティの型情報が示されていません。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-122">Each entity type has several properties, although type information for each property is not conveyed in the diagram.</span></span> <span data-ttu-id="6aa6a-123">プロパティを[エンティティ キー](../../../../docs/framework/data/adonet/entity-key.md) (キー) と示されています。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-123">Properties that are [entity keys](../../../../docs/framework/data/adonet/entity-key.md) are denoted with (Key).</span></span>  
  
 ![次の 3 つのエンティティの種類とモデルの例](./media/property/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="6aa6a-125">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)概念スキーマ定義言語と呼ばれるドメイン固有言語 (DSL) を使用して ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-125">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="6aa6a-126">次の CSDL は、`Book` エンティティ型 (上のダイアグラムに示されたように) を定義し、XML 属性により各プロパティの型と名前を示しています。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-126">The following CSDL defines the `Book` entity type (as shown in the diagram above) and indicates the type and name of each property by using XML attributes.</span></span> <span data-ttu-id="6aa6a-127">ファセット `Nullable` (省略可能) も XML 属性により定義されています。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-127">An optional facet, `Nullable`, is also defined by using an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="6aa6a-128">ダイアグラムに示されたいずれかのプロパティが複合型のプロパティであることも考えられます。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-128">It is possible that one of the properties shown in the diagram is a complex type property.</span></span> <span data-ttu-id="6aa6a-129">たとえば、`Address` エンティティ型の `Publisher` プロパティは、`StreetAddress`、`City`、`StateOrProvince`、`Country`、`PostalCode` などいくつかのスカラー プロパティから構成された複合型のプロパティである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-129">For example, the `Address` property on the `Publisher` entity type could be a complex type property composed of several scalar properties, such as `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span> <span data-ttu-id="6aa6a-130">このような複合型の CSDL 表現は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-130">The CSDL representation of such a complex type would be as follows:</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="6aa6a-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="6aa6a-131">See also</span></span>

- [<span data-ttu-id="6aa6a-132">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="6aa6a-132">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="6aa6a-133">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="6aa6a-133">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
