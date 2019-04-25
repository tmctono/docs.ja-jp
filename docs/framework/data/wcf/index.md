---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 6910bfbc94f69292bb8c2a52bf3ebef8fcfb3a8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61876461"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="038db-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="038db-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="038db-103">(旧称"ADO.NET Data Services")、WCF Data Services を使用するサービスを作成することができます、.NET Framework のコンポーネントである、[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]公開およびのセマンティクスを使用して、Web またはイントラネット上のデータを使用する[(REST) representational state transfer](https://go.microsoft.com/fwlink/?LinkId=113919)します。</span><span class="sxs-lookup"><span data-stu-id="038db-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919).</span></span> <span data-ttu-id="038db-104">OData は、URI でアドレス指定できるリソースとしてデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="038db-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="038db-105">標準的な HTTP 動詞である GET、PUT、POST、および DELETE を使用してデータにアクセスし、変更できます。</span><span class="sxs-lookup"><span data-stu-id="038db-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="038db-106">OData エンティティとリレーションシップの規則を使用して、 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)アソシエーションによって関連付けられたエンティティのセットとしてリソースを公開します。</span><span class="sxs-lookup"><span data-stu-id="038db-106">OData uses the entity-relationship conventions of the [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="038db-107">WCF Data Services は、アドレス指定およびリソースを更新するための OData プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="038db-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="038db-108">この方法では、これらのサービスを OData をサポートする任意のクライアントからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="038db-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="038db-109">OData では要求をリソースに知られている転送形式を使用してデータを書き込むことができます。Atom、交換および JavaScript Object Notation (JSON) と、XML としてデータを更新するための標準のセット AJAX アプリケーションで広く使用されて、テキスト ベースのデータ交換形式。</span><span class="sxs-lookup"><span data-stu-id="038db-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="038db-110">WCF Data Services は OData フィードとしてさまざまなソースから取得したデータを公開できます。</span><span class="sxs-lookup"><span data-stu-id="038db-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="038db-111">Visual Studio tools を容易に ADO.NET Entity Framework データ モデルを使用して、OData ベースのサービスを作成するためです。</span><span class="sxs-lookup"><span data-stu-id="038db-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="038db-112">共通言語ランタイム (CLR) クラスとも遅延バインディングまたは型指定されていないデータに基づいて OData フィードを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="038db-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="038db-113">WCF Data Services には、一般的な .NET Framework クライアント アプリケーションと Silverlight ベース アプリケーション用のクライアント ライブラリのセットも含まれています。</span><span class="sxs-lookup"><span data-stu-id="038db-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="038db-114">これらのクライアント ライブラリは、.NET Framework や Silverlight などの環境から OData フィードにアクセスするときに、オブジェクト ベースのプログラミング モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="038db-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="038db-115">開始すべき場所</span><span class="sxs-lookup"><span data-stu-id="038db-115">Where Should I Start?</span></span>

<span data-ttu-id="038db-116">ご自分の興味に応じて、次のトピックのいずれかで WCF Data Services の概要を検討してください。</span><span class="sxs-lookup"><span data-stu-id="038db-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="038db-117">すぐに使用を開始する…</span><span class="sxs-lookup"><span data-stu-id="038db-117">I want to jump right in...</span></span>

- [<span data-ttu-id="038db-118">クイック スタート</span><span class="sxs-lookup"><span data-stu-id="038db-118">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

- [<span data-ttu-id="038db-119">はじめに</span><span class="sxs-lookup"><span data-stu-id="038db-119">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

- [<span data-ttu-id="038db-120">Silverlight クイックスタート</span><span class="sxs-lookup"><span data-stu-id="038db-120">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

- [<span data-ttu-id="038db-121">Windows Phone 開発用の Silverlight クイック スタート</span><span class="sxs-lookup"><span data-stu-id="038db-121">Silverlight Quickstart for Windows Phone Development</span></span>](https://go.microsoft.com/fwlink/?LinkID=214535)

<span data-ttu-id="038db-122">だけ私にいくつかのコードを表示してください.</span><span class="sxs-lookup"><span data-stu-id="038db-122">Just show me some code...</span></span>

- [<span data-ttu-id="038db-123">クイック スタート</span><span class="sxs-lookup"><span data-stu-id="038db-123">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

- [<span data-ttu-id="038db-124">方法: データ サービス クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="038db-124">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="038db-125">方法: Windows Presentation Foundation 要素にデータをバインドします。</span><span class="sxs-lookup"><span data-stu-id="038db-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="038db-126">OData の詳細を理解する.</span><span class="sxs-lookup"><span data-stu-id="038db-126">I want to know more about OData...</span></span>

- [<span data-ttu-id="038db-127">ホワイト ペーパー:OData の概要</span><span class="sxs-lookup"><span data-stu-id="038db-127">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

- [<span data-ttu-id="038db-128">Open Data Protocol Web サイト</span><span class="sxs-lookup"><span data-stu-id="038db-128">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

- [<span data-ttu-id="038db-129">OData:SDK</span><span class="sxs-lookup"><span data-stu-id="038db-129">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

- [<span data-ttu-id="038db-130">OData:よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="038db-130">OData: Frequently Asked Questions</span></span>](https://go.microsoft.com/fwlink/?LinkId=185867)

<span data-ttu-id="038db-131">いくつかのビデオを視聴する.</span><span class="sxs-lookup"><span data-stu-id="038db-131">I want to watch some videos...</span></span>

- [<span data-ttu-id="038db-132">WCF Data Services のビギナーズ ガイド</span><span class="sxs-lookup"><span data-stu-id="038db-132">Beginner's Guide to WCF Data Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=220864)

- [<span data-ttu-id="038db-133">WCF Data Services 開発者用ビデオ</span><span class="sxs-lookup"><span data-stu-id="038db-133">WCF Data Services Developer Videos</span></span>](https://go.microsoft.com/fwlink/?LinkId=220861)

- [<span data-ttu-id="038db-134">OData:開発者 Web サイト</span><span class="sxs-lookup"><span data-stu-id="038db-134">OData: Developers Web site</span></span>](https://go.microsoft.com/fwlink/?LinkId=185866)

<span data-ttu-id="038db-135">エンド ツー エンドのサンプルを表示する.</span><span class="sxs-lookup"><span data-stu-id="038db-135">I want to see end-to-end samples...</span></span>

- [<span data-ttu-id="038db-136">MSDN サンプル ギャラリーの WCF Data Services ドキュメントのサンプル</span><span class="sxs-lookup"><span data-stu-id="038db-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkID=220865)

- [<span data-ttu-id="038db-137">MSDN サンプル ギャラリーのその他の WCF Data Services サンプル</span><span class="sxs-lookup"><span data-stu-id="038db-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkId=220866)

- [<span data-ttu-id="038db-138">OData:SDK</span><span class="sxs-lookup"><span data-stu-id="038db-138">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

<span data-ttu-id="038db-139">Visual Studio との統合について知りたい</span><span class="sxs-lookup"><span data-stu-id="038db-139">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="038db-140">データ サービス クライアント ライブラリの生成</span><span class="sxs-lookup"><span data-stu-id="038db-140">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="038db-141">データ サービスの作成</span><span class="sxs-lookup"><span data-stu-id="038db-141">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

- [<span data-ttu-id="038db-142">Entity Framework プロバイダー</span><span class="sxs-lookup"><span data-stu-id="038db-142">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="038db-143">何に使用できるかを知りたい</span><span class="sxs-lookup"><span data-stu-id="038db-143">What can I do with it?</span></span>

- [<span data-ttu-id="038db-144">概要</span><span class="sxs-lookup"><span data-stu-id="038db-144">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

- [<span data-ttu-id="038db-145">ホワイト ペーパー:OData の概要</span><span class="sxs-lookup"><span data-stu-id="038db-145">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

- [<span data-ttu-id="038db-146">アプリケーション シナリオ</span><span class="sxs-lookup"><span data-stu-id="038db-146">Application Scenarios</span></span>](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)

<span data-ttu-id="038db-147">Silverlight を使用する.</span><span class="sxs-lookup"><span data-stu-id="038db-147">I want to use Silverlight...</span></span>

- [<span data-ttu-id="038db-148">Silverlight クイックスタート</span><span class="sxs-lookup"><span data-stu-id="038db-148">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

- [<span data-ttu-id="038db-149">WCF Data Services (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="038db-149">WCF Data Services (Silverlight)</span></span>](https://go.microsoft.com/fwlink/?LinkID=143149)

- [<span data-ttu-id="038db-150">Silverlight について</span><span class="sxs-lookup"><span data-stu-id="038db-150">Getting Started with Silverlight</span></span>](https://go.microsoft.com/fwlink/?LinkId=148366)

<span data-ttu-id="038db-151">LINQ を使用する.</span><span class="sxs-lookup"><span data-stu-id="038db-151">I want to use LINQ...</span></span>

- [<span data-ttu-id="038db-152">データ サービスに対するクエリ</span><span class="sxs-lookup"><span data-stu-id="038db-152">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="038db-153">LINQ に関する留意点</span><span class="sxs-lookup"><span data-stu-id="038db-153">LINQ Considerations</span></span>](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="038db-154">方法: データ サービス クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="038db-154">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="038db-155">詳細についてはいくつか必要があります.</span><span class="sxs-lookup"><span data-stu-id="038db-155">I still need some more information...</span></span>

- [<span data-ttu-id="038db-156">WCF Data Services チームのブログ</span><span class="sxs-lookup"><span data-stu-id="038db-156">WCF Data Services Team Blog</span></span>](https://go.microsoft.com/fwlink/?LinkID=150511)

- [<span data-ttu-id="038db-157">リソース</span><span class="sxs-lookup"><span data-stu-id="038db-157">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)

- [<span data-ttu-id="038db-158">WCF Data Services デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="038db-158">WCF Data Services Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=220868)

- [<span data-ttu-id="038db-159">Open Data Protocol Web サイト</span><span class="sxs-lookup"><span data-stu-id="038db-159">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a><span data-ttu-id="038db-160">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="038db-160">In This Section</span></span>

[<span data-ttu-id="038db-161">概要</span><span class="sxs-lookup"><span data-stu-id="038db-161">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

<span data-ttu-id="038db-162">WCF Data Services で利用できる機能と機能の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="038db-162">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="038db-163">[WCF Data Services 5.0 の新機能新機能](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="038db-163">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="038db-164">WCF Data Services と OData の新機能のサポートで新しい機能をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="038db-164">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="038db-165">はじめに</span><span class="sxs-lookup"><span data-stu-id="038db-165">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

<span data-ttu-id="038db-166">公開および WCF Data Services を使用して OData フィードを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="038db-166">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="038db-167">WCF Data Services の定義</span><span class="sxs-lookup"><span data-stu-id="038db-167">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)

<span data-ttu-id="038db-168">作成して、OData フィードを公開するデータ サービスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="038db-168">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="038db-169">WCF Data Services クライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="038db-169">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

<span data-ttu-id="038db-170">クライアント ライブラリを使用して、.NET Framework クライアント アプリケーションから OData フィードを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="038db-170">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="038db-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="038db-171">See also</span></span>

- [<span data-ttu-id="038db-172">Representational State Transfer (REST)</span><span class="sxs-lookup"><span data-stu-id="038db-172">Representational State Transfer (REST)</span></span>](https://go.microsoft.com/fwlink/?LinkId=113919)
