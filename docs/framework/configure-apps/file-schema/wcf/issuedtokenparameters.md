---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 6bdf56e3d2084dec8d44e1c4d3f0c1e50b711b92
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758238"
---
# <a name="issuedtokenparameters"></a><span data-ttu-id="2d1ab-101">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="2d1ab-101">\<issuedTokenParameters></span></span>
<span data-ttu-id="2d1ab-102">フェデレーション セキュリティのシナリオで発行されるセキュリティ トークンのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-102">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="2d1ab-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2d1ab-103">\<system.serviceModel></span></span>  
<span data-ttu-id="2d1ab-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2d1ab-104">\<bindings></span></span>  
<span data-ttu-id="2d1ab-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2d1ab-105">\<customBinding></span></span>  
<span data-ttu-id="2d1ab-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="2d1ab-106">\<binding></span></span>  
<span data-ttu-id="2d1ab-107">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="2d1ab-107">\<security></span></span>  
<span data-ttu-id="2d1ab-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="2d1ab-108">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d1ab-109">構文</span><span class="sxs-lookup"><span data-stu-id="2d1ab-109">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="2d1ab-110">型</span><span class="sxs-lookup"><span data-stu-id="2d1ab-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d1ab-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2d1ab-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2d1ab-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d1ab-113">属性</span><span class="sxs-lookup"><span data-stu-id="2d1ab-113">Attributes</span></span>  
  
|<span data-ttu-id="2d1ab-114">属性</span><span class="sxs-lookup"><span data-stu-id="2d1ab-114">Attribute</span></span>|<span data-ttu-id="2d1ab-115">説明</span><span class="sxs-lookup"><span data-stu-id="2d1ab-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2d1ab-116">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="2d1ab-116">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="2d1ab-117">バインドでサポートする必要があるセキュリティ仕様 (WS-Security、WS-Trust、WS-Secure Conversation、および WS-Security Policy) のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-117">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="2d1ab-118">この値は、<xref:System.ServiceModel.MessageSecurityVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-118">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="2d1ab-119">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="2d1ab-119">inclusionMode</span></span>|<span data-ttu-id="2d1ab-120">トークン包含要件を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-120">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="2d1ab-121">この属性は <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-121">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="2d1ab-122">keySize</span><span class="sxs-lookup"><span data-stu-id="2d1ab-122">keySize</span></span>|<span data-ttu-id="2d1ab-123">トークン キー サイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-123">An integer that specifies the token key size.</span></span> <span data-ttu-id="2d1ab-124">既定値は 256 です。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-124">The default value is 256.</span></span>|  
|<span data-ttu-id="2d1ab-125">keyType</span><span class="sxs-lookup"><span data-stu-id="2d1ab-125">keyType</span></span>|<span data-ttu-id="2d1ab-126">キーの型を指定する <xref:System.IdentityModel.Tokens.SecurityKeyType> の有効な値。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-126">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="2d1ab-127">既定値は `SymmetricKey` です。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-127">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="2d1ab-128">tokenType</span><span class="sxs-lookup"><span data-stu-id="2d1ab-128">tokenType</span></span>|<span data-ttu-id="2d1ab-129">トークンの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-129">A string that specifies the token type.</span></span> <span data-ttu-id="2d1ab-130">既定値は "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML" です。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-130">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d1ab-131">子要素</span><span class="sxs-lookup"><span data-stu-id="2d1ab-131">Child Elements</span></span>  
  
|<span data-ttu-id="2d1ab-132">要素</span><span class="sxs-lookup"><span data-stu-id="2d1ab-132">Element</span></span>|<span data-ttu-id="2d1ab-133">説明</span><span class="sxs-lookup"><span data-stu-id="2d1ab-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d1ab-134">\<additionalRequestParameters></span><span class="sxs-lookup"><span data-stu-id="2d1ab-134">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="2d1ab-135">追加の要求パラメーターを指定する構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-135">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="2d1ab-136">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="2d1ab-136">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="2d1ab-137">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-137">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="2d1ab-138">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="2d1ab-139">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="2d1ab-140">このコレクションの要素はそれぞれ、フェデレーション資格情報に表示されると予想される必須の要求および省略可能な要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-140">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="2d1ab-141">\<issuer></span><span class="sxs-lookup"><span data-stu-id="2d1ab-141">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="2d1ab-142">現在のトークンを発行するエンドポイントを指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-142">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="2d1ab-143">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="2d1ab-143">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="2d1ab-144">トークン発行者のメタデータのエンドポイント アドレスを指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-144">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2d1ab-145">親要素</span><span class="sxs-lookup"><span data-stu-id="2d1ab-145">Parent Elements</span></span>  
  
|<span data-ttu-id="2d1ab-146">要素</span><span class="sxs-lookup"><span data-stu-id="2d1ab-146">Element</span></span>|<span data-ttu-id="2d1ab-147">説明</span><span class="sxs-lookup"><span data-stu-id="2d1ab-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d1ab-148">\<secureConversationBootstrap></span><span class="sxs-lookup"><span data-stu-id="2d1ab-148">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="2d1ab-149">セキュリティで保護されたメッセージ交換サービスの開始に使用される既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-149">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="2d1ab-150">\<security></span><span class="sxs-lookup"><span data-stu-id="2d1ab-150">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="2d1ab-151">カスタム バインドのセキュリティ オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-151">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d1ab-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d1ab-152">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2d1ab-153">バインディング</span><span class="sxs-lookup"><span data-stu-id="2d1ab-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="2d1ab-154">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="2d1ab-154">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2d1ab-155">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="2d1ab-155">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="2d1ab-156">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2d1ab-156">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="2d1ab-157">方法: SecurityBindingElement を使用してカスタム バインディングを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d1ab-157">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="2d1ab-158">カスタム バインド セキュリティ</span><span class="sxs-lookup"><span data-stu-id="2d1ab-158">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="2d1ab-159">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="2d1ab-159">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2d1ab-160">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="2d1ab-160">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2d1ab-161">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="2d1ab-161">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="2d1ab-162">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="2d1ab-162">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
