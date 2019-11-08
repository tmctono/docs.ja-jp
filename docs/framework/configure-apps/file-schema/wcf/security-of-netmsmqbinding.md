---
title: <security> の <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 7877fd59aff581eee5b62a1ca224dbf51c956069
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738667"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="22cf2-102">\<netMsmqBinding のセキュリティ > の \<</span><span class="sxs-lookup"><span data-stu-id="22cf2-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="22cf2-103">MSMQ バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="22cf2-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="22cf2-104">トランスポートまたは SOAP セキュリティが有効であるかどうか、および有効である場合は、どの認証モードと保護レベルを使用するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="22cf2-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
<span data-ttu-id="22cf2-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="22cf2-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="22cf2-106">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="22cf2-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="22cf2-107">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="22cf2-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="22cf2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**netMsmqBinding >** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="22cf2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="22cf2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="22cf2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="22cf2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="22cf2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22cf2-111">構文</span><span class="sxs-lookup"><span data-stu-id="22cf2-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22cf2-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="22cf2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="22cf2-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="22cf2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22cf2-114">属性</span><span class="sxs-lookup"><span data-stu-id="22cf2-114">Attributes</span></span>  
  
|<span data-ttu-id="22cf2-115">属性</span><span class="sxs-lookup"><span data-stu-id="22cf2-115">Attribute</span></span>|<span data-ttu-id="22cf2-116">説明</span><span class="sxs-lookup"><span data-stu-id="22cf2-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22cf2-117">モード</span><span class="sxs-lookup"><span data-stu-id="22cf2-117">mode</span></span>|<span data-ttu-id="22cf2-118">整合性、機密性、および認証を制御するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="22cf2-118">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="22cf2-119">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="22cf2-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="22cf2-120">-None: セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="22cf2-120">-   None: This disables security.</span></span><br /><span data-ttu-id="22cf2-121">-Transport: 保護と認証はトランスポートによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="22cf2-121">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="22cf2-122">これは、2 つのキュー マネージャー間のメッセージ セキュリティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="22cf2-122">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="22cf2-123">アプリケーションとキュー マネージャーとの間にセキュリティは提供されません。</span><span class="sxs-lookup"><span data-stu-id="22cf2-123">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="22cf2-124">既存の Msmq アプリケーションは、この種類のセキュリティ モードと機能的に等価です。</span><span class="sxs-lookup"><span data-stu-id="22cf2-124">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="22cf2-125">-Message: エンドツーエンドアプリケーションのセキュリティを指定します。</span><span class="sxs-lookup"><span data-stu-id="22cf2-125">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="22cf2-126">トランスポート層で提供されるセキュリティありません。</span><span class="sxs-lookup"><span data-stu-id="22cf2-126">There is no security offered at the transport layer.</span></span> <span data-ttu-id="22cf2-127">これは、他の標準バインディングによって提供されたセキュリティと同様です。</span><span class="sxs-lookup"><span data-stu-id="22cf2-127">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="22cf2-128">-Both: トランスポートと SOAP メッセージング層の両方でセキュリティを提供します。</span><span class="sxs-lookup"><span data-stu-id="22cf2-128">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="22cf2-129">同じ資格情報が、両方のレベルで要求されます。</span><span class="sxs-lookup"><span data-stu-id="22cf2-129">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="22cf2-130">既定値は、Transport です。</span><span class="sxs-lookup"><span data-stu-id="22cf2-130">The default value is Transport.</span></span> <span data-ttu-id="22cf2-131">この属性は <xref:System.ServiceModel.NetMsmqSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="22cf2-131">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22cf2-132">子要素</span><span class="sxs-lookup"><span data-stu-id="22cf2-132">Child Elements</span></span>  
  
|<span data-ttu-id="22cf2-133">要素</span><span class="sxs-lookup"><span data-stu-id="22cf2-133">Element</span></span>|<span data-ttu-id="22cf2-134">説明</span><span class="sxs-lookup"><span data-stu-id="22cf2-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22cf2-135">\< メッセージ ></span><span class="sxs-lookup"><span data-stu-id="22cf2-135">\<message></span></span>](message-of-netmsmqbinding.md)|<span data-ttu-id="22cf2-136">SOAP メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="22cf2-136">Defines the SOAP message security settings.</span></span> <span data-ttu-id="22cf2-137">この要素は <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="22cf2-137">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="22cf2-138">\<transport ></span><span class="sxs-lookup"><span data-stu-id="22cf2-138">\<transport></span></span>](transport-of-netmsmqbinding.md)|<span data-ttu-id="22cf2-139">MSMQ トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="22cf2-139">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="22cf2-140">この要素は <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="22cf2-140">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22cf2-141">親要素</span><span class="sxs-lookup"><span data-stu-id="22cf2-141">Parent Elements</span></span>  
  
|<span data-ttu-id="22cf2-142">要素</span><span class="sxs-lookup"><span data-stu-id="22cf2-142">Element</span></span>|<span data-ttu-id="22cf2-143">説明</span><span class="sxs-lookup"><span data-stu-id="22cf2-143">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22cf2-144">バインド</span><span class="sxs-lookup"><span data-stu-id="22cf2-144">binding</span></span>|<span data-ttu-id="22cf2-145">[\<netMsmqBinding](netmsmqbinding.md)の binding 要素 ></span><span class="sxs-lookup"><span data-stu-id="22cf2-145">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22cf2-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="22cf2-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="22cf2-147">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="22cf2-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="22cf2-148">バインディング</span><span class="sxs-lookup"><span data-stu-id="22cf2-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="22cf2-149">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="22cf2-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="22cf2-150">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="22cf2-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="22cf2-151">\<binding ></span><span class="sxs-lookup"><span data-stu-id="22cf2-151">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="22cf2-152">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="22cf2-152">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
