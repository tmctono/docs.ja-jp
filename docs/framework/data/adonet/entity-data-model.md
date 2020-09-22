---
title: エンティティ データ モデル
description: Entity Data Model では、格納される形式に関係なくデータ構造が記述されます。これにより、さまざまな形式でデータを格納することが原因で生じる問題に対処できます。
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: d32207e3a9dd35d2d8f8990bcbbd35e38d21d8bb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557620"
---
# <a name="entity-data-model"></a><span data-ttu-id="35558-103">エンティティ データ モデル</span><span class="sxs-lookup"><span data-stu-id="35558-103">Entity Data Model</span></span>
<span data-ttu-id="35558-104">Entity Data Model (EDM) は、格納される形式に関係なく、データ構造を記述する一連の概念です。</span><span class="sxs-lookup"><span data-stu-id="35558-104">The Entity Data Model (EDM) is a set of concepts that describe the structure of data, regardless of its stored form.</span></span> <span data-ttu-id="35558-105">EDM は、1976 年に Peter Chen により記述されたエンティティ リレーションシップ モデルを取り入れていますが、これを土台にして利用法が拡張されています。</span><span class="sxs-lookup"><span data-stu-id="35558-105">The EDM borrows from the Entity-Relationship Model described by Peter Chen in 1976, but it also builds on the Entity-Relationship Model and extends its traditional uses.</span></span>  
  
 <span data-ttu-id="35558-106">EDM は、データを多くの形式で格納する場合につきまとう問題に対応しています。</span><span class="sxs-lookup"><span data-stu-id="35558-106">The EDM addresses the challenges that arise from having data stored in many forms.</span></span> <span data-ttu-id="35558-107">たとえば、データをリレーショナル データベース、テキスト ファイル、XML ファイル、スプレッドシート、およびレポートに格納している企業について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="35558-107">For example, consider a business that stores data in relational databases, text files, XML files, spreadsheets, and reports.</span></span> <span data-ttu-id="35558-108">この状況は、データ モデリング、アプリケーション設計、データ アクセスに深刻な問題を提示しています。</span><span class="sxs-lookup"><span data-stu-id="35558-108">This presents significant challenges in data modeling, application design, and data access.</span></span> <span data-ttu-id="35558-109">データ指向のアプリケーションを設計する場合、データ アクセス、ストレージ、およびスケーラビリティの効率性を損なうことなく、効率的で保守性に優れたコードを作成することが問題になります。</span><span class="sxs-lookup"><span data-stu-id="35558-109">When designing a data-oriented application, the challenge is to write efficient and maintainable code without sacrificing efficient data access, storage, and scalability.</span></span> <span data-ttu-id="35558-110">データがリレーショナル構造の場合は、データ アクセス、ストレージ、およびスケーラビリティの効率性が非常に高くなるものの、効率的で保守性に優れたコードを書くことが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="35558-110">When data has a relational structure, data access, storage, and scalability are very efficient, but writing efficient and maintainable code becomes more difficult.</span></span> <span data-ttu-id="35558-111">データがオブジェクト構造の場合は、これが反対になります。効率的で保守性に優れたコードを作成しやすくなる一方で、データ アクセス、ストレージ、およびスケーラビリティの効率性が損なわれます。</span><span class="sxs-lookup"><span data-stu-id="35558-111">When data has an object structure, the trade-offs are reversed: Writing efficient and maintainable code comes at the cost of efficient data access, storage, and scalability.</span></span> <span data-ttu-id="35558-112">これらの要因の間で適切なバランスを取れる場合でも、データを 1 つの形式から別の形式に移動する際に新しい問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="35558-112">Even if the right balance between these trade-offs can be found, new challenges arise when data is moved from one form to another.</span></span> <span data-ttu-id="35558-113">Entity Data Model は、ストレージ スキーマに依存しないエンティティとリレーションシップでデータ構造を記述することで、これらの問題に対応しています。</span><span class="sxs-lookup"><span data-stu-id="35558-113">The Entity Data Model addresses these challenges by describing the structure of data in terms of entities and relationships that are independent of any storage schema.</span></span> <span data-ttu-id="35558-114">このため、アプリケーションの設計と開発でデータの格納形式が問題になりません。</span><span class="sxs-lookup"><span data-stu-id="35558-114">This makes the stored form of data irrelevant to application design and development.</span></span> <span data-ttu-id="35558-115">さらに、エンティティおよびリレーションシップによりアプリケーションで使用されるデータ構造 (格納形式ではなく) が記述されるため、アプリケーションの進化に伴ってこれらを進化させることができます。</span><span class="sxs-lookup"><span data-stu-id="35558-115">And, because entities and relationships describe the structure of data as it is used in an application (not its stored form), they can evolve as an application evolves.</span></span>  
  
 <span data-ttu-id="35558-116">`conceptual model` は、データ構造をエンティティおよびリレーションシップとして表現したもので、一般的には、EDM の概念を実装するドメイン固有言語 (DSL) で記述されます。</span><span class="sxs-lookup"><span data-stu-id="35558-116">A `conceptual model` is a specific representation of the structure of data as entities and relationships, and is generally defined in a domain-specific language (DSL) that implements the concepts of the EDM.</span></span> <span data-ttu-id="35558-117">[概念スキーマ定義言語 (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec) もこのようなドメイン固有言語の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="35558-117">[Conceptual schema definition language (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec) is an example of such a domain-specific language.</span></span> <span data-ttu-id="35558-118">概念モデルで記述されるエンティティおよびリレーションシップは、アプリケーションにおけるオブジェクトとアソシエーションの抽象化と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="35558-118">Entities and relationships described in a conceptual model can be thought of as abstractions of objects and associations in an application.</span></span> <span data-ttu-id="35558-119">これにより開発者は、ストレージ スキーマを気にすることなく概念モデルに集中でき、効率的で保守性に優れたコードを書けるようになります。</span><span class="sxs-lookup"><span data-stu-id="35558-119">This allows developers to focus on the conceptual model without concern for the storage schema, and allows them to write code with efficiency and maintainability in mind.</span></span> <span data-ttu-id="35558-120">同時にストレージ スキーマの設計者は、データ アクセス、ストレージ、およびスケーラビリティの効率性に集中できます。</span><span class="sxs-lookup"><span data-stu-id="35558-120">Meanwhile storage schema designers can focus on the efficiency of data access, storage, and scalability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35558-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="35558-121">In This Section</span></span>  
 <span data-ttu-id="35558-122">このセクションのトピックでは、Entity Data Model の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="35558-122">Topics in this section describe the concepts of the Entity Data Model.</span></span> <span data-ttu-id="35558-123">EDM を実装する DSL には、ここで解説した概念を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="35558-123">Any DSL that implements the EDM should include the concepts described here.</span></span> <span data-ttu-id="35558-124">[ADO.NET Entity Framework](./ef/index.md) では CSDL を使用して概念モデルを定義することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="35558-124">Note that the [ADO.NET Entity Framework](./ef/index.md) uses CSDL to define conceptual models.</span></span> <span data-ttu-id="35558-125">詳細については、「 [CSDL Specification](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35558-125">For more information, see [CSDL Specification](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).</span></span>  
  
 [<span data-ttu-id="35558-126">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="35558-126">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)  
  
 [<span data-ttu-id="35558-127">Entity Data Model: 名前空間</span><span class="sxs-lookup"><span data-stu-id="35558-127">Entity Data Model: Namespaces</span></span>](entity-data-model-namespaces.md)  
  
 [<span data-ttu-id="35558-128">Entity Data Model: プリミティブ データ型</span><span class="sxs-lookup"><span data-stu-id="35558-128">Entity Data Model: Primitive Data Types</span></span>](entity-data-model-primitive-data-types.md)  
  
 [<span data-ttu-id="35558-129">Entity Data Model: 継承</span><span class="sxs-lookup"><span data-stu-id="35558-129">Entity Data Model: Inheritance</span></span>](entity-data-model-inheritance.md)  
  
 [<span data-ttu-id="35558-130">アソシエーション End</span><span class="sxs-lookup"><span data-stu-id="35558-130">association end</span></span>](association-end.md)  
  
 [<span data-ttu-id="35558-131">アソシエーション End の多重度</span><span class="sxs-lookup"><span data-stu-id="35558-131">association end multiplicity</span></span>](association-end-multiplicity.md)  
  
 [<span data-ttu-id="35558-132">アソシエーション セット</span><span class="sxs-lookup"><span data-stu-id="35558-132">association set</span></span>](association-set.md)  
  
 [<span data-ttu-id="35558-133">アソシエーション セット End</span><span class="sxs-lookup"><span data-stu-id="35558-133">association set end</span></span>](association-set-end.md)  
  
 [<span data-ttu-id="35558-134">アソシエーション型</span><span class="sxs-lookup"><span data-stu-id="35558-134">association type</span></span>](association-type.md)  
  
 [<span data-ttu-id="35558-135">複合型</span><span class="sxs-lookup"><span data-stu-id="35558-135">complex type</span></span>](complex-type.md)  
  
 [<span data-ttu-id="35558-136">エンティティ コンテナー</span><span class="sxs-lookup"><span data-stu-id="35558-136">entity container</span></span>](entity-container.md)  
  
 [<span data-ttu-id="35558-137">エンティティ キー</span><span class="sxs-lookup"><span data-stu-id="35558-137">entity key</span></span>](entity-key.md)  
  
 [<span data-ttu-id="35558-138">エンティティ セット</span><span class="sxs-lookup"><span data-stu-id="35558-138">entity set</span></span>](entity-set.md)  
  
 [<span data-ttu-id="35558-139">エンティティ型</span><span class="sxs-lookup"><span data-stu-id="35558-139">entity type</span></span>](entity-type.md)  
  
 [<span data-ttu-id="35558-140">facet</span><span class="sxs-lookup"><span data-stu-id="35558-140">facet</span></span>](facet.md)  
  
 [<span data-ttu-id="35558-141">外部キーのプロパティ</span><span class="sxs-lookup"><span data-stu-id="35558-141">foreign key property</span></span>](foreign-key-property.md)  
  
 [<span data-ttu-id="35558-142">モデル宣言関数</span><span class="sxs-lookup"><span data-stu-id="35558-142">model-declared function</span></span>](model-declared-function.md)  
  
 [<span data-ttu-id="35558-143">モデル定義関数</span><span class="sxs-lookup"><span data-stu-id="35558-143">model-defined function</span></span>](model-defined-function.md)  
  
 [<span data-ttu-id="35558-144">ナビゲーション プロパティ</span><span class="sxs-lookup"><span data-stu-id="35558-144">navigation property</span></span>](navigation-property.md)  
  
 [<span data-ttu-id="35558-145">プロパティ</span><span class="sxs-lookup"><span data-stu-id="35558-145">property</span></span>](property.md)  
  
 [<span data-ttu-id="35558-146">参照整合性制約</span><span class="sxs-lookup"><span data-stu-id="35558-146">referential integrity constraint</span></span>](referential-integrity-constraint.md)  
  
## <a name="see-also"></a><span data-ttu-id="35558-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="35558-147">See also</span></span>

- <span data-ttu-id="35558-148">[ADO.NET Entity Data Model ツール](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="35558-148">[ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="35558-149">[.edmx ファイルの概要](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="35558-149">[.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="35558-150">CSDL 仕様</span><span class="sxs-lookup"><span data-stu-id="35558-150">CSDL Specification</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
