---
title: <security> の <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 2268bf48a2b86c3b3b25db006e6f8f55ea33af73
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738684"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="1bc28-102">\<security> の \<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="1bc28-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="1bc28-103">メッセージ キュー (MSMQ) 統合チャネルのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="1bc28-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="1bc28-104">構文</span><span class="sxs-lookup"><span data-stu-id="1bc28-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bc28-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1bc28-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1bc28-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bc28-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bc28-107">属性</span><span class="sxs-lookup"><span data-stu-id="1bc28-107">Attributes</span></span>  
  
|<span data-ttu-id="1bc28-108">属性</span><span class="sxs-lookup"><span data-stu-id="1bc28-108">Attribute</span></span>|<span data-ttu-id="1bc28-109">説明</span><span class="sxs-lookup"><span data-stu-id="1bc28-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1bc28-110">mode</span><span class="sxs-lookup"><span data-stu-id="1bc28-110">mode</span></span>|<span data-ttu-id="1bc28-111">メッセージ キュー統合チャネルの整合性、機密性、および認証を制御するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="1bc28-111">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="1bc28-112">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1bc28-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1bc28-113">-None: セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1bc28-113">-   None: This disables security.</span></span><br /><span data-ttu-id="1bc28-114">-Transport: 保護と認証はトランスポートによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="1bc28-114">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="1bc28-115">これは、2 つのキュー マネージャー間のメッセージ セキュリティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1bc28-115">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="1bc28-116">アプリケーションとキュー マネージャーとの間にセキュリティは提供されません。</span><span class="sxs-lookup"><span data-stu-id="1bc28-116">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="1bc28-117">既存の Msmq アプリケーションは、この種類のセキュリティ モードと機能的に等価です。</span><span class="sxs-lookup"><span data-stu-id="1bc28-117">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="1bc28-118">既定値は `Transport` です。</span><span class="sxs-lookup"><span data-stu-id="1bc28-118">The default value is `Transport`.</span></span> <span data-ttu-id="1bc28-119">この属性は <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="1bc28-119">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bc28-120">子要素</span><span class="sxs-lookup"><span data-stu-id="1bc28-120">Child Elements</span></span>  
  
|<span data-ttu-id="1bc28-121">要素</span><span class="sxs-lookup"><span data-stu-id="1bc28-121">Element</span></span>|<span data-ttu-id="1bc28-122">Description</span><span class="sxs-lookup"><span data-stu-id="1bc28-122">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="1bc28-123">メッセージ キュー統合トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="1bc28-123">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="1bc28-124">この要素は <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="1bc28-124">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1bc28-125">親要素</span><span class="sxs-lookup"><span data-stu-id="1bc28-125">Parent Elements</span></span>  
  
|<span data-ttu-id="1bc28-126">要素</span><span class="sxs-lookup"><span data-stu-id="1bc28-126">Element</span></span>|<span data-ttu-id="1bc28-127">Description</span><span class="sxs-lookup"><span data-stu-id="1bc28-127">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="1bc28-128">のバインディング要素 [\<msmqIntegrationBinding>](msmqintegrationbinding.md) 。</span><span class="sxs-lookup"><span data-stu-id="1bc28-128">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1bc28-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bc28-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="1bc28-130">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="1bc28-130">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="1bc28-131">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="1bc28-131">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1bc28-132">バインド</span><span class="sxs-lookup"><span data-stu-id="1bc28-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1bc28-133">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="1bc28-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1bc28-134">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="1bc28-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [\<msmqIntegrationBinding>](msmqintegrationbinding.md)
