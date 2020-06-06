---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: c3bae4dfee36e9de62c27bbccecd9a31a5b7d459
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736783"
---
# \<compositeDuplex>
<span data-ttu-id="b75c8-101">サービスがメッセージをクライアントに返送するためのエンドポイントをクライアントが公開する必要がある場合に使用される、バインド要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="b75c8-101">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**  
  
## <a name="syntax"></a><span data-ttu-id="b75c8-102">構文</span><span class="sxs-lookup"><span data-stu-id="b75c8-102">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b75c8-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b75c8-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b75c8-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b75c8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b75c8-105">属性</span><span class="sxs-lookup"><span data-stu-id="b75c8-105">Attributes</span></span>  
  
|<span data-ttu-id="b75c8-106">属性</span><span class="sxs-lookup"><span data-stu-id="b75c8-106">Attribute</span></span>|<span data-ttu-id="b75c8-107">説明</span><span class="sxs-lookup"><span data-stu-id="b75c8-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b75c8-108">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="b75c8-108">clientBaseAddress</span></span>|<span data-ttu-id="b75c8-109">二重モードのバック チャネルのアドレスを設定する URI。</span><span class="sxs-lookup"><span data-stu-id="b75c8-109">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="b75c8-110">サービスは、このアドレスを使用して、クライアントへのアクセス、接続の確立を行います。</span><span class="sxs-lookup"><span data-stu-id="b75c8-110">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="b75c8-111">この属性が設定されていない場合、既定のアドレス " `full qualified name+default port\TemporaryIndigoAddress\guid` " が生成されます。</span><span class="sxs-lookup"><span data-stu-id="b75c8-111">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="b75c8-112">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="b75c8-112">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b75c8-113">子要素</span><span class="sxs-lookup"><span data-stu-id="b75c8-113">Child Elements</span></span>  
 <span data-ttu-id="b75c8-114">なし</span><span class="sxs-lookup"><span data-stu-id="b75c8-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b75c8-115">親要素</span><span class="sxs-lookup"><span data-stu-id="b75c8-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b75c8-116">要素</span><span class="sxs-lookup"><span data-stu-id="b75c8-116">Element</span></span>|<span data-ttu-id="b75c8-117">Description</span><span class="sxs-lookup"><span data-stu-id="b75c8-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="b75c8-118">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="b75c8-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b75c8-119">解説</span><span class="sxs-lookup"><span data-stu-id="b75c8-119">Remarks</span></span>  
 <span data-ttu-id="b75c8-120">たとえば HTTP のように、この構成要素はネイティブでの二重通信を許可しないトランスポートで使用されます。</span><span class="sxs-lookup"><span data-stu-id="b75c8-120">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="b75c8-121">これとは対照的に、TCP では、二重通信がネイティブで許可されているので、クライアントにメッセージを返信するためにこのバインディング要素をサービスで使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b75c8-121">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="b75c8-122">クライアントは、サービスのアドレスを公開して、アクセスおよび接続の確立ができるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b75c8-122">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="b75c8-123">このクライアント アドレスは、`clientBaseAddress` 属性によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="b75c8-123">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="b75c8-124">ClientBaseAddress がユーザーによって明示的に設定されていない場合は、WCF (Windows Communication Foundation) によって自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="b75c8-124">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b75c8-125">例</span><span class="sxs-lookup"><span data-stu-id="b75c8-125">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="b75c8-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="b75c8-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b75c8-127">バインド</span><span class="sxs-lookup"><span data-stu-id="b75c8-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b75c8-128">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="b75c8-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b75c8-129">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="b75c8-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
