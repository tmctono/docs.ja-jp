---
title: エンティティ コンテナー
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: 95740fb9d8b357a4fa160af6fdafb139711283cd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795250"
---
# <a name="entity-container"></a><span data-ttu-id="44088-102">エンティティ コンテナー</span><span class="sxs-lookup"><span data-stu-id="44088-102">entity container</span></span>
<span data-ttu-id="44088-103">*エンティティコンテナー*は、[エンティティセット](entity-set.md)、[アソシエーションセット](association-set.md)、および[関数インポート](model-declared-function.md)の論理的なグループです。</span><span class="sxs-lookup"><span data-stu-id="44088-103">An *entity container* is a logical grouping of [entity sets](entity-set.md), [association sets](association-set.md), and [function imports](model-declared-function.md).</span></span>  
  
 <span data-ttu-id="44088-104">概念モデルで定義するエンティティ コンテナーは、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="44088-104">The following must be true of an entity container defined in a conceptual model:</span></span>  
  
- <span data-ttu-id="44088-105">1 つ以上のエンティティ コンテナーを各概念モデルに定義すること。</span><span class="sxs-lookup"><span data-stu-id="44088-105">At least one entity container must be defined in each conceptual model.</span></span>  
  
- <span data-ttu-id="44088-106">各概念モデル内のエンティティ コンテナー名が一意であること。</span><span class="sxs-lookup"><span data-stu-id="44088-106">The entity container must have a unique name within each conceptual model.</span></span>  
  
 <span data-ttu-id="44088-107">エンティティ コンテナーは、1 つ以上の名前空間に定義されたエンティティ型またはアソシエーションを使用するエンティティ セットまたはアソシエーション セットを定義できます。</span><span class="sxs-lookup"><span data-stu-id="44088-107">An entity container can define entity sets or association sets that use entity types or associations defined in one or more namespaces.</span></span> <span data-ttu-id="44088-108">詳細については[、Entity Data Model を参照してください。名前](entity-data-model-namespaces.md)空間。</span><span class="sxs-lookup"><span data-stu-id="44088-108">For more information, see [Entity Data Model: Namespaces](entity-data-model-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="44088-109">例</span><span class="sxs-lookup"><span data-stu-id="44088-109">Example</span></span>  
 <span data-ttu-id="44088-110">下のダイアグラムは、`Book`、`Publisher`、および `Author` という 3 つのエンティティ型の概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="44088-110">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  <span data-ttu-id="44088-111">詳細については、次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44088-111">See the next example for more information.</span></span>  
  
 ![3種類のエンティティを持つモデルの例](./media/entity-container/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="44088-113">ダイアグラムにはエンティティ コンテナー情報が示されていませんが、概念モデルにはエンティティ コンテナーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44088-113">Although the diagram does not convey entity container information, the conceptual model must define an entity container.</span></span> <span data-ttu-id="44088-114">[ADO.NET Entity Framework](./ef/index.md)は、概念スキーマ定義言語 ([CSDL](./ef/language-reference/csdl-specification.md)) と呼ばれる DSL を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="44088-114">The [ADO.NET Entity Framework](./ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="44088-115">次の CSDL は、上のダイアグラムに示された概念モデルのエンティティ コンテナーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="44088-115">The following CSDL defines an entity container for the conceptual model shown in the diagram above.</span></span> <span data-ttu-id="44088-116">エンティティ コンテナー名は XML 属性に定義されています。</span><span class="sxs-lookup"><span data-stu-id="44088-116">Note that the entity container name is defined in an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="44088-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="44088-117">See also</span></span>

- [<span data-ttu-id="44088-118">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="44088-118">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="44088-119">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="44088-119">Entity Data Model</span></span>](entity-data-model.md)
