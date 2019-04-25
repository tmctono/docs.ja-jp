---
title: 外部キーのプロパティ
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: 74117b30ca54f7c57bd970003fc6f5dcc54d553f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879082"
---
# <a name="foreign-key-property"></a><span data-ttu-id="269ab-102">外部キーのプロパティ</span><span class="sxs-lookup"><span data-stu-id="269ab-102">foreign key property</span></span>
<span data-ttu-id="269ab-103">A*外部キー プロパティ*Entity Data Model (EDM) では、プリミティブ型[プロパティ](../../../../docs/framework/data/adonet/property.md)(または一連のプリミティブ型のプロパティ) で、[エンティティ型](../../../../docs/framework/data/adonet/entity-type.md)を格納しています。[エンティティ キー](../../../../docs/framework/data/adonet/entity-key.md)別のエンティティ型。</span><span class="sxs-lookup"><span data-stu-id="269ab-103">A *foreign key property* in the Entity Data Model (EDM) is a primitive type [property](../../../../docs/framework/data/adonet/property.md) (or a set of primitive type properties) on an [entity type](../../../../docs/framework/data/adonet/entity-type.md) that contains the [entity key](../../../../docs/framework/data/adonet/entity-key.md) of another entity type.</span></span>  
  
 <span data-ttu-id="269ab-104">外部キーのプロパティは、リレーショナル データベースの外部キー列に似ています。</span><span class="sxs-lookup"><span data-stu-id="269ab-104">A foreign key property is analogous to a foreign key column in a relational database.</span></span> <span data-ttu-id="269ab-105">外部キー列がテーブルの行の間のリレーションシップを作成するリレーショナル データベースで使用されること、同じ方法で概念モデルで外部キー プロパティが確立するために使用される[アソシエーション](../../../../docs/framework/data/adonet/association-type.md)エンティティ型の間。</span><span class="sxs-lookup"><span data-stu-id="269ab-105">In the same way that foreign key columns are used in a relational database to create relationships between rows in tables, foreign key properties in a conceptual model are used to establish [associations](../../../../docs/framework/data/adonet/association-type.md) between entity types.</span></span> <span data-ttu-id="269ab-106">A[参照整合性制約](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)2 つのエンティティ型、型のいずれかがある、外部キー プロパティとの間のアソシエーションを定義するために使用します。</span><span class="sxs-lookup"><span data-stu-id="269ab-106">A [referential integrity constraint](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) is used to define an association between two entity types when one of the types has a foreign key property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="269ab-107">例</span><span class="sxs-lookup"><span data-stu-id="269ab-107">Example</span></span>  
 <span data-ttu-id="269ab-108">下のダイアグラムは、`Book`、`Publisher`、および `Author` という 3 つのエンティティ型の概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="269ab-108">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="269ab-109">`Book` エンティティ型には、`PublisherId` というプロパティがあります。`Publisher` アソシエーションに参照整合性制約を定義するときに、このプロパティは `PublishedBy` エンティティ型のエンティティ キーを参照します。</span><span class="sxs-lookup"><span data-stu-id="269ab-109">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="269ab-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "参照に関する制約のモデルの例")</span><span class="sxs-lookup"><span data-stu-id="269ab-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="269ab-111">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)概念スキーマ定義言語と呼ばれるドメイン固有言語 (DSL) を使用して ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="269ab-111">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="269ab-112">次の CSDL は、外部キーのプロパティ `PublisherId` を使用して、上の概念モデルに示された `PublishedBy` アソシエーションに参照整合性制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="269ab-112">The following CSDL uses the foreign key property `PublisherId` to define a referential integrity constraint on the `PublishedBy` association shown in the conceptual model shown above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="269ab-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="269ab-113">See also</span></span>

- [<span data-ttu-id="269ab-114">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="269ab-114">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="269ab-115">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="269ab-115">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
