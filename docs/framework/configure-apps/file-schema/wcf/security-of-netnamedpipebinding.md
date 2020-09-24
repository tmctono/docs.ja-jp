---
title: <security> の <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 1a231a60d29cc6a4460de69a98753c23c0386027
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170039"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="dc429-102">\<security> の \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="dc429-102">\<security> of \<netNamedPipeBinding></span></span>

<span data-ttu-id="dc429-103">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="dc429-103">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="dc429-104">構文</span><span class="sxs-lookup"><span data-stu-id="dc429-104">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc429-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dc429-105">Attributes and Elements</span></span>  

 <span data-ttu-id="dc429-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc429-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc429-107">属性</span><span class="sxs-lookup"><span data-stu-id="dc429-107">Attributes</span></span>  
  
|<span data-ttu-id="dc429-108">属性</span><span class="sxs-lookup"><span data-stu-id="dc429-108">Attribute</span></span>|<span data-ttu-id="dc429-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="dc429-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc429-110">mode</span><span class="sxs-lookup"><span data-stu-id="dc429-110">mode</span></span>|<span data-ttu-id="dc429-111">このバインディングに適用されるセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="dc429-111">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="dc429-112">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc429-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dc429-113">-None: セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="dc429-113">-   None: This disables security.</span></span><br /><span data-ttu-id="dc429-114">-Transport: セキュリティは、基になるトランスポートベースのセキュリティを使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="dc429-114">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="dc429-115">このモードでは保護レベルを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="dc429-115">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="dc429-116">-既定値は Transport です。</span><span class="sxs-lookup"><span data-stu-id="dc429-116">-   The default value is Transport.</span></span> <span data-ttu-id="dc429-117">この属性は <xref:System.ServiceModel.NetNamedPipeSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="dc429-117">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc429-118">子要素</span><span class="sxs-lookup"><span data-stu-id="dc429-118">Child Elements</span></span>  
  
|<span data-ttu-id="dc429-119">要素</span><span class="sxs-lookup"><span data-stu-id="dc429-119">Element</span></span>|<span data-ttu-id="dc429-120">説明</span><span class="sxs-lookup"><span data-stu-id="dc429-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc429-121">transport</span><span class="sxs-lookup"><span data-stu-id="dc429-121">transport</span></span>|<span data-ttu-id="dc429-122">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="dc429-122">Defines the security settings for the transport.</span></span> <span data-ttu-id="dc429-123">この要素は <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="dc429-123">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc429-124">親要素</span><span class="sxs-lookup"><span data-stu-id="dc429-124">Parent Elements</span></span>  
  
|<span data-ttu-id="dc429-125">要素</span><span class="sxs-lookup"><span data-stu-id="dc429-125">Element</span></span>|<span data-ttu-id="dc429-126">説明</span><span class="sxs-lookup"><span data-stu-id="dc429-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc429-127">binding</span><span class="sxs-lookup"><span data-stu-id="dc429-127">binding</span></span>|<span data-ttu-id="dc429-128">のバインディング要素 [\<netNamedPipeBinding>](netnamedpipebinding.md) 。</span><span class="sxs-lookup"><span data-stu-id="dc429-128">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc429-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc429-129">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="dc429-130">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="dc429-130">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="dc429-131">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="dc429-131">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="dc429-132">バインド</span><span class="sxs-lookup"><span data-stu-id="dc429-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="dc429-133">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="dc429-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="dc429-134">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="dc429-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
