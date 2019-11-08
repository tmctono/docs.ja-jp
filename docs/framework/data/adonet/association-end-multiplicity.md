---
title: アソシエーション End の多重度
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 3f3d8ba9f7e68065024dd3efb599b847496740cd
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738571"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="1c5a3-102">アソシエーション End の多重度</span><span class="sxs-lookup"><span data-stu-id="1c5a3-102">association end multiplicity</span></span>
<span data-ttu-id="1c5a3-103">*アソシエーション end の多重度*は、[アソシエーション](association-type.md)の1つの end に存在できる[エンティティ型](entity-type.md)のインスタンスの数を定義します。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-103">*Association end multiplicity* defines the number of [entity type](entity-type.md) instances that can be at one end of an [association](association-type.md).</span></span>  
  
 <span data-ttu-id="1c5a3-104">アソシエーション End の多重度には、次のいずれかの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-104">An association end multiplicity can have one of the following values:</span></span>  
  
- <span data-ttu-id="1c5a3-105">1 (1): アソシエーション End に 1 つのエンティティ型のインスタンスが存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
- <span data-ttu-id="1c5a3-106">0 または 1 (0..1): アソシエーション End に 0 または 1 つのエンティティ型のインスタンスが存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
- <span data-ttu-id="1c5a3-107">many (\*): アソシエーション end に0個以上のエンティティ型のインスタンスが存在することを示します。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="1c5a3-108">アソシエーションは、多くの場合、そのアソシエーション End の多重度により特徴付けられます。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="1c5a3-109">たとえば、アソシエーションの end に多重度 1 (1) と多く (\*) がある場合、アソシエーションは一対多のアソシエーションと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="1c5a3-110">次の例で、`PublishedBy` アソシエーションは一対多のアソシエーションです (出版社が多くの書籍を出版し、書籍は 1 社の出版社により出版されます)。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="1c5a3-111">`WrittenBy` アソシエーションは多対多のアソシエーションです (書籍の著者が複数の場合があり、著者は複数の書籍を執筆することができます)。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c5a3-112">例</span><span class="sxs-lookup"><span data-stu-id="1c5a3-112">Example</span></span>  
 <span data-ttu-id="1c5a3-113">下のダイアグラムは、`PublishedBy` および `WrittenBy` という 2 つのアソシエーションの概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="1c5a3-114">`PublishedBy` アソシエーションのアソシエーション End は `Book` および `Publisher` のエンティティ型です。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="1c5a3-115">`Publisher` end の多重度は 1 (1) で、`Book` end の多重度は多数 (\*) です。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 ![3種類のエンティティを持つモデルの例](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="1c5a3-117">ADO.NET Entity Framework は、概念スキーマ定義言語 ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) と呼ばれるドメイン固有言語 (DSL) を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="1c5a3-118">次の CSDL は、上のダイアグラムに示された `PublishedBy` アソシエーションを定義しています。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="1c5a3-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c5a3-119">See also</span></span>

- [<span data-ttu-id="1c5a3-120">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="1c5a3-120">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="1c5a3-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="1c5a3-121">Entity Data Model</span></span>](entity-data-model.md)
