---
title: <security> の <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 2268bf48a2b86c3b3b25db006e6f8f55ea33af73
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738684"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="15a68-102">\<msmqIntegrationBinding > のセキュリティ > の \<</span><span class="sxs-lookup"><span data-stu-id="15a68-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="15a68-103">メッセージ キュー (MSMQ) 統合チャネルのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="15a68-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
<span data-ttu-id="15a68-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="15a68-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="15a68-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="15a68-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="15a68-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="15a68-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="15a68-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<msmqIntegrationBinding >** ](msmqintegrationbinding.md)</span><span class="sxs-lookup"><span data-stu-id="15a68-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)</span></span>\
<span data-ttu-id="15a68-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="15a68-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="15a68-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="15a68-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15a68-110">構文</span><span class="sxs-lookup"><span data-stu-id="15a68-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15a68-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="15a68-111">Attributes and Elements</span></span>  
 <span data-ttu-id="15a68-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="15a68-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15a68-113">属性</span><span class="sxs-lookup"><span data-stu-id="15a68-113">Attributes</span></span>  
  
|<span data-ttu-id="15a68-114">属性</span><span class="sxs-lookup"><span data-stu-id="15a68-114">Attribute</span></span>|<span data-ttu-id="15a68-115">説明</span><span class="sxs-lookup"><span data-stu-id="15a68-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15a68-116">モード</span><span class="sxs-lookup"><span data-stu-id="15a68-116">mode</span></span>|<span data-ttu-id="15a68-117">メッセージ キュー統合チャネルの整合性、機密性、および認証を制御するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="15a68-117">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="15a68-118">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="15a68-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="15a68-119">-None: セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="15a68-119">-   None: This disables security.</span></span><br /><span data-ttu-id="15a68-120">-Transport: 保護と認証はトランスポートによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="15a68-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="15a68-121">これは、2 つのキュー マネージャー間のメッセージ セキュリティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="15a68-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="15a68-122">アプリケーションとキュー マネージャーとの間にセキュリティは提供されません。</span><span class="sxs-lookup"><span data-stu-id="15a68-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="15a68-123">既存の Msmq アプリケーションは、この種類のセキュリティ モードと機能的に等価です。</span><span class="sxs-lookup"><span data-stu-id="15a68-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="15a68-124">既定値は `Transport`です。</span><span class="sxs-lookup"><span data-stu-id="15a68-124">The default value is `Transport`.</span></span> <span data-ttu-id="15a68-125">この属性は <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="15a68-125">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15a68-126">子要素</span><span class="sxs-lookup"><span data-stu-id="15a68-126">Child Elements</span></span>  
  
|<span data-ttu-id="15a68-127">要素</span><span class="sxs-lookup"><span data-stu-id="15a68-127">Element</span></span>|<span data-ttu-id="15a68-128">説明</span><span class="sxs-lookup"><span data-stu-id="15a68-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15a68-129">\<transport ></span><span class="sxs-lookup"><span data-stu-id="15a68-129">\<transport></span></span>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="15a68-130">メッセージ キュー統合トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="15a68-130">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="15a68-131">この要素は <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="15a68-131">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="15a68-132">親要素</span><span class="sxs-lookup"><span data-stu-id="15a68-132">Parent Elements</span></span>  
  
|<span data-ttu-id="15a68-133">要素</span><span class="sxs-lookup"><span data-stu-id="15a68-133">Element</span></span>|<span data-ttu-id="15a68-134">説明</span><span class="sxs-lookup"><span data-stu-id="15a68-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15a68-135">\<binding ></span><span class="sxs-lookup"><span data-stu-id="15a68-135">\<binding></span></span>](bindings.md)|<span data-ttu-id="15a68-136">[\<msmqIntegrationBinding >](msmqintegrationbinding.md)のバインド要素。</span><span class="sxs-lookup"><span data-stu-id="15a68-136">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15a68-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="15a68-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="15a68-138">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="15a68-138">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="15a68-139">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="15a68-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="15a68-140">バインディング</span><span class="sxs-lookup"><span data-stu-id="15a68-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="15a68-141">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="15a68-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="15a68-142">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="15a68-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="15a68-143">\<binding ></span><span class="sxs-lookup"><span data-stu-id="15a68-143">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="15a68-144">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="15a68-144">\<msmqIntegrationBinding></span></span>](msmqintegrationbinding.md)
