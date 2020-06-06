---
title: <issuerMetadata> の <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: fcdd66ecd162dff5be86a1d4ab1b196f50dbd445
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400340"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="e7579-102">\<issuerMetadata> の \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="e7579-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="e7579-103">構文</span><span class="sxs-lookup"><span data-stu-id="e7579-103">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7579-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e7579-104">Attributes and Elements</span></span>  
 <span data-ttu-id="e7579-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7579-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7579-106">属性</span><span class="sxs-lookup"><span data-stu-id="e7579-106">Attributes</span></span>  
  
|<span data-ttu-id="e7579-107">属性</span><span class="sxs-lookup"><span data-stu-id="e7579-107">Attribute</span></span>|<span data-ttu-id="e7579-108">説明</span><span class="sxs-lookup"><span data-stu-id="e7579-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7579-109">address</span><span class="sxs-lookup"><span data-stu-id="e7579-109">address</span></span>|<span data-ttu-id="e7579-110">必須。</span><span class="sxs-lookup"><span data-stu-id="e7579-110">Required.</span></span> <span data-ttu-id="e7579-111">エンドポイントのアドレスを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="e7579-111">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="e7579-112">アドレスは、絶対 URI にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7579-112">The address must be an absolute URI.</span></span> <span data-ttu-id="e7579-113">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="e7579-113">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7579-114">子要素</span><span class="sxs-lookup"><span data-stu-id="e7579-114">Child Elements</span></span>  
  
|<span data-ttu-id="e7579-115">要素</span><span class="sxs-lookup"><span data-stu-id="e7579-115">Element</span></span>|<span data-ttu-id="e7579-116">Description</span><span class="sxs-lookup"><span data-stu-id="e7579-116">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="e7579-117">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="e7579-117">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="e7579-118">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="e7579-118">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e7579-119">親要素</span><span class="sxs-lookup"><span data-stu-id="e7579-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e7579-120">要素</span><span class="sxs-lookup"><span data-stu-id="e7579-120">Element</span></span>|<span data-ttu-id="e7579-121">Description</span><span class="sxs-lookup"><span data-stu-id="e7579-121">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="e7579-122">フェデレーション セキュリティのシナリオで発行されるセキュリティ トークンのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7579-122">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7579-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7579-123">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e7579-124">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="e7579-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e7579-125">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="e7579-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e7579-126">カスタム バインディングを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="e7579-126">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="e7579-127">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="e7579-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e7579-128">バインド</span><span class="sxs-lookup"><span data-stu-id="e7579-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e7579-129">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="e7579-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e7579-130">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="e7579-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="e7579-131">方法: SecurityBindingElement を使用してカスタム バインドを作成する</span><span class="sxs-lookup"><span data-stu-id="e7579-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="e7579-132">カスタム バインディング セキュリティ</span><span class="sxs-lookup"><span data-stu-id="e7579-132">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
