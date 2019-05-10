---
title: Windows Communication Foundation エンドポイント
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
ms.assetid: bd0c310f-dd9f-4081-9be2-3db5909850b6
ms.openlocfilehash: 1a18e2ab31998b7759803e023151892694757119
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613381"
---
# <a name="windows-communication-foundation-endpoints"></a><span data-ttu-id="42302-102">Windows Communication Foundation エンドポイント</span><span class="sxs-lookup"><span data-stu-id="42302-102">Windows Communication Foundation Endpoints</span></span>
<span data-ttu-id="42302-103">を介して Windows Communication Foundation (WCF) サービスとすべての通信が行われます、*エンドポイント*サービス。</span><span class="sxs-lookup"><span data-stu-id="42302-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="42302-104">エンドポイントは、WCF サービスを提供する機能へのアクセスをクライアントに提供します。</span><span class="sxs-lookup"><span data-stu-id="42302-104">Endpoints provide clients access to the functionality that a WCF service offers.</span></span>  
  
 <span data-ttu-id="42302-105">エンドポイントを作成する方法の概要については、次を参照してください。[エンドポイントの作成の概要](../../../docs/framework/wcf/endpoint-creation-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="42302-105">For an overview about how to create an endpoint, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="42302-106">エンドポイントは次の要素から成ります。</span><span class="sxs-lookup"><span data-stu-id="42302-106">Each endpoint contains:</span></span>  
  
- <span data-ttu-id="42302-107">そのエンドポイントの場所を示すアドレス。</span><span class="sxs-lookup"><span data-stu-id="42302-107">An address that indicates where to find the endpoint.</span></span>  
  
- <span data-ttu-id="42302-108">クライアントがエンドポイントと通信する方法を指定するバインディング。</span><span class="sxs-lookup"><span data-stu-id="42302-108">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
- <span data-ttu-id="42302-109">利用可能なメソッドを指定するためのコントラクト。</span><span class="sxs-lookup"><span data-stu-id="42302-109">A contract that identifies the methods available.</span></span>  
  
 <span data-ttu-id="42302-110">エンドポイントを構成する個々の要素を指定する方法については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42302-110">For descriptions about how to specify these individual parts of an endpoint, see:</span></span>  
  
- [<span data-ttu-id="42302-111">エンドポイント アドレスの指定</span><span class="sxs-lookup"><span data-stu-id="42302-111">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
  
- [<span data-ttu-id="42302-112">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="42302-112">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
  
- [<span data-ttu-id="42302-113">サービスの設計と実装</span><span class="sxs-lookup"><span data-stu-id="42302-113">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="in-this-section"></a><span data-ttu-id="42302-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="42302-114">In This Section</span></span>  
 [<span data-ttu-id="42302-115">エンドポイントの作成の概要</span><span class="sxs-lookup"><span data-stu-id="42302-115">Endpoint Creation Overview</span></span>](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 <span data-ttu-id="42302-116">エンドポイントの構造を説明し、構成やコード内にエンドポイントを定義する方法と、ランタイムによって提供される既定のエンドポイント、バインディング、および動作の使用方法を解説します。</span><span class="sxs-lookup"><span data-stu-id="42302-116">Describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code, as well as how to use the default endpoints, bindings, and behaviors provided by the runtime.</span></span>  
  
 [<span data-ttu-id="42302-117">エンドポイント アドレスの指定</span><span class="sxs-lookup"><span data-stu-id="42302-117">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 <span data-ttu-id="42302-118">エンドポイントを介して WCF サービスとの通信を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42302-118">Describes how communication with a WCF service occurs through endpoints.</span></span>  
  
 [<span data-ttu-id="42302-119">方法: 構成でサービス エンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="42302-119">How to: Create a Service Endpoint in Configuration</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="42302-120">構成でサービス エンドポイントを作成する方法を解説します。</span><span class="sxs-lookup"><span data-stu-id="42302-120">Demonstrates how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="42302-121">方法: コードでサービス エンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="42302-121">How to: Create a Service Endpoint in Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="42302-122">コードでサービス エンドポイントを作成する方法を解説します。</span><span class="sxs-lookup"><span data-stu-id="42302-122">Demonstrates how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="42302-123">メタデータ エンドポイントを公開する</span><span class="sxs-lookup"><span data-stu-id="42302-123">Publishing Metadata Endpoints</span></span>](../../../docs/framework/wcf/publishing-metadata-endpoints.md)  
 <span data-ttu-id="42302-124">構成およびコードでメタデータ エンドポイントを公開することによりってメタデータを公開する方法を解説します。</span><span class="sxs-lookup"><span data-stu-id="42302-124">Demonstrates how to publish metadata by publishing metadata endpoints in configuration and in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="42302-125">参照</span><span class="sxs-lookup"><span data-stu-id="42302-125">Reference</span></span>  
 <xref:System.ServiceModel.EndpointAddress>  
  
## <a name="related-sections"></a><span data-ttu-id="42302-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="42302-126">Related Sections</span></span>  
 [<span data-ttu-id="42302-127">基本的なプログラミング ライフサイクル</span><span class="sxs-lookup"><span data-stu-id="42302-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)
