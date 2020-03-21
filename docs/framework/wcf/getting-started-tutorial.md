---
title: 'チュートリアル: Windows コミュニケーション ファウンデーション アプリケーションの使用を開始する'
description: これらのチュートリアルでは、WCF アプリケーションを作成するための概要を提供します。
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: df73f953372202796cebce9d3e3f28bd617c67ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184120"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a><span data-ttu-id="6703b-103">チュートリアル: Windows コミュニケーション ファウンデーション アプリケーションの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="6703b-103">Tutorial: Get started with Windows Communication Foundation applications</span></span>
<span data-ttu-id="6703b-104">次の一連のチュートリアルでは、Windows 通信基盤 (WCF) プログラミングエクスペリエンスを紹介します。</span><span class="sxs-lookup"><span data-stu-id="6703b-104">The following series of tutorials introduce you to the Windows Communication Foundation (WCF) programming experience.</span></span> <span data-ttu-id="6703b-105">これらのチュートリアルを順番に操作すると、WCF アプリケーションの作成に必要な手順を理解できます。</span><span class="sxs-lookup"><span data-stu-id="6703b-105">Working through these tutorials in order will give you an introductory understanding of the steps required to create WCF applications.</span></span> <span data-ttu-id="6703b-106">完了すると、実行中の WCF サービスと、サービスを呼び出す WCF クライアントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6703b-106">After you finish, you'll have a running WCF service and a WCF client that calls the service.</span></span>

<span data-ttu-id="6703b-107">このチュートリアルでは、開発環境として Visual Studio を使用していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="6703b-107">The tutorial assumes you're using Visual Studio as the development environment.</span></span> <span data-ttu-id="6703b-108">別の開発環境を使用している場合は、Visual Studio 固有の手順を無視します。</span><span class="sxs-lookup"><span data-stu-id="6703b-108">If you're using another development environment, ignore the Visual Studio-specific instructions.</span></span>

<span data-ttu-id="6703b-109">ダウンロードして実行できるサンプル WCF アプリケーションについては[、「Windows コミュニケーション ファウンデーションのサンプル](samples/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6703b-109">For sample WCF applications that you can download and run, see [Windows Communication Foundation samples](samples/index.md).</span></span> <span data-ttu-id="6703b-110">サンプルの概要については、「[はじめにのサンプル](samples/getting-started-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6703b-110">For an introduction to the samples, see [Getting started sample](samples/getting-started-sample.md).</span></span>

<span data-ttu-id="6703b-111">サービスとクライアントの作成の詳細については、「[基本 WCF プログラミング](basic-wcf-programming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6703b-111">For more in-depth information about creating services and clients, see [Basic WCF programming](basic-wcf-programming.md).</span></span>

## <a name="wcf-tutorials"></a><span data-ttu-id="6703b-112">WCF チュートリアル</span><span class="sxs-lookup"><span data-stu-id="6703b-112">WCF tutorials</span></span>

<span data-ttu-id="6703b-113">最初の 3 つのチュートリアルでは、WCF サービス コントラクトを定義する方法、実装する方法、およびそれをホストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6703b-113">The first three tutorials describe how to define a WCF service contract, how to implement it, and how to host it.</span></span> <span data-ttu-id="6703b-114">作成するサービスは、コンソール アプリケーション内で自己ホストされます。</span><span class="sxs-lookup"><span data-stu-id="6703b-114">The service that you create is self-hosted within a console application.</span></span> <span data-ttu-id="6703b-115">また、Microsoft インターネット インフォメーション サービス (IIS) でサービスをホストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6703b-115">You can also host services under Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="6703b-116">詳細については、「[方法 : IIS で WCF サービスをホストする](feature-details/how-to-host-a-wcf-service-in-iis.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6703b-116">For more information, see [How to: Host a WCF Service in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span> <span data-ttu-id="6703b-117">チュートリアルでは、コードを使用してサービスを構成しますが、[構成ファイル内でサービスを構成](configuring-services-using-configuration-files.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="6703b-117">Although you use code to configure the service in the tutorial, you can also [configure services within a configuration file](configuring-services-using-configuration-files.md).</span></span>

- [<span data-ttu-id="6703b-118">チュートリアル: サービス コントラクトの定義</span><span class="sxs-lookup"><span data-stu-id="6703b-118">Tutorial: Define a service contract</span></span>](how-to-define-a-wcf-service-contract.md)

    <span data-ttu-id="6703b-119">ユーザー定義のインターフェイスを使用して WCF コントラクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6703b-119">You create a WCF contract with a user-defined interface.</span></span> <span data-ttu-id="6703b-120">このコントラクトは、サービスが公開する機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="6703b-120">This contract defines the functionality that the service exposes.</span></span>

- [<span data-ttu-id="6703b-121">チュートリアル: サービス コントラクトの実装</span><span class="sxs-lookup"><span data-stu-id="6703b-121">Tutorial: Implement a service contract</span></span>](how-to-implement-a-wcf-contract.md)

    <span data-ttu-id="6703b-122">コントラクトを定義したら、サービス クラスを使用してコントラクトを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6703b-122">After you define a contract, you must implement it with a service class.</span></span>

- [<span data-ttu-id="6703b-123">チュートリアル: 基本サービスをホストして実行する</span><span class="sxs-lookup"><span data-stu-id="6703b-123">Tutorial: Host and run a basic service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)

    <span data-ttu-id="6703b-124">サービスのエンドポイントを構成し、コンソール アプリケーションでサービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="6703b-124">Configure an endpoint for the service and host the service in a console application.</span></span> <span data-ttu-id="6703b-125">サービスをアクティブにするには、サービスを構成し、ランタイム環境内でホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6703b-125">For a service to become active, you must configure it and host it within a run-time environment.</span></span> <span data-ttu-id="6703b-126">このランタイム環境は、サービスを作成し、そのコンテキストと有効期間を制御します。</span><span class="sxs-lookup"><span data-stu-id="6703b-126">This run-time environment creates the service and controls its context and lifetime.</span></span>

<span data-ttu-id="6703b-127">次の 2 つのチュートリアルでは、クライアント アプリケーションを作成、構成、および使用して、サービスが公開する操作を呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6703b-127">The next two tutorials describe how to create, configure, and use a client application to call the operations the service exposes.</span></span> <span data-ttu-id="6703b-128">サービスは、クライアント アプリケーションがサービスと通信するために必要な情報を定義したメタデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="6703b-128">Services publish metadata that define the information a client application needs to communicate with the service.</span></span> <span data-ttu-id="6703b-129">Visual Studio は、このメタデータにアクセスするプロセスを自動化し、サービスのクライアント アプリケーションを構築するために使用します。</span><span class="sxs-lookup"><span data-stu-id="6703b-129">Visual Studio automates the process of accessing this metadata and uses it to construct the client application for the service.</span></span> <span data-ttu-id="6703b-130">Visual Studio を使用しない場合は、代わりに[サービス モデル メタデータ ユーティリティ ツール (*Svcutil.exe*) を](servicemodel-metadata-utility-tool-svcutil-exe.md)使用できます。</span><span class="sxs-lookup"><span data-stu-id="6703b-130">If you decide not to use Visual Studio, you can use the [ServiceModel Metadata Utility tool (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) instead.</span></span>

- [<span data-ttu-id="6703b-131">チュートリアル: クライアントの作成</span><span class="sxs-lookup"><span data-stu-id="6703b-131">Tutorial: Create a client</span></span>](how-to-create-a-wcf-client.md)

    <span data-ttu-id="6703b-132">WCF サービスから WCF クライアント プロキシを作成するためのメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="6703b-132">Retrieve metadata for creating a WCF client proxy from a WCF service.</span></span> <span data-ttu-id="6703b-133">メタデータを取得するには、Visual Studio を使用してサービス参照を追加するか、サービス モデル メタデータ ユーティリティ ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6703b-133">You retrieve metadata by using Visual Studio to add a service reference or you can use the ServiceModel Metadata Utility tool.</span></span> <span data-ttu-id="6703b-134">クライアントがサービスにアクセスするために使用するエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="6703b-134">You specify the endpoint that the client uses to access the service.</span></span>

- [<span data-ttu-id="6703b-135">チュートリアル: クライアントを使用する</span><span class="sxs-lookup"><span data-stu-id="6703b-135">Tutorial: Use a client</span></span>](how-to-use-a-wcf-client.md)

    <span data-ttu-id="6703b-136">WCF クライアント プロキシを使用して、サービス操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6703b-136">Use the WCF client proxy to call the service operations.</span></span>

## <a name="reference"></a><span data-ttu-id="6703b-137">リファレンス</span><span class="sxs-lookup"><span data-stu-id="6703b-137">Reference</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a><span data-ttu-id="6703b-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="6703b-138">See also</span></span>

- [<span data-ttu-id="6703b-139">概念の概要</span><span class="sxs-lookup"><span data-stu-id="6703b-139">Conceptual overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="6703b-140">ドキュメントのガイド</span><span class="sxs-lookup"><span data-stu-id="6703b-140">Guide to the documentation</span></span>](guide-to-the-documentation.md)
- [<span data-ttu-id="6703b-141">Windows コミュニケーション ファウンデーションとは</span><span class="sxs-lookup"><span data-stu-id="6703b-141">What is Windows Communication Foundation</span></span>](whats-wcf.md)
- [<span data-ttu-id="6703b-142">WCF 機能の詳細</span><span class="sxs-lookup"><span data-stu-id="6703b-142">WCF feature details</span></span>](feature-details/index.md)
- [<span data-ttu-id="6703b-143">基本的なプログラミングライフサイクル</span><span class="sxs-lookup"><span data-stu-id="6703b-143">Basic programming lifecycle</span></span>](basic-programming-lifecycle.md)
- [<span data-ttu-id="6703b-144">クライアントの構築</span><span class="sxs-lookup"><span data-stu-id="6703b-144">Building clients</span></span>](building-clients.md)
- [<span data-ttu-id="6703b-145">基本的な WCF プログラミング</span><span class="sxs-lookup"><span data-stu-id="6703b-145">Basic WCF programming</span></span>](basic-wcf-programming.md)
- [<span data-ttu-id="6703b-146">方法: 双方向コントラクトを作成する</span><span class="sxs-lookup"><span data-stu-id="6703b-146">How to: Create a duplex contract</span></span>](feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="6703b-147">方法: 双方向コントラクトでサービスにアクセスする</span><span class="sxs-lookup"><span data-stu-id="6703b-147">How to: Access services with a duplex contract</span></span>](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="6703b-148">サービスモデル メタデータ ユーティリティ ツール (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="6703b-148">ServiceModel Metadata Utility tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="6703b-149">方法: Svcutil.exe を使用してメタデータ ドキュメントをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="6703b-149">How to: Use Svcutil.exe to download metadata documents</span></span>](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- <span data-ttu-id="6703b-150">[[方法] 構成ファイルを使用してサービスのメタデータを公開する](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)</span><span class="sxs-lookup"><span data-stu-id="6703b-150">[How to: Publish metadata for a service using a configuration file](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)</span></span>
- [<span data-ttu-id="6703b-151">バインディングを使用したサービスとクライアントの構成</span><span class="sxs-lookup"><span data-stu-id="6703b-151">Using bindings to configure services and clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6703b-152">はじめにのサンプル</span><span class="sxs-lookup"><span data-stu-id="6703b-152">Getting started sample</span></span>](samples/getting-started-sample.md)
- [<span data-ttu-id="6703b-153">Windows コミュニケーション ファウンデーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="6703b-153">Windows Communication Foundation samples</span></span>](samples/index.md)
- [<span data-ttu-id="6703b-154">自己ホスト</span><span class="sxs-lookup"><span data-stu-id="6703b-154">Self-Host</span></span>](samples/self-host.md)
