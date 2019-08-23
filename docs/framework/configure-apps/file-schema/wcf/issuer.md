---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 08fda249b526961ff711f439cf729a18e15b412b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929372"
---
# <a name="issuer"></a><span data-ttu-id="f3558-101">\<発行者の ></span><span class="sxs-lookup"><span data-stu-id="f3558-101">\<issuer></span></span>
<span data-ttu-id="f3558-102">セキュリティ トークンを発行するセキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3558-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="f3558-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f3558-103">\<system.serviceModel></span></span>  
<span data-ttu-id="f3558-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f3558-104">\<bindings></span></span>  
<span data-ttu-id="f3558-105">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="f3558-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="f3558-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="f3558-106">\<binding></span></span>  
<span data-ttu-id="f3558-107">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="f3558-107">\<security></span></span>  
<span data-ttu-id="f3558-108">\<message></span><span class="sxs-lookup"><span data-stu-id="f3558-108">\<message></span></span>  
<span data-ttu-id="f3558-109">\<発行者の ></span><span class="sxs-lookup"><span data-stu-id="f3558-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3558-110">構文</span><span class="sxs-lookup"><span data-stu-id="f3558-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3558-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f3558-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f3558-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3558-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3558-113">属性</span><span class="sxs-lookup"><span data-stu-id="f3558-113">Attributes</span></span>  
  
|<span data-ttu-id="f3558-114">属性</span><span class="sxs-lookup"><span data-stu-id="f3558-114">Attribute</span></span>|<span data-ttu-id="f3558-115">説明</span><span class="sxs-lookup"><span data-stu-id="f3558-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3558-116">address</span><span class="sxs-lookup"><span data-stu-id="f3558-116">address</span></span>|<span data-ttu-id="f3558-117">必須の文字列。</span><span class="sxs-lookup"><span data-stu-id="f3558-117">Required string.</span></span> <span data-ttu-id="f3558-118">STS の URL です。</span><span class="sxs-lookup"><span data-stu-id="f3558-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3558-119">子要素</span><span class="sxs-lookup"><span data-stu-id="f3558-119">Child Elements</span></span>  
  
|<span data-ttu-id="f3558-120">要素</span><span class="sxs-lookup"><span data-stu-id="f3558-120">Element</span></span>|<span data-ttu-id="f3558-121">説明</span><span class="sxs-lookup"><span data-stu-id="f3558-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3558-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="f3558-122">\<headers></span></span>](headers-element.md)|<span data-ttu-id="f3558-123">ビルダーが作成できるエンドポイントのアドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="f3558-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="f3558-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="f3558-124">\<identity></span></span>](identity.md)|<span data-ttu-id="f3558-125">発行されたトークンを使用する場合、クライアントでサーバーの認証を有効にする設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3558-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f3558-126">親要素</span><span class="sxs-lookup"><span data-stu-id="f3558-126">Parent Elements</span></span>  
  
|<span data-ttu-id="f3558-127">要素</span><span class="sxs-lookup"><span data-stu-id="f3558-127">Element</span></span>|<span data-ttu-id="f3558-128">説明</span><span class="sxs-lookup"><span data-stu-id="f3558-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3558-129">\<message></span><span class="sxs-lookup"><span data-stu-id="f3558-129">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="f3558-130">WsFederationHttpBinding > 要素の[ \<](wsfederationhttpbinding.md)メッセージレベルセキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="f3558-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3558-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3558-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="f3558-132">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="f3558-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f3558-133">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="f3558-133">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f3558-134">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="f3558-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f3558-135">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="f3558-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f3558-136">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="f3558-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="f3558-137">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="f3558-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
