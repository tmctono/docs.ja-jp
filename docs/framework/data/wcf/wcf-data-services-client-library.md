---
title: WCF Data Services クライアント ライブラリ
description: WCF Data Services クライアント ライブラリを使用して .NET Framework クライアント アプリケーションからデータにアクセスしてデータを変更する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: d1554dd149e3d447a67cd2ef41aef9042e14fd06
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204360"
---
# <a name="wcf-data-services-client-library"></a><span data-ttu-id="ca585-103">WCF Data Services クライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="ca585-103">WCF Data Services Client Library</span></span>

<span data-ttu-id="ca585-104">HTTP 要求を送信し、データ サービスが返す Open Data Protocol (OData) フィードを処理できるのであれば、どのようなアプリケーションでも OData ベースのデータ サービスと対話できます。</span><span class="sxs-lookup"><span data-stu-id="ca585-104">Any application can interact with an Open Data Protocol (OData)-based data service if it can send an HTTP request and process the OData feed that a data service returns.</span></span> <span data-ttu-id="ca585-105">この相互運用性によって、広範な Web 対応アプリケーションから OData ベースのサービスにアクセスすることが可能になります。</span><span class="sxs-lookup"><span data-stu-id="ca585-105">This interoperability enables you to access OData-based services from a broad range of Web-enabled applications.</span></span> <span data-ttu-id="ca585-106">WCF Data Services には、.NET Framework ベースのアプリケーションまたは Silverlight ベースのアプリケーションから OData フィードを使用する際のプログラミング エクスペリエンスを向上させるクライアント ライブラリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ca585-106">WCF Data Services includes client libraries that provide a richer programming experience when you consume OData feeds from .NET Framework or Silverlight-based applications.</span></span>  
  
 <span data-ttu-id="ca585-107">クライアント ライブラリの 2 つの主要なクラスは、<xref:System.Data.Services.Client.DataServiceContext> クラスと <xref:System.Data.Services.Client.DataServiceQuery%601> クラスです。</span><span class="sxs-lookup"><span data-stu-id="ca585-107">The two main classes of the client library are the <xref:System.Data.Services.Client.DataServiceContext> class and the <xref:System.Data.Services.Client.DataServiceQuery%601> class.</span></span> <span data-ttu-id="ca585-108"><xref:System.Data.Services.Client.DataServiceContext> クラスは、特定のデータ サービスに対してサポートされている操作をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="ca585-108">The <xref:System.Data.Services.Client.DataServiceContext> class encapsulates operations that are supported against a specified data service.</span></span> <span data-ttu-id="ca585-109">OData サービスはステートレスですが、コンテキストはステートレスではありません。</span><span class="sxs-lookup"><span data-stu-id="ca585-109">Although OData services are stateless, the context is not.</span></span> <span data-ttu-id="ca585-110">このため <xref:System.Data.Services.Client.DataServiceContext> クラスを使用すると、変更管理などの機能をサポートするためにデータ サービスとの対話操作間におけるクライアントの状態を保持できます。</span><span class="sxs-lookup"><span data-stu-id="ca585-110">Therefore, you can use the <xref:System.Data.Services.Client.DataServiceContext> class to maintain state on the client between interactions with the data service in order to support features such as change management.</span></span> <span data-ttu-id="ca585-111">このクラスは、ID の管理と変更の追跡も行います。</span><span class="sxs-lookup"><span data-stu-id="ca585-111">This class also manages identities and tracks changes.</span></span> <span data-ttu-id="ca585-112"><xref:System.Data.Services.Client.DataServiceQuery%601> クラスは、特定のエンティティ セットに対するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="ca585-112">The <xref:System.Data.Services.Client.DataServiceQuery%601> class represents a query against a specific entity set.</span></span>  
  
 <span data-ttu-id="ca585-113">このセクションでは、クライアント ライブラリを使用して .NET Framework クライアント アプリケーションからデータにアクセスしてデータを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca585-113">This section describes how to use client libraries to access and change data from a .NET Framework client application.</span></span> <span data-ttu-id="ca585-114">Silverlight ベースのアプリケーションで WCF Data Services クライアント ライブラリを使用する方法については、「[WCF Data Services (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca585-114">For more information about how to use the WCF Data Services client library with a Silverlight-based application, see [WCF Data Services (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)).</span></span> <span data-ttu-id="ca585-115">その他の種類のアプリケーションで OData フィードを使用する場合は、それぞれに対応したクライアント ライブラリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ca585-115">Other client libraries are available that enable you to consume an OData feed in other kinds of applications.</span></span> <span data-ttu-id="ca585-116">OData SDK の詳細については、[OData SDK のサンプルコード](https://www.odata.org/ecosystem/#sdk)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca585-116">For more information on OData SDK, see [OData SDK - Sample Code](https://www.odata.org/ecosystem/#sdk).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="ca585-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ca585-117">In This Section</span></span>  

 [<span data-ttu-id="ca585-118">データ サービス クライアント ライブラリの生成</span><span class="sxs-lookup"><span data-stu-id="ca585-118">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)  
 <span data-ttu-id="ca585-119">クライアント ライブラリ、および OData フィードに基づくクライアント データ サービス クラスを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca585-119">Describes how to generate a client library and client data service classes that are based on OData feeds.</span></span>  
  
 [<span data-ttu-id="ca585-120">データ サービスに対するクエリ</span><span class="sxs-lookup"><span data-stu-id="ca585-120">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="ca585-121">クライアント ライブラリを使用して .NET Framework ベースのアプリケーションからデータ サービスを照会する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca585-121">Describes how to query a data service from a .NET Framework-based application by using client libraries.</span></span>  
  
 [<span data-ttu-id="ca585-122">遅延コンテンツの読み込み</span><span class="sxs-lookup"><span data-stu-id="ca585-122">Loading Deferred Content</span></span>](loading-deferred-content-wcf-data-services.md)  
 <span data-ttu-id="ca585-123">最初のクエリ応答に含まれない追加のコンテンツを読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca585-123">Describes how to load additional content not included in the initial query response.</span></span>  
  
 [<span data-ttu-id="ca585-124">データ サービスの更新</span><span class="sxs-lookup"><span data-stu-id="ca585-124">Updating the Data Service</span></span>](updating-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="ca585-125">クライアント ライブラリを使用してエンティティおよびリレーションシップを作成、変更、および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca585-125">Describes how to create, modify, and delete entities and relationships by using the client libraries.</span></span>  
  
 [<span data-ttu-id="ca585-126">非同期操作</span><span class="sxs-lookup"><span data-stu-id="ca585-126">Asynchronous Operations</span></span>](asynchronous-operations-wcf-data-services.md)  
 <span data-ttu-id="ca585-127">非同期でデータ サービスを操作するためにクライアント ライブラリで提供される機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca585-127">Describes the facilities provided by the client libraries for working with a data service in an asynchronous manner.</span></span>  
  
 [<span data-ttu-id="ca585-128">バッチ処理</span><span class="sxs-lookup"><span data-stu-id="ca585-128">Batching Operations</span></span>](batching-operations-wcf-data-services.md)  
 <span data-ttu-id="ca585-129">クライアント ライブラリを使用して複数の要求を 1 つのバッチでデータ サービスに送信する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca585-129">Describes how to send multiple requests to the data service in a single batch by using the client libraries.</span></span>  
  
 [<span data-ttu-id="ca585-130">コントロールへのデータのバインド</span><span class="sxs-lookup"><span data-stu-id="ca585-130">Binding Data to Controls</span></span>](binding-data-to-controls-wcf-data-services.md)  
 <span data-ttu-id="ca585-131">コントロールをデータ サービスによって返される OData フィードにバインドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca585-131">Describes how to bind controls to a OData feed returned by a data service.</span></span>  
  
 [<span data-ttu-id="ca585-132">サービス操作の呼び出し</span><span class="sxs-lookup"><span data-stu-id="ca585-132">Calling Service Operations</span></span>](calling-service-operations-wcf-data-services.md)  
 <span data-ttu-id="ca585-133">クライアント ライブラリを使用してサービス操作を呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca585-133">Describes how to use the client library to call service operations.</span></span>  
  
 [<span data-ttu-id="ca585-134">データ サービス コンテキストの管理</span><span class="sxs-lookup"><span data-stu-id="ca585-134">Managing the Data Service Context</span></span>](managing-the-data-service-context-wcf-data-services.md)  
 <span data-ttu-id="ca585-135">クライアント ライブラリの動作を管理するオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ca585-135">Describes options for managing the behavior of the client library.</span></span>  
  
 [<span data-ttu-id="ca585-136">バイナリ データの操作</span><span class="sxs-lookup"><span data-stu-id="ca585-136">Working with Binary Data</span></span>](working-with-binary-data-wcf-data-services.md)  
 <span data-ttu-id="ca585-137">データ サービスによってデータ ストリームとして返されるバイナリ データにアクセスしてバイナリ データを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca585-137">Describes how to access and change binary data returned by the data service as a data stream.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca585-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca585-138">See also</span></span>

- [<span data-ttu-id="ca585-139">WCF Data Services の定義</span><span class="sxs-lookup"><span data-stu-id="ca585-139">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="ca585-140">はじめに</span><span class="sxs-lookup"><span data-stu-id="ca585-140">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
