---
title: Entity Data Model
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: 1742b04d0e3d8387e990d40d832e355dd15c4311
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783959"
---
# <a name="entity-data-model"></a><span data-ttu-id="1e0ec-102">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="1e0ec-102">Entity Data Model</span></span>
<span data-ttu-id="1e0ec-103">Entity Data Model (EDM) は、格納される形式に関係なく、データ構造を記述する一連の概念です。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-103">The Entity Data Model (EDM) is a set of concepts that describe the structure of data, regardless of its stored form.</span></span> <span data-ttu-id="1e0ec-104">EDM は、1976 年に Peter Chen により記述されたエンティティ リレーションシップ モデルを取り入れていますが、これを土台にして利用法が拡張されています。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-104">The EDM borrows from the Entity-Relationship Model described by Peter Chen in 1976, but it also builds on the Entity-Relationship Model and extends its traditional uses.</span></span>  
  
 <span data-ttu-id="1e0ec-105">EDM は、データを多くの形式で格納する場合につきまとう問題に対応しています。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-105">The EDM addresses the challenges that arise from having data stored in many forms.</span></span> <span data-ttu-id="1e0ec-106">たとえば、データをリレーショナル データベース、テキスト ファイル、XML ファイル、スプレッドシート、およびレポートに格納している企業について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-106">For example, consider a business that stores data in relational databases, text files, XML files, spreadsheets, and reports.</span></span> <span data-ttu-id="1e0ec-107">この状況は、データ モデリング、アプリケーション設計、データ アクセスに深刻な問題を提示しています。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-107">This presents significant challenges in data modeling, application design, and data access.</span></span> <span data-ttu-id="1e0ec-108">データ指向のアプリケーションを設計する場合、データ アクセス、ストレージ、およびスケーラビリティの効率性を損なうことなく、効率的で保守性に優れたコードを作成することが問題になります。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-108">When designing a data-oriented application, the challenge is to write efficient and maintainable code without sacrificing efficient data access, storage, and scalability.</span></span> <span data-ttu-id="1e0ec-109">データがリレーショナル構造の場合は、データ アクセス、ストレージ、およびスケーラビリティの効率性が非常に高くなるものの、効率的で保守性に優れたコードを書くことが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-109">When data has a relational structure, data access, storage, and scalability are very efficient, but writing efficient and maintainable code becomes more difficult.</span></span> <span data-ttu-id="1e0ec-110">データにオブジェクト構造がある場合、トレードオフは逆になります。効率的で保守性に優れたコードを作成することは、効率的なデータアクセス、ストレージ、およびスケーラビリティのコストを伴います。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-110">When data has an object structure, the trade-offs are reversed: Writing efficient and maintainable code comes at the cost of efficient data access, storage, and scalability.</span></span> <span data-ttu-id="1e0ec-111">これらの要因の間で適切なバランスを取れる場合でも、データを 1 つの形式から別の形式に移動する際に新しい問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-111">Even if the right balance between these trade-offs can be found, new challenges arise when data is moved from one form to another.</span></span> <span data-ttu-id="1e0ec-112">Entity Data Model は、ストレージ スキーマに依存しないエンティティとリレーションシップでデータ構造を記述することで、これらの問題に対応しています。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-112">The Entity Data Model addresses these challenges by describing the structure of data in terms of entities and relationships that are independent of any storage schema.</span></span> <span data-ttu-id="1e0ec-113">このため、アプリケーションの設計と開発でデータの格納形式が問題になりません。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-113">This makes the stored form of data irrelevant to application design and development.</span></span> <span data-ttu-id="1e0ec-114">さらに、エンティティおよびリレーションシップによりアプリケーションで使用されるデータ構造 (格納形式ではなく) が記述されるため、アプリケーションの進化に伴ってこれらを進化させることができます。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-114">And, because entities and relationships describe the structure of data as it is used in an application (not its stored form), they can evolve as an application evolves.</span></span>  
  
 <span data-ttu-id="1e0ec-115">`conceptual model` は、データ構造をエンティティおよびリレーションシップとして表現したもので、一般的には、EDM の概念を実装するドメイン固有言語 (DSL) で記述されます。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-115">A `conceptual model` is a specific representation of the structure of data as entities and relationships, and is generally defined in a domain-specific language (DSL) that implements the concepts of the EDM.</span></span> <span data-ttu-id="1e0ec-116">[概念スキーマ定義言語 (CSDL)](./ef/language-reference/csdl-specification.md)は、このようなドメイン固有言語の一例です。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-116">[Conceptual schema definition language (CSDL)](./ef/language-reference/csdl-specification.md) is an example of such a domain-specific language.</span></span> <span data-ttu-id="1e0ec-117">概念モデルで記述されるエンティティおよびリレーションシップは、アプリケーションにおけるオブジェクトとアソシエーションの抽象化と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-117">Entities and relationships described in a conceptual model can be thought of as abstractions of objects and associations in an application.</span></span> <span data-ttu-id="1e0ec-118">これにより開発者は、ストレージ スキーマを気にすることなく概念モデルに集中でき、効率的で保守性に優れたコードを書けるようになります。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-118">This allows developers to focus on the conceptual model without concern for the storage schema, and allows them to write code with efficiency and maintainability in mind.</span></span> <span data-ttu-id="1e0ec-119">同時にストレージ スキーマの設計者は、データ アクセス、ストレージ、およびスケーラビリティの効率性に集中できます。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-119">Meanwhile storage schema designers can focus on the efficiency of data access, storage, and scalability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e0ec-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1e0ec-120">In This Section</span></span>  
 <span data-ttu-id="1e0ec-121">このセクションのトピックでは、Entity Data Model の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-121">Topics in this section describe the concepts of the Entity Data Model.</span></span> <span data-ttu-id="1e0ec-122">EDM を実装する DSL には、ここで解説した概念を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-122">Any DSL that implements the EDM should include the concepts described here.</span></span> <span data-ttu-id="1e0ec-123">[ADO.NET Entity Framework](./ef/index.md)は CSDL を使用して概念モデルを定義することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-123">Note that the [ADO.NET Entity Framework](./ef/index.md) uses CSDL to define conceptual models.</span></span> <span data-ttu-id="1e0ec-124">詳細については、「 [CSDL Specification](./ef/language-reference/csdl-specification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e0ec-124">For more information, see [CSDL Specification](./ef/language-reference/csdl-specification.md).</span></span>  
  
 [<span data-ttu-id="1e0ec-125">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="1e0ec-125">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)  
  
 [<span data-ttu-id="1e0ec-126">Entity Data Model:空間</span><span class="sxs-lookup"><span data-stu-id="1e0ec-126">Entity Data Model: Namespaces</span></span>](entity-data-model-namespaces.md)  
  
 [<span data-ttu-id="1e0ec-127">Entity Data Model:プリミティブデータ型</span><span class="sxs-lookup"><span data-stu-id="1e0ec-127">Entity Data Model: Primitive Data Types</span></span>](entity-data-model-primitive-data-types.md)  
  
 [<span data-ttu-id="1e0ec-128">Entity Data Model:おける</span><span class="sxs-lookup"><span data-stu-id="1e0ec-128">Entity Data Model: Inheritance</span></span>](entity-data-model-inheritance.md)  
  
 [<span data-ttu-id="1e0ec-129">アソシエーション End</span><span class="sxs-lookup"><span data-stu-id="1e0ec-129">association end</span></span>](association-end.md)  
  
 [<span data-ttu-id="1e0ec-130">アソシエーション End の多重度</span><span class="sxs-lookup"><span data-stu-id="1e0ec-130">association end multiplicity</span></span>](association-end-multiplicity.md)  
  
 [<span data-ttu-id="1e0ec-131">アソシエーション セット</span><span class="sxs-lookup"><span data-stu-id="1e0ec-131">association set</span></span>](association-set.md)  
  
 [<span data-ttu-id="1e0ec-132">アソシエーション セット End</span><span class="sxs-lookup"><span data-stu-id="1e0ec-132">association set end</span></span>](association-set-end.md)  
  
 [<span data-ttu-id="1e0ec-133">アソシエーション型</span><span class="sxs-lookup"><span data-stu-id="1e0ec-133">association type</span></span>](association-type.md)  
  
 [<span data-ttu-id="1e0ec-134">複合型</span><span class="sxs-lookup"><span data-stu-id="1e0ec-134">complex type</span></span>](complex-type.md)  
  
 [<span data-ttu-id="1e0ec-135">エンティティ コンテナー</span><span class="sxs-lookup"><span data-stu-id="1e0ec-135">entity container</span></span>](entity-container.md)  
  
 [<span data-ttu-id="1e0ec-136">エンティティ キー</span><span class="sxs-lookup"><span data-stu-id="1e0ec-136">entity key</span></span>](entity-key.md)  
  
 [<span data-ttu-id="1e0ec-137">エンティティ セット</span><span class="sxs-lookup"><span data-stu-id="1e0ec-137">entity set</span></span>](entity-set.md)  
  
 [<span data-ttu-id="1e0ec-138">エンティティ型</span><span class="sxs-lookup"><span data-stu-id="1e0ec-138">entity type</span></span>](entity-type.md)  
  
 [<span data-ttu-id="1e0ec-139">facet</span><span class="sxs-lookup"><span data-stu-id="1e0ec-139">facet</span></span>](facet.md)  
  
 [<span data-ttu-id="1e0ec-140">外部キーのプロパティ</span><span class="sxs-lookup"><span data-stu-id="1e0ec-140">foreign key property</span></span>](foreign-key-property.md)  
  
 [<span data-ttu-id="1e0ec-141">モデル宣言関数</span><span class="sxs-lookup"><span data-stu-id="1e0ec-141">model-declared function</span></span>](model-declared-function.md)  
  
 [<span data-ttu-id="1e0ec-142">モデル定義関数</span><span class="sxs-lookup"><span data-stu-id="1e0ec-142">model-defined function</span></span>](model-defined-function.md)  
  
 [<span data-ttu-id="1e0ec-143">ナビゲーション プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e0ec-143">navigation property</span></span>](navigation-property.md)  
  
 [<span data-ttu-id="1e0ec-144">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e0ec-144">property</span></span>](property.md)  
  
 [<span data-ttu-id="1e0ec-145">参照整合性制約</span><span class="sxs-lookup"><span data-stu-id="1e0ec-145">referential integrity constraint</span></span>](referential-integrity-constraint.md)  
  
## <a name="see-also"></a><span data-ttu-id="1e0ec-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e0ec-146">See also</span></span>

- <span data-ttu-id="1e0ec-147">[ADO.NET Entity Data Model ツール](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1e0ec-147">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="1e0ec-148">[.edmx ファイルの概要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1e0ec-148">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="1e0ec-149">CSDL 仕様</span><span class="sxs-lookup"><span data-stu-id="1e0ec-149">CSDL Specification</span></span>](./ef/language-reference/csdl-specification.md)
