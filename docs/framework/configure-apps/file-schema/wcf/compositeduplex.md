---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: 1e5ecc2b937aa0cdb159a6cbd1222fe6d4af79fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159849"
---
# <a name="compositeduplex"></a><span data-ttu-id="0aecb-101">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="0aecb-101">\<compositeDuplex></span></span>
<span data-ttu-id="0aecb-102">サービスがメッセージをクライアントに返送するためのエンドポイントをクライアントが公開する必要がある場合に使用される、バインド要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="0aecb-102">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
 <span data-ttu-id="0aecb-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0aecb-103">\<system.serviceModel></span></span>  
<span data-ttu-id="0aecb-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0aecb-104">\<bindings></span></span>  
<span data-ttu-id="0aecb-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0aecb-105">\<customBinding></span></span>  
<span data-ttu-id="0aecb-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="0aecb-106">\<binding></span></span>  
<span data-ttu-id="0aecb-107">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="0aecb-107">\<compositeDuplex></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aecb-108">構文</span><span class="sxs-lookup"><span data-stu-id="0aecb-108">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0aecb-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0aecb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0aecb-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0aecb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0aecb-111">属性</span><span class="sxs-lookup"><span data-stu-id="0aecb-111">Attributes</span></span>  
  
|<span data-ttu-id="0aecb-112">属性</span><span class="sxs-lookup"><span data-stu-id="0aecb-112">Attribute</span></span>|<span data-ttu-id="0aecb-113">説明</span><span class="sxs-lookup"><span data-stu-id="0aecb-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0aecb-114">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="0aecb-114">clientBaseAddress</span></span>|<span data-ttu-id="0aecb-115">二重モードのバック チャネルのアドレスを設定する URI。</span><span class="sxs-lookup"><span data-stu-id="0aecb-115">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="0aecb-116">サービスは、このアドレスを使用して、クライアントへのアクセス、接続の確立を行います。</span><span class="sxs-lookup"><span data-stu-id="0aecb-116">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="0aecb-117">この属性が設定しないかどうか、既定のアドレスを"`full qualified name+default port\TemporaryIndigoAddress\guid`"が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0aecb-117">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="0aecb-118">既定値は `null` です。</span><span class="sxs-lookup"><span data-stu-id="0aecb-118">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0aecb-119">子要素</span><span class="sxs-lookup"><span data-stu-id="0aecb-119">Child Elements</span></span>  
 <span data-ttu-id="0aecb-120">なし</span><span class="sxs-lookup"><span data-stu-id="0aecb-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0aecb-121">親要素</span><span class="sxs-lookup"><span data-stu-id="0aecb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0aecb-122">要素</span><span class="sxs-lookup"><span data-stu-id="0aecb-122">Element</span></span>|<span data-ttu-id="0aecb-123">説明</span><span class="sxs-lookup"><span data-stu-id="0aecb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0aecb-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="0aecb-124">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="0aecb-125">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="0aecb-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0aecb-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="0aecb-126">Remarks</span></span>  
 <span data-ttu-id="0aecb-127">たとえば HTTP のように、この構成要素はネイティブでの二重通信を許可しないトランスポートで使用されます。</span><span class="sxs-lookup"><span data-stu-id="0aecb-127">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="0aecb-128">これとは対照的に、TCP では、二重通信がネイティブで許可されているので、クライアントにメッセージを返信するためにこのバインディング要素をサービスで使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0aecb-128">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="0aecb-129">クライアントは、サービスのアドレスを公開して、アクセスおよび接続の確立ができるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0aecb-129">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="0aecb-130">このクライアント アドレスは、`clientBaseAddress` 属性によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="0aecb-130">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="0aecb-131">ClientBaseAddress がユーザーによって明示的に設定されていない場合は、WCF (Windows Communication Foundation) によって自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="0aecb-131">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0aecb-132">例</span><span class="sxs-lookup"><span data-stu-id="0aecb-132">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="0aecb-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="0aecb-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0aecb-134">バインディング</span><span class="sxs-lookup"><span data-stu-id="0aecb-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="0aecb-135">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="0aecb-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0aecb-136">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="0aecb-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0aecb-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0aecb-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
