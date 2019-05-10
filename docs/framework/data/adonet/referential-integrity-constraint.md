---
title: 参照整合性制約
ms.date: 03/30/2017
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
ms.openlocfilehash: b442e15c75554e1b06e9ff89c7224430a0605f9c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649631"
---
# <a name="referential-integrity-constraint"></a><span data-ttu-id="905e4-102">参照整合性制約</span><span class="sxs-lookup"><span data-stu-id="905e4-102">referential integrity constraint</span></span>
<span data-ttu-id="905e4-103">A*参照整合性制約*Entity Data Model (EDM) では、リレーショナル データベースで参照整合性制約に似ています。</span><span class="sxs-lookup"><span data-stu-id="905e4-103">A *referential integrity constraint* in the Entity Data Model (EDM) is similar to a referential integrity constraint in a relational database.</span></span> <span data-ttu-id="905e4-104">同様に、データベース テーブルから列 (または列) は、別のテーブルの主キーで参照できます、[プロパティ](../../../../docs/framework/data/adonet/property.md)(またはプロパティ) の[エンティティ型](../../../../docs/framework/data/adonet/entity-type.md)参照できる、[エンティティ キー](../../../../docs/framework/data/adonet/entity-key.md)別のエンティティ型。</span><span class="sxs-lookup"><span data-stu-id="905e4-104">In the same way that a column (or columns) from a database table can reference the primary key of another table, a [property](../../../../docs/framework/data/adonet/property.md) (or properties) of an [entity type](../../../../docs/framework/data/adonet/entity-type.md) can reference the [entity key](../../../../docs/framework/data/adonet/entity-key.md) of another entity type.</span></span> <span data-ttu-id="905e4-105">参照されるエンティティ型が呼び出される、*プリンシパル end*の制約。</span><span class="sxs-lookup"><span data-stu-id="905e4-105">The entity type that is referenced is called the *principal end* of the constraint.</span></span> <span data-ttu-id="905e4-106">プリンシパル end を参照するエンティティ型が呼び出される、*依存 end*の制約。</span><span class="sxs-lookup"><span data-stu-id="905e4-106">The entity type that references the principal end is called the *dependent end* of the constraint.</span></span>  
  
 <span data-ttu-id="905e4-107">参照整合性制約がの一部として定義されている、[アソシエーション](../../../../docs/framework/data/adonet/association-type.md)2 つのエンティティ型の間。</span><span class="sxs-lookup"><span data-stu-id="905e4-107">A referential integrity constraint is defined as part of an [association](../../../../docs/framework/data/adonet/association-type.md) between two entity types.</span></span> <span data-ttu-id="905e4-108">参照整合性制約の定義には、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="905e4-108">The definition for a referential integrity constraint specifies the following information:</span></span>  
  
- <span data-ttu-id="905e4-109">制約のプリンシパル End。</span><span class="sxs-lookup"><span data-stu-id="905e4-109">The principal end of the constraint.</span></span> <span data-ttu-id="905e4-110">(エンティティ キーが依存 End により参照されるエンティティ型)</span><span class="sxs-lookup"><span data-stu-id="905e4-110">(An entity type whose entity key is referenced by the dependent end.)</span></span>  
  
- <span data-ttu-id="905e4-111">プリンシパル End のエンティティ キー。</span><span class="sxs-lookup"><span data-stu-id="905e4-111">The entity key of the principal end.</span></span>  
  
- <span data-ttu-id="905e4-112">制約の依存 End。</span><span class="sxs-lookup"><span data-stu-id="905e4-112">The dependent end of the constraint.</span></span> <span data-ttu-id="905e4-113">(プリンシパル End のエンティティ キーを参照するプロパティを持つエンティティ型)</span><span class="sxs-lookup"><span data-stu-id="905e4-113">(An entity type that has a property or properties that reference the entity key of the principal end.)</span></span>  
  
- <span data-ttu-id="905e4-114">依存 End の参照プロパティ。</span><span class="sxs-lookup"><span data-stu-id="905e4-114">The referencing property or properties of the dependent end.</span></span>  
  
 <span data-ttu-id="905e4-115">EDM の参照整合性制約の目的は、常に有効なアソシエーションが存在することを確認するためです。</span><span class="sxs-lookup"><span data-stu-id="905e4-115">The purpose of referential integrity constraints in the EDM is to ensure that valid associations always exist.</span></span> <span data-ttu-id="905e4-116">詳細については、次を参照してください。[外部キー プロパティ](../../../../docs/framework/data/adonet/foreign-key-property.md)します。</span><span class="sxs-lookup"><span data-stu-id="905e4-116">For more information, see [foreign key property](../../../../docs/framework/data/adonet/foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="905e4-117">例</span><span class="sxs-lookup"><span data-stu-id="905e4-117">Example</span></span>  
 <span data-ttu-id="905e4-118">下のダイアグラムは、`WrittenBy` および `PublishedBy` という 2 つのアソシエーションの概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="905e4-118">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span> <span data-ttu-id="905e4-119">`Book` エンティティ型には、`PublisherId` というプロパティがあります。`Publisher` アソシエーションに参照整合性制約を定義するときに、このプロパティは `PublishedBy` エンティティ型のエンティティ キーを参照します。</span><span class="sxs-lookup"><span data-stu-id="905e4-119">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="905e4-120">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "参照に関する制約のモデルの例")</span><span class="sxs-lookup"><span data-stu-id="905e4-120">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="905e4-121">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)概念スキーマ定義言語と呼ばれるドメイン固有言語 (DSL) を使用して ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="905e4-121">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="905e4-122">次の CSDL は、上の概念モデルに示された `PublishedBy` アソシエーションの参照整合性制約を定義しています。</span><span class="sxs-lookup"><span data-stu-id="905e4-122">The following CSDL defines a referential integrity constraint on the `PublishedBy` association shown in the conceptual model above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="905e4-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="905e4-123">See also</span></span>

- [<span data-ttu-id="905e4-124">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="905e4-124">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="905e4-125">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="905e4-125">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
