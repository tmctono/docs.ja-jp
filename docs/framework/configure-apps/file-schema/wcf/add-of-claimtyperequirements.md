---
title: <add> の <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 53da9dacbd3277bd8b608296a1515e3da7296f1c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398368"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="124d4-102">\<add> of \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="124d4-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="124d4-103">フェデレーション資格情報に表示されると予想される必須のクレームおよび省略可能なクレームの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="124d4-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="124d4-104">たとえば、サービスは、クレームの種類の特定のセットを処理する必要がある受信資格情報について要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="124d4-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="124d4-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="124d4-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="124d4-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="124d4-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="124d4-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="124d4-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="124d4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="124d4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="124d4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="124d4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="124d4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<セキュリティ >** ](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="124d4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="124d4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenParameters >** ](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="124d4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="124d4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<claimTypeRequirements >** ](claimtyperequirements-element.md)</span><span class="sxs-lookup"><span data-stu-id="124d4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)</span></span>\
<span data-ttu-id="124d4-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="124d4-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="124d4-114">構文</span><span class="sxs-lookup"><span data-stu-id="124d4-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="124d4-115">属性および要素</span><span class="sxs-lookup"><span data-stu-id="124d4-115">Attributes and Elements</span></span>  
 <span data-ttu-id="124d4-116">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="124d4-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="124d4-117">属性</span><span class="sxs-lookup"><span data-stu-id="124d4-117">Attributes</span></span>  
  
|<span data-ttu-id="124d4-118">属性</span><span class="sxs-lookup"><span data-stu-id="124d4-118">Attribute</span></span>|<span data-ttu-id="124d4-119">説明</span><span class="sxs-lookup"><span data-stu-id="124d4-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="124d4-120">claimType</span><span class="sxs-lookup"><span data-stu-id="124d4-120">claimType</span></span>|<span data-ttu-id="124d4-121">クレームの種類を定義する URI。</span><span class="sxs-lookup"><span data-stu-id="124d4-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="124d4-122">たとえば、Web サイトから製品を購入するために、ユーザーは、十分な与信限度額を備えた有効なクレジット カードを示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="124d4-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="124d4-123">クレームの種類として、クレジット カードの URI があります。</span><span class="sxs-lookup"><span data-stu-id="124d4-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="124d4-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="124d4-124">isOptional</span></span>|<span data-ttu-id="124d4-125">これが省略可能なクレームかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="124d4-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="124d4-126">これが必須のクレームの場合は、この属性を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="124d4-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="124d4-127">サービスが必須でない情報を求めるときにこの属性を使用できます。</span><span class="sxs-lookup"><span data-stu-id="124d4-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="124d4-128">たとえば、ユーザーに氏名と住所の入力を要求し、電話番号は省略可能にする場合などです。</span><span class="sxs-lookup"><span data-stu-id="124d4-128">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="124d4-129">子要素</span><span class="sxs-lookup"><span data-stu-id="124d4-129">Child Elements</span></span>  
 <span data-ttu-id="124d4-130">なし。</span><span class="sxs-lookup"><span data-stu-id="124d4-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="124d4-131">親要素</span><span class="sxs-lookup"><span data-stu-id="124d4-131">Parent Elements</span></span>  
  
|<span data-ttu-id="124d4-132">要素</span><span class="sxs-lookup"><span data-stu-id="124d4-132">Element</span></span>|<span data-ttu-id="124d4-133">説明</span><span class="sxs-lookup"><span data-stu-id="124d4-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="124d4-134">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="124d4-134">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="124d4-135">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="124d4-135">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="124d4-136">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="124d4-136">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="124d4-137">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="124d4-137">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="124d4-138">このコレクションの要素はそれぞれ、フェデレーション資格情報に表示されると予想される必須の要求および省略可能な要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="124d4-138">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="124d4-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="124d4-139">Remarks</span></span>  
 <span data-ttu-id="124d4-140">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="124d4-140">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="124d4-141">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="124d4-141">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="124d4-142">この要件はセキュリティ ポリシー内に明記されます。</span><span class="sxs-lookup"><span data-stu-id="124d4-142">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="124d4-143">クライアントがフェデレーション サービスの資格情報 (CardSpace など) を要求する場合、クライアントは要件をトークン要求 (RequestSecurityToken) に設定します。これにより、フェデレーション サービスは、要件どおりの資格情報を発行できます。</span><span class="sxs-lookup"><span data-stu-id="124d4-143">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="124d4-144">例</span><span class="sxs-lookup"><span data-stu-id="124d4-144">Example</span></span>  
 <span data-ttu-id="124d4-145">次の構成では、2 つのクレームの種類の要件をセキュリティ バインディングに追加しています。</span><span class="sxs-lookup"><span data-stu-id="124d4-145">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="myFederatedBinding">
      <security mode="Message">
        <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">
          <claimTypeRequirements>
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress" />
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"
                 optional="true" />
          </claimTypeRequirements>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="124d4-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="124d4-146">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="124d4-147">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="124d4-147">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)
- [<span data-ttu-id="124d4-148">バインディング</span><span class="sxs-lookup"><span data-stu-id="124d4-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="124d4-149">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="124d4-149">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="124d4-150">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="124d4-150">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="124d4-151">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="124d4-151">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="124d4-152">方法: 設定を使用してカスタムバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="124d4-152">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="124d4-153">カスタム バインド セキュリティ</span><span class="sxs-lookup"><span data-stu-id="124d4-153">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
