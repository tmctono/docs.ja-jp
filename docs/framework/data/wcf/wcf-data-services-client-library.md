---
title: WCF Data Services クライアント ライブラリ
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: e078ba07072f71332aa2f19681b142df946ec391
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975071"
---
# <a name="wcf-data-services-client-library"></a><span data-ttu-id="4f3c0-102">WCF Data Services クライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="4f3c0-102">WCF Data Services Client Library</span></span>
<span data-ttu-id="4f3c0-103">任意のアプリケーションが HTTP 要求を送信し、データサービスが返す OData フィードを処理できる場合は、Open Data Protocol (OData) ベースのデータサービスと対話できます。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-103">Any application can interact with an Open Data Protocol (OData)-based data service if it can send an HTTP request and process the OData feed that a data service returns.</span></span> <span data-ttu-id="4f3c0-104">この相互運用性により、さまざまな Web 対応アプリケーションから OData ベースのサービスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-104">This interoperability enables you to access OData-based services from a broad range of Web-enabled applications.</span></span> [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="4f3c0-105">には、.NET Framework または Silverlight ベースのアプリケーションから OData フィードを使用する際のプログラミングエクスペリエンスを向上させるクライアントライブラリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-105">includes client libraries that provide a richer programming experience when you consume OData feeds from .NET Framework or Silverlight-based applications.</span></span>  
  
 <span data-ttu-id="4f3c0-106">クライアント ライブラリの 2 つの主要なクラスは、<xref:System.Data.Services.Client.DataServiceContext> クラスと <xref:System.Data.Services.Client.DataServiceQuery%601> クラスです。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-106">The two main classes of the client library are the <xref:System.Data.Services.Client.DataServiceContext> class and the <xref:System.Data.Services.Client.DataServiceQuery%601> class.</span></span> <span data-ttu-id="4f3c0-107"><xref:System.Data.Services.Client.DataServiceContext> クラスは、特定のデータ サービスに対してサポートされている操作をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-107">The <xref:System.Data.Services.Client.DataServiceContext> class encapsulates operations that are supported against a specified data service.</span></span> <span data-ttu-id="4f3c0-108">OData サービスはステートレスですが、コンテキストは異なります。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-108">Although OData services are stateless, the context is not.</span></span> <span data-ttu-id="4f3c0-109">したがって、変更管理などの機能をサポートするために、<xref:System.Data.Services.Client.DataServiceContext> クラスを使用して、データサービスとの対話間でクライアント上の状態を維持できます。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-109">Therefore, you can use the <xref:System.Data.Services.Client.DataServiceContext> class to maintain state on the client between interactions with the data service in order to support features such as change management.</span></span> <span data-ttu-id="4f3c0-110">このクラスは、ID の管理と変更の追跡も行います。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-110">This class also manages identities and tracks changes.</span></span> <span data-ttu-id="4f3c0-111"><xref:System.Data.Services.Client.DataServiceQuery%601> クラスは、特定のエンティティ セットに対するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-111">The <xref:System.Data.Services.Client.DataServiceQuery%601> class represents a query against a specific entity set.</span></span>  
  
 <span data-ttu-id="4f3c0-112">このセクションでは、クライアント ライブラリを使用して .NET Framework クライアント アプリケーションからデータにアクセスしてデータを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-112">This section describes how to use client libraries to access and change data from a .NET Framework client application.</span></span> <span data-ttu-id="4f3c0-113">Silverlight ベースのアプリケーションで [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] クライアントライブラリを使用する方法の詳細については、「 [WCF Data Services (silverlight)](https://go.microsoft.com/fwlink/?LinkId=186016)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-113">For more information about how to use the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] client library with a Silverlight-based application, see [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=186016).</span></span> <span data-ttu-id="4f3c0-114">他の種類のアプリケーションで OData フィードを使用できるようにするその他のクライアントライブラリも用意されています。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-114">Other client libraries are available that enable you to consume an OData feed in other kinds of applications.</span></span> <span data-ttu-id="4f3c0-115">詳細については、 [ODATA SDK](https://go.microsoft.com/fwlink/?LinkID=185796)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-115">For more information, see the [OData SDK](https://go.microsoft.com/fwlink/?LinkID=185796).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f3c0-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4f3c0-116">In This Section</span></span>  
 [<span data-ttu-id="4f3c0-117">データ サービス クライアント ライブラリの生成</span><span class="sxs-lookup"><span data-stu-id="4f3c0-117">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)  
 <span data-ttu-id="4f3c0-118">OData フィードに基づくクライアントライブラリとクライアントデータサービスクラスを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-118">Describes how to generate a client library and client data service classes that are based on OData feeds.</span></span>  
  
 [<span data-ttu-id="4f3c0-119">データ サービスに対するクエリ</span><span class="sxs-lookup"><span data-stu-id="4f3c0-119">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="4f3c0-120">クライアント ライブラリを使用して .NET Framework ベースのアプリケーションからデータ サービスを照会する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-120">Describes how to query a data service from a .NET Framework-based application by using client libraries.</span></span>  
  
 [<span data-ttu-id="4f3c0-121">遅延コンテンツの読み込み</span><span class="sxs-lookup"><span data-stu-id="4f3c0-121">Loading Deferred Content</span></span>](loading-deferred-content-wcf-data-services.md)  
 <span data-ttu-id="4f3c0-122">最初のクエリ応答に含まれない追加のコンテンツを読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-122">Describes how to load additional content not included in the initial query response.</span></span>  
  
 [<span data-ttu-id="4f3c0-123">データ サービスの更新</span><span class="sxs-lookup"><span data-stu-id="4f3c0-123">Updating the Data Service</span></span>](updating-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="4f3c0-124">クライアント ライブラリを使用してエンティティおよびリレーションシップを作成、変更、および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-124">Describes how to create, modify, and delete entities and relationships by using the client libraries.</span></span>  
  
 [<span data-ttu-id="4f3c0-125">非同期操作</span><span class="sxs-lookup"><span data-stu-id="4f3c0-125">Asynchronous Operations</span></span>](asynchronous-operations-wcf-data-services.md)  
 <span data-ttu-id="4f3c0-126">非同期でデータ サービスを操作するためにクライアント ライブラリで提供される機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-126">Describes the facilities provided by the client libraries for working with a data service in an asynchronous manner.</span></span>  
  
 [<span data-ttu-id="4f3c0-127">バッチ処理</span><span class="sxs-lookup"><span data-stu-id="4f3c0-127">Batching Operations</span></span>](batching-operations-wcf-data-services.md)  
 <span data-ttu-id="4f3c0-128">クライアント ライブラリを使用して複数の要求を 1 つのバッチでデータ サービスに送信する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-128">Describes how to send multiple requests to the data service in a single batch by using the client libraries.</span></span>  
  
 [<span data-ttu-id="4f3c0-129">コントロールへのデータのバインド</span><span class="sxs-lookup"><span data-stu-id="4f3c0-129">Binding Data to Controls</span></span>](binding-data-to-controls-wcf-data-services.md)  
 <span data-ttu-id="4f3c0-130">データサービスによって返される OData フィードにコントロールをバインドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-130">Describes how to bind controls to a OData feed returned by a data service.</span></span>  
  
 [<span data-ttu-id="4f3c0-131">サービス操作の呼び出し</span><span class="sxs-lookup"><span data-stu-id="4f3c0-131">Calling Service Operations</span></span>](calling-service-operations-wcf-data-services.md)  
 <span data-ttu-id="4f3c0-132">クライアント ライブラリを使用してサービス操作を呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-132">Describes how to use the client library to call service operations.</span></span>  
  
 [<span data-ttu-id="4f3c0-133">データ サービス コンテキストの管理</span><span class="sxs-lookup"><span data-stu-id="4f3c0-133">Managing the Data Service Context</span></span>](managing-the-data-service-context-wcf-data-services.md)  
 <span data-ttu-id="4f3c0-134">クライアント ライブラリの動作を管理するオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-134">Describes options for managing the behavior of the client library.</span></span>  
  
 [<span data-ttu-id="4f3c0-135">バイナリ データの操作</span><span class="sxs-lookup"><span data-stu-id="4f3c0-135">Working with Binary Data</span></span>](working-with-binary-data-wcf-data-services.md)  
 <span data-ttu-id="4f3c0-136">データ サービスによってデータ ストリームとして返されるバイナリ データにアクセスしてバイナリ データを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f3c0-136">Describes how to access and change binary data returned by the data service as a data stream.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f3c0-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f3c0-137">See also</span></span>

- [<span data-ttu-id="4f3c0-138">WCF Data Services の定義</span><span class="sxs-lookup"><span data-stu-id="4f3c0-138">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="4f3c0-139">はじめに</span><span class="sxs-lookup"><span data-stu-id="4f3c0-139">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
