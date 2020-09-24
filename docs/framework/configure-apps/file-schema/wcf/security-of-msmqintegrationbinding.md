---
title: <security> の <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: be2f48f7d9c3be4ea0a5fe95436930b3f23c7551
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170065"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="7b38f-102">\<security> の \<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="7b38f-102">\<security> of \<msmqIntegrationBinding></span></span>

<span data-ttu-id="7b38f-103">メッセージ キュー (MSMQ) 統合チャネルのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="7b38f-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="7b38f-104">構文</span><span class="sxs-lookup"><span data-stu-id="7b38f-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b38f-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7b38f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7b38f-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b38f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b38f-107">属性</span><span class="sxs-lookup"><span data-stu-id="7b38f-107">Attributes</span></span>  
  
|<span data-ttu-id="7b38f-108">属性</span><span class="sxs-lookup"><span data-stu-id="7b38f-108">Attribute</span></span>|<span data-ttu-id="7b38f-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="7b38f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7b38f-110">mode</span><span class="sxs-lookup"><span data-stu-id="7b38f-110">mode</span></span>|<span data-ttu-id="7b38f-111">メッセージ キュー統合チャネルの整合性、機密性、および認証を制御するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b38f-111">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="7b38f-112">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7b38f-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7b38f-113">-None: セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="7b38f-113">-   None: This disables security.</span></span><br /><span data-ttu-id="7b38f-114">-Transport: 保護と認証はトランスポートによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="7b38f-114">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="7b38f-115">これは、2 つのキュー マネージャー間のメッセージ セキュリティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7b38f-115">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="7b38f-116">アプリケーションとキュー マネージャーとの間にセキュリティは提供されません。</span><span class="sxs-lookup"><span data-stu-id="7b38f-116">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="7b38f-117">既存の Msmq アプリケーションは、この種類のセキュリティ モードと機能的に等価です。</span><span class="sxs-lookup"><span data-stu-id="7b38f-117">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="7b38f-118">既定値は `Transport` です。</span><span class="sxs-lookup"><span data-stu-id="7b38f-118">The default value is `Transport`.</span></span> <span data-ttu-id="7b38f-119">この属性は <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="7b38f-119">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b38f-120">子要素</span><span class="sxs-lookup"><span data-stu-id="7b38f-120">Child Elements</span></span>  
  
|<span data-ttu-id="7b38f-121">要素</span><span class="sxs-lookup"><span data-stu-id="7b38f-121">Element</span></span>|<span data-ttu-id="7b38f-122">説明</span><span class="sxs-lookup"><span data-stu-id="7b38f-122">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="7b38f-123">メッセージ キュー統合トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="7b38f-123">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="7b38f-124">この要素は <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="7b38f-124">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7b38f-125">親要素</span><span class="sxs-lookup"><span data-stu-id="7b38f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7b38f-126">要素</span><span class="sxs-lookup"><span data-stu-id="7b38f-126">Element</span></span>|<span data-ttu-id="7b38f-127">説明</span><span class="sxs-lookup"><span data-stu-id="7b38f-127">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="7b38f-128">のバインディング要素 [\<msmqIntegrationBinding>](msmqintegrationbinding.md) 。</span><span class="sxs-lookup"><span data-stu-id="7b38f-128">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b38f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b38f-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="7b38f-130">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="7b38f-130">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="7b38f-131">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="7b38f-131">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7b38f-132">バインド</span><span class="sxs-lookup"><span data-stu-id="7b38f-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7b38f-133">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="7b38f-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7b38f-134">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="7b38f-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [\<msmqIntegrationBinding>](msmqintegrationbinding.md)
