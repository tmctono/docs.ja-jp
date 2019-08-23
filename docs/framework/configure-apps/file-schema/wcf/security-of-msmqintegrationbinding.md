---
title: <security> の <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 5b74c95ef2933fcf7e8d49aed89d95acbd288b80
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936706"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="a2887-102">\<msmqIntegrationBinding > の\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="a2887-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="a2887-103">メッセージ キュー (MSMQ) 統合チャネルのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="a2887-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="a2887-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a2887-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a2887-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a2887-105">\<bindings></span></span>  
<span data-ttu-id="a2887-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="a2887-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="a2887-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="a2887-107">\<binding></span></span>  
<span data-ttu-id="a2887-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="a2887-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2887-109">構文</span><span class="sxs-lookup"><span data-stu-id="a2887-109">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>
  <binding>
    <security mode="None/Transport">
      <transport msmqAuthenticationMode="None/Windows/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               defaultProtectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2887-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a2887-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a2887-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2887-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2887-112">属性</span><span class="sxs-lookup"><span data-stu-id="a2887-112">Attributes</span></span>  
  
|<span data-ttu-id="a2887-113">属性</span><span class="sxs-lookup"><span data-stu-id="a2887-113">Attribute</span></span>|<span data-ttu-id="a2887-114">説明</span><span class="sxs-lookup"><span data-stu-id="a2887-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a2887-115">モード</span><span class="sxs-lookup"><span data-stu-id="a2887-115">mode</span></span>|<span data-ttu-id="a2887-116">メッセージ キュー統合チャネルの整合性、機密性、および認証を制御するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2887-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="a2887-117">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a2887-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a2887-118">存在これにより、セキュリティが無効になります。</span><span class="sxs-lookup"><span data-stu-id="a2887-118">-   None: This disables security.</span></span><br /><span data-ttu-id="a2887-119">トランスポート保護と認証はトランスポートによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="a2887-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="a2887-120">これは、2 つのキュー マネージャー間のメッセージ セキュリティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a2887-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="a2887-121">アプリケーションとキュー マネージャーとの間にセキュリティは提供されません。</span><span class="sxs-lookup"><span data-stu-id="a2887-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="a2887-122">既存の Msmq アプリケーションは、この種類のセキュリティ モードと機能的に等価です。</span><span class="sxs-lookup"><span data-stu-id="a2887-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="a2887-123">既定値は `Transport` です。</span><span class="sxs-lookup"><span data-stu-id="a2887-123">The default value is `Transport`.</span></span> <span data-ttu-id="a2887-124">この属性は <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="a2887-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2887-125">子要素</span><span class="sxs-lookup"><span data-stu-id="a2887-125">Child Elements</span></span>  
  
|<span data-ttu-id="a2887-126">要素</span><span class="sxs-lookup"><span data-stu-id="a2887-126">Element</span></span>|<span data-ttu-id="a2887-127">説明</span><span class="sxs-lookup"><span data-stu-id="a2887-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2887-128">\<transport></span><span class="sxs-lookup"><span data-stu-id="a2887-128">\<transport></span></span>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="a2887-129">メッセージ キュー統合トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="a2887-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="a2887-130">この要素は <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="a2887-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2887-131">親要素</span><span class="sxs-lookup"><span data-stu-id="a2887-131">Parent Elements</span></span>  
  
|<span data-ttu-id="a2887-132">要素</span><span class="sxs-lookup"><span data-stu-id="a2887-132">Element</span></span>|<span data-ttu-id="a2887-133">説明</span><span class="sxs-lookup"><span data-stu-id="a2887-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2887-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="a2887-134">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="a2887-135">[ \<MsmqIntegrationBinding >](msmqintegrationbinding.md)のバインド要素。</span><span class="sxs-lookup"><span data-stu-id="a2887-135">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2887-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2887-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="a2887-137">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="a2887-137">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="a2887-138">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="a2887-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a2887-139">バインディング</span><span class="sxs-lookup"><span data-stu-id="a2887-139">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a2887-140">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="a2887-140">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a2887-141">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="a2887-141">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a2887-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="a2887-142">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="a2887-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="a2887-143">\<msmqIntegrationBinding></span></span>](msmqintegrationbinding.md)
