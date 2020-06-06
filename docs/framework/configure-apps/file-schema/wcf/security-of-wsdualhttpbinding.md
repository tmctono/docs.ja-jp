---
title: <security> の <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 4969c041678bbf3490975bc0ec53507b6cf762bb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738608"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="ffc87-102">\<security> の \<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="ffc87-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="ffc87-103">のセキュリティ機能を定義 [\<wsDualHttpBinding>](wsdualhttpbinding.md) します。</span><span class="sxs-lookup"><span data-stu-id="ffc87-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="ffc87-104">構文</span><span class="sxs-lookup"><span data-stu-id="ffc87-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ffc87-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ffc87-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ffc87-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ffc87-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ffc87-107">属性</span><span class="sxs-lookup"><span data-stu-id="ffc87-107">Attributes</span></span>  
  
|<span data-ttu-id="ffc87-108">属性</span><span class="sxs-lookup"><span data-stu-id="ffc87-108">Attribute</span></span>|<span data-ttu-id="ffc87-109">説明</span><span class="sxs-lookup"><span data-stu-id="ffc87-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ffc87-110">mode</span><span class="sxs-lookup"><span data-stu-id="ffc87-110">mode</span></span>|<span data-ttu-id="ffc87-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="ffc87-111">-   Optional.</span></span> <span data-ttu-id="ffc87-112">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="ffc87-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="ffc87-113">既定値は `Message` です。</span><span class="sxs-lookup"><span data-stu-id="ffc87-113">The default value is `Message`.</span></span> <span data-ttu-id="ffc87-114">この属性は <xref:System.ServiceModel.WSDualHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="ffc87-114">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="ffc87-115">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="ffc87-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="ffc87-116">値</span><span class="sxs-lookup"><span data-stu-id="ffc87-116">Value</span></span>|<span data-ttu-id="ffc87-117">説明</span><span class="sxs-lookup"><span data-stu-id="ffc87-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ffc87-118">なし</span><span class="sxs-lookup"><span data-stu-id="ffc87-118">None</span></span>|<span data-ttu-id="ffc87-119">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ffc87-119">Security is disabled.</span></span>|  
|<span data-ttu-id="ffc87-120">Message</span><span class="sxs-lookup"><span data-stu-id="ffc87-120">Message</span></span>|<span data-ttu-id="ffc87-121">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="ffc87-121">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ffc87-122">子要素</span><span class="sxs-lookup"><span data-stu-id="ffc87-122">Child Elements</span></span>  
  
|<span data-ttu-id="ffc87-123">要素</span><span class="sxs-lookup"><span data-stu-id="ffc87-123">Element</span></span>|<span data-ttu-id="ffc87-124">Description</span><span class="sxs-lookup"><span data-stu-id="ffc87-124">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="ffc87-125">メッセージ レベル セキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="ffc87-125">Defines the settings for the message-level security.</span></span> <span data-ttu-id="ffc87-126">この要素は <xref:System.ServiceModel.MessageSecurityOverHttp> 型です。</span><span class="sxs-lookup"><span data-stu-id="ffc87-126">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ffc87-127">親要素</span><span class="sxs-lookup"><span data-stu-id="ffc87-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ffc87-128">要素</span><span class="sxs-lookup"><span data-stu-id="ffc87-128">Element</span></span>|<span data-ttu-id="ffc87-129">Description</span><span class="sxs-lookup"><span data-stu-id="ffc87-129">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="ffc87-130">のすべてのバインディング機能を定義 [\<wsDualHttpBinding>](wsdualhttpbinding.md) します。</span><span class="sxs-lookup"><span data-stu-id="ffc87-130">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffc87-131">解説</span><span class="sxs-lookup"><span data-stu-id="ffc87-131">Remarks</span></span>  
 <span data-ttu-id="ffc87-132">二重バインディングでは、クライアントの IP アドレスをサービスに公開します。</span><span class="sxs-lookup"><span data-stu-id="ffc87-132">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="ffc87-133">クライアントは、セキュリティを使用して信頼するサービスに対して接続のみを可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffc87-133">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffc87-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="ffc87-134">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="ffc87-135">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="ffc87-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ffc87-136">バインド</span><span class="sxs-lookup"><span data-stu-id="ffc87-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ffc87-137">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="ffc87-137">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ffc87-138">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="ffc87-138">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
