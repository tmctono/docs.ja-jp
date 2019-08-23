---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: e79b3e1aeecc52bf41ae759dc15ebf1c8211beb2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926066"
---
# <a name="compositeduplex"></a><span data-ttu-id="d08cb-101">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="d08cb-101">\<compositeDuplex></span></span>
<span data-ttu-id="d08cb-102">サービスがメッセージをクライアントに返送するためのエンドポイントをクライアントが公開する必要がある場合に使用される、バインド要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="d08cb-102">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
 <span data-ttu-id="d08cb-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d08cb-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d08cb-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d08cb-104">\<bindings></span></span>  
<span data-ttu-id="d08cb-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d08cb-105">\<customBinding></span></span>  
<span data-ttu-id="d08cb-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="d08cb-106">\<binding></span></span>  
<span data-ttu-id="d08cb-107">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="d08cb-107">\<compositeDuplex></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d08cb-108">構文</span><span class="sxs-lookup"><span data-stu-id="d08cb-108">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d08cb-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d08cb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d08cb-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d08cb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d08cb-111">属性</span><span class="sxs-lookup"><span data-stu-id="d08cb-111">Attributes</span></span>  
  
|<span data-ttu-id="d08cb-112">属性</span><span class="sxs-lookup"><span data-stu-id="d08cb-112">Attribute</span></span>|<span data-ttu-id="d08cb-113">説明</span><span class="sxs-lookup"><span data-stu-id="d08cb-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d08cb-114">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="d08cb-114">clientBaseAddress</span></span>|<span data-ttu-id="d08cb-115">二重モードのバック チャネルのアドレスを設定する URI。</span><span class="sxs-lookup"><span data-stu-id="d08cb-115">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="d08cb-116">サービスは、このアドレスを使用して、クライアントへのアクセス、接続の確立を行います。</span><span class="sxs-lookup"><span data-stu-id="d08cb-116">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="d08cb-117">この属性が設定されていない場合、`full qualified name+default port\TemporaryIndigoAddress\guid`既定のアドレス "" が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d08cb-117">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="d08cb-118">既定値は `null` です。</span><span class="sxs-lookup"><span data-stu-id="d08cb-118">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d08cb-119">子要素</span><span class="sxs-lookup"><span data-stu-id="d08cb-119">Child Elements</span></span>  
 <span data-ttu-id="d08cb-120">なし</span><span class="sxs-lookup"><span data-stu-id="d08cb-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d08cb-121">親要素</span><span class="sxs-lookup"><span data-stu-id="d08cb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d08cb-122">要素</span><span class="sxs-lookup"><span data-stu-id="d08cb-122">Element</span></span>|<span data-ttu-id="d08cb-123">説明</span><span class="sxs-lookup"><span data-stu-id="d08cb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d08cb-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="d08cb-124">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="d08cb-125">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="d08cb-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d08cb-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="d08cb-126">Remarks</span></span>  
 <span data-ttu-id="d08cb-127">たとえば HTTP のように、この構成要素はネイティブでの二重通信を許可しないトランスポートで使用されます。</span><span class="sxs-lookup"><span data-stu-id="d08cb-127">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="d08cb-128">これとは対照的に、TCP では、二重通信がネイティブで許可されているので、クライアントにメッセージを返信するためにこのバインディング要素をサービスで使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d08cb-128">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="d08cb-129">クライアントは、サービスのアドレスを公開して、アクセスおよび接続の確立ができるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d08cb-129">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="d08cb-130">このクライアント アドレスは、`clientBaseAddress` 属性によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="d08cb-130">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="d08cb-131">ClientBaseAddress がユーザーによって明示的に設定されていない場合は、WCF (Windows Communication Foundation) によって自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="d08cb-131">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d08cb-132">例</span><span class="sxs-lookup"><span data-stu-id="d08cb-132">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="d08cb-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="d08cb-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d08cb-134">バインディング</span><span class="sxs-lookup"><span data-stu-id="d08cb-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d08cb-135">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="d08cb-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d08cb-136">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="d08cb-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d08cb-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d08cb-137">\<customBinding></span></span>](custombinding.md)
