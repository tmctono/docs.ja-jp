---
title: Tutorial1 を作業の開始
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], getting started
- Windows Communication Foundation [WCF], getting started
- getting started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: b7ba25795dd69e5bd978c77928f9b9797f4d4e19
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200885"
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="204a1-102">チュートリアル入門</span><span class="sxs-lookup"><span data-stu-id="204a1-102">Getting Started Tutorial</span></span>
<span data-ttu-id="204a1-103">このセクションのトピックはクイック露出を Windows Communication Foundation (WCF) プログラミングの経験を提供するためのものです。</span><span class="sxs-lookup"><span data-stu-id="204a1-103">The topics contained in this section are intended to give you quick exposure to the Windows Communication Foundation (WCF) programming experience.</span></span> <span data-ttu-id="204a1-104">これらは、このトピックに記載されているリストの順番どおりに完了するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="204a1-104">They are designed to be completed in the order of the list at the bottom of this topic.</span></span> <span data-ttu-id="204a1-105">このチュートリアルに従って作業では、WCF サービスとクライアント アプリケーションの作成に必要な手順の概要を理解するできます。</span><span class="sxs-lookup"><span data-stu-id="204a1-105">Working through this tutorial gives you an introductory understanding of the steps required to create WCF service and client applications.</span></span> <span data-ttu-id="204a1-106">サービスは 1 つ以上のエンドポイントを公開し、それぞれのエンドポイントは 1 つ以上のサービス操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="204a1-106">A service exposes one or more endpoints, each of which exposes one or more service operations.</span></span> <span data-ttu-id="204a1-107">*エンドポイント*サービスのサービスの場所、アドレス、クライアントが、サービスと機能を定義するコントラクトと通信する必要がある方法を説明する情報を格納するバインディングを指定します。サービスのクライアントに提供します。</span><span class="sxs-lookup"><span data-stu-id="204a1-107">The *endpoint* of a service specifies an address where the service can be found, a binding that contains the information that describes how a client must communicate with the service, and a contract that defines the functionality provided by the service to its clients.</span></span>

 <span data-ttu-id="204a1-108">このチュートリアルの一連のトピックを終了すると、サービスを実行し、クライアントからそのサービスを呼び出すことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="204a1-108">After you work through the sequence of topics in this tutorial, you will have a running service, and a client that calls the service.</span></span> <span data-ttu-id="204a1-109">最初の 3 つのトピックでは、サービス コントラクトを定義する方法、サービス コントラクトを実装する方法、およびサービスをホストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="204a1-109">The first three topics describe how to define a service contract, how to implement the service contract, and how to host the service.</span></span> <span data-ttu-id="204a1-110">作成したサービスは、コンソール アプリケーション内で自己ホストされます。</span><span class="sxs-lookup"><span data-stu-id="204a1-110">The service that is created is self-hosted within a console application.</span></span> <span data-ttu-id="204a1-111">また、サービスは、インターネット インフォメーション サービス (IIS) でホストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="204a1-111">Services can also be hosted under Internet Information Services (IIS).</span></span> <span data-ttu-id="204a1-112">この方法の詳細については、「[方法 : IIS で WCF サービスをホスト](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)します。</span><span class="sxs-lookup"><span data-stu-id="204a1-112">For more information about how to do this, see [How to: Host a WCF Service in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span> <span data-ttu-id="204a1-113">サービスはコードで構成されますが、構成ファイル内で構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="204a1-113">The service is configured in code; however, services can also be configured within a configuration file.</span></span> <span data-ttu-id="204a1-114">構成ファイルの使用の詳細については、次を参照してください。[構成ファイルを使用してサービスを構成する](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)します。</span><span class="sxs-lookup"><span data-stu-id="204a1-114">For more information about using a configuration file see [Configuring Services Using Configuration Files](../../../docs/framework/wcf/configuring-services-using-configuration-files.md).</span></span>

 <span data-ttu-id="204a1-115">次の 3 つのトピックでは、クライアント プロキシを作成する方法、クライアント アプリケーションを構成する方法、およびサービスが公開するサービス操作をクライアント プロキシを使って呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="204a1-115">The next three topics describe how to create a client proxy, configure the client application, and use the client proxy to call service operation exposed by the service.</span></span> <span data-ttu-id="204a1-116">サービスは、クライアント アプリケーションがサービスと通信するために必要な情報を定義したメタデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="204a1-116">Services publish metadata that define the information a client application needs to communicate with the service.</span></span> <span data-ttu-id="204a1-117">Visual Studio 2012 では、このメタデータにアクセスするプロセスを自動化し、構築して、サービスのクライアント アプリケーションを構成することを使用します。</span><span class="sxs-lookup"><span data-stu-id="204a1-117">Visual Studio 2012 automates the process of accessing this metadata and uses it to construct and configure the client application for the service.</span></span> <span data-ttu-id="204a1-118">Visual Studio 2012 を使用していない場合は使用できます、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)を構築およびサービスのクライアント アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="204a1-118">If you are not using Visual Studio 2012, you can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to construct and configure the client application for the service.</span></span>

<span data-ttu-id="204a1-119">このセクションのトピックでは、開発環境として Visual Studio を使用するいると仮定します。</span><span class="sxs-lookup"><span data-stu-id="204a1-119">The topics in this section assume you are using Visual Studio as the development environment.</span></span> <span data-ttu-id="204a1-120">他の開発環境を使用している場合は、Visual Studio 固有の手順を無視します。</span><span class="sxs-lookup"><span data-stu-id="204a1-120">If you are using another development environment, ignore the Visual Studio-specific instructions.</span></span>

<span data-ttu-id="204a1-121">ハード_ディスクにダウンロードできるようにしてトピックを参照して、実行するサンプル アプリケーションの[Windows Communication Foundation (WCF) サンプル](./samples/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="204a1-121">For sample applications that can be downloaded to your hard disk and run, see the topics in [Windows Communication Foundation (WCF) samples](./samples/index.md).</span></span> <span data-ttu-id="204a1-122">このトピックでは、具体的を参照、 [Getting Started](../../../docs/framework/wcf/samples/getting-started-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="204a1-122">For this topic, see, in particular, the [Getting Started](../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>

<span data-ttu-id="204a1-123">サービスとクライアントの作成の詳細の詳細については、次を参照してください。[基本的な WCF プログラミング](../../../docs/framework/wcf/basic-wcf-programming.md)します。</span><span class="sxs-lookup"><span data-stu-id="204a1-123">For more in-depth information about creating services and clients, see [Basic WCF Programming](../../../docs/framework/wcf/basic-wcf-programming.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="204a1-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="204a1-124">In This Section</span></span>
 [<span data-ttu-id="204a1-125">方法: サービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="204a1-125">How to: Define a Service Contract</span></span>](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)

 <span data-ttu-id="204a1-126">ユーザー定義のインターフェイスを使用して WCF コントラクトを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="204a1-126">Describes how to create a WCF contract using a user-defined interface.</span></span> <span data-ttu-id="204a1-127">コントラクトは、サービスが公開する機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="204a1-127">The contract defines the functionality exposed by the service.</span></span>

 [<span data-ttu-id="204a1-128">方法: サービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="204a1-128">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)

 <span data-ttu-id="204a1-129">サービス コントラクトを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="204a1-129">Describes how to implement a service contract.</span></span> <span data-ttu-id="204a1-130">コントラクトを定義するは、サービス クラスを使用して実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="204a1-130">Once a contract is defined, it must be implemented with a service class.</span></span>

 [<span data-ttu-id="204a1-131">方法: ホストし、基本的なサービスの実行</span><span class="sxs-lookup"><span data-stu-id="204a1-131">How to: Host and Run a Basic Service</span></span>](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)

 <span data-ttu-id="204a1-132">サービスのエンドポイントをコードで構成する方法と、コンソール アプリケーションでサービスをホストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="204a1-132">Describes how to configure an endpoint for the service in code and how to host the service in a console application.</span></span> <span data-ttu-id="204a1-133">サービスをアクティブにするには、サービスをランタイム環境内で構成してホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="204a1-133">To become active, a service must be configured and hosted within a run-time environment.</span></span> <span data-ttu-id="204a1-134">この環境によってサービスが作成され、サービスのコンテキストと有効期間が制御されます。</span><span class="sxs-lookup"><span data-stu-id="204a1-134">This environment creates the service and controls its context and lifetime.</span></span>

 [<span data-ttu-id="204a1-135">方法: クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="204a1-135">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)

 <span data-ttu-id="204a1-136">WCF サービスからの WCF クライアント プロキシを作成するために使用するメタデータを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="204a1-136">Describes how to retrieve metadata used to create a WCF client proxy from a WCF service.</span></span> <span data-ttu-id="204a1-137">このプロセスは、Visual Studio 内でサービス参照の追加機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="204a1-137">This process uses the Add Service Reference functionality within Visual Studio.</span></span>

 [<span data-ttu-id="204a1-138">方法: クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="204a1-138">How to: Configure a Client</span></span>](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)

 <span data-ttu-id="204a1-139">WCF クライアントの構成方法について説明します。クライアントを構成するには、クライアントがサービスへのアクセスに使用するエンドポイントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="204a1-139">Describes how to configure a WCF client Configuring the client requires specifying the endpoint that the client uses to access the service.</span></span>

 [<span data-ttu-id="204a1-140">方法: クライアントを使用します。</span><span class="sxs-lookup"><span data-stu-id="204a1-140">How to: Use a Client</span></span>](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)

 <span data-ttu-id="204a1-141">サービス操作を呼び出す、WCF クライアント プロキシを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="204a1-141">Describes how to use the WCF client proxy to invoke service operations.</span></span>

## <a name="reference"></a><span data-ttu-id="204a1-142">参照</span><span class="sxs-lookup"><span data-stu-id="204a1-142">Reference</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="related-sections"></a><span data-ttu-id="204a1-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="204a1-143">Related Sections</span></span>

- [<span data-ttu-id="204a1-144">Windows Communication Foundation (WCF) のサンプル</span><span class="sxs-lookup"><span data-stu-id="204a1-144">Windows Communication Foundation (WCF) samples</span></span>](./samples/index.md)
- [<span data-ttu-id="204a1-145">基本的なプログラミング ライフサイクル</span><span class="sxs-lookup"><span data-stu-id="204a1-145">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)

## <a name="see-also"></a><span data-ttu-id="204a1-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="204a1-146">See also</span></span>

- [<span data-ttu-id="204a1-147">概念</span><span class="sxs-lookup"><span data-stu-id="204a1-147">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)
- [<span data-ttu-id="204a1-148">ドキュメントのガイド</span><span class="sxs-lookup"><span data-stu-id="204a1-148">Guide to the Documentation</span></span>](../../../docs/framework/wcf/guide-to-the-documentation.md)
- [<span data-ttu-id="204a1-149">Windows Communication Foundation とは</span><span class="sxs-lookup"><span data-stu-id="204a1-149">What Is Windows Communication Foundation</span></span>](../../../docs/framework/wcf/whats-wcf.md)
- [<span data-ttu-id="204a1-150">WCF 機能の詳細</span><span class="sxs-lookup"><span data-stu-id="204a1-150">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)
