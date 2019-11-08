---
title: 参照整合性制約
ms.date: 03/30/2017
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
ms.openlocfilehash: ad35df7bcca62ffdbc3842b0817b22c5482a3d4d
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738377"
---
# <a name="referential-integrity-constraint"></a><span data-ttu-id="e8279-102">参照整合性制約</span><span class="sxs-lookup"><span data-stu-id="e8279-102">referential integrity constraint</span></span>
<span data-ttu-id="e8279-103">Entity Data Model (EDM) の*参照整合性制約*は、リレーショナルデータベースの参照整合性制約に似ています。</span><span class="sxs-lookup"><span data-stu-id="e8279-103">A *referential integrity constraint* in the Entity Data Model (EDM) is similar to a referential integrity constraint in a relational database.</span></span> <span data-ttu-id="e8279-104">データベーステーブルの列が別のテーブルの主キーを参照できるのと同じように、[エンティティ型](entity-type.md)の[プロパティ](property.md)(またはプロパティ) は、別のエンティティ型の[エンティティキー](entity-key.md)を参照できます。</span><span class="sxs-lookup"><span data-stu-id="e8279-104">In the same way that a column (or columns) from a database table can reference the primary key of another table, a [property](property.md) (or properties) of an [entity type](entity-type.md) can reference the [entity key](entity-key.md) of another entity type.</span></span> <span data-ttu-id="e8279-105">参照されるエンティティ型は、制約の*プリンシパル end*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e8279-105">The entity type that is referenced is called the *principal end* of the constraint.</span></span> <span data-ttu-id="e8279-106">プリンシパル end を参照するエンティティ型は、制約の*依存 end*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e8279-106">The entity type that references the principal end is called the *dependent end* of the constraint.</span></span>  
  
 <span data-ttu-id="e8279-107">参照整合性制約は、2つのエンティティ型間の[アソシエーション](association-type.md)の一部として定義されます。</span><span class="sxs-lookup"><span data-stu-id="e8279-107">A referential integrity constraint is defined as part of an [association](association-type.md) between two entity types.</span></span> <span data-ttu-id="e8279-108">参照整合性制約の定義には、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8279-108">The definition for a referential integrity constraint specifies the following information:</span></span>  
  
- <span data-ttu-id="e8279-109">制約のプリンシパル End。</span><span class="sxs-lookup"><span data-stu-id="e8279-109">The principal end of the constraint.</span></span> <span data-ttu-id="e8279-110">(エンティティ キーが依存 End により参照されるエンティティ型)</span><span class="sxs-lookup"><span data-stu-id="e8279-110">(An entity type whose entity key is referenced by the dependent end.)</span></span>  
  
- <span data-ttu-id="e8279-111">プリンシパル End のエンティティ キー。</span><span class="sxs-lookup"><span data-stu-id="e8279-111">The entity key of the principal end.</span></span>  
  
- <span data-ttu-id="e8279-112">制約の依存 End。</span><span class="sxs-lookup"><span data-stu-id="e8279-112">The dependent end of the constraint.</span></span> <span data-ttu-id="e8279-113">(プリンシパル End のエンティティ キーを参照するプロパティを持つエンティティ型)</span><span class="sxs-lookup"><span data-stu-id="e8279-113">(An entity type that has a property or properties that reference the entity key of the principal end.)</span></span>  
  
- <span data-ttu-id="e8279-114">依存 End の参照プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e8279-114">The referencing property or properties of the dependent end.</span></span>  
  
 <span data-ttu-id="e8279-115">EDM の参照整合性制約の目的は、常に有効なアソシエーションが存在することを確認するためです。</span><span class="sxs-lookup"><span data-stu-id="e8279-115">The purpose of referential integrity constraints in the EDM is to ensure that valid associations always exist.</span></span> <span data-ttu-id="e8279-116">詳細については、「[外部キーのプロパティ](foreign-key-property.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8279-116">For more information, see [foreign key property](foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8279-117">例</span><span class="sxs-lookup"><span data-stu-id="e8279-117">Example</span></span>  
 <span data-ttu-id="e8279-118">下のダイアグラムは、`WrittenBy` および `PublishedBy` という 2 つのアソシエーションの概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="e8279-118">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span> <span data-ttu-id="e8279-119">`Book` エンティティ型には、`PublisherId` というプロパティがあります。`Publisher` アソシエーションに参照整合性制約を定義するときに、このプロパティは `PublishedBy` エンティティ型のエンティティ キーを参照します。</span><span class="sxs-lookup"><span data-stu-id="e8279-119">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="e8279-120">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "参照制約モデルの例")</span><span class="sxs-lookup"><span data-stu-id="e8279-120">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="e8279-121">[ADO.NET Entity Framework](./ef/index.md)は、概念スキーマ定義言語 ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) と呼ばれるドメイン固有言語 (DSL) を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="e8279-121">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="e8279-122">次の CSDL は、上の概念モデルに示された `PublishedBy` アソシエーションの参照整合性制約を定義しています。</span><span class="sxs-lookup"><span data-stu-id="e8279-122">The following CSDL defines a referential integrity constraint on the `PublishedBy` association shown in the conceptual model above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="e8279-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8279-123">See also</span></span>

- [<span data-ttu-id="e8279-124">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="e8279-124">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="e8279-125">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="e8279-125">Entity Data Model</span></span>](entity-data-model.md)
