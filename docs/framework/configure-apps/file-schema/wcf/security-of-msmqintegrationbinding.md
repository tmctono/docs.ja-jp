---
title: <security> の <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: e4f10ab994429c6cbb690caef38114b8340e6839
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399866"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="d5b8d-102">\<msmqIntegrationBinding > の\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="d5b8d-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="d5b8d-103">メッセージ キュー (MSMQ) 統合チャネルのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
<span data-ttu-id="d5b8d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d5b8d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d5b8d-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d5b8d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d5b8d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="d5b8d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="d5b8d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<msmqIntegrationBinding >** ](msmqintegrationbinding.md)</span><span class="sxs-lookup"><span data-stu-id="d5b8d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)</span></span>\
<span data-ttu-id="d5b8d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="d5b8d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="d5b8d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="d5b8d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5b8d-110">構文</span><span class="sxs-lookup"><span data-stu-id="d5b8d-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5b8d-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d5b8d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d5b8d-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5b8d-113">属性</span><span class="sxs-lookup"><span data-stu-id="d5b8d-113">Attributes</span></span>  
  
|<span data-ttu-id="d5b8d-114">属性</span><span class="sxs-lookup"><span data-stu-id="d5b8d-114">Attribute</span></span>|<span data-ttu-id="d5b8d-115">説明</span><span class="sxs-lookup"><span data-stu-id="d5b8d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d5b8d-116">モード</span><span class="sxs-lookup"><span data-stu-id="d5b8d-116">mode</span></span>|<span data-ttu-id="d5b8d-117">メッセージ キュー統合チャネルの整合性、機密性、および認証を制御するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-117">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="d5b8d-118">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d5b8d-119">存在これにより、セキュリティが無効になります。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-119">-   None: This disables security.</span></span><br /><span data-ttu-id="d5b8d-120">トランスポート保護と認証はトランスポートによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="d5b8d-121">これは、2 つのキュー マネージャー間のメッセージ セキュリティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="d5b8d-122">アプリケーションとキュー マネージャーとの間にセキュリティは提供されません。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="d5b8d-123">既存の Msmq アプリケーションは、この種類のセキュリティ モードと機能的に等価です。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="d5b8d-124">既定値は `Transport` です。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-124">The default value is `Transport`.</span></span> <span data-ttu-id="d5b8d-125">この属性は <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-125">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5b8d-126">子要素</span><span class="sxs-lookup"><span data-stu-id="d5b8d-126">Child Elements</span></span>  
  
|<span data-ttu-id="d5b8d-127">要素</span><span class="sxs-lookup"><span data-stu-id="d5b8d-127">Element</span></span>|<span data-ttu-id="d5b8d-128">説明</span><span class="sxs-lookup"><span data-stu-id="d5b8d-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5b8d-129">\<transport></span><span class="sxs-lookup"><span data-stu-id="d5b8d-129">\<transport></span></span>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="d5b8d-130">メッセージ キュー統合トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-130">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="d5b8d-131">この要素は <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-131">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5b8d-132">親要素</span><span class="sxs-lookup"><span data-stu-id="d5b8d-132">Parent Elements</span></span>  
  
|<span data-ttu-id="d5b8d-133">要素</span><span class="sxs-lookup"><span data-stu-id="d5b8d-133">Element</span></span>|<span data-ttu-id="d5b8d-134">説明</span><span class="sxs-lookup"><span data-stu-id="d5b8d-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5b8d-135">\<binding></span><span class="sxs-lookup"><span data-stu-id="d5b8d-135">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="d5b8d-136">[ \<MsmqIntegrationBinding >](msmqintegrationbinding.md)のバインド要素。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-136">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5b8d-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5b8d-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="d5b8d-138">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="d5b8d-138">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="d5b8d-139">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="d5b8d-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d5b8d-140">バインディング</span><span class="sxs-lookup"><span data-stu-id="d5b8d-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d5b8d-141">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="d5b8d-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d5b8d-142">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="d5b8d-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d5b8d-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="d5b8d-143">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="d5b8d-144">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="d5b8d-144">\<msmqIntegrationBinding></span></span>](msmqintegrationbinding.md)
