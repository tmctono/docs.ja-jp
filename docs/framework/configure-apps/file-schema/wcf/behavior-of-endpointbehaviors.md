---
title: <behavior> の <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: 489678a5adeae3965acae90a847c4b087478354d
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140813"
---
# <a name="behavior-of-endpointbehaviors"></a><span data-ttu-id="1558b-102">\<endpointBehaviors の \<動作 > ></span><span class="sxs-lookup"><span data-stu-id="1558b-102">\<behavior> of \<endpointBehaviors></span></span>
<span data-ttu-id="1558b-103">エンドポイントの動作設定のコレクションを含む `behavior` 要素。</span><span class="sxs-lookup"><span data-stu-id="1558b-103">The `behavior` element contains a collection of settings for the behavior of an endpoint.</span></span> <span data-ttu-id="1558b-104">各動作には、それぞれの `name` によってインデックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="1558b-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="1558b-105">エンドポイントは、この名前を使用して各動作にリンクできます。</span><span class="sxs-lookup"><span data-stu-id="1558b-105">Endpoints can link to each behavior through this name.</span></span> <span data-ttu-id="1558b-106">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1558b-106">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="1558b-107">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1558b-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
<span data-ttu-id="1558b-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1558b-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1558b-109">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="1558b-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1558b-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<の動作**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1558b-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="1558b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1558b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="1558b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**動作 >**</span><span class="sxs-lookup"><span data-stu-id="1558b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1558b-113">構文</span><span class="sxs-lookup"><span data-stu-id="1558b-113">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1558b-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1558b-114">Attributes and Elements</span></span>  
 <span data-ttu-id="1558b-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1558b-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1558b-116">属性</span><span class="sxs-lookup"><span data-stu-id="1558b-116">Attributes</span></span>  
  
|<span data-ttu-id="1558b-117">属性</span><span class="sxs-lookup"><span data-stu-id="1558b-117">Attribute</span></span>|<span data-ttu-id="1558b-118">説明</span><span class="sxs-lookup"><span data-stu-id="1558b-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1558b-119">name</span><span class="sxs-lookup"><span data-stu-id="1558b-119">name</span></span>|<span data-ttu-id="1558b-120">動作の構成名を含む一意の文字列。</span><span class="sxs-lookup"><span data-stu-id="1558b-120">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="1558b-121">この値は、要素の識別文字列として機能するため、一意のユーザー定義の文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1558b-121">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="1558b-122">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1558b-122">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="1558b-123">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1558b-123">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1558b-124">子要素</span><span class="sxs-lookup"><span data-stu-id="1558b-124">Child Elements</span></span>  
  
|<span data-ttu-id="1558b-125">要素</span><span class="sxs-lookup"><span data-stu-id="1558b-125">Element</span></span>|<span data-ttu-id="1558b-126">説明</span><span class="sxs-lookup"><span data-stu-id="1558b-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1558b-127">clientCredentials > の \<</span><span class="sxs-lookup"><span data-stu-id="1558b-127">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="1558b-128">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="1558b-128">Specifies the credentials used to authenticate the client to a service.</span></span>|  
|[<span data-ttu-id="1558b-129">\<のデバッグ ></span><span class="sxs-lookup"><span data-stu-id="1558b-129">\<callbackDebug></span></span>](callbackdebug.md)|<span data-ttu-id="1558b-130">Windows Communication Foundation (WCF) コールバックオブジェクトのサービスデバッグを指定します。</span><span class="sxs-lookup"><span data-stu-id="1558b-130">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>|  
|[<span data-ttu-id="1558b-131">\<の > のタイムアウト</span><span class="sxs-lookup"><span data-stu-id="1558b-131">\<callbackTimeouts></span></span>](callbacktimeouts.md)|<span data-ttu-id="1558b-132">クライアント コールバックのタイムアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="1558b-132">Specifies the timeout for the client callback.</span></span>|  
|[<span data-ttu-id="1558b-133">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="1558b-133">\<clientVia></span></span>](clientvia.md)|<span data-ttu-id="1558b-134">メッセージの経路を指定します。</span><span class="sxs-lookup"><span data-stu-id="1558b-134">Specifies the route a message should take.</span></span>|  
|[<span data-ttu-id="1558b-135">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="1558b-135">\<dataContractSerializer></span></span>](datacontractserializer.md)|<span data-ttu-id="1558b-136">DataContractSerializer 用の構成データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1558b-136">Contains configuration data for the DataContractSerializer.</span></span>|  
|[<span data-ttu-id="1558b-137">\<dispatcherSynchronization ></span><span class="sxs-lookup"><span data-stu-id="1558b-137">\<dispatcherSynchronization></span></span>](dispatchersynchronization.md)|<span data-ttu-id="1558b-138">サービスが非同期に応答を返すことができるようにするエンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="1558b-138">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>|  
|[<span data-ttu-id="1558b-139">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="1558b-139">\<enableWebScript></span></span>](enablewebscript.md)|<span data-ttu-id="1558b-140">ASP.NET AJAX Web ページからサービスを使用できるようにするエンドポイントの動作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1558b-140">Enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span> <span data-ttu-id="1558b-141">この動作は、\<webHttpBinding > 標準バインディング、または \<webMessageEncoding > binding 要素と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1558b-141">The behavior should only be used in conjunction with either the \<webHttpBinding> standard binding, or the \<webMessageEncoding> binding element.</span></span>|  
|[<span data-ttu-id="1558b-142">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="1558b-142">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="1558b-143">エンドポイントのさまざまな探索設定を指定します (探索可能性、スコープ、メタデータに対するカスタム拡張など)。</span><span class="sxs-lookup"><span data-stu-id="1558b-143">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
|[<span data-ttu-id="1558b-144">soapProcessing > の \<</span><span class="sxs-lookup"><span data-stu-id="1558b-144">\<soapProcessing></span></span>](soapprocessing.md)|<span data-ttu-id="1558b-145">異なるバインディングの種類およびメッセージ バージョンの間でメッセージのマーシャリングに使用されるクライアント エンドポイントの動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="1558b-145">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>|  
|[<span data-ttu-id="1558b-146">\<synchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="1558b-146">\<synchronousReceive></span></span>](synchronousreceive-element.md)|<span data-ttu-id="1558b-147">サービスまたはクライアント アプリケーションでメッセージを受信する場合のランタイム動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="1558b-147">Specifies run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="1558b-148">属性や子要素はありません。</span><span class="sxs-lookup"><span data-stu-id="1558b-148">It does not have any attributes or child elements.</span></span>|  
|[<span data-ttu-id="1558b-149">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="1558b-149">\<transactedBatching></span></span>](transactedbatching.md)|<span data-ttu-id="1558b-150">受信操作でトランザクション バッチがサポートされるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1558b-150">Specifies whether transaction batching is supported for receive operations.</span></span>|  
|[<span data-ttu-id="1558b-151">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="1558b-151">\<webHttp></span></span>](webhttp.md)|<span data-ttu-id="1558b-152">構成によってエンドポイントに WebHttpBehavior を指定します。</span><span class="sxs-lookup"><span data-stu-id="1558b-152">Specifies the WebHttpBehavior on an endpoint through configuration.</span></span> <span data-ttu-id="1558b-153">この動作は、\<webHttpBinding > 標準バインドと組み合わせて使用すると、WCF サービスの Web プログラミングモデルが有効になります。</span><span class="sxs-lookup"><span data-stu-id="1558b-153">This behavior, when used in conjunction with the \<webHttpBinding> standard binding, enables the Web programming model for a WCF service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1558b-154">親要素</span><span class="sxs-lookup"><span data-stu-id="1558b-154">Parent Elements</span></span>  
  
|<span data-ttu-id="1558b-155">要素</span><span class="sxs-lookup"><span data-stu-id="1558b-155">Element</span></span>|<span data-ttu-id="1558b-156">説明</span><span class="sxs-lookup"><span data-stu-id="1558b-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1558b-157">endpointBehaviors > の \<</span><span class="sxs-lookup"><span data-stu-id="1558b-157">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="1558b-158">エンドポイント動作要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="1558b-158">A collection of endpoint behavior elements.</span></span>|
