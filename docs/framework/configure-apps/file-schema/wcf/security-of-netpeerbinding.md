---
title: <security> の <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 3d1ac85073c44f683fe0c054737c5ec7ed1cbf52
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738662"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="e182c-102">\<security> の \<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="e182c-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="e182c-103">[\<netPeerTcpBinding>](netpeertcpbinding.md)使用される認証の種類とメッセージトランスポートに使用されるセキュリティを含む、のセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e182c-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="e182c-104">構文</span><span class="sxs-lookup"><span data-stu-id="e182c-104">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e182c-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e182c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e182c-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e182c-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e182c-107">属性</span><span class="sxs-lookup"><span data-stu-id="e182c-107">Attributes</span></span>  
  
|<span data-ttu-id="e182c-108">属性</span><span class="sxs-lookup"><span data-stu-id="e182c-108">Attribute</span></span>|<span data-ttu-id="e182c-109">説明</span><span class="sxs-lookup"><span data-stu-id="e182c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e182c-110">mode</span><span class="sxs-lookup"><span data-stu-id="e182c-110">mode</span></span>|<span data-ttu-id="e182c-111">省略可能。</span><span class="sxs-lookup"><span data-stu-id="e182c-111">Optional.</span></span> <span data-ttu-id="e182c-112">このバインディングで構成されたピアが使用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="e182c-112">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="e182c-113">既定値は `Message` です。</span><span class="sxs-lookup"><span data-stu-id="e182c-113">The default value is `Message`.</span></span> <span data-ttu-id="e182c-114">この属性は <xref:System.ServiceModel.SecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="e182c-114">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="e182c-115">mode 属性</span><span class="sxs-lookup"><span data-stu-id="e182c-115">mode Attribute</span></span>  
  
|<span data-ttu-id="e182c-116">値</span><span class="sxs-lookup"><span data-stu-id="e182c-116">Value</span></span>|<span data-ttu-id="e182c-117">Description</span><span class="sxs-lookup"><span data-stu-id="e182c-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e182c-118">Message</span><span class="sxs-lookup"><span data-stu-id="e182c-118">Message</span></span>|<span data-ttu-id="e182c-119">SOAP セキュリティにより、認証、整合性、および機密性が実現します。</span><span class="sxs-lookup"><span data-stu-id="e182c-119">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="e182c-120">なし</span><span class="sxs-lookup"><span data-stu-id="e182c-120">None</span></span>|<span data-ttu-id="e182c-121">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e182c-121">Security is disabled.</span></span>|  
|<span data-ttu-id="e182c-122">トランスポート</span><span class="sxs-lookup"><span data-stu-id="e182c-122">Transport</span></span>|<span data-ttu-id="e182c-123">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="e182c-123">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="e182c-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="e182c-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="e182c-125">HTTPS により、認証および機密性が実現します。</span><span class="sxs-lookup"><span data-stu-id="e182c-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="e182c-126">SOAP メッセージには、豊富な資格情報の種類が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e182c-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e182c-127">子要素</span><span class="sxs-lookup"><span data-stu-id="e182c-127">Child Elements</span></span>  
  
|<span data-ttu-id="e182c-128">要素</span><span class="sxs-lookup"><span data-stu-id="e182c-128">Element</span></span>|<span data-ttu-id="e182c-129">Description</span><span class="sxs-lookup"><span data-stu-id="e182c-129">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="e182c-130">このバインディングで構成されたピアが送信するセキュリティで保護されたメッセージのトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="e182c-130">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="e182c-131">この要素は <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="e182c-131">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e182c-132">親要素</span><span class="sxs-lookup"><span data-stu-id="e182c-132">Parent Elements</span></span>  
  
|<span data-ttu-id="e182c-133">要素</span><span class="sxs-lookup"><span data-stu-id="e182c-133">Element</span></span>|<span data-ttu-id="e182c-134">Description</span><span class="sxs-lookup"><span data-stu-id="e182c-134">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="e182c-135">のすべてのバインディング機能を定義 [\<netPeerTcpBinding>](netpeertcpbinding.md) します。</span><span class="sxs-lookup"><span data-stu-id="e182c-135">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e182c-136">解説</span><span class="sxs-lookup"><span data-stu-id="e182c-136">Remarks</span></span>  
 <span data-ttu-id="e182c-137">セキュリティは、メッセージ固有にすることも、トランスポート固有にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e182c-137">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e182c-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="e182c-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="e182c-139">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="e182c-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e182c-140">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="e182c-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="e182c-141">バインド</span><span class="sxs-lookup"><span data-stu-id="e182c-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e182c-142">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="e182c-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e182c-143">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="e182c-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
