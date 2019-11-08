---
title: <security> の <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 31ea31ce6880a770c966350cd931e487396c4d63
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736442"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="1a40b-102">\<netNamedPipeBinding > のセキュリティ > の \<</span><span class="sxs-lookup"><span data-stu-id="1a40b-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="1a40b-103">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="1a40b-103">Defines the security settings for a binding.</span></span>  
  
<span data-ttu-id="1a40b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1a40b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1a40b-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="1a40b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1a40b-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="1a40b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="1a40b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netNamedPipeBinding >** ](netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="1a40b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="1a40b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="1a40b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="1a40b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="1a40b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a40b-110">構文</span><span class="sxs-lookup"><span data-stu-id="1a40b-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a40b-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1a40b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1a40b-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a40b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a40b-113">属性</span><span class="sxs-lookup"><span data-stu-id="1a40b-113">Attributes</span></span>  
  
|<span data-ttu-id="1a40b-114">属性</span><span class="sxs-lookup"><span data-stu-id="1a40b-114">Attribute</span></span>|<span data-ttu-id="1a40b-115">説明</span><span class="sxs-lookup"><span data-stu-id="1a40b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1a40b-116">モード</span><span class="sxs-lookup"><span data-stu-id="1a40b-116">mode</span></span>|<span data-ttu-id="1a40b-117">このバインディングに適用されるセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a40b-117">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="1a40b-118">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="1a40b-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1a40b-119">-None: セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1a40b-119">-   None: This disables security.</span></span><br /><span data-ttu-id="1a40b-120">-Transport: セキュリティは、基になるトランスポートベースのセキュリティを使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="1a40b-120">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="1a40b-121">このモードでの保護レベルを制御できます。</span><span class="sxs-lookup"><span data-stu-id="1a40b-121">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="1a40b-122">-既定値は Transport です。</span><span class="sxs-lookup"><span data-stu-id="1a40b-122">-   The default value is Transport.</span></span> <span data-ttu-id="1a40b-123">この属性は <xref:System.ServiceModel.NetNamedPipeSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="1a40b-123">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a40b-124">子要素</span><span class="sxs-lookup"><span data-stu-id="1a40b-124">Child Elements</span></span>  
  
|<span data-ttu-id="1a40b-125">要素</span><span class="sxs-lookup"><span data-stu-id="1a40b-125">Element</span></span>|<span data-ttu-id="1a40b-126">説明</span><span class="sxs-lookup"><span data-stu-id="1a40b-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a40b-127">transport</span><span class="sxs-lookup"><span data-stu-id="1a40b-127">transport</span></span>|<span data-ttu-id="1a40b-128">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="1a40b-128">Defines the security settings for the transport.</span></span> <span data-ttu-id="1a40b-129">この要素は <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="1a40b-129">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1a40b-130">親要素</span><span class="sxs-lookup"><span data-stu-id="1a40b-130">Parent Elements</span></span>  
  
|<span data-ttu-id="1a40b-131">要素</span><span class="sxs-lookup"><span data-stu-id="1a40b-131">Element</span></span>|<span data-ttu-id="1a40b-132">説明</span><span class="sxs-lookup"><span data-stu-id="1a40b-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a40b-133">バインド</span><span class="sxs-lookup"><span data-stu-id="1a40b-133">binding</span></span>|<span data-ttu-id="1a40b-134">[\<netNamedPipeBinding >](netnamedpipebinding.md)のバインド要素。</span><span class="sxs-lookup"><span data-stu-id="1a40b-134">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a40b-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a40b-135">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="1a40b-136">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="1a40b-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1a40b-137">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="1a40b-137">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="1a40b-138">バインディング</span><span class="sxs-lookup"><span data-stu-id="1a40b-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1a40b-139">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="1a40b-139">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1a40b-140">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="1a40b-140">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="1a40b-141">\<binding ></span><span class="sxs-lookup"><span data-stu-id="1a40b-141">\<binding></span></span>](bindings.md)
