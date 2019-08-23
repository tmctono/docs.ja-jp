---
title: <security> の <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 0996a98438dc344d96d640abced52ac99709adbf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936674"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="db27e-102">\<netNamedPipeBinding > の\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="db27e-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="db27e-103">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="db27e-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="db27e-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="db27e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="db27e-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="db27e-105">\<bindings></span></span>  
<span data-ttu-id="db27e-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="db27e-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="db27e-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="db27e-107">\<binding></span></span>  
<span data-ttu-id="db27e-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="db27e-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db27e-109">構文</span><span class="sxs-lookup"><span data-stu-id="db27e-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db27e-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="db27e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="db27e-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="db27e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db27e-112">属性</span><span class="sxs-lookup"><span data-stu-id="db27e-112">Attributes</span></span>  
  
|<span data-ttu-id="db27e-113">属性</span><span class="sxs-lookup"><span data-stu-id="db27e-113">Attribute</span></span>|<span data-ttu-id="db27e-114">説明</span><span class="sxs-lookup"><span data-stu-id="db27e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db27e-115">モード</span><span class="sxs-lookup"><span data-stu-id="db27e-115">mode</span></span>|<span data-ttu-id="db27e-116">このバインディングに適用されるセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="db27e-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="db27e-117">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="db27e-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="db27e-118">存在これにより、セキュリティが無効になります。</span><span class="sxs-lookup"><span data-stu-id="db27e-118">-   None: This disables security.</span></span><br /><span data-ttu-id="db27e-119">トランスポートセキュリティは、基になるトランスポートベースのセキュリティを使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="db27e-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="db27e-120">このモードでは保護レベルを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="db27e-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="db27e-121">-既定値は Transport です。</span><span class="sxs-lookup"><span data-stu-id="db27e-121">-   The default value is Transport.</span></span> <span data-ttu-id="db27e-122">この属性は <xref:System.ServiceModel.NetNamedPipeSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="db27e-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db27e-123">子要素</span><span class="sxs-lookup"><span data-stu-id="db27e-123">Child Elements</span></span>  
  
|<span data-ttu-id="db27e-124">要素</span><span class="sxs-lookup"><span data-stu-id="db27e-124">Element</span></span>|<span data-ttu-id="db27e-125">説明</span><span class="sxs-lookup"><span data-stu-id="db27e-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db27e-126">transport</span><span class="sxs-lookup"><span data-stu-id="db27e-126">transport</span></span>|<span data-ttu-id="db27e-127">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="db27e-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="db27e-128">この要素は <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="db27e-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="db27e-129">親要素</span><span class="sxs-lookup"><span data-stu-id="db27e-129">Parent Elements</span></span>  
  
|<span data-ttu-id="db27e-130">要素</span><span class="sxs-lookup"><span data-stu-id="db27e-130">Element</span></span>|<span data-ttu-id="db27e-131">説明</span><span class="sxs-lookup"><span data-stu-id="db27e-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db27e-132">バインド</span><span class="sxs-lookup"><span data-stu-id="db27e-132">binding</span></span>|<span data-ttu-id="db27e-133">[ \<NetNamedPipeBinding >](netnamedpipebinding.md)のバインド要素。</span><span class="sxs-lookup"><span data-stu-id="db27e-133">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db27e-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="db27e-134">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="db27e-135">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="db27e-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="db27e-136">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="db27e-136">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="db27e-137">バインディング</span><span class="sxs-lookup"><span data-stu-id="db27e-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="db27e-138">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="db27e-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="db27e-139">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="db27e-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="db27e-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="db27e-140">\<binding></span></span>](../../../misc/binding.md)
