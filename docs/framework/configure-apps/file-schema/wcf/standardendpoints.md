---
title: <standardEndpoints>
ms.date: 03/30/2017
ms.assetid: d62153d7-a6e6-462a-a784-cca61e9c2ba1
ms.openlocfilehash: 76a5303650c4e2b2887d29f511d3088c78b58fe2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399508"
---
# \<standardEndpoints>
<span data-ttu-id="dfc41-101">この構成セクションでは、再使用可能な構成済みのエンドポイントである標準エンドポイントのコレクションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="dfc41-101">This configuration section allows you to define a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="dfc41-102">標準エンドポイントは、固定値に設定されたアドレス、バインディング、およびコントラクトの 1 つ以上の属性を持ちます。</span><span class="sxs-lookup"><span data-stu-id="dfc41-102">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="dfc41-103">たとえば、探索エンドポイントでは、コントラクトが固定されています。</span><span class="sxs-lookup"><span data-stu-id="dfc41-103">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="dfc41-104">標準エンドポイントを使用して、カスタム バインドの定義と同様に新しいプロパティを指定して、サービス エンドポイントを拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="dfc41-104">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoints>**  
  
## <a name="syntax"></a><span data-ttu-id="dfc41-105">構文</span><span class="sxs-lookup"><span data-stu-id="dfc41-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfc41-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dfc41-106">Attributes and Elements</span></span>  
 <span data-ttu-id="dfc41-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfc41-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfc41-108">属性</span><span class="sxs-lookup"><span data-stu-id="dfc41-108">Attributes</span></span>  
 <span data-ttu-id="dfc41-109">なし。</span><span class="sxs-lookup"><span data-stu-id="dfc41-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dfc41-110">子要素</span><span class="sxs-lookup"><span data-stu-id="dfc41-110">Child Elements</span></span>  
  
|<span data-ttu-id="dfc41-111">要素</span><span class="sxs-lookup"><span data-stu-id="dfc41-111">Element</span></span>|<span data-ttu-id="dfc41-112">説明</span><span class="sxs-lookup"><span data-stu-id="dfc41-112">Description</span></span>|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|<span data-ttu-id="dfc41-113">固定アナウンス コントラクトが含まれた標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="dfc41-113">Defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="dfc41-114">サービスは、サービスが開いたとき、または閉じたときにオンラインおよびオフラインのアナウンス メッセージを送信することによって、その可用性をアナウンスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dfc41-114">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="dfc41-115">Windows Communication Foundation (WCF) サービスでは、要素内のアナウンスエンドポイントを指定 [\<serviceDiscovery>](servicediscovery.md) し、アナウンスメント Ementclient を使用してアナウンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfc41-115">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="dfc41-116">他のサービスからのアナウンスをリッスンするクライアントは、実際には WCF サービスとして機能します。そのため、「」セクションで、そのクライアントのアナウンスエンドポイントを構成する必要があり [\<services>](services.md) ます。</span><span class="sxs-lookup"><span data-stu-id="dfc41-116">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|<span data-ttu-id="dfc41-117">固定探索コントラクトが含まれた標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="dfc41-117">Defines a standard endpoint with a fixed discovery contract.</span></span> <span data-ttu-id="dfc41-118">サービスの構成に追加すると、この要素により、探索メッセージをリッスンする場所が指定されます。</span><span class="sxs-lookup"><span data-stu-id="dfc41-118">When added to the service configuration, it specifies where to listen for the discovery messages.</span></span> <span data-ttu-id="dfc41-119">クライアントの構成に追加すると、この要素により、探索クエリの送信先となる場所が指定されます。</span><span class="sxs-lookup"><span data-stu-id="dfc41-119">When added to the client configuration it specifies where to send the discovery queries.</span></span>|  
|[\<dynamicEndpoint>](dynamicendpoint.md)|<span data-ttu-id="dfc41-120">この構成要素は、アプリケーションが、実行時に動的にエンドポイント アドレスを検索するクライアント プログラムとして機能するための情報を格納する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="dfc41-120">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
|[\<mexEndpoint>](mexendpoint.md)|<span data-ttu-id="dfc41-121">固定 IMetadataExchange コントラクトが含まれた標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="dfc41-121">Defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="dfc41-122">IMetadataExchange はすべてのメタデータ交換エンドポイントでコントラクトとして指定されるため、独自のエンドポイントを定義せずにこの標準エンドポイントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dfc41-122">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>|  
|[\<udpAnnouncementEndpoint>](udpannouncementendpoint.md)|<span data-ttu-id="dfc41-123">サービスが UDP バインディングでアナウンス メッセージを送信するために使用する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="dfc41-123">Defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="dfc41-124">これには固定コントラクトがあり、2 つの探索のバージョンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="dfc41-124">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="dfc41-125">また、WS-Discovery の仕様 (WS-Discovery April 2005 または WS-Discovery V1.1) に規定された固定 UDP バインディングと既定のアドレスも備えています。</span><span class="sxs-lookup"><span data-stu-id="dfc41-125">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="dfc41-126">アナウンス メッセージの送受信に使用するマルチキャスト アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dfc41-126">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>|  
|[\<udpDiscoveryEndpoint>](udpdiscoveryendpoint.md)|<span data-ttu-id="dfc41-127">UDP マルチキャスト バインディングを使用した探索操作用に事前に構成される標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="dfc41-127">Defines a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="dfc41-128">このエンドポイントには固定コントラクトがあり、WS-Discovery プロトコルの 2 つのバージョンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="dfc41-128">This endpoint has a fixed contract and supports two WS-Discovery protocol versions.</span></span> <span data-ttu-id="dfc41-129">また、WS-Discovery の仕様 (WS-Discovery April 2005 または WS-Discovery V1.1) に規定された固定 UDP バインディングと既定のアドレスも備えています。</span><span class="sxs-lookup"><span data-stu-id="dfc41-129">In addition, it has a fixed UDP binding and a default address as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery V1.1).</span></span>|  
|[\<webHttpEndpoint>](webhttpendpoint.md)|<span data-ttu-id="dfc41-130">動作を自動的に追加する固定バインドを持つ標準エンドポイントを定義し [\<webHttpBinding>](webhttpbinding.md) [\<webHttp>](webhttp.md) ます。</span><span class="sxs-lookup"><span data-stu-id="dfc41-130">Defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="dfc41-131">このエンドポイントは、REST サービスを作成する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="dfc41-131">Use this endpoint when writing a REST service.</span></span>|  
|[\<webScriptEndpoint>](webscriptendpoint.md)|<span data-ttu-id="dfc41-132">動作を自動的に追加する固定バインドを持つ標準エンドポイントを定義し [\<webHttpBinding>](webhttpbinding.md) [\<enableWebScript>](enablewebscript.md) ます。</span><span class="sxs-lookup"><span data-stu-id="dfc41-132">Defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="dfc41-133">このエンドポイントは、ASP.NET AJAX アプリケーションから呼び出されるサービスを作成する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="dfc41-133">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>|  
|[\<workflowControlEndpoint>](workflowcontrolendpoint.md)|<span data-ttu-id="dfc41-134">ワークフロー インスタンスの実行の制御 (作成、実行、保留、終了など) に使用する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="dfc41-134">Defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dfc41-135">親要素</span><span class="sxs-lookup"><span data-stu-id="dfc41-135">Parent Elements</span></span>  
  
|<span data-ttu-id="dfc41-136">要素</span><span class="sxs-lookup"><span data-stu-id="dfc41-136">Element</span></span>|<span data-ttu-id="dfc41-137">説明</span><span class="sxs-lookup"><span data-stu-id="dfc41-137">Description</span></span>|  
|-------------|-----------------|  
|\<system.ServiceModel>|<span data-ttu-id="dfc41-138">すべての WCF 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="dfc41-138">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dfc41-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfc41-139">See also</span></span>

- [<span data-ttu-id="dfc41-140">標準エンドポイント</span><span class="sxs-lookup"><span data-stu-id="dfc41-140">Standard Endpoints</span></span>](../../../wcf/feature-details/standard-endpoints.md)
