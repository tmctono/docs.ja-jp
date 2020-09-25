---
title: <issuerMetadata> の <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: 389ac9e96c1462f59bc42b2e20cb511acdefda00
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185666"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="3cf37-102">\<issuerMetadata> の \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="3cf37-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="3cf37-103">構文</span><span class="sxs-lookup"><span data-stu-id="3cf37-103">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cf37-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3cf37-104">Attributes and Elements</span></span>  

 <span data-ttu-id="3cf37-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cf37-106">属性</span><span class="sxs-lookup"><span data-stu-id="3cf37-106">Attributes</span></span>  
  
|<span data-ttu-id="3cf37-107">属性</span><span class="sxs-lookup"><span data-stu-id="3cf37-107">Attribute</span></span>|<span data-ttu-id="3cf37-108">説明</span><span class="sxs-lookup"><span data-stu-id="3cf37-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3cf37-109">address</span><span class="sxs-lookup"><span data-stu-id="3cf37-109">address</span></span>|<span data-ttu-id="3cf37-110">必須。</span><span class="sxs-lookup"><span data-stu-id="3cf37-110">Required.</span></span> <span data-ttu-id="3cf37-111">エンドポイントのアドレスを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="3cf37-111">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="3cf37-112">アドレスは、絶対 URI にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf37-112">The address must be an absolute URI.</span></span> <span data-ttu-id="3cf37-113">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="3cf37-113">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cf37-114">子要素</span><span class="sxs-lookup"><span data-stu-id="3cf37-114">Child Elements</span></span>  
  
|<span data-ttu-id="3cf37-115">要素</span><span class="sxs-lookup"><span data-stu-id="3cf37-115">Element</span></span>|<span data-ttu-id="3cf37-116">説明</span><span class="sxs-lookup"><span data-stu-id="3cf37-116">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="3cf37-117">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="3cf37-117">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="3cf37-118">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="3cf37-118">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3cf37-119">親要素</span><span class="sxs-lookup"><span data-stu-id="3cf37-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3cf37-120">要素</span><span class="sxs-lookup"><span data-stu-id="3cf37-120">Element</span></span>|<span data-ttu-id="3cf37-121">説明</span><span class="sxs-lookup"><span data-stu-id="3cf37-121">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="3cf37-122">フェデレーション セキュリティのシナリオで発行されるセキュリティ トークンのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="3cf37-122">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3cf37-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cf37-123">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="3cf37-124">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="3cf37-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="3cf37-125">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="3cf37-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3cf37-126">カスタム バインディングを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="3cf37-126">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="3cf37-127">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="3cf37-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3cf37-128">バインド</span><span class="sxs-lookup"><span data-stu-id="3cf37-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3cf37-129">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="3cf37-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3cf37-130">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="3cf37-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="3cf37-131">方法: SecurityBindingElement を使用してカスタム バインドを作成する</span><span class="sxs-lookup"><span data-stu-id="3cf37-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="3cf37-132">カスタム バインディング セキュリティ</span><span class="sxs-lookup"><span data-stu-id="3cf37-132">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
