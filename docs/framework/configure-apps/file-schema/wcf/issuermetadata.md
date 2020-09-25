---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 10a6d2aaad7d63d00b3a57032d0d218f756454d8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175955"
---
# \<issuerMetadata>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="3e8a6-101">構文</span><span class="sxs-lookup"><span data-stu-id="3e8a6-101">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e8a6-102">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3e8a6-102">Attributes and Elements</span></span>  

 <span data-ttu-id="3e8a6-103">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e8a6-103">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e8a6-104">属性</span><span class="sxs-lookup"><span data-stu-id="3e8a6-104">Attributes</span></span>  
  
|<span data-ttu-id="3e8a6-105">属性</span><span class="sxs-lookup"><span data-stu-id="3e8a6-105">Attribute</span></span>|<span data-ttu-id="3e8a6-106">説明</span><span class="sxs-lookup"><span data-stu-id="3e8a6-106">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e8a6-107">address</span><span class="sxs-lookup"><span data-stu-id="3e8a6-107">address</span></span>|<span data-ttu-id="3e8a6-108">必須の `string` 属性です。</span><span class="sxs-lookup"><span data-stu-id="3e8a6-108">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="3e8a6-109">エンドポイントのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e8a6-109">Specifies the address of the endpoint.</span></span> <span data-ttu-id="3e8a6-110">アドレスは、絶対 URI にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e8a6-110">The address must be an absolute URI.</span></span> <span data-ttu-id="3e8a6-111">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="3e8a6-111">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e8a6-112">子要素</span><span class="sxs-lookup"><span data-stu-id="3e8a6-112">Child Elements</span></span>  
  
|<span data-ttu-id="3e8a6-113">要素</span><span class="sxs-lookup"><span data-stu-id="3e8a6-113">Element</span></span>|<span data-ttu-id="3e8a6-114">説明</span><span class="sxs-lookup"><span data-stu-id="3e8a6-114">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="3e8a6-115">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="3e8a6-115">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="3e8a6-116">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="3e8a6-116">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3e8a6-117">親要素</span><span class="sxs-lookup"><span data-stu-id="3e8a6-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3e8a6-118">要素</span><span class="sxs-lookup"><span data-stu-id="3e8a6-118">Element</span></span>|<span data-ttu-id="3e8a6-119">説明</span><span class="sxs-lookup"><span data-stu-id="3e8a6-119">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="3e8a6-120">要素のメッセージレベルセキュリティの設定を定義し [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="3e8a6-120">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e8a6-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e8a6-121">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="3e8a6-122">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="3e8a6-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="3e8a6-123">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="3e8a6-123">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3e8a6-124">カスタム バインディングを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="3e8a6-124">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="3e8a6-125">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="3e8a6-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
