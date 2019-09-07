---
title: <security> の <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: c780b157d0d566e24c6826c253401a51fbfab69d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399834"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="cddec-102">\<netmsmqbinding \<> のセキュリティ ></span><span class="sxs-lookup"><span data-stu-id="cddec-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="cddec-103">MSMQ バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="cddec-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="cddec-104">トランスポートまたは SOAP セキュリティが有効であるかどうか、および有効である場合は、どの認証モードと保護レベルを使用するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="cddec-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
<span data-ttu-id="cddec-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cddec-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cddec-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="cddec-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="cddec-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="cddec-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="cddec-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netMsmqBinding >** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="cddec-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="cddec-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="cddec-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="cddec-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="cddec-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cddec-111">構文</span><span class="sxs-lookup"><span data-stu-id="cddec-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cddec-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cddec-112">Attributes and Elements</span></span>  
 <span data-ttu-id="cddec-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cddec-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cddec-114">属性</span><span class="sxs-lookup"><span data-stu-id="cddec-114">Attributes</span></span>  
  
|<span data-ttu-id="cddec-115">属性</span><span class="sxs-lookup"><span data-stu-id="cddec-115">Attribute</span></span>|<span data-ttu-id="cddec-116">説明</span><span class="sxs-lookup"><span data-stu-id="cddec-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cddec-117">モード</span><span class="sxs-lookup"><span data-stu-id="cddec-117">mode</span></span>|<span data-ttu-id="cddec-118">整合性、機密性、および認証を制御するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="cddec-118">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="cddec-119">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cddec-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cddec-120">存在これにより、セキュリティが無効になります。</span><span class="sxs-lookup"><span data-stu-id="cddec-120">-   None: This disables security.</span></span><br /><span data-ttu-id="cddec-121">トランスポート保護と認証はトランスポートによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="cddec-121">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="cddec-122">これは、2 つのキュー マネージャー間のメッセージ セキュリティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="cddec-122">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="cddec-123">アプリケーションとキュー マネージャーとの間にセキュリティは提供されません。</span><span class="sxs-lookup"><span data-stu-id="cddec-123">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="cddec-124">既存の Msmq アプリケーションは、この種類のセキュリティ モードと機能的に等価です。</span><span class="sxs-lookup"><span data-stu-id="cddec-124">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="cddec-125">メッセージエンドツーエンドアプリケーションのセキュリティを指定します。</span><span class="sxs-lookup"><span data-stu-id="cddec-125">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="cddec-126">トランスポート層で提供されるセキュリティありません。</span><span class="sxs-lookup"><span data-stu-id="cddec-126">There is no security offered at the transport layer.</span></span> <span data-ttu-id="cddec-127">これは、他の標準バインディングによって提供されたセキュリティと同様です。</span><span class="sxs-lookup"><span data-stu-id="cddec-127">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="cddec-128">・は、トランスポートと SOAP メッセージング層の両方でセキュリティを提供します。</span><span class="sxs-lookup"><span data-stu-id="cddec-128">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="cddec-129">同じ資格情報が、両方のレベルで要求されます。</span><span class="sxs-lookup"><span data-stu-id="cddec-129">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="cddec-130">既定値は、Transport です。</span><span class="sxs-lookup"><span data-stu-id="cddec-130">The default value is Transport.</span></span> <span data-ttu-id="cddec-131">この属性は <xref:System.ServiceModel.NetMsmqSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="cddec-131">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cddec-132">子要素</span><span class="sxs-lookup"><span data-stu-id="cddec-132">Child Elements</span></span>  
  
|<span data-ttu-id="cddec-133">要素</span><span class="sxs-lookup"><span data-stu-id="cddec-133">Element</span></span>|<span data-ttu-id="cddec-134">説明</span><span class="sxs-lookup"><span data-stu-id="cddec-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cddec-135">\<message></span><span class="sxs-lookup"><span data-stu-id="cddec-135">\<message></span></span>](message-of-netmsmqbinding.md)|<span data-ttu-id="cddec-136">SOAP メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="cddec-136">Defines the SOAP message security settings.</span></span> <span data-ttu-id="cddec-137">この要素は <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="cddec-137">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="cddec-138">\<transport></span><span class="sxs-lookup"><span data-stu-id="cddec-138">\<transport></span></span>](transport-of-netmsmqbinding.md)|<span data-ttu-id="cddec-139">MSMQ トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="cddec-139">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="cddec-140">この要素は <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="cddec-140">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cddec-141">親要素</span><span class="sxs-lookup"><span data-stu-id="cddec-141">Parent Elements</span></span>  
  
|<span data-ttu-id="cddec-142">要素</span><span class="sxs-lookup"><span data-stu-id="cddec-142">Element</span></span>|<span data-ttu-id="cddec-143">説明</span><span class="sxs-lookup"><span data-stu-id="cddec-143">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cddec-144">バインド</span><span class="sxs-lookup"><span data-stu-id="cddec-144">binding</span></span>|<span data-ttu-id="cddec-145">[ \<Netmsmqbinding のバインド要素 >](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="cddec-145">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cddec-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="cddec-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="cddec-147">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="cddec-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="cddec-148">バインディング</span><span class="sxs-lookup"><span data-stu-id="cddec-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="cddec-149">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="cddec-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="cddec-150">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="cddec-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="cddec-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="cddec-151">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="cddec-152">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="cddec-152">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
