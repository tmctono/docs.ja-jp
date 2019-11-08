---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: c3bae4dfee36e9de62c27bbccecd9a31a5b7d459
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736783"
---
# <a name="compositeduplex"></a><span data-ttu-id="229af-101">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="229af-101">\<compositeDuplex></span></span>
<span data-ttu-id="229af-102">サービスがメッセージをクライアントに返送するためのエンドポイントをクライアントが公開する必要がある場合に使用される、バインド要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="229af-102">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
<span data-ttu-id="229af-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="229af-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="229af-104">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="229af-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="229af-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="229af-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="229af-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="229af-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="229af-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="229af-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="229af-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**compositeDuplex >**</span><span class="sxs-lookup"><span data-stu-id="229af-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="229af-109">構文</span><span class="sxs-lookup"><span data-stu-id="229af-109">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="229af-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="229af-110">Attributes and Elements</span></span>  
 <span data-ttu-id="229af-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="229af-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="229af-112">属性</span><span class="sxs-lookup"><span data-stu-id="229af-112">Attributes</span></span>  
  
|<span data-ttu-id="229af-113">属性</span><span class="sxs-lookup"><span data-stu-id="229af-113">Attribute</span></span>|<span data-ttu-id="229af-114">説明</span><span class="sxs-lookup"><span data-stu-id="229af-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="229af-115">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="229af-115">clientBaseAddress</span></span>|<span data-ttu-id="229af-116">二重モードのバック チャネルのアドレスを設定する URI。</span><span class="sxs-lookup"><span data-stu-id="229af-116">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="229af-117">サービスは、このアドレスを使用して、クライアントへのアクセス、接続の確立を行います。</span><span class="sxs-lookup"><span data-stu-id="229af-117">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="229af-118">この属性が設定されていない場合、既定のアドレス "`full qualified name+default port\TemporaryIndigoAddress\guid`" が生成されます。</span><span class="sxs-lookup"><span data-stu-id="229af-118">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="229af-119">既定値は、 `null`です。</span><span class="sxs-lookup"><span data-stu-id="229af-119">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="229af-120">子要素</span><span class="sxs-lookup"><span data-stu-id="229af-120">Child Elements</span></span>  
 <span data-ttu-id="229af-121">None</span><span class="sxs-lookup"><span data-stu-id="229af-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="229af-122">親要素</span><span class="sxs-lookup"><span data-stu-id="229af-122">Parent Elements</span></span>  
  
|<span data-ttu-id="229af-123">要素</span><span class="sxs-lookup"><span data-stu-id="229af-123">Element</span></span>|<span data-ttu-id="229af-124">説明</span><span class="sxs-lookup"><span data-stu-id="229af-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="229af-125">\<binding ></span><span class="sxs-lookup"><span data-stu-id="229af-125">\<binding></span></span>](bindings.md)|<span data-ttu-id="229af-126">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="229af-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="229af-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="229af-127">Remarks</span></span>  
 <span data-ttu-id="229af-128">たとえば HTTP のように、この構成要素はネイティブでの二重通信を許可しないトランスポートで使用されます。</span><span class="sxs-lookup"><span data-stu-id="229af-128">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="229af-129">これとは対照的に、TCP では、二重通信がネイティブで許可されているので、クライアントにメッセージを返信するためにこのバインディング要素をサービスで使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="229af-129">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="229af-130">クライアントは、サービスのアドレスを公開して、アクセスおよび接続の確立ができるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="229af-130">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="229af-131">このクライアント アドレスは、`clientBaseAddress` 属性によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="229af-131">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="229af-132">ClientBaseAddress がユーザーによって明示的に設定されていない場合は、WCF (Windows Communication Foundation) によって自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="229af-132">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="229af-133">例</span><span class="sxs-lookup"><span data-stu-id="229af-133">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="229af-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="229af-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="229af-135">バインディング</span><span class="sxs-lookup"><span data-stu-id="229af-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="229af-136">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="229af-136">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="229af-137">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="229af-137">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="229af-138">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="229af-138">\<customBinding></span></span>](custombinding.md)
