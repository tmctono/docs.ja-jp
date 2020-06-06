---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 8432463ff62e4b5e54a491b574cc6a5285efe220
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397953"
---
# \<issuedTokenParameters>
<span data-ttu-id="ccf9c-101">フェデレーション セキュリティのシナリオで発行されるセキュリティ トークンのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-101">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenParameters>**  
  
## <a name="syntax"></a><span data-ttu-id="ccf9c-102">構文</span><span class="sxs-lookup"><span data-stu-id="ccf9c-102">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="ccf9c-103">Type</span><span class="sxs-lookup"><span data-stu-id="ccf9c-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccf9c-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ccf9c-104">Attributes and Elements</span></span>  
 <span data-ttu-id="ccf9c-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccf9c-106">属性</span><span class="sxs-lookup"><span data-stu-id="ccf9c-106">Attributes</span></span>  
  
|<span data-ttu-id="ccf9c-107">属性</span><span class="sxs-lookup"><span data-stu-id="ccf9c-107">Attribute</span></span>|<span data-ttu-id="ccf9c-108">説明</span><span class="sxs-lookup"><span data-stu-id="ccf9c-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ccf9c-109">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="ccf9c-109">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="ccf9c-110">バインドでサポートする必要があるセキュリティ仕様 (WS-Security、WS-Trust、WS-Secure Conversation、および WS-Security Policy) のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-110">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="ccf9c-111">この値は、<xref:System.ServiceModel.MessageSecurityVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-111">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="ccf9c-112">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="ccf9c-112">inclusionMode</span></span>|<span data-ttu-id="ccf9c-113">トークン包含要件を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-113">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="ccf9c-114">この属性は <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-114">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="ccf9c-115">keySize</span><span class="sxs-lookup"><span data-stu-id="ccf9c-115">keySize</span></span>|<span data-ttu-id="ccf9c-116">トークン キー サイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-116">An integer that specifies the token key size.</span></span> <span data-ttu-id="ccf9c-117">既定値は 256 です。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-117">The default value is 256.</span></span>|  
|<span data-ttu-id="ccf9c-118">keyType</span><span class="sxs-lookup"><span data-stu-id="ccf9c-118">keyType</span></span>|<span data-ttu-id="ccf9c-119">キーの型を指定する <xref:System.IdentityModel.Tokens.SecurityKeyType> の有効な値。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-119">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="ccf9c-120">既定値は、`SymmetricKey` です。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-120">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="ccf9c-121">tokenType</span><span class="sxs-lookup"><span data-stu-id="ccf9c-121">tokenType</span></span>|<span data-ttu-id="ccf9c-122">トークンの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-122">A string that specifies the token type.</span></span> <span data-ttu-id="ccf9c-123">既定値は "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML" です。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-123">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ccf9c-124">子要素</span><span class="sxs-lookup"><span data-stu-id="ccf9c-124">Child Elements</span></span>  
  
|<span data-ttu-id="ccf9c-125">要素</span><span class="sxs-lookup"><span data-stu-id="ccf9c-125">Element</span></span>|<span data-ttu-id="ccf9c-126">Description</span><span class="sxs-lookup"><span data-stu-id="ccf9c-126">Description</span></span>|  
|-------------|-----------------|  
|[\<additionalRequestParameters>](additionalrequestparameters-element.md)|<span data-ttu-id="ccf9c-127">追加の要求パラメーターを指定する構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-127">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="ccf9c-128">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-128">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="ccf9c-129">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-129">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="ccf9c-130">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-130">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="ccf9c-131">このコレクションの要素はそれぞれ、フェデレーション資格情報に表示されると予想される必須の要求および省略可能な要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-131">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[\<issuer>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="ccf9c-132">現在のトークンを発行するエンドポイントを指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-132">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[\<issuerMetadata>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="ccf9c-133">トークン発行者のメタデータのエンドポイント アドレスを指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-133">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ccf9c-134">親要素</span><span class="sxs-lookup"><span data-stu-id="ccf9c-134">Parent Elements</span></span>  
  
|<span data-ttu-id="ccf9c-135">要素</span><span class="sxs-lookup"><span data-stu-id="ccf9c-135">Element</span></span>|<span data-ttu-id="ccf9c-136">Description</span><span class="sxs-lookup"><span data-stu-id="ccf9c-136">Description</span></span>|  
|-------------|-----------------|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="ccf9c-137">セキュリティで保護されたメッセージ交換サービスの開始に使用される既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-137">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="ccf9c-138">カスタム バインドのセキュリティ オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ccf9c-138">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ccf9c-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccf9c-139">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ccf9c-140">バインド</span><span class="sxs-lookup"><span data-stu-id="ccf9c-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ccf9c-141">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="ccf9c-141">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ccf9c-142">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="ccf9c-142">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="ccf9c-143">方法: SecurityBindingElement を使用してカスタム バインドを作成する</span><span class="sxs-lookup"><span data-stu-id="ccf9c-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="ccf9c-144">カスタム バインディング セキュリティ</span><span class="sxs-lookup"><span data-stu-id="ccf9c-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="ccf9c-145">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="ccf9c-145">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ccf9c-146">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="ccf9c-146">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ccf9c-147">カスタム バインディングを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="ccf9c-147">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="ccf9c-148">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="ccf9c-148">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
