---
title: 外部キーのプロパティ
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: be0fcb94b0b457a33c17e7125cd22db50f298cc6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189319"
---
# <a name="foreign-key-property"></a><span data-ttu-id="bd4e7-102">外部キーのプロパティ</span><span class="sxs-lookup"><span data-stu-id="bd4e7-102">foreign key property</span></span>

<span data-ttu-id="bd4e7-103">Entity Data Model (EDM) における "*外部キーのプロパティ*" は、別の[エンティティ型](entity-type.md)の[エンティティ キー](entity-key.md)を含むエンティティ型のプリミティブ型の[プロパティ](property.md) (または一連のプリミティブ型のプロパティ) です。</span><span class="sxs-lookup"><span data-stu-id="bd4e7-103">A *foreign key property* in the Entity Data Model (EDM) is a primitive type [property](property.md) (or a set of primitive type properties) on an [entity type](entity-type.md) that contains the [entity key](entity-key.md) of another entity type.</span></span>  
  
 <span data-ttu-id="bd4e7-104">外部キーのプロパティは、リレーショナル データベースの外部キー列に似ています。</span><span class="sxs-lookup"><span data-stu-id="bd4e7-104">A foreign key property is analogous to a foreign key column in a relational database.</span></span> <span data-ttu-id="bd4e7-105">リレーショナル データベースで外部キー列を使用してテーブル内の行の間のリレーションシップを作成するのと同様に、概念モデルでは外部キーのプロパティを使用してエンティティ型の間の[アソシエーション](association-type.md)を設定します。</span><span class="sxs-lookup"><span data-stu-id="bd4e7-105">In the same way that foreign key columns are used in a relational database to create relationships between rows in tables, foreign key properties in a conceptual model are used to establish [associations](association-type.md) between entity types.</span></span> <span data-ttu-id="bd4e7-106">エンティティ型の 1 つに外部キーのプロパティがある場合に、2 つのエンティティ型の間のアソシエーションを定義するには、[参照整合性制約](referential-integrity-constraint.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd4e7-106">A [referential integrity constraint](referential-integrity-constraint.md) is used to define an association between two entity types when one of the types has a foreign key property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd4e7-107">例</span><span class="sxs-lookup"><span data-stu-id="bd4e7-107">Example</span></span>  

 <span data-ttu-id="bd4e7-108">下のダイアグラムは、`Book`、`Publisher`、および `Author` という 3 つのエンティティ型の概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="bd4e7-108">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="bd4e7-109">`Book` エンティティ型には、`PublisherId` というプロパティがあります。`Publisher` アソシエーションに参照整合性制約を定義するときに、このプロパティは `PublishedBy` エンティティ型のエンティティ キーを参照します。</span><span class="sxs-lookup"><span data-stu-id="bd4e7-109">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="bd4e7-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "参照制約モデルの例")</span><span class="sxs-lookup"><span data-stu-id="bd4e7-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="bd4e7-111">[ADO.NET Entity Framework](./ef/index.md) では、概念スキーマ定義言語 ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) と呼ばれるドメイン固有言語 (DSL) を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="bd4e7-111">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="bd4e7-112">次の CSDL は、外部キーのプロパティ `PublisherId` を使用して、上の概念モデルに示された `PublishedBy` アソシエーションに参照整合性制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="bd4e7-112">The following CSDL uses the foreign key property `PublisherId` to define a referential integrity constraint on the `PublishedBy` association shown in the conceptual model shown above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="bd4e7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd4e7-113">See also</span></span>

- [<span data-ttu-id="bd4e7-114">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="bd4e7-114">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="bd4e7-115">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="bd4e7-115">Entity Data Model</span></span>](entity-data-model.md)
