---
title: アソシエーション End の多重度
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 151b15a6df021a25f6c3ecea00af147c6b7196ff
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185676"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="18408-102">アソシエーション End の多重度</span><span class="sxs-lookup"><span data-stu-id="18408-102">association end multiplicity</span></span>
<span data-ttu-id="18408-103">*アソシエーション end の多重度*の数を定義[エンティティ型](../../../../docs/framework/data/adonet/entity-type.md)の 1 つの end に存在できるインスタンス、[アソシエーション](../../../../docs/framework/data/adonet/association-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="18408-103">*Association end multiplicity* defines the number of [entity type](../../../../docs/framework/data/adonet/entity-type.md) instances that can be at one end of an [association](../../../../docs/framework/data/adonet/association-type.md).</span></span>  
  
 <span data-ttu-id="18408-104">アソシエーション End の多重度には、次のいずれかの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="18408-104">An association end multiplicity can have one of the following values:</span></span>  
  
-   <span data-ttu-id="18408-105">1 (1):その 1 つのエンティティ型のインスタンスは、アソシエーション end に存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="18408-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
-   <span data-ttu-id="18408-106">0 または 1 (0..1)。アソシエーション end に 0 個または 1 つのエンティティ型のインスタンスが存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="18408-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
-   <span data-ttu-id="18408-107">多数 (\*)。アソシエーション end に 0、1、または複数のエンティティ型のインスタンスが存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="18408-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="18408-108">アソシエーションは、多くの場合、そのアソシエーション End の多重度により特徴付けられます。</span><span class="sxs-lookup"><span data-stu-id="18408-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="18408-109">たとえば、アソシエーションの end が 1 つ (1) と多くの多重度である場合 (\*)、アソシエーションは一対多のアソシエーションと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="18408-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="18408-110">次の例で、`PublishedBy` アソシエーションは一対多のアソシエーションです (出版社が多くの書籍を出版し、書籍は 1 社の出版社により出版されます)。</span><span class="sxs-lookup"><span data-stu-id="18408-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="18408-111">`WrittenBy` アソシエーションは多対多のアソシエーションです (書籍の著者が複数の場合があり、著者は複数の書籍を執筆することができます)。</span><span class="sxs-lookup"><span data-stu-id="18408-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="18408-112">例</span><span class="sxs-lookup"><span data-stu-id="18408-112">Example</span></span>  
 <span data-ttu-id="18408-113">下のダイアグラムは、`PublishedBy` および `WrittenBy` という 2 つのアソシエーションの概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="18408-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="18408-114">
  `PublishedBy\` アソシエーションのアソシエーション End は `Book\` および `Publisher\` のエンティティ型です。</span><span class="sxs-lookup"><span data-stu-id="18408-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="18408-115">多重度、 `Publisher` end が 1 つ (1) との多重度、 `Book` end が多く (\*)。</span><span class="sxs-lookup"><span data-stu-id="18408-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 <span data-ttu-id="18408-116">![モデルの例](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="18408-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="18408-117">ADO.NET Entity Framework は概念スキーマ定義言語と呼ばれるドメイン固有言語 (DSL) を使用して ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="18408-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="18408-118">次の CSDL は、上のダイアグラムに示された `PublishedBy` アソシエーションを定義しています。</span><span class="sxs-lookup"><span data-stu-id="18408-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="18408-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="18408-119">See also</span></span>
- [<span data-ttu-id="18408-120">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="18408-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="18408-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="18408-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
