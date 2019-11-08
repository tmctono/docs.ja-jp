---
title: 複合型
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: e21ca90a7be8f2bd9be9483c66a1e95e6ba1bee2
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738538"
---
# <a name="complex-type"></a><span data-ttu-id="41f32-102">複合型</span><span class="sxs-lookup"><span data-stu-id="41f32-102">complex type</span></span>
<span data-ttu-id="41f32-103">*複合型*は、[エンティティ型](entity-type.md)またはその他の複合型に対して、構造化された豊富なプロパティを定義するためのテンプレートです。</span><span class="sxs-lookup"><span data-stu-id="41f32-103">A *complex type* is a template for defining rich, structured properties on [entity types](entity-type.md) or on other complex types.</span></span> <span data-ttu-id="41f32-104">各テンプレートには、以下が含まれています。</span><span class="sxs-lookup"><span data-stu-id="41f32-104">Each template contains the following:</span></span>  
  
- <span data-ttu-id="41f32-105">一意の名前</span><span class="sxs-lookup"><span data-stu-id="41f32-105">A unique name.</span></span> <span data-ttu-id="41f32-106">(必須)</span><span class="sxs-lookup"><span data-stu-id="41f32-106">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="41f32-107">複合型の名前は、同じ名前空間のエンティティ型の名前と同じにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="41f32-107">The name of a complex type cannot be the same as an entity type name within the same namespace.</span></span>  
  
- <span data-ttu-id="41f32-108">1つ以上の[プロパティ](property.md)の形式のデータ。</span><span class="sxs-lookup"><span data-stu-id="41f32-108">Data in the form of one or more [properties](property.md).</span></span> <span data-ttu-id="41f32-109">(省略可能)</span><span class="sxs-lookup"><span data-stu-id="41f32-109">(Optional.)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="41f32-110">複合型のプロパティには、別の複合型を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="41f32-110">A property of a complex type can be another complex type.</span></span>  
  
 <span data-ttu-id="41f32-111">複合型は、プリミティブ型のプロパティまたはその他の複合型の形式でデータ ペイロードを伝達できる点がエンティティ型と似ています。</span><span class="sxs-lookup"><span data-stu-id="41f32-111">A complex type is similar to an entity type in that a complex type can carry a data payload in the form of primitive type properties or other complex types.</span></span> <span data-ttu-id="41f32-112">ただし、複合型とエンティティ型の間にはいくつかの重要な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="41f32-112">However, there are some key differences between complex types and entity types:</span></span>  
  
- <span data-ttu-id="41f32-113">複合型には ID がないため、独立して存在することができません。</span><span class="sxs-lookup"><span data-stu-id="41f32-113">Complex types do not have identities and therefore cannot exist independently.</span></span> <span data-ttu-id="41f32-114">複合型は、エンティティ型またはその他の複合型のプロパティとしてのみ存在できます。</span><span class="sxs-lookup"><span data-stu-id="41f32-114">Complex types can only exist as properties on entity types or other complex types.</span></span>  
  
- <span data-ttu-id="41f32-115">複合型は[アソシエーション](association-type.md)に参加できません。</span><span class="sxs-lookup"><span data-stu-id="41f32-115">Complex types cannot participate in [associations](association-type.md).</span></span> <span data-ttu-id="41f32-116">アソシエーションの end に複合型を指定することはできません。したがって、[ナビゲーションプロパティ](navigation-property.md)を複合型に対して定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="41f32-116">Neither end of an association can be a complex type, and therefore [navigation properties](navigation-property.md) cannot be defined on complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41f32-117">例</span><span class="sxs-lookup"><span data-stu-id="41f32-117">Example</span></span>  
 <span data-ttu-id="41f32-118">[ADO.NET Entity Framework](./ef/index.md)は、概念スキーマ定義言語 ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) と呼ばれるドメイン固有言語 (DSL) を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="41f32-118">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="41f32-119">次の CSDL は、`StreetAddress`、`City`、`StateOrProvince`、`Country`、および `PostalCode` のプリミティブ型のプロパティの複合型 Address を定義しています。</span><span class="sxs-lookup"><span data-stu-id="41f32-119">The following CSDL defines a complex type, Address, with the primitive type properties `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 <span data-ttu-id="41f32-120">エンティティ型のプロパティとして複合型 `Address` (上の図) を定義するには、エンティティ型の定義にプロパティの型を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41f32-120">To define the complex type `Address` (above) as a property on an entity type, you must declare the property type in the entity type definition.</span></span> <span data-ttu-id="41f32-121">次の CSDL は、エンティティ型 (Publisher) に複合型として `Address` プロパティを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="41f32-121">The following CSDL declares the `Address` property as a complex type on an entity type (Publisher):</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a><span data-ttu-id="41f32-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="41f32-122">See also</span></span>

- [<span data-ttu-id="41f32-123">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="41f32-123">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="41f32-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="41f32-124">Entity Data Model</span></span>](entity-data-model.md)
