---
title: 参照整合性制約
description: エンティティ型間で常に有効なアソシエーションが存在するようにする、Entity Data Model の参照整合性制約について説明します。
ms.date: 03/30/2017
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
ms.openlocfilehash: 65c811b2a12a64870107ff771d5acc64e86f2c1f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286625"
---
# <a name="referential-integrity-constraint"></a><span data-ttu-id="68706-103">参照整合性制約</span><span class="sxs-lookup"><span data-stu-id="68706-103">referential integrity constraint</span></span>
<span data-ttu-id="68706-104">Entity Data Model (EDM) の "*参照整合性制約*" は、リレーショナル データベースの参照整合性制約と似ています。</span><span class="sxs-lookup"><span data-stu-id="68706-104">A *referential integrity constraint* in the Entity Data Model (EDM) is similar to a referential integrity constraint in a relational database.</span></span> <span data-ttu-id="68706-105">データベース テーブルの列が別のテーブルの主キーを参照できるのと同じように、[エンティティ型](entity-type.md)の[プロパティ](property.md)が別のエンティティ型の[エンティティ キー](entity-key.md)を参照できます。</span><span class="sxs-lookup"><span data-stu-id="68706-105">In the same way that a column (or columns) from a database table can reference the primary key of another table, a [property](property.md) (or properties) of an [entity type](entity-type.md) can reference the [entity key](entity-key.md) of another entity type.</span></span> <span data-ttu-id="68706-106">参照されるエンティティ型は、制約の "*プリンシパル End*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="68706-106">The entity type that is referenced is called the *principal end* of the constraint.</span></span> <span data-ttu-id="68706-107">プリンシパル End を参照するエンティティ型は、制約の "*依存 End*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="68706-107">The entity type that references the principal end is called the *dependent end* of the constraint.</span></span>  
  
 <span data-ttu-id="68706-108">参照整合性制約は、2 つのエンティティ型の間の[アソシエーション](association-type.md)の一部として定義されます。</span><span class="sxs-lookup"><span data-stu-id="68706-108">A referential integrity constraint is defined as part of an [association](association-type.md) between two entity types.</span></span> <span data-ttu-id="68706-109">参照整合性制約の定義には、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="68706-109">The definition for a referential integrity constraint specifies the following information:</span></span>  
  
- <span data-ttu-id="68706-110">制約のプリンシパル End。</span><span class="sxs-lookup"><span data-stu-id="68706-110">The principal end of the constraint.</span></span> <span data-ttu-id="68706-111">(エンティティ キーが依存 End により参照されるエンティティ型)</span><span class="sxs-lookup"><span data-stu-id="68706-111">(An entity type whose entity key is referenced by the dependent end.)</span></span>  
  
- <span data-ttu-id="68706-112">プリンシパル End のエンティティ キー。</span><span class="sxs-lookup"><span data-stu-id="68706-112">The entity key of the principal end.</span></span>  
  
- <span data-ttu-id="68706-113">制約の依存 End。</span><span class="sxs-lookup"><span data-stu-id="68706-113">The dependent end of the constraint.</span></span> <span data-ttu-id="68706-114">(プリンシパル End のエンティティ キーを参照するプロパティを持つエンティティ型)</span><span class="sxs-lookup"><span data-stu-id="68706-114">(An entity type that has a property or properties that reference the entity key of the principal end.)</span></span>  
  
- <span data-ttu-id="68706-115">依存 End の参照プロパティ。</span><span class="sxs-lookup"><span data-stu-id="68706-115">The referencing property or properties of the dependent end.</span></span>  
  
 <span data-ttu-id="68706-116">EDM の参照整合性制約の目的は、常に有効なアソシエーションが存在することを確認するためです。</span><span class="sxs-lookup"><span data-stu-id="68706-116">The purpose of referential integrity constraints in the EDM is to ensure that valid associations always exist.</span></span> <span data-ttu-id="68706-117">詳しくは、「[外部キーのプロパティ](foreign-key-property.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="68706-117">For more information, see [foreign key property](foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="68706-118">例</span><span class="sxs-lookup"><span data-stu-id="68706-118">Example</span></span>  
 <span data-ttu-id="68706-119">下のダイアグラムは、`WrittenBy` および `PublishedBy` という 2 つのアソシエーションの概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="68706-119">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span> <span data-ttu-id="68706-120">`Book` エンティティ型には、`PublisherId` というプロパティがあります。`Publisher` アソシエーションに参照整合性制約を定義するときに、このプロパティは `PublishedBy` エンティティ型のエンティティ キーを参照します。</span><span class="sxs-lookup"><span data-stu-id="68706-120">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="68706-121">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "参照制約モデルの例")</span><span class="sxs-lookup"><span data-stu-id="68706-121">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="68706-122">[ADO.NET Entity Framework](./ef/index.md) では、概念スキーマ定義言語 ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) と呼ばれるドメイン固有言語 (DSL) を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="68706-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="68706-123">次の CSDL は、上の概念モデルに示された `PublishedBy` アソシエーションの参照整合性制約を定義しています。</span><span class="sxs-lookup"><span data-stu-id="68706-123">The following CSDL defines a referential integrity constraint on the `PublishedBy` association shown in the conceptual model above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="68706-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="68706-124">See also</span></span>

- [<span data-ttu-id="68706-125">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="68706-125">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="68706-126">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="68706-126">Entity Data Model</span></span>](entity-data-model.md)
