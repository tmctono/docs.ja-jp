---
title: <behavior> の <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: 489678a5adeae3965acae90a847c4b087478354d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140813"
---
# <a name="behavior-of-endpointbehaviors"></a><span data-ttu-id="df2db-102">\<behavior> の \<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="df2db-102">\<behavior> of \<endpointBehaviors></span></span>
<span data-ttu-id="df2db-103">エンドポイントの動作設定のコレクションを含む `behavior` 要素。</span><span class="sxs-lookup"><span data-stu-id="df2db-103">The `behavior` element contains a collection of settings for the behavior of an endpoint.</span></span> <span data-ttu-id="df2db-104">各動作には、それぞれの `name` によってインデックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="df2db-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="df2db-105">エンドポイントは、この名前を使用して各動作にリンクできます。</span><span class="sxs-lookup"><span data-stu-id="df2db-105">Endpoints can link to each behavior through this name.</span></span> <span data-ttu-id="df2db-106">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="df2db-106">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="df2db-107">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df2db-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="df2db-108">構文</span><span class="sxs-lookup"><span data-stu-id="df2db-108">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df2db-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="df2db-109">Attributes and Elements</span></span>  
 <span data-ttu-id="df2db-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="df2db-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df2db-111">属性</span><span class="sxs-lookup"><span data-stu-id="df2db-111">Attributes</span></span>  
  
|<span data-ttu-id="df2db-112">属性</span><span class="sxs-lookup"><span data-stu-id="df2db-112">Attribute</span></span>|<span data-ttu-id="df2db-113">説明</span><span class="sxs-lookup"><span data-stu-id="df2db-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df2db-114">name</span><span class="sxs-lookup"><span data-stu-id="df2db-114">name</span></span>|<span data-ttu-id="df2db-115">動作の構成名を含む一意の文字列。</span><span class="sxs-lookup"><span data-stu-id="df2db-115">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="df2db-116">この値は、要素の識別文字列として機能するため、一意のユーザー定義の文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2db-116">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="df2db-117">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="df2db-117">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="df2db-118">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df2db-118">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df2db-119">子要素</span><span class="sxs-lookup"><span data-stu-id="df2db-119">Child Elements</span></span>  
  
|<span data-ttu-id="df2db-120">要素</span><span class="sxs-lookup"><span data-stu-id="df2db-120">Element</span></span>|<span data-ttu-id="df2db-121">Description</span><span class="sxs-lookup"><span data-stu-id="df2db-121">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="df2db-122">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="df2db-122">Specifies the credentials used to authenticate the client to a service.</span></span>|  
|[\<callbackDebug>](callbackdebug.md)|<span data-ttu-id="df2db-123">Windows Communication Foundation (WCF) コールバックオブジェクトのサービスデバッグを指定します。</span><span class="sxs-lookup"><span data-stu-id="df2db-123">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>|  
|[\<callbackTimeouts>](callbacktimeouts.md)|<span data-ttu-id="df2db-124">クライアント コールバックのタイムアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="df2db-124">Specifies the timeout for the client callback.</span></span>|  
|[\<clientVia>](clientvia.md)|<span data-ttu-id="df2db-125">メッセージの経路を指定します。</span><span class="sxs-lookup"><span data-stu-id="df2db-125">Specifies the route a message should take.</span></span>|  
|[\<dataContractSerializer>](datacontractserializer.md)|<span data-ttu-id="df2db-126">DataContractSerializer 用の構成データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df2db-126">Contains configuration data for the DataContractSerializer.</span></span>|  
|[\<dispatcherSynchronization>](dispatchersynchronization.md)|<span data-ttu-id="df2db-127">サービスが非同期に応答を返すことができるようにするエンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="df2db-127">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>|  
|[\<enableWebScript>](enablewebscript.md)|<span data-ttu-id="df2db-128">ASP.NET AJAX Web ページからサービスを使用できるようにするエンドポイントの動作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="df2db-128">Enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span> <span data-ttu-id="df2db-129">動作は、 \<webHttpBinding> 標準バインディングまたはバインディング要素と組み合わせて使用する必要があり \<webMessageEncoding> ます。</span><span class="sxs-lookup"><span data-stu-id="df2db-129">The behavior should only be used in conjunction with either the \<webHttpBinding> standard binding, or the \<webMessageEncoding> binding element.</span></span>|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="df2db-130">エンドポイントのさまざまな探索設定を指定します (探索可能性、スコープ、メタデータに対するカスタム拡張など)。</span><span class="sxs-lookup"><span data-stu-id="df2db-130">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
|[\<soapProcessing>](soapprocessing.md)|<span data-ttu-id="df2db-131">異なるバインディングの種類およびメッセージ バージョンの間でメッセージのマーシャリングに使用されるクライアント エンドポイントの動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="df2db-131">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>|  
|[\<synchronousReceive>](synchronousreceive-element.md)|<span data-ttu-id="df2db-132">サービスまたはクライアント アプリケーションでメッセージを受信する場合のランタイム動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="df2db-132">Specifies run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="df2db-133">属性や子要素はありません。</span><span class="sxs-lookup"><span data-stu-id="df2db-133">It does not have any attributes or child elements.</span></span>|  
|[\<transactedBatching>](transactedbatching.md)|<span data-ttu-id="df2db-134">受信操作でトランザクション バッチがサポートされるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="df2db-134">Specifies whether transaction batching is supported for receive operations.</span></span>|  
|[\<webHttp>](webhttp.md)|<span data-ttu-id="df2db-135">構成によってエンドポイントに WebHttpBehavior を指定します。</span><span class="sxs-lookup"><span data-stu-id="df2db-135">Specifies the WebHttpBehavior on an endpoint through configuration.</span></span> <span data-ttu-id="df2db-136">この動作は、標準バインディングと組み合わせて使用すると \<webHttpBinding> 、WCF サービスの Web プログラミングモデルを有効にします。</span><span class="sxs-lookup"><span data-stu-id="df2db-136">This behavior, when used in conjunction with the \<webHttpBinding> standard binding, enables the Web programming model for a WCF service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df2db-137">親要素</span><span class="sxs-lookup"><span data-stu-id="df2db-137">Parent Elements</span></span>  
  
|<span data-ttu-id="df2db-138">要素</span><span class="sxs-lookup"><span data-stu-id="df2db-138">Element</span></span>|<span data-ttu-id="df2db-139">Description</span><span class="sxs-lookup"><span data-stu-id="df2db-139">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|<span data-ttu-id="df2db-140">エンドポイント動作要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="df2db-140">A collection of endpoint behavior elements.</span></span>|
