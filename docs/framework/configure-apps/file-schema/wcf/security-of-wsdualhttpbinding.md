---
title: <security> の <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: bed7f4ce325e0d5e387e310ca15a3b72ac93f18e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936541"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="99211-102">\<wsDualHttpBinding > の\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="99211-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="99211-103">[ \<WsDualHttpBinding >](wsdualhttpbinding.md)のセキュリティ機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="99211-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="99211-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="99211-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="99211-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="99211-105">\<bindings></span></span>  
<span data-ttu-id="99211-106">\<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="99211-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="99211-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="99211-107">\<binding></span></span>  
<span data-ttu-id="99211-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="99211-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99211-109">構文</span><span class="sxs-lookup"><span data-stu-id="99211-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99211-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="99211-110">Attributes and Elements</span></span>  
 <span data-ttu-id="99211-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="99211-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99211-112">属性</span><span class="sxs-lookup"><span data-stu-id="99211-112">Attributes</span></span>  
  
|<span data-ttu-id="99211-113">属性</span><span class="sxs-lookup"><span data-stu-id="99211-113">Attribute</span></span>|<span data-ttu-id="99211-114">説明</span><span class="sxs-lookup"><span data-stu-id="99211-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99211-115">モード</span><span class="sxs-lookup"><span data-stu-id="99211-115">mode</span></span>|<span data-ttu-id="99211-116">Optional.</span><span class="sxs-lookup"><span data-stu-id="99211-116">-   Optional.</span></span> <span data-ttu-id="99211-117">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="99211-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="99211-118">既定値は `Message` です。</span><span class="sxs-lookup"><span data-stu-id="99211-118">The default value is `Message`.</span></span> <span data-ttu-id="99211-119">この属性は <xref:System.ServiceModel.WSDualHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="99211-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="99211-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="99211-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="99211-121">値</span><span class="sxs-lookup"><span data-stu-id="99211-121">Value</span></span>|<span data-ttu-id="99211-122">説明</span><span class="sxs-lookup"><span data-stu-id="99211-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99211-123">なし</span><span class="sxs-lookup"><span data-stu-id="99211-123">None</span></span>|<span data-ttu-id="99211-124">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="99211-124">Security is disabled.</span></span>|  
|<span data-ttu-id="99211-125">Message</span><span class="sxs-lookup"><span data-stu-id="99211-125">Message</span></span>|<span data-ttu-id="99211-126">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="99211-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99211-127">子要素</span><span class="sxs-lookup"><span data-stu-id="99211-127">Child Elements</span></span>  
  
|<span data-ttu-id="99211-128">要素</span><span class="sxs-lookup"><span data-stu-id="99211-128">Element</span></span>|<span data-ttu-id="99211-129">説明</span><span class="sxs-lookup"><span data-stu-id="99211-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99211-130">\<message></span><span class="sxs-lookup"><span data-stu-id="99211-130">\<message></span></span>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="99211-131">メッセージ レベル セキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="99211-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="99211-132">この要素は <xref:System.ServiceModel.MessageSecurityOverHttp> 型です。</span><span class="sxs-lookup"><span data-stu-id="99211-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="99211-133">親要素</span><span class="sxs-lookup"><span data-stu-id="99211-133">Parent Elements</span></span>  
  
|<span data-ttu-id="99211-134">要素</span><span class="sxs-lookup"><span data-stu-id="99211-134">Element</span></span>|<span data-ttu-id="99211-135">説明</span><span class="sxs-lookup"><span data-stu-id="99211-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99211-136">\<binding></span><span class="sxs-lookup"><span data-stu-id="99211-136">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="99211-137">WsDualHttpBinding > のすべてのバインド機能を[ \<](wsdualhttpbinding.md)定義します。</span><span class="sxs-lookup"><span data-stu-id="99211-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99211-138">Remarks</span><span class="sxs-lookup"><span data-stu-id="99211-138">Remarks</span></span>  
 <span data-ttu-id="99211-139">二重バインディングでは、クライアントの IP アドレスをサービスに公開します。</span><span class="sxs-lookup"><span data-stu-id="99211-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="99211-140">クライアントは、セキュリティを使用して信頼するサービスに対して接続のみを可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="99211-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99211-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="99211-141">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="99211-142">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="99211-142">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="99211-143">バインディング</span><span class="sxs-lookup"><span data-stu-id="99211-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="99211-144">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="99211-144">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="99211-145">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="99211-145">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="99211-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="99211-146">\<binding></span></span>](../../../misc/binding.md)
