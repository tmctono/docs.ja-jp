---
title: <security> の <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: fa31dda3274c9768694bdf5232f31554899e1d82
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203393"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="00c1e-102">\<セキュリティ > の\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="00c1e-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="00c1e-103">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="00c1e-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="00c1e-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="00c1e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="00c1e-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="00c1e-105">\<bindings></span></span>  
<span data-ttu-id="00c1e-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="00c1e-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="00c1e-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="00c1e-107">\<binding></span></span>  
<span data-ttu-id="00c1e-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="00c1e-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00c1e-109">構文</span><span class="sxs-lookup"><span data-stu-id="00c1e-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00c1e-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="00c1e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="00c1e-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="00c1e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00c1e-112">属性</span><span class="sxs-lookup"><span data-stu-id="00c1e-112">Attributes</span></span>  
  
|<span data-ttu-id="00c1e-113">属性</span><span class="sxs-lookup"><span data-stu-id="00c1e-113">Attribute</span></span>|<span data-ttu-id="00c1e-114">説明</span><span class="sxs-lookup"><span data-stu-id="00c1e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00c1e-115">モード</span><span class="sxs-lookup"><span data-stu-id="00c1e-115">mode</span></span>|<span data-ttu-id="00c1e-116">このバインディングに適用されるセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="00c1e-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="00c1e-117">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="00c1e-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="00c1e-118">-None。これには、セキュリティが無効にします。</span><span class="sxs-lookup"><span data-stu-id="00c1e-118">-   None: This disables security.</span></span><br /><span data-ttu-id="00c1e-119">-トランスポート。基になるトランスポート ベースのセキュリティを使用してセキュリティが提供されます。</span><span class="sxs-lookup"><span data-stu-id="00c1e-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="00c1e-120">このモードでの保護レベルを制御できます。</span><span class="sxs-lookup"><span data-stu-id="00c1e-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="00c1e-121">-既定値は、トランスポートです。</span><span class="sxs-lookup"><span data-stu-id="00c1e-121">-   The default value is Transport.</span></span> <span data-ttu-id="00c1e-122">この属性は <xref:System.ServiceModel.NetNamedPipeSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="00c1e-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00c1e-123">子要素</span><span class="sxs-lookup"><span data-stu-id="00c1e-123">Child Elements</span></span>  
  
|<span data-ttu-id="00c1e-124">要素</span><span class="sxs-lookup"><span data-stu-id="00c1e-124">Element</span></span>|<span data-ttu-id="00c1e-125">説明</span><span class="sxs-lookup"><span data-stu-id="00c1e-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00c1e-126">transport</span><span class="sxs-lookup"><span data-stu-id="00c1e-126">transport</span></span>|<span data-ttu-id="00c1e-127">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="00c1e-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="00c1e-128">この要素は <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="00c1e-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00c1e-129">親要素</span><span class="sxs-lookup"><span data-stu-id="00c1e-129">Parent Elements</span></span>  
  
|<span data-ttu-id="00c1e-130">要素</span><span class="sxs-lookup"><span data-stu-id="00c1e-130">Element</span></span>|<span data-ttu-id="00c1e-131">説明</span><span class="sxs-lookup"><span data-stu-id="00c1e-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00c1e-132">バインド</span><span class="sxs-lookup"><span data-stu-id="00c1e-132">binding</span></span>|<span data-ttu-id="00c1e-133">バインド要素、 [ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="00c1e-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00c1e-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="00c1e-134">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="00c1e-135">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="00c1e-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="00c1e-136">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="00c1e-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="00c1e-137">バインディング</span><span class="sxs-lookup"><span data-stu-id="00c1e-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="00c1e-138">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="00c1e-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="00c1e-139">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="00c1e-139">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="00c1e-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="00c1e-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
