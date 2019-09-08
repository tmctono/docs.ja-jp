---
title: 参照整合性制約
ms.date: 03/30/2017
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
ms.openlocfilehash: 28880c7085f8b4e3dd2e51b5633c1f0e2a984a4b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794448"
---
# <a name="referential-integrity-constraint"></a><span data-ttu-id="e9ba2-102">参照整合性制約</span><span class="sxs-lookup"><span data-stu-id="e9ba2-102">referential integrity constraint</span></span>
<span data-ttu-id="e9ba2-103">Entity Data Model (EDM) の*参照整合性制約*は、リレーショナルデータベースの参照整合性制約に似ています。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-103">A *referential integrity constraint* in the Entity Data Model (EDM) is similar to a referential integrity constraint in a relational database.</span></span> <span data-ttu-id="e9ba2-104">データベーステーブルの列が別のテーブルの主キーを参照できるのと同じように、[エンティティ型](entity-type.md)の[プロパティ](property.md)(またはプロパティ) は、別のエンティティ型の[エンティティキー](entity-key.md)を参照できます。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-104">In the same way that a column (or columns) from a database table can reference the primary key of another table, a [property](property.md) (or properties) of an [entity type](entity-type.md) can reference the [entity key](entity-key.md) of another entity type.</span></span> <span data-ttu-id="e9ba2-105">参照されるエンティティ型は、制約の*プリンシパル end*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-105">The entity type that is referenced is called the *principal end* of the constraint.</span></span> <span data-ttu-id="e9ba2-106">プリンシパル end を参照するエンティティ型は、制約の*依存 end*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-106">The entity type that references the principal end is called the *dependent end* of the constraint.</span></span>  
  
 <span data-ttu-id="e9ba2-107">参照整合性制約は、2つのエンティティ型間の[アソシエーション](association-type.md)の一部として定義されます。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-107">A referential integrity constraint is defined as part of an [association](association-type.md) between two entity types.</span></span> <span data-ttu-id="e9ba2-108">参照整合性制約の定義には、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-108">The definition for a referential integrity constraint specifies the following information:</span></span>  
  
- <span data-ttu-id="e9ba2-109">制約のプリンシパル End。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-109">The principal end of the constraint.</span></span> <span data-ttu-id="e9ba2-110">(エンティティ キーが依存 End により参照されるエンティティ型)</span><span class="sxs-lookup"><span data-stu-id="e9ba2-110">(An entity type whose entity key is referenced by the dependent end.)</span></span>  
  
- <span data-ttu-id="e9ba2-111">プリンシパル End のエンティティ キー。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-111">The entity key of the principal end.</span></span>  
  
- <span data-ttu-id="e9ba2-112">制約の依存 End。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-112">The dependent end of the constraint.</span></span> <span data-ttu-id="e9ba2-113">(プリンシパル End のエンティティ キーを参照するプロパティを持つエンティティ型)</span><span class="sxs-lookup"><span data-stu-id="e9ba2-113">(An entity type that has a property or properties that reference the entity key of the principal end.)</span></span>  
  
- <span data-ttu-id="e9ba2-114">依存 End の参照プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-114">The referencing property or properties of the dependent end.</span></span>  
  
 <span data-ttu-id="e9ba2-115">EDM の参照整合性制約の目的は、常に有効なアソシエーションが存在することを確認するためです。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-115">The purpose of referential integrity constraints in the EDM is to ensure that valid associations always exist.</span></span> <span data-ttu-id="e9ba2-116">詳細については、「[外部キーのプロパティ](foreign-key-property.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-116">For more information, see [foreign key property](foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9ba2-117">例</span><span class="sxs-lookup"><span data-stu-id="e9ba2-117">Example</span></span>  
 <span data-ttu-id="e9ba2-118">下のダイアグラムは、`WrittenBy` および `PublishedBy` という 2 つのアソシエーションの概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-118">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span> <span data-ttu-id="e9ba2-119">`Book` エンティティ型には、`PublisherId` というプロパティがあります。`Publisher` アソシエーションに参照整合性制約を定義するときに、このプロパティは `PublishedBy` エンティティ型のエンティティ キーを参照します。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-119">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="e9ba2-120">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "参照制約モデルの例")</span><span class="sxs-lookup"><span data-stu-id="e9ba2-120">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="e9ba2-121">[ADO.NET Entity Framework](./ef/index.md)は、概念スキーマ定義言語 ([CSDL](./ef/language-reference/csdl-specification.md)) と呼ばれるドメイン固有言語 (DSL) を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-121">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="e9ba2-122">次の CSDL は、上の概念モデルに示された `PublishedBy` アソシエーションの参照整合性制約を定義しています。</span><span class="sxs-lookup"><span data-stu-id="e9ba2-122">The following CSDL defines a referential integrity constraint on the `PublishedBy` association shown in the conceptual model above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="e9ba2-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9ba2-123">See also</span></span>

- [<span data-ttu-id="e9ba2-124">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="e9ba2-124">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="e9ba2-125">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="e9ba2-125">Entity Data Model</span></span>](entity-data-model.md)
