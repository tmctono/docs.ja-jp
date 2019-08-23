---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: bf512c427637ca65a7271ec8300a373a38632108
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913517"
---
# <a name="issuermetadata"></a><span data-ttu-id="828e1-101">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="828e1-101">\<issuerMetadata></span></span>
<span data-ttu-id="828e1-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="828e1-102">\<system.serviceModel></span></span>  
<span data-ttu-id="828e1-103">\<bindings></span><span class="sxs-lookup"><span data-stu-id="828e1-103">\<bindings></span></span>  
<span data-ttu-id="828e1-104">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="828e1-104">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="828e1-105">\<binding></span><span class="sxs-lookup"><span data-stu-id="828e1-105">\<binding></span></span>  
<span data-ttu-id="828e1-106">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="828e1-106">\<security></span></span>  
<span data-ttu-id="828e1-107">\<message></span><span class="sxs-lookup"><span data-stu-id="828e1-107">\<message></span></span>  
<span data-ttu-id="828e1-108">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="828e1-108">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="828e1-109">構文</span><span class="sxs-lookup"><span data-stu-id="828e1-109">Syntax</span></span>  
  
```xml  
<issuerMetadata address="String">
  <headers>
    <add name="String"
         namespace="String" />
  </headers>
  <identity>
    <certificate encodedValue="String" />
    <certificateReference findValue="String"
                          isChainIncluded="Boolean"
                          storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                          storeLocation="LocalMachine/CurrentUser"
                          x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
    <dns value="String" />
    <rsa value="String" />
    <servicePrincipalName value="String" />
    <usePrincipalName value="String" />
  </identity>
</issuerMetadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="828e1-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="828e1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="828e1-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="828e1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="828e1-112">属性</span><span class="sxs-lookup"><span data-stu-id="828e1-112">Attributes</span></span>  
  
|<span data-ttu-id="828e1-113">属性</span><span class="sxs-lookup"><span data-stu-id="828e1-113">Attribute</span></span>|<span data-ttu-id="828e1-114">説明</span><span class="sxs-lookup"><span data-stu-id="828e1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="828e1-115">address</span><span class="sxs-lookup"><span data-stu-id="828e1-115">address</span></span>|<span data-ttu-id="828e1-116">必須の `string` 属性です。</span><span class="sxs-lookup"><span data-stu-id="828e1-116">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="828e1-117">エンドポイントのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="828e1-117">Specifies the address of the endpoint.</span></span> <span data-ttu-id="828e1-118">アドレスは、絶対 URI にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="828e1-118">The address must be an absolute URI.</span></span> <span data-ttu-id="828e1-119">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="828e1-119">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="828e1-120">子要素</span><span class="sxs-lookup"><span data-stu-id="828e1-120">Child Elements</span></span>  
  
|<span data-ttu-id="828e1-121">要素</span><span class="sxs-lookup"><span data-stu-id="828e1-121">Element</span></span>|<span data-ttu-id="828e1-122">説明</span><span class="sxs-lookup"><span data-stu-id="828e1-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="828e1-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="828e1-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="828e1-124">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="828e1-124">A collection of address headers.</span></span>|  
|[<span data-ttu-id="828e1-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="828e1-125">\<identity></span></span>](identity.md)|<span data-ttu-id="828e1-126">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="828e1-126">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="828e1-127">親要素</span><span class="sxs-lookup"><span data-stu-id="828e1-127">Parent Elements</span></span>  
  
|<span data-ttu-id="828e1-128">要素</span><span class="sxs-lookup"><span data-stu-id="828e1-128">Element</span></span>|<span data-ttu-id="828e1-129">説明</span><span class="sxs-lookup"><span data-stu-id="828e1-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="828e1-130">\<message></span><span class="sxs-lookup"><span data-stu-id="828e1-130">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="828e1-131">WsFederationHttpBinding > 要素の[ \<](wsfederationhttpbinding.md)メッセージレベルセキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="828e1-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="828e1-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="828e1-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="828e1-133">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="828e1-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="828e1-134">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="828e1-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="828e1-135">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="828e1-135">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="828e1-136">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="828e1-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
