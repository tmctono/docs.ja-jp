---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: aace683b1a105445b5a3ba3de0a6a671859588b5
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937441"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="ce2f2-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="ce2f2-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="ce2f2-103">WCF Data Services (旧称 "ADO.NET Data Services" と呼ばれていた) は、 [Representational State Transfer (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)のセマンティクスを使用して、Web またはイントラネット上のデータを公開および使用するための Open Data Protocol (OData) を使用するサービスを作成できるようにする、.NET Framework のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the Open Data Protocol (OData) to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).</span></span> <span data-ttu-id="ce2f2-104">OData は、URI でアドレス指定できるリソースとしてデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="ce2f2-105">データへのアクセスやデータの変更には、HTTP の標準の動詞である GET、PUT、POST、および DELETE を使用します。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="ce2f2-106">OData は、 [Entity Data Model](../adonet/entity-data-model.md)のエンティティとリレーションシップの規則を使用して、アソシエーションによって関連付けられたエンティティのセットとしてリソースを公開します。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-106">OData uses the entity-relationship conventions of the [Entity Data Model](../adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="ce2f2-107">WCF Data Services は、OData プロトコルを使用してリソースのアドレス指定と更新を行います。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="ce2f2-108">このようにして、OData をサポートする任意のクライアントからこれらのサービスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="ce2f2-109">OData を使用すると、一般的な転送形式 (Atom、データを XML として交換および更新するための標準のセット)、および AJAX で幅広く使用されるテキストベースのデータ交換形式である JavaScript Object Notation (JSON) を使用して、リソースにデータを要求して書き込むことができます。プログラム.</span><span class="sxs-lookup"><span data-stu-id="ce2f2-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="ce2f2-110">WCF Data Services は、さまざまなソースから送信されたデータを OData フィードとして公開できます。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="ce2f2-111">Visual Studio tools を使用すると、ADO.NET Entity Framework データモデルを使用して、OData ベースのサービスを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="ce2f2-112">また、共通言語ランタイム (CLR) クラスに基づいて OData フィードを作成したり、遅延バインディングまたは型指定されていないデータを作成したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="ce2f2-113">WCF Data Services には、一般的な .NET Framework クライアントアプリケーション用と Silverlight ベースのアプリケーション用のクライアントライブラリのセットも含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="ce2f2-114">これらのクライアントライブラリは、.NET Framework や Silverlight などの環境から OData フィードにアクセスするときに、オブジェクトベースのプログラミングモデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="ce2f2-115">開始すべき場所</span><span class="sxs-lookup"><span data-stu-id="ce2f2-115">Where Should I Start?</span></span>

<span data-ttu-id="ce2f2-116">興味に応じて、次のトピックのいずれかで WCF Data Services の使用を開始することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="ce2f2-117">すぐに使用を開始する…</span><span class="sxs-lookup"><span data-stu-id="ce2f2-117">I want to jump right in...</span></span>

- [<span data-ttu-id="ce2f2-118">クイック スタート</span><span class="sxs-lookup"><span data-stu-id="ce2f2-118">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="ce2f2-119">はじめに</span><span class="sxs-lookup"><span data-stu-id="ce2f2-119">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="ce2f2-120">コードを表示するだけです...</span><span class="sxs-lookup"><span data-stu-id="ce2f2-120">Just show me some code...</span></span>

- [<span data-ttu-id="ce2f2-121">クイック スタート</span><span class="sxs-lookup"><span data-stu-id="ce2f2-121">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="ce2f2-122">方法: データ サービス クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="ce2f2-122">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="ce2f2-123">方法: Windows Presentation Foundation 要素にデータをバインドする</span><span class="sxs-lookup"><span data-stu-id="ce2f2-123">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="ce2f2-124">OData の詳細を知りたい...</span><span class="sxs-lookup"><span data-stu-id="ce2f2-124">I want to know more about OData...</span></span>

- [<span data-ttu-id="ce2f2-125">ホワイトペーパー: OData の概要</span><span class="sxs-lookup"><span data-stu-id="ce2f2-125">White paper: Introducing OData</span></span>](https://download.microsoft.com/download/E/5/A/E5A59052-EE48-4D64-897B-5F7C608165B8/IntroducingOData.pdf)
- [<span data-ttu-id="ce2f2-126">Open Data Protocol web サイト</span><span class="sxs-lookup"><span data-stu-id="ce2f2-126">Open Data Protocol website</span></span>](https://www.odata.org/)
- [<span data-ttu-id="ce2f2-127">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="ce2f2-127">OData: SDK</span></span>](https://www.odata.org/ecosystem/)

<span data-ttu-id="ce2f2-128">エンドツーエンドのサンプルを確認するには...</span><span class="sxs-lookup"><span data-stu-id="ce2f2-128">I want to see end-to-end samples...</span></span>

- <span data-ttu-id="ce2f2-129">[WCF Data Services クイックスタート](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span><span class="sxs-lookup"><span data-stu-id="ce2f2-129">[WCF Data Services Quickstart](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span></span>
- [<span data-ttu-id="ce2f2-130">OData SDK-サンプルコード</span><span class="sxs-lookup"><span data-stu-id="ce2f2-130">OData SDK - Sample Code</span></span>](https://www.odata.org/ecosystem/#sdk)

<span data-ttu-id="ce2f2-131">Visual Studio との統合について知りたい</span><span class="sxs-lookup"><span data-stu-id="ce2f2-131">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="ce2f2-132">データ サービス クライアント ライブラリの生成</span><span class="sxs-lookup"><span data-stu-id="ce2f2-132">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="ce2f2-133">データ サービスの作成</span><span class="sxs-lookup"><span data-stu-id="ce2f2-133">Creating the Data Service</span></span>](creating-the-data-service.md)

- [<span data-ttu-id="ce2f2-134">Entity Framework プロバイダー</span><span class="sxs-lookup"><span data-stu-id="ce2f2-134">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="ce2f2-135">何に使用できるかを知りたい</span><span class="sxs-lookup"><span data-stu-id="ce2f2-135">What can I do with it?</span></span>

- [<span data-ttu-id="ce2f2-136">概要</span><span class="sxs-lookup"><span data-stu-id="ce2f2-136">Overview</span></span>](wcf-data-services-overview.md)

- [<span data-ttu-id="ce2f2-137">アプリケーション シナリオ</span><span class="sxs-lookup"><span data-stu-id="ce2f2-137">Application Scenarios</span></span>](application-scenarios-wcf-data-services.md)

<span data-ttu-id="ce2f2-138">LINQ...</span><span class="sxs-lookup"><span data-stu-id="ce2f2-138">I want to use LINQ...</span></span>

- [<span data-ttu-id="ce2f2-139">データ サービスに対するクエリ</span><span class="sxs-lookup"><span data-stu-id="ce2f2-139">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="ce2f2-140">LINQ に関する留意点</span><span class="sxs-lookup"><span data-stu-id="ce2f2-140">LINQ Considerations</span></span>](linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="ce2f2-141">方法: データ サービス クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="ce2f2-141">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="ce2f2-142">まだいくつかの情報が必要です...</span><span class="sxs-lookup"><span data-stu-id="ce2f2-142">I still need some more information...</span></span>

- [<span data-ttu-id="ce2f2-143">WCF Data Services チームのブログ</span><span class="sxs-lookup"><span data-stu-id="ce2f2-143">WCF Data Services Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/astoriateam/)

- [<span data-ttu-id="ce2f2-144">リソース</span><span class="sxs-lookup"><span data-stu-id="ce2f2-144">Resources</span></span>](wcf-data-services-resources.md)

## <a name="in-this-section"></a><span data-ttu-id="ce2f2-145">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ce2f2-145">In This Section</span></span>

[<span data-ttu-id="ce2f2-146">概要</span><span class="sxs-lookup"><span data-stu-id="ce2f2-146">Overview</span></span>](wcf-data-services-overview.md)

<span data-ttu-id="ce2f2-147">WCF Data Services で使用できる機能の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-147">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="ce2f2-148">[WCF Data Services 5.0 の新機能](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="ce2f2-148">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="ce2f2-149">WCF Data Services の新機能と、新しい OData 機能のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-149">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="ce2f2-150">はじめに</span><span class="sxs-lookup"><span data-stu-id="ce2f2-150">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="ce2f2-151">WCF Data Services を使用して OData フィードを公開および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-151">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="ce2f2-152">WCF Data Services の定義</span><span class="sxs-lookup"><span data-stu-id="ce2f2-152">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)

<span data-ttu-id="ce2f2-153">OData フィードを公開するデータサービスを作成および構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-153">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="ce2f2-154">WCF Data Services クライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="ce2f2-154">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)

<span data-ttu-id="ce2f2-155">クライアントライブラリを使用して、.NET Framework クライアントアプリケーションから OData フィードを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ce2f2-155">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce2f2-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce2f2-156">See also</span></span>

- [<span data-ttu-id="ce2f2-157">Representational State Transfer (REST)</span><span class="sxs-lookup"><span data-stu-id="ce2f2-157">Representational State Transfer (REST)</span></span>](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
