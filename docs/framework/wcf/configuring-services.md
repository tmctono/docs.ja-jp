---
title: WCF サービスの構成
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: e8ac62809b1269ae810f026c003c7611b3ec548c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593334"
---
# <a name="configuring-wcf-services"></a><span data-ttu-id="b5c0b-102">WCF サービスの構成</span><span class="sxs-lookup"><span data-stu-id="b5c0b-102">Configuring WCF services</span></span>

<span data-ttu-id="b5c0b-103">サービス コントラクトの設計、実装が終われば、サービスを構成できる状態になります。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-103">Once you have designed and implemented your service contract, you are ready to configure your service.</span></span> <span data-ttu-id="b5c0b-104">クライアント側から見たサービスの動作は、ここで定義、カスタマイズします。サービスと通信するためのアドレス、メッセージの送受信に使うトランスポートやエンコーディング、必要なセキュリティ型などを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-104">This is where you define and customize how your service is exposed to clients, including specifying the address where it can be found, the transport and message encoding it uses to send and receive messages, and the type of security it requires.</span></span>  
  
 <span data-ttu-id="b5c0b-105">定義やカスタマイズは、コード内で強制的に (簡単には変更できないような形で) 行う方法と、構成ファイルに記述して行う方法があります。エンドポイントのアドレス、実際に使うトランスポート、セキュリティ スキーマなど、サービスに関するさまざまな事項を定義、カスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-105">Configuration as used here includes all the ways, imperatively in code or by using a configuration file, in which you can define and customize the various aspects of a service, such as specifying its endpoint addresses, the transports used, and its security schemes.</span></span> <span data-ttu-id="b5c0b-106">実際には、構成ファイルの記述は、大規模な WCF アプリケーションのプログラミングの一部です。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-106">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5c0b-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b5c0b-107">In This Section</span></span>  
 [<span data-ttu-id="b5c0b-108">簡略化された構成</span><span class="sxs-lookup"><span data-stu-id="b5c0b-108">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 <span data-ttu-id="b5c0b-109">以降で[!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)]WCF が付属して新しい既定の構成モデルを WCF 構成の要件を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="b5c0b-110">特定のサービスの WCF 構成を指定しない場合、ランタイムでサービスの既定のエンドポイント、バインディング、および動作を自動的に構成します。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-110">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with default endpoints, bindings, and behaviors.</span></span>  
  
 [<span data-ttu-id="b5c0b-111">構成ファイルを使用してサービスを構成する方法</span><span class="sxs-lookup"><span data-stu-id="b5c0b-111">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 <span data-ttu-id="b5c0b-112">Windows Communication Foundation (WCF) サービスは、.NET Framework のテクノロジの構成を使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-112">A Windows Communication Foundation (WCF) service is configurable using the .NET Framework configuration technology.</span></span> <span data-ttu-id="b5c0b-113">ほとんどの場合、XML 要素は、WCF サービスをホストするインターネット インフォメーション サービス (IIS) サイトの Web.config ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-113">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="b5c0b-114">この要素によって、コンピューターごとにエンドポイント アドレス (サービスと通信するために使用する実際のアドレス) などの詳細情報を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-114">The elements allow you to change details, such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span>  
  
 [<span data-ttu-id="b5c0b-115">バインディング</span><span class="sxs-lookup"><span data-stu-id="b5c0b-115">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 <span data-ttu-id="b5c0b-116">さらに、WCF には、クライアントとサービスの通信方法は、トランスポート、セキュリティ、およびエンコーディングが使用されるメッセージなどの最も基本的な機能をすばやく選択するためのバインディングの形式でのシステム指定のいくつかの一般的な構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-116">In addition, WCF includes several system-provided common configurations in the form of bindings that allow you to quickly select the most basic features for how a client and service communicate, such as the transports, security, and message encodings used.</span></span>  
  
 [<span data-ttu-id="b5c0b-117">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="b5c0b-117">Endpoints</span></span>](../../../docs/framework/wcf/endpoints.md)  
 <span data-ttu-id="b5c0b-118">を介して WCF サービスとすべての通信が行われます、*エンドポイント*サービス。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-118">All communication with a WCF service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="b5c0b-119">エンドポイントには、コントラクト、バインディングで指定されている構成情報、およびサービスの検索場所やサービスに関する情報の取得場所を示すアドレスが設定されています。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-119">Endpoints contain the contract, the configuration information that is specified in the bindings, and the addresses that indicate where to find the service or where to obtain information about the service.</span></span>  
  
 [<span data-ttu-id="b5c0b-120">サービスのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="b5c0b-120">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 <span data-ttu-id="b5c0b-121">WCF を使用して、既存のセキュリティ メカニズムでは、機密性、整合性、認証、および任意のサービスに承認を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-121">Using WCF and existing security mechanisms, you can implement confidentiality, integrity, authentication, and authorization into any service.</span></span> <span data-ttu-id="b5c0b-122">また、セキュリティに関する成功および失敗を監査することも可能です。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-122">You can also audit for security successes and failures.</span></span>  
  
 [<span data-ttu-id="b5c0b-123">WS-I Basic Profile 1.1 の相互運用可能サービスの作成</span><span class="sxs-lookup"><span data-stu-id="b5c0b-123">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 <span data-ttu-id="b5c0b-124">他のプラットフォームやオペレーティング システム上で動作するサービスやクライアントと、相互に運用できるような形でサービスを配置するために必要な事項は、WS-I Basic Profile 1.1 の仕様に記載されています。</span><span class="sxs-lookup"><span data-stu-id="b5c0b-124">The requirements for deploying a service that is interoperable with services and clients on any other platform or operating system are outlined in the WS-I Basic Profile 1.1 specification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b5c0b-125">参照</span><span class="sxs-lookup"><span data-stu-id="b5c0b-125">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="b5c0b-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5c0b-126">Related Sections</span></span>  
 [<span data-ttu-id="b5c0b-127">基本的なプログラミング ライフサイクル</span><span class="sxs-lookup"><span data-stu-id="b5c0b-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [<span data-ttu-id="b5c0b-128">サービスの設計と実装</span><span class="sxs-lookup"><span data-stu-id="b5c0b-128">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [<span data-ttu-id="b5c0b-129">ホスティング サービス</span><span class="sxs-lookup"><span data-stu-id="b5c0b-129">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
  
 [<span data-ttu-id="b5c0b-130">クライアントを構築する</span><span class="sxs-lookup"><span data-stu-id="b5c0b-130">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
  
 [<span data-ttu-id="b5c0b-131">拡張機能の概要</span><span class="sxs-lookup"><span data-stu-id="b5c0b-131">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [<span data-ttu-id="b5c0b-132">管理と診断</span><span class="sxs-lookup"><span data-stu-id="b5c0b-132">Administration and Diagnostics</span></span>](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="b5c0b-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5c0b-133">See also</span></span>

- [<span data-ttu-id="b5c0b-134">基本的な WCF プログラミング</span><span class="sxs-lookup"><span data-stu-id="b5c0b-134">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="b5c0b-135">概念</span><span class="sxs-lookup"><span data-stu-id="b5c0b-135">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)
- [<span data-ttu-id="b5c0b-136">WCF 機能の詳細</span><span class="sxs-lookup"><span data-stu-id="b5c0b-136">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)
