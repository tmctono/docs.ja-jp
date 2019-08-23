---
title: <behavior> の <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: f14e80798a9b088508f23d718c8b386286ad65a3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919843"
---
# <a name="behavior-of-endpointbehaviors"></a><span data-ttu-id="49d52-102">\<endpointbehaviors の\<> 動作 ></span><span class="sxs-lookup"><span data-stu-id="49d52-102">\<behavior> of \<endpointBehaviors></span></span>
<span data-ttu-id="49d52-103">`behavior` 要素はエンドポイントの動作設定のコレクションを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="49d52-103">The `behavior` element contains a collection of settings for the behavior of an endpoint.</span></span> <span data-ttu-id="49d52-104">各動作には、それぞれの `name` によってインデックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="49d52-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="49d52-105">エンドポイントは、この名前を使用して各動作にリンクできます。</span><span class="sxs-lookup"><span data-stu-id="49d52-105">Endpoints can link to each behavior through this name.</span></span> <span data-ttu-id="49d52-106">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="49d52-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="49d52-107">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49d52-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="49d52-108">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="49d52-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="49d52-109">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="49d52-109">\<behaviors></span></span>  
<span data-ttu-id="49d52-110">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="49d52-110">\<endpointBehaviors></span></span>  
<span data-ttu-id="49d52-111">\<behavior></span><span class="sxs-lookup"><span data-stu-id="49d52-111">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49d52-112">構文</span><span class="sxs-lookup"><span data-stu-id="49d52-112">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49d52-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="49d52-113">Attributes and Elements</span></span>  
 <span data-ttu-id="49d52-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="49d52-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49d52-115">属性</span><span class="sxs-lookup"><span data-stu-id="49d52-115">Attributes</span></span>  
  
|<span data-ttu-id="49d52-116">属性</span><span class="sxs-lookup"><span data-stu-id="49d52-116">Attribute</span></span>|<span data-ttu-id="49d52-117">説明</span><span class="sxs-lookup"><span data-stu-id="49d52-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="49d52-118">name</span><span class="sxs-lookup"><span data-stu-id="49d52-118">name</span></span>|<span data-ttu-id="49d52-119">動作の構成名を含む一意の文字列。</span><span class="sxs-lookup"><span data-stu-id="49d52-119">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="49d52-120">この値は、要素の識別文字列として機能するため、一意のユーザー定義の文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="49d52-120">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="49d52-121">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="49d52-121">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="49d52-122">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49d52-122">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49d52-123">子要素</span><span class="sxs-lookup"><span data-stu-id="49d52-123">Child Elements</span></span>  
  
|<span data-ttu-id="49d52-124">要素</span><span class="sxs-lookup"><span data-stu-id="49d52-124">Element</span></span>|<span data-ttu-id="49d52-125">説明</span><span class="sxs-lookup"><span data-stu-id="49d52-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49d52-126">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="49d52-126">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="49d52-127">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="49d52-127">Specifies the credentials used to authenticate the client to a service.</span></span>|  
|[<span data-ttu-id="49d52-128">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="49d52-128">\<callbackDebug></span></span>](callbackdebug.md)|<span data-ttu-id="49d52-129">Windows Communication Foundation (WCF) コールバックオブジェクトのサービスデバッグを指定します。</span><span class="sxs-lookup"><span data-stu-id="49d52-129">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>|  
|[<span data-ttu-id="49d52-130">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="49d52-130">\<callbackTimeouts></span></span>](callbacktimeouts.md)|<span data-ttu-id="49d52-131">クライアント コールバックのタイムアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="49d52-131">Specifies the timeout for the client callback.</span></span>|  
|[<span data-ttu-id="49d52-132">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="49d52-132">\<clientVia></span></span>](clientvia.md)|<span data-ttu-id="49d52-133">メッセージの経路を指定します。</span><span class="sxs-lookup"><span data-stu-id="49d52-133">Specifies the route a message should take.</span></span>|  
|[<span data-ttu-id="49d52-134">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="49d52-134">\<dataContractSerializer></span></span>](datacontractserializer.md)|<span data-ttu-id="49d52-135">DataContractSerializer 用の構成データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="49d52-135">Contains configuration data for the DataContractSerializer.</span></span>|  
|[<span data-ttu-id="49d52-136">\<dispatcherSynchronization ></span><span class="sxs-lookup"><span data-stu-id="49d52-136">\<dispatcherSynchronization></span></span>](dispatchersynchronization.md)|<span data-ttu-id="49d52-137">サービスが非同期に応答を返すことができるようにするエンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="49d52-137">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>|  
|[<span data-ttu-id="49d52-138">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="49d52-138">\<enableWebScript></span></span>](enablewebscript.md)|<span data-ttu-id="49d52-139">ASP.NET AJAX Web ページからサービスを使用できるようにするエンドポイントの動作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="49d52-139">Enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span> <span data-ttu-id="49d52-140">この動作は、 \<webHttpBinding > 標準バインディング、 \<または webMessageEncoding > binding 要素と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49d52-140">The behavior should only be used in conjunction with either the \<webHttpBinding> standard binding, or the \<webMessageEncoding> binding element.</span></span>|  
|[<span data-ttu-id="49d52-141">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="49d52-141">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="49d52-142">エンドポイントのさまざまな探索設定を指定します (探索可能性、スコープ、メタデータに対するカスタム拡張など)。</span><span class="sxs-lookup"><span data-stu-id="49d52-142">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
|[<span data-ttu-id="49d52-143">\<soapProcessing ></span><span class="sxs-lookup"><span data-stu-id="49d52-143">\<soapProcessing></span></span>](soapprocessing.md)|<span data-ttu-id="49d52-144">異なるバインディングの種類およびメッセージ バージョンの間でメッセージのマーシャリングに使用されるクライアント エンドポイントの動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="49d52-144">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>|  
|[<span data-ttu-id="49d52-145">\<synchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="49d52-145">\<synchronousReceive></span></span>](synchronousreceive-element.md)|<span data-ttu-id="49d52-146">サービスまたはクライアント アプリケーションでメッセージを受信する場合のランタイム動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="49d52-146">Specifies run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="49d52-147">属性や子要素はありません。</span><span class="sxs-lookup"><span data-stu-id="49d52-147">It does not have any attributes or child elements.</span></span>|  
|[<span data-ttu-id="49d52-148">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="49d52-148">\<transactedBatching></span></span>](transactedbatching.md)|<span data-ttu-id="49d52-149">受信操作でトランザクション バッチがサポートされるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="49d52-149">Specifies whether transaction batching is supported for receive operations.</span></span>|  
|[<span data-ttu-id="49d52-150">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="49d52-150">\<webHttp></span></span>](webhttp.md)|<span data-ttu-id="49d52-151">構成によってエンドポイントに WebHttpBehavior を指定します。</span><span class="sxs-lookup"><span data-stu-id="49d52-151">Specifies the WebHttpBehavior on an endpoint through configuration.</span></span> <span data-ttu-id="49d52-152">この動作は、 \<webHttpBinding > の標準バインディングと組み合わせて使用すると、WCF サービスの Web プログラミングモデルを有効にします。</span><span class="sxs-lookup"><span data-stu-id="49d52-152">This behavior, when used in conjunction with the \<webHttpBinding> standard binding, enables the Web programming model for a WCF service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49d52-153">親要素</span><span class="sxs-lookup"><span data-stu-id="49d52-153">Parent Elements</span></span>  
  
|<span data-ttu-id="49d52-154">要素</span><span class="sxs-lookup"><span data-stu-id="49d52-154">Element</span></span>|<span data-ttu-id="49d52-155">説明</span><span class="sxs-lookup"><span data-stu-id="49d52-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49d52-156">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="49d52-156">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="49d52-157">エンドポイント動作要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="49d52-157">A collection of endpoint behavior elements.</span></span>|
