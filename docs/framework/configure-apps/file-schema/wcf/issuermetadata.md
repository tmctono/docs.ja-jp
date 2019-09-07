---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: a28223127f7987a80bdf12d2dcf42878f717a377
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397892"
---
# <a name="issuermetadata"></a><span data-ttu-id="36ff0-101">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="36ff0-101">\<issuerMetadata></span></span>

<span data-ttu-id="36ff0-102">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="36ff0-102">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="36ff0-103">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="36ff0-103">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="36ff0-104">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="36ff0-104">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="36ff0-105">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="36ff0-105">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="36ff0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="36ff0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="36ff0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<セキュリティ >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="36ff0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="36ff0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<メッセージ >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="36ff0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="36ff0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerMetadata >**</span><span class="sxs-lookup"><span data-stu-id="36ff0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36ff0-110">構文</span><span class="sxs-lookup"><span data-stu-id="36ff0-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36ff0-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="36ff0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="36ff0-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="36ff0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36ff0-113">属性</span><span class="sxs-lookup"><span data-stu-id="36ff0-113">Attributes</span></span>  
  
|<span data-ttu-id="36ff0-114">属性</span><span class="sxs-lookup"><span data-stu-id="36ff0-114">Attribute</span></span>|<span data-ttu-id="36ff0-115">説明</span><span class="sxs-lookup"><span data-stu-id="36ff0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="36ff0-116">address</span><span class="sxs-lookup"><span data-stu-id="36ff0-116">address</span></span>|<span data-ttu-id="36ff0-117">必須の `string` 属性です。</span><span class="sxs-lookup"><span data-stu-id="36ff0-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="36ff0-118">エンドポイントのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="36ff0-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="36ff0-119">アドレスは、絶対 URI にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ff0-119">The address must be an absolute URI.</span></span> <span data-ttu-id="36ff0-120">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="36ff0-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36ff0-121">子要素</span><span class="sxs-lookup"><span data-stu-id="36ff0-121">Child Elements</span></span>  
  
|<span data-ttu-id="36ff0-122">要素</span><span class="sxs-lookup"><span data-stu-id="36ff0-122">Element</span></span>|<span data-ttu-id="36ff0-123">説明</span><span class="sxs-lookup"><span data-stu-id="36ff0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36ff0-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="36ff0-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="36ff0-125">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="36ff0-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="36ff0-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="36ff0-126">\<identity></span></span>](identity.md)|<span data-ttu-id="36ff0-127">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="36ff0-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36ff0-128">親要素</span><span class="sxs-lookup"><span data-stu-id="36ff0-128">Parent Elements</span></span>  
  
|<span data-ttu-id="36ff0-129">要素</span><span class="sxs-lookup"><span data-stu-id="36ff0-129">Element</span></span>|<span data-ttu-id="36ff0-130">説明</span><span class="sxs-lookup"><span data-stu-id="36ff0-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36ff0-131">\<message></span><span class="sxs-lookup"><span data-stu-id="36ff0-131">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="36ff0-132">WsFederationHttpBinding > 要素の[ \<](wsfederationhttpbinding.md)メッセージレベルセキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="36ff0-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36ff0-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="36ff0-133">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="36ff0-134">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="36ff0-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="36ff0-135">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="36ff0-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="36ff0-136">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="36ff0-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="36ff0-137">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="36ff0-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
