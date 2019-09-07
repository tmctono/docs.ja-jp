---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 8432463ff62e4b5e54a491b574cc6a5285efe220
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397953"
---
# <a name="issuedtokenparameters"></a><span data-ttu-id="2492c-101">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="2492c-101">\<issuedTokenParameters></span></span>
<span data-ttu-id="2492c-102">フェデレーション セキュリティのシナリオで発行されるセキュリティ トークンのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="2492c-102">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
<span data-ttu-id="2492c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2492c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2492c-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2492c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2492c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2492c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2492c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="2492c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="2492c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="2492c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2492c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<セキュリティ >** ](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="2492c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="2492c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuedTokenParameters >**</span><span class="sxs-lookup"><span data-stu-id="2492c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenParameters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2492c-110">構文</span><span class="sxs-lookup"><span data-stu-id="2492c-110">Syntax</span></span>  
  
```xml  
<issuedTokenParameters defaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"
                       inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"
                       keySize="Integer"
                       keyType="AsymmetricKey/BearerKey/SymmetricKey"
                       tokenType="String">
  <additionalRequestParameters />
  <claimTypeRequirements>
    <add claimType="URI"
         isOptional="Boolean" />
  </claimTypeRequirements>
  <issuer address="String"
          binding="" />
  <issuerMetadata address="String" />
</issuedTokenParameters>
```  
  
## <a name="type"></a><span data-ttu-id="2492c-111">型</span><span class="sxs-lookup"><span data-stu-id="2492c-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2492c-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2492c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2492c-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2492c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2492c-114">属性</span><span class="sxs-lookup"><span data-stu-id="2492c-114">Attributes</span></span>  
  
|<span data-ttu-id="2492c-115">属性</span><span class="sxs-lookup"><span data-stu-id="2492c-115">Attribute</span></span>|<span data-ttu-id="2492c-116">説明</span><span class="sxs-lookup"><span data-stu-id="2492c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2492c-117">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="2492c-117">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="2492c-118">バインドでサポートする必要があるセキュリティ仕様 (WS-Security、WS-Trust、WS-Secure Conversation、および WS-Security Policy) のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="2492c-118">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="2492c-119">この値は、<xref:System.ServiceModel.MessageSecurityVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="2492c-119">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="2492c-120">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="2492c-120">inclusionMode</span></span>|<span data-ttu-id="2492c-121">トークン包含要件を指定します。</span><span class="sxs-lookup"><span data-stu-id="2492c-121">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="2492c-122">この属性は <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="2492c-122">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="2492c-123">keySize</span><span class="sxs-lookup"><span data-stu-id="2492c-123">keySize</span></span>|<span data-ttu-id="2492c-124">トークン キー サイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="2492c-124">An integer that specifies the token key size.</span></span> <span data-ttu-id="2492c-125">既定値は 256 です。</span><span class="sxs-lookup"><span data-stu-id="2492c-125">The default value is 256.</span></span>|  
|<span data-ttu-id="2492c-126">keyType</span><span class="sxs-lookup"><span data-stu-id="2492c-126">keyType</span></span>|<span data-ttu-id="2492c-127">キーの型を指定する <xref:System.IdentityModel.Tokens.SecurityKeyType> の有効な値。</span><span class="sxs-lookup"><span data-stu-id="2492c-127">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="2492c-128">既定値は `SymmetricKey` です。</span><span class="sxs-lookup"><span data-stu-id="2492c-128">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="2492c-129">tokenType</span><span class="sxs-lookup"><span data-stu-id="2492c-129">tokenType</span></span>|<span data-ttu-id="2492c-130">トークンの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="2492c-130">A string that specifies the token type.</span></span> <span data-ttu-id="2492c-131">既定値は "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML" です。</span><span class="sxs-lookup"><span data-stu-id="2492c-131">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2492c-132">子要素</span><span class="sxs-lookup"><span data-stu-id="2492c-132">Child Elements</span></span>  
  
|<span data-ttu-id="2492c-133">要素</span><span class="sxs-lookup"><span data-stu-id="2492c-133">Element</span></span>|<span data-ttu-id="2492c-134">説明</span><span class="sxs-lookup"><span data-stu-id="2492c-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2492c-135">\<additionalRequestParameters></span><span class="sxs-lookup"><span data-stu-id="2492c-135">\<additionalRequestParameters></span></span>](additionalrequestparameters-element.md)|<span data-ttu-id="2492c-136">追加の要求パラメーターを指定する構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="2492c-136">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="2492c-137">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="2492c-137">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="2492c-138">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="2492c-138">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="2492c-139">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="2492c-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="2492c-140">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2492c-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="2492c-141">このコレクションの要素はそれぞれ、フェデレーション資格情報に表示されると予想される必須の要求および省略可能な要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="2492c-141">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="2492c-142">\<issuer></span><span class="sxs-lookup"><span data-stu-id="2492c-142">\<issuer></span></span>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="2492c-143">現在のトークンを発行するエンドポイントを指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="2492c-143">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="2492c-144">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="2492c-144">\<issuerMetadata></span></span>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="2492c-145">トークン発行者のメタデータのエンドポイント アドレスを指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="2492c-145">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2492c-146">親要素</span><span class="sxs-lookup"><span data-stu-id="2492c-146">Parent Elements</span></span>  
  
|<span data-ttu-id="2492c-147">要素</span><span class="sxs-lookup"><span data-stu-id="2492c-147">Element</span></span>|<span data-ttu-id="2492c-148">説明</span><span class="sxs-lookup"><span data-stu-id="2492c-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2492c-149">\<secureConversationBootstrap></span><span class="sxs-lookup"><span data-stu-id="2492c-149">\<secureConversationBootstrap></span></span>](secureconversationbootstrap.md)|<span data-ttu-id="2492c-150">セキュリティで保護されたメッセージ交換サービスの開始に使用される既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2492c-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="2492c-151">\<security></span><span class="sxs-lookup"><span data-stu-id="2492c-151">\<security></span></span>](security-of-custombinding.md)|<span data-ttu-id="2492c-152">カスタム バインドのセキュリティ オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="2492c-152">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2492c-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="2492c-153">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2492c-154">バインディング</span><span class="sxs-lookup"><span data-stu-id="2492c-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2492c-155">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="2492c-155">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2492c-156">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="2492c-156">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="2492c-157">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2492c-157">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="2492c-158">方法: 設定を使用してカスタムバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="2492c-158">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="2492c-159">カスタム バインド セキュリティ</span><span class="sxs-lookup"><span data-stu-id="2492c-159">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="2492c-160">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="2492c-160">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2492c-161">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="2492c-161">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2492c-162">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="2492c-162">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="2492c-163">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="2492c-163">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
