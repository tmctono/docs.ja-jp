---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 37d935287fa7dfba640c39071295fd660f4db7c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756261"
---
# <a name="issuer"></a><span data-ttu-id="d1dbf-101">\<発行者 ></span><span class="sxs-lookup"><span data-stu-id="d1dbf-101">\<issuer></span></span>
<span data-ttu-id="d1dbf-102">セキュリティ トークンを発行するセキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1dbf-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="d1dbf-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d1dbf-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d1dbf-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d1dbf-104">\<bindings></span></span>  
<span data-ttu-id="d1dbf-105">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="d1dbf-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="d1dbf-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="d1dbf-106">\<binding></span></span>  
<span data-ttu-id="d1dbf-107">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="d1dbf-107">\<security></span></span>  
<span data-ttu-id="d1dbf-108">\<message></span><span class="sxs-lookup"><span data-stu-id="d1dbf-108">\<message></span></span>  
<span data-ttu-id="d1dbf-109">\<発行者 ></span><span class="sxs-lookup"><span data-stu-id="d1dbf-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1dbf-110">構文</span><span class="sxs-lookup"><span data-stu-id="d1dbf-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1dbf-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d1dbf-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d1dbf-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1dbf-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1dbf-113">属性</span><span class="sxs-lookup"><span data-stu-id="d1dbf-113">Attributes</span></span>  
  
|<span data-ttu-id="d1dbf-114">属性</span><span class="sxs-lookup"><span data-stu-id="d1dbf-114">Attribute</span></span>|<span data-ttu-id="d1dbf-115">説明</span><span class="sxs-lookup"><span data-stu-id="d1dbf-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d1dbf-116">address</span><span class="sxs-lookup"><span data-stu-id="d1dbf-116">address</span></span>|<span data-ttu-id="d1dbf-117">必須の文字列。</span><span class="sxs-lookup"><span data-stu-id="d1dbf-117">Required string.</span></span> <span data-ttu-id="d1dbf-118">STS の URL です。</span><span class="sxs-lookup"><span data-stu-id="d1dbf-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1dbf-119">子要素</span><span class="sxs-lookup"><span data-stu-id="d1dbf-119">Child Elements</span></span>  
  
|<span data-ttu-id="d1dbf-120">要素</span><span class="sxs-lookup"><span data-stu-id="d1dbf-120">Element</span></span>|<span data-ttu-id="d1dbf-121">説明</span><span class="sxs-lookup"><span data-stu-id="d1dbf-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1dbf-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="d1dbf-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="d1dbf-123">ビルダーが作成できるエンドポイントのアドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="d1dbf-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="d1dbf-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="d1dbf-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="d1dbf-125">発行されたトークンを使用する場合、クライアントでサーバーの認証を有効にする設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1dbf-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d1dbf-126">親要素</span><span class="sxs-lookup"><span data-stu-id="d1dbf-126">Parent Elements</span></span>  
  
|<span data-ttu-id="d1dbf-127">要素</span><span class="sxs-lookup"><span data-stu-id="d1dbf-127">Element</span></span>|<span data-ttu-id="d1dbf-128">説明</span><span class="sxs-lookup"><span data-stu-id="d1dbf-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1dbf-129">\<message></span><span class="sxs-lookup"><span data-stu-id="d1dbf-129">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="d1dbf-130">メッセージ レベル セキュリティの設定を定義、 [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)要素。</span><span class="sxs-lookup"><span data-stu-id="d1dbf-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1dbf-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1dbf-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="d1dbf-132">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="d1dbf-132">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d1dbf-133">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="d1dbf-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d1dbf-134">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="d1dbf-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d1dbf-135">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="d1dbf-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d1dbf-136">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="d1dbf-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="d1dbf-137">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="d1dbf-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
