---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 74f5f2fc1a0fa1ffbbb510e4e700c33a13d02ab3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397912"
---
# <a name="issuer"></a><span data-ttu-id="6bd2e-101">\<発行者の ></span><span class="sxs-lookup"><span data-stu-id="6bd2e-101">\<issuer></span></span>
<span data-ttu-id="6bd2e-102">セキュリティ トークンを発行するセキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6bd2e-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
<span data-ttu-id="6bd2e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6bd2e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6bd2e-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6bd2e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6bd2e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="6bd2e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="6bd2e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6bd2e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="6bd2e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="6bd2e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="6bd2e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<セキュリティ >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6bd2e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="6bd2e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<メッセージ >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6bd2e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="6bd2e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<発行者の >**</span><span class="sxs-lookup"><span data-stu-id="6bd2e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bd2e-111">構文</span><span class="sxs-lookup"><span data-stu-id="6bd2e-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri">
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
</issuer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bd2e-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6bd2e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6bd2e-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6bd2e-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bd2e-114">属性</span><span class="sxs-lookup"><span data-stu-id="6bd2e-114">Attributes</span></span>  
  
|<span data-ttu-id="6bd2e-115">属性</span><span class="sxs-lookup"><span data-stu-id="6bd2e-115">Attribute</span></span>|<span data-ttu-id="6bd2e-116">説明</span><span class="sxs-lookup"><span data-stu-id="6bd2e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6bd2e-117">address</span><span class="sxs-lookup"><span data-stu-id="6bd2e-117">address</span></span>|<span data-ttu-id="6bd2e-118">必須の文字列。</span><span class="sxs-lookup"><span data-stu-id="6bd2e-118">Required string.</span></span> <span data-ttu-id="6bd2e-119">STS の URL です。</span><span class="sxs-lookup"><span data-stu-id="6bd2e-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6bd2e-120">子要素</span><span class="sxs-lookup"><span data-stu-id="6bd2e-120">Child Elements</span></span>  
  
|<span data-ttu-id="6bd2e-121">要素</span><span class="sxs-lookup"><span data-stu-id="6bd2e-121">Element</span></span>|<span data-ttu-id="6bd2e-122">説明</span><span class="sxs-lookup"><span data-stu-id="6bd2e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6bd2e-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="6bd2e-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="6bd2e-124">ビルダーが作成できるエンドポイントのアドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="6bd2e-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="6bd2e-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="6bd2e-125">\<identity></span></span>](identity.md)|<span data-ttu-id="6bd2e-126">発行されたトークンを使用する場合、クライアントでサーバーの認証を有効にする設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6bd2e-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6bd2e-127">親要素</span><span class="sxs-lookup"><span data-stu-id="6bd2e-127">Parent Elements</span></span>  
  
|<span data-ttu-id="6bd2e-128">要素</span><span class="sxs-lookup"><span data-stu-id="6bd2e-128">Element</span></span>|<span data-ttu-id="6bd2e-129">説明</span><span class="sxs-lookup"><span data-stu-id="6bd2e-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6bd2e-130">\<message></span><span class="sxs-lookup"><span data-stu-id="6bd2e-130">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="6bd2e-131">WsFederationHttpBinding > 要素の[ \<](wsfederationhttpbinding.md)メッセージレベルセキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="6bd2e-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6bd2e-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bd2e-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="6bd2e-133">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="6bd2e-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="6bd2e-134">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="6bd2e-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="6bd2e-135">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="6bd2e-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="6bd2e-136">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="6bd2e-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="6bd2e-137">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="6bd2e-137">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="6bd2e-138">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="6bd2e-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
