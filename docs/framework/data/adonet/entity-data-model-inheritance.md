---
title: Entity Data Model:継承
ms.date: 03/30/2017
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
ms.openlocfilehash: 057040eee411988c46adc9c4cabcfe5f5a185e1b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175461"
---
# <a name="entity-data-model-inheritance"></a><span data-ttu-id="3b29e-102">Entity Data Model:継承</span><span class="sxs-lookup"><span data-stu-id="3b29e-102">Entity Data Model: Inheritance</span></span>

<span data-ttu-id="3b29e-103">Entity Data Model (EDM) では、[エンティティ型](entity-type.md)の継承がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3b29e-103">The Entity Data Model (EDM) supports inheritance for [entity types](entity-type.md).</span></span> <span data-ttu-id="3b29e-104">EDM の継承は、オブジェクト指向プログラミング言語におけるクラスの継承に似ています。</span><span class="sxs-lookup"><span data-stu-id="3b29e-104">Inheritance in the EDM is similar to inheritance for classes in object-oriented programming languages.</span></span> <span data-ttu-id="3b29e-105">オブジェクト指向言語のクラスと同様、概念モデルでは、別のエンティティ型 ("*基本型*") を継承するエンティティ型 ("*派生型*") を定義できます。</span><span class="sxs-lookup"><span data-stu-id="3b29e-105">Like with classes in object-oriented languages, in a conceptual model you can define an entity type (a *derived type*) that inherits from another entity type (the *base type*).</span></span> <span data-ttu-id="3b29e-106">ただし、オブジェクト指向プログラミングのクラスとは異なり、概念モデルでは、派生型は基本型のすべての[プロパティ](property.md)と[ナビゲーション プロパティ](navigation-property.md)を常に継承します。</span><span class="sxs-lookup"><span data-stu-id="3b29e-106">However, unlike classes in object-oriented programming, in a conceptual model the derived type always inherits all the [properties](property.md) and [navigation properties](navigation-property.md) of the base type.</span></span> <span data-ttu-id="3b29e-107">派生型の継承プロパティは、オーバーライドできません。</span><span class="sxs-lookup"><span data-stu-id="3b29e-107">You cannot override inherited properties in a derived type.</span></span>  
  
 <span data-ttu-id="3b29e-108">概念モデルでは、派生型が別の派生型を継承する継承階層を構築することができます。</span><span class="sxs-lookup"><span data-stu-id="3b29e-108">In a conceptual model you can build inheritance hierarchies in which a derived type inherits from another derived type.</span></span> <span data-ttu-id="3b29e-109">階層の最上位にある型 (階層内で派生型ではない唯一の型) は、"*ルート型*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3b29e-109">The type at the top of the hierarchy (the one type in the hierarchy that is not a derived type) is called the *root type*.</span></span> <span data-ttu-id="3b29e-110">継承階層では、ルート型に[エンティティ キー](entity-key.md)を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b29e-110">In an inheritance hierarchy, the [entity key](entity-key.md) must be defined on the root type.</span></span>  
  
 <span data-ttu-id="3b29e-111">複数の型から派生型を継承する継承階層を構築することはできません。</span><span class="sxs-lookup"><span data-stu-id="3b29e-111">You cannot build inheritance hierarchies in which a derived type inherits from more than one type.</span></span> <span data-ttu-id="3b29e-112">たとえば、`Book` エンティティ型の概念モデルでは、それぞれ `FictionBook` から継承する派生型、`NonFictionBook` および `Book` を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="3b29e-112">For example, in a conceptual model with a `Book` entity type, you could define derived types `FictionBook` and `NonFictionBook` that each inherit from `Book`.</span></span> <span data-ttu-id="3b29e-113">しかし、`FictionBook` 型と `NonFictionBook` 型の両方から継承する型を定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="3b29e-113">However, you could not then define a type that inherits from both the `FictionBook` and `NonFictionBook` types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b29e-114">例</span><span class="sxs-lookup"><span data-stu-id="3b29e-114">Example</span></span>  

<span data-ttu-id="3b29e-115">次の図では、`Book`、`FictionBook`、`Publisher`、`Author` という 4 つのエンティティ型の概念モデルを示します。</span><span class="sxs-lookup"><span data-stu-id="3b29e-115">The following diagram shows a conceptual model with four entity types: `Book`, `FictionBook`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="3b29e-116">`FictionBook` エンティティ型は、`Book` エンティティ型から継承する派生型です。</span><span class="sxs-lookup"><span data-stu-id="3b29e-116">The `FictionBook` entity type is a derived type, inheriting from the `Book` entity type.</span></span> <span data-ttu-id="3b29e-117">`FictionBook` 型は、`ISBN (Key)` プロパティ、`Title` プロパティ、および `Revision` プロパティを継承し、`Genre` と呼ばれる追加プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3b29e-117">The `FictionBook` type inherits the `ISBN (Key)`, `Title`, and `Revision` properties, and defines an additional property called `Genre`.</span></span>  
  
 ![4 つのエンティティ型を含む概念モデルを示す図。](./media/entity-data-model-inheritance/entity-type-inheritance.gif)  
  
 <span data-ttu-id="3b29e-119">[ADO.NET Entity Framework](./ef/index.md) では、概念スキーマ定義言語 ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) と呼ばれるドメイン固有言語 (DSL) を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="3b29e-119">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="3b29e-120">次の CSDL は、上のダイアグラムに示された `FictionBook` 型を継承する `Book` エンティティ型を定義しています。</span><span class="sxs-lookup"><span data-stu-id="3b29e-120">The following CSDL defines an entity type, `FictionBook`, that inherits from the `Book` type (as in the diagram above):</span></span>  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a><span data-ttu-id="3b29e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b29e-121">See also</span></span>

- [<span data-ttu-id="3b29e-122">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="3b29e-122">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="3b29e-123">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="3b29e-123">Entity Data Model</span></span>](entity-data-model.md)
