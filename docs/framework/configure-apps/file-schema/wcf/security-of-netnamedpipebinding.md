---
title: <security> の <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: cd3ff5d3983283f9b4783912b4b9525c5000df61
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399825"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="d77a2-102">\<netNamedPipeBinding > の\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="d77a2-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="d77a2-103">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="d77a2-103">Defines the security settings for a binding.</span></span>  
  
<span data-ttu-id="d77a2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d77a2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d77a2-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d77a2-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d77a2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="d77a2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="d77a2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netNamedPipeBinding >** ](netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="d77a2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="d77a2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="d77a2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="d77a2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="d77a2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d77a2-110">構文</span><span class="sxs-lookup"><span data-stu-id="d77a2-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d77a2-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d77a2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d77a2-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d77a2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d77a2-113">属性</span><span class="sxs-lookup"><span data-stu-id="d77a2-113">Attributes</span></span>  
  
|<span data-ttu-id="d77a2-114">属性</span><span class="sxs-lookup"><span data-stu-id="d77a2-114">Attribute</span></span>|<span data-ttu-id="d77a2-115">説明</span><span class="sxs-lookup"><span data-stu-id="d77a2-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d77a2-116">モード</span><span class="sxs-lookup"><span data-stu-id="d77a2-116">mode</span></span>|<span data-ttu-id="d77a2-117">このバインディングに適用されるセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d77a2-117">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="d77a2-118">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d77a2-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d77a2-119">存在これにより、セキュリティが無効になります。</span><span class="sxs-lookup"><span data-stu-id="d77a2-119">-   None: This disables security.</span></span><br /><span data-ttu-id="d77a2-120">トランスポートセキュリティは、基になるトランスポートベースのセキュリティを使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="d77a2-120">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="d77a2-121">このモードでは保護レベルを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="d77a2-121">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="d77a2-122">-既定値は Transport です。</span><span class="sxs-lookup"><span data-stu-id="d77a2-122">-   The default value is Transport.</span></span> <span data-ttu-id="d77a2-123">この属性は <xref:System.ServiceModel.NetNamedPipeSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="d77a2-123">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d77a2-124">子要素</span><span class="sxs-lookup"><span data-stu-id="d77a2-124">Child Elements</span></span>  
  
|<span data-ttu-id="d77a2-125">要素</span><span class="sxs-lookup"><span data-stu-id="d77a2-125">Element</span></span>|<span data-ttu-id="d77a2-126">説明</span><span class="sxs-lookup"><span data-stu-id="d77a2-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d77a2-127">transport</span><span class="sxs-lookup"><span data-stu-id="d77a2-127">transport</span></span>|<span data-ttu-id="d77a2-128">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="d77a2-128">Defines the security settings for the transport.</span></span> <span data-ttu-id="d77a2-129">この要素は <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="d77a2-129">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d77a2-130">親要素</span><span class="sxs-lookup"><span data-stu-id="d77a2-130">Parent Elements</span></span>  
  
|<span data-ttu-id="d77a2-131">要素</span><span class="sxs-lookup"><span data-stu-id="d77a2-131">Element</span></span>|<span data-ttu-id="d77a2-132">説明</span><span class="sxs-lookup"><span data-stu-id="d77a2-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d77a2-133">バインド</span><span class="sxs-lookup"><span data-stu-id="d77a2-133">binding</span></span>|<span data-ttu-id="d77a2-134">[ \<NetNamedPipeBinding >](netnamedpipebinding.md)のバインド要素。</span><span class="sxs-lookup"><span data-stu-id="d77a2-134">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d77a2-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="d77a2-135">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="d77a2-136">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="d77a2-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d77a2-137">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="d77a2-137">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="d77a2-138">バインディング</span><span class="sxs-lookup"><span data-stu-id="d77a2-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d77a2-139">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="d77a2-139">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d77a2-140">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="d77a2-140">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d77a2-141">\<binding></span><span class="sxs-lookup"><span data-stu-id="d77a2-141">\<binding></span></span>](../../../misc/binding.md)
