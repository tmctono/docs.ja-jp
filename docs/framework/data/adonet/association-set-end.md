---
title: アソシエーション セット End
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 48ba84d46e380462405551cc2d826d84368b351a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786930"
---
# <a name="association-set-end"></a><span data-ttu-id="4d431-102">アソシエーション セット End</span><span class="sxs-lookup"><span data-stu-id="4d431-102">association set end</span></span>
<span data-ttu-id="4d431-103">*アソシエーションセット end*は、[アソシエーションセット](association-set.md)の末尾にある[エンティティ型](entity-type.md)と[エンティティセット](entity-set.md)を識別します。</span><span class="sxs-lookup"><span data-stu-id="4d431-103">An *association set end* identifies the [entity type](entity-type.md) and the [entity set](entity-set.md) at the end of an [association set](association-set.md).</span></span> <span data-ttu-id="4d431-104">アソシエーション セット End はアソシエーション セットの一部として定義されます。アソシエーション セットには、アソシエーション セット End が 2 つ必要です。</span><span class="sxs-lookup"><span data-stu-id="4d431-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="4d431-105">アソシエーション セット End の定義には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d431-105">An association set end definition contains the following information:</span></span>  
  
- <span data-ttu-id="4d431-106">アソシエーション セットに含まれるエンティティ型の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="4d431-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="4d431-107">(必須)</span><span class="sxs-lookup"><span data-stu-id="4d431-107">(Required)</span></span>  
  
- <span data-ttu-id="4d431-108">アソシエーション セットに含まれるエンティティ型のエンティティ セット。</span><span class="sxs-lookup"><span data-stu-id="4d431-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="4d431-109">(必須)</span><span class="sxs-lookup"><span data-stu-id="4d431-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d431-110">例</span><span class="sxs-lookup"><span data-stu-id="4d431-110">Example</span></span>  
 <span data-ttu-id="4d431-111">下のダイアグラムは、`WrittenBy` および `PublishedBy` という 2 つのアソシエーションの概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="4d431-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 ![3種類のエンティティを持つモデルの例](./media/association-set-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="4d431-113">次のダイアグラムには、上の概念モデルに基づくアソシエーション セット (`PublishedBy`) と 2 つのエンティティ セット (`Books` および `Publishers`) を示しています。</span><span class="sxs-lookup"><span data-stu-id="4d431-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="4d431-114">アソシエーション セット End は `Books` および `Publishers` エンティティ セットです。</span><span class="sxs-lookup"><span data-stu-id="4d431-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="4d431-115">`Books`エンティティセット内の Bi は、 `Book`実行時にエンティティ型のインスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="4d431-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="4d431-116">同様に、Pj は`Publisher` `Publishers`エンティティセット内のインスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="4d431-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="4d431-117">Bipj は、 `PublishedBy`アソシエーションセット内`PublishedBy`のアソシエーションのインスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="4d431-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![セットの例を示すスクリーンショット。](./media/association-set-end/sets-example-association.gif)  
  
 <span data-ttu-id="4d431-119">[ADO.NET Entity Framework](./ef/index.md)は、概念スキーマ定義言語 ([CSDL](./ef/language-reference/csdl-specification.md)) と呼ばれる DSL を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="4d431-119">The [ADO.NET Entity Framework](./ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="4d431-120">次の CSDL は、上のダイアグラムの各アソシエーションに対して 1 つのアソシエーション セットを持つエンティティ コンテナーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="4d431-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="4d431-121">アソシエーション セット End はアソシエーション セット定義の一部として定義されています。</span><span class="sxs-lookup"><span data-stu-id="4d431-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="4d431-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d431-122">See also</span></span>

- [<span data-ttu-id="4d431-123">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="4d431-123">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="4d431-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="4d431-124">Entity Data Model</span></span>](entity-data-model.md)
