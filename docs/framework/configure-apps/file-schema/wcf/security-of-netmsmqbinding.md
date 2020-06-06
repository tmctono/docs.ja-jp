---
title: <security> の <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 7877fd59aff581eee5b62a1ca224dbf51c956069
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738667"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="aad3a-102">\<security> の \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="aad3a-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="aad3a-103">MSMQ バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="aad3a-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="aad3a-104">トランスポートまたは SOAP セキュリティが有効であるかどうか、および有効である場合は、どの認証モードと保護レベルを使用するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="aad3a-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="aad3a-105">構文</span><span class="sxs-lookup"><span data-stu-id="aad3a-105">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aad3a-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="aad3a-106">Attributes and Elements</span></span>  
 <span data-ttu-id="aad3a-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="aad3a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aad3a-108">属性</span><span class="sxs-lookup"><span data-stu-id="aad3a-108">Attributes</span></span>  
  
|<span data-ttu-id="aad3a-109">属性</span><span class="sxs-lookup"><span data-stu-id="aad3a-109">Attribute</span></span>|<span data-ttu-id="aad3a-110">説明</span><span class="sxs-lookup"><span data-stu-id="aad3a-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aad3a-111">mode</span><span class="sxs-lookup"><span data-stu-id="aad3a-111">mode</span></span>|<span data-ttu-id="aad3a-112">整合性、機密性、および認証を制御するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="aad3a-112">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="aad3a-113">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aad3a-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="aad3a-114">-None: セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="aad3a-114">-   None: This disables security.</span></span><br /><span data-ttu-id="aad3a-115">-Transport: 保護と認証はトランスポートによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="aad3a-115">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="aad3a-116">これは、2 つのキュー マネージャー間のメッセージ セキュリティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="aad3a-116">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="aad3a-117">アプリケーションとキュー マネージャーとの間にセキュリティは提供されません。</span><span class="sxs-lookup"><span data-stu-id="aad3a-117">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="aad3a-118">既存の Msmq アプリケーションは、この種類のセキュリティ モードと機能的に等価です。</span><span class="sxs-lookup"><span data-stu-id="aad3a-118">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="aad3a-119">-Message: エンドツーエンドアプリケーションのセキュリティを指定します。</span><span class="sxs-lookup"><span data-stu-id="aad3a-119">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="aad3a-120">トランスポート層で提供されるセキュリティありません。</span><span class="sxs-lookup"><span data-stu-id="aad3a-120">There is no security offered at the transport layer.</span></span> <span data-ttu-id="aad3a-121">これは、他の標準バインディングによって提供されたセキュリティと同様です。</span><span class="sxs-lookup"><span data-stu-id="aad3a-121">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="aad3a-122">-Both: トランスポートと SOAP メッセージング層の両方でセキュリティを提供します。</span><span class="sxs-lookup"><span data-stu-id="aad3a-122">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="aad3a-123">同じ資格情報が、両方のレベルで要求されます。</span><span class="sxs-lookup"><span data-stu-id="aad3a-123">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="aad3a-124">既定値は、Transport です。</span><span class="sxs-lookup"><span data-stu-id="aad3a-124">The default value is Transport.</span></span> <span data-ttu-id="aad3a-125">この属性は <xref:System.ServiceModel.NetMsmqSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="aad3a-125">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aad3a-126">子要素</span><span class="sxs-lookup"><span data-stu-id="aad3a-126">Child Elements</span></span>  
  
|<span data-ttu-id="aad3a-127">要素</span><span class="sxs-lookup"><span data-stu-id="aad3a-127">Element</span></span>|<span data-ttu-id="aad3a-128">Description</span><span class="sxs-lookup"><span data-stu-id="aad3a-128">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-netmsmqbinding.md)|<span data-ttu-id="aad3a-129">SOAP メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="aad3a-129">Defines the SOAP message security settings.</span></span> <span data-ttu-id="aad3a-130">この要素は <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="aad3a-130">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[\<transport>](transport-of-netmsmqbinding.md)|<span data-ttu-id="aad3a-131">MSMQ トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="aad3a-131">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="aad3a-132">この要素は <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="aad3a-132">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aad3a-133">親要素</span><span class="sxs-lookup"><span data-stu-id="aad3a-133">Parent Elements</span></span>  
  
|<span data-ttu-id="aad3a-134">要素</span><span class="sxs-lookup"><span data-stu-id="aad3a-134">Element</span></span>|<span data-ttu-id="aad3a-135">Description</span><span class="sxs-lookup"><span data-stu-id="aad3a-135">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aad3a-136">binding</span><span class="sxs-lookup"><span data-stu-id="aad3a-136">binding</span></span>|<span data-ttu-id="aad3a-137">のバインド要素[\<netMsmqBinding>](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="aad3a-137">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aad3a-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="aad3a-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="aad3a-139">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="aad3a-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="aad3a-140">バインド</span><span class="sxs-lookup"><span data-stu-id="aad3a-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="aad3a-141">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="aad3a-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="aad3a-142">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="aad3a-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="aad3a-143">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="aad3a-143">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
