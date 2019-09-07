---
title: <issuer> の <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bdd5ad45984fae7b39defe82c4af75845dfda1b6
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397942"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="51d89-102">\<issuedTokenParameters > の\<発行者 ></span><span class="sxs-lookup"><span data-stu-id="51d89-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="51d89-103">セキュリティ トークンを発行するセキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="51d89-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
<span data-ttu-id="51d89-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="51d89-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="51d89-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="51d89-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="51d89-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="51d89-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="51d89-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="51d89-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="51d89-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="51d89-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="51d89-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<セキュリティ >** ](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="51d89-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="51d89-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenParameters >** ](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="51d89-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="51d89-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<発行者の >**</span><span class="sxs-lookup"><span data-stu-id="51d89-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51d89-112">構文</span><span class="sxs-lookup"><span data-stu-id="51d89-112">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51d89-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="51d89-113">Attributes and Elements</span></span>  
 <span data-ttu-id="51d89-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="51d89-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51d89-115">属性</span><span class="sxs-lookup"><span data-stu-id="51d89-115">Attributes</span></span>  
  
|<span data-ttu-id="51d89-116">属性</span><span class="sxs-lookup"><span data-stu-id="51d89-116">Attribute</span></span>|<span data-ttu-id="51d89-117">説明</span><span class="sxs-lookup"><span data-stu-id="51d89-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51d89-118">address</span><span class="sxs-lookup"><span data-stu-id="51d89-118">address</span></span>|<span data-ttu-id="51d89-119">必須の文字列。</span><span class="sxs-lookup"><span data-stu-id="51d89-119">Required string.</span></span> <span data-ttu-id="51d89-120">STS の URL です。</span><span class="sxs-lookup"><span data-stu-id="51d89-120">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51d89-121">子要素</span><span class="sxs-lookup"><span data-stu-id="51d89-121">Child Elements</span></span>  
  
|<span data-ttu-id="51d89-122">要素</span><span class="sxs-lookup"><span data-stu-id="51d89-122">Element</span></span>|<span data-ttu-id="51d89-123">説明</span><span class="sxs-lookup"><span data-stu-id="51d89-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51d89-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="51d89-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="51d89-125">ビルダーが作成できるエンドポイントのアドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="51d89-125">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="51d89-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="51d89-126">\<identity></span></span>](identity.md)|<span data-ttu-id="51d89-127">発行されたトークンを使用する場合、クライアントでサーバーの認証を有効にする設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="51d89-127">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51d89-128">親要素</span><span class="sxs-lookup"><span data-stu-id="51d89-128">Parent Elements</span></span>  
  
|<span data-ttu-id="51d89-129">要素</span><span class="sxs-lookup"><span data-stu-id="51d89-129">Element</span></span>|<span data-ttu-id="51d89-130">説明</span><span class="sxs-lookup"><span data-stu-id="51d89-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51d89-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="51d89-131">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="51d89-132">現在発行されているトークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="51d89-132">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51d89-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="51d89-133">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="51d89-134">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="51d89-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="51d89-135">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="51d89-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="51d89-136">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="51d89-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="51d89-137">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="51d89-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="51d89-138">バインディング</span><span class="sxs-lookup"><span data-stu-id="51d89-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="51d89-139">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="51d89-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="51d89-140">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="51d89-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="51d89-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="51d89-141">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="51d89-142">方法: 設定を使用してカスタムバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="51d89-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="51d89-143">カスタム バインド セキュリティ</span><span class="sxs-lookup"><span data-stu-id="51d89-143">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
