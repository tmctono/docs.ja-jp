---
title: エンティティ コンテナー
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: 95fb59c86f951e75f0988f45219fd07cbb003c01
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200824"
---
# <a name="entity-container"></a><span data-ttu-id="a694d-102">エンティティ コンテナー</span><span class="sxs-lookup"><span data-stu-id="a694d-102">entity container</span></span>

<span data-ttu-id="a694d-103">"*エンティティ コンテナー*" は、[エンティティ セット](entity-set.md)、[アソシエーション セット](association-set.md)、および[関数インポート](model-declared-function.md)の論理グループです。</span><span class="sxs-lookup"><span data-stu-id="a694d-103">An *entity container* is a logical grouping of [entity sets](entity-set.md), [association sets](association-set.md), and [function imports](model-declared-function.md).</span></span>  
  
 <span data-ttu-id="a694d-104">概念モデルで定義するエンティティ コンテナーは、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a694d-104">The following must be true of an entity container defined in a conceptual model:</span></span>  
  
- <span data-ttu-id="a694d-105">1 つ以上のエンティティ コンテナーを各概念モデルに定義すること。</span><span class="sxs-lookup"><span data-stu-id="a694d-105">At least one entity container must be defined in each conceptual model.</span></span>  
  
- <span data-ttu-id="a694d-106">各概念モデル内のエンティティ コンテナー名が一意であること。</span><span class="sxs-lookup"><span data-stu-id="a694d-106">The entity container must have a unique name within each conceptual model.</span></span>  
  
 <span data-ttu-id="a694d-107">エンティティ コンテナーは、1 つ以上の名前空間に定義されたエンティティ型またはアソシエーションを使用するエンティティ セットまたはアソシエーション セットを定義できます。</span><span class="sxs-lookup"><span data-stu-id="a694d-107">An entity container can define entity sets or association sets that use entity types or associations defined in one or more namespaces.</span></span> <span data-ttu-id="a694d-108">詳しくは、「[Entity Data Model: 名前空間](entity-data-model-namespaces.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a694d-108">For more information, see [Entity Data Model: Namespaces](entity-data-model-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a694d-109">例</span><span class="sxs-lookup"><span data-stu-id="a694d-109">Example</span></span>  

 <span data-ttu-id="a694d-110">下のダイアグラムは、`Book`、`Publisher`、および `Author` という 3 つのエンティティ型の概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="a694d-110">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  <span data-ttu-id="a694d-111">詳細については、次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a694d-111">See the next example for more information.</span></span>  
  
 ![3 種類のエンティティを持つモデルの例](./media/entity-container/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="a694d-113">ダイアグラムにはエンティティ コンテナー情報が示されていませんが、概念モデルにはエンティティ コンテナーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a694d-113">Although the diagram does not convey entity container information, the conceptual model must define an entity container.</span></span> <span data-ttu-id="a694d-114">[ADO.NET Entity Framework](./ef/index.md) では、概念スキーマ定義言語 ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) と呼ばれる DSL を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="a694d-114">The [ADO.NET Entity Framework](./ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="a694d-115">次の CSDL は、上のダイアグラムに示された概念モデルのエンティティ コンテナーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="a694d-115">The following CSDL defines an entity container for the conceptual model shown in the diagram above.</span></span> <span data-ttu-id="a694d-116">エンティティ コンテナー名は XML 属性に定義されています。</span><span class="sxs-lookup"><span data-stu-id="a694d-116">Note that the entity container name is defined in an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="a694d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a694d-117">See also</span></span>

- [<span data-ttu-id="a694d-118">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="a694d-118">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="a694d-119">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="a694d-119">Entity Data Model</span></span>](entity-data-model.md)
