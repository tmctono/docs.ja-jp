---
title: <add>要素<claimTypeRequirements>の
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: f6948052c62684faa734b592f5bdfc2e7827a07a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153101"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="8edd3-102">\<>を\<追加する必要>要素</span><span class="sxs-lookup"><span data-stu-id="8edd3-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="8edd3-103">フェデレーション資格情報に表示されると予想される必須のクレームおよび省略可能なクレームの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="8edd3-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="8edd3-104">たとえば、サービスは、クレームの種類の特定のセットを処理する必要がある受信資格情報について要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="8edd3-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="8edd3-105">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8edd3-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8edd3-106">&nbsp;&nbsp;[**\<システム.サービスモデル>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8edd3-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8edd3-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<バインディング>**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="8edd3-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8edd3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8edd3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="8edd3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<バインド>**</span><span class="sxs-lookup"><span data-stu-id="8edd3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8edd3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<セキュリティ>**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="8edd3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="8edd3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<メッセージ>**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8edd3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="8edd3-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<要求型要件>**](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="8edd3-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="8edd3-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>を追加する**</span><span class="sxs-lookup"><span data-stu-id="8edd3-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="8edd3-114">構文</span><span class="sxs-lookup"><span data-stu-id="8edd3-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8edd3-115">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8edd3-115">Attributes and Elements</span></span>  
 <span data-ttu-id="8edd3-116">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8edd3-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8edd3-117">属性</span><span class="sxs-lookup"><span data-stu-id="8edd3-117">Attributes</span></span>  
  
|<span data-ttu-id="8edd3-118">属性</span><span class="sxs-lookup"><span data-stu-id="8edd3-118">Attribute</span></span>|<span data-ttu-id="8edd3-119">説明</span><span class="sxs-lookup"><span data-stu-id="8edd3-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8edd3-120">claimType</span><span class="sxs-lookup"><span data-stu-id="8edd3-120">claimType</span></span>|<span data-ttu-id="8edd3-121">クレームの種類を定義する URI。</span><span class="sxs-lookup"><span data-stu-id="8edd3-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="8edd3-122">たとえば、Web サイトから製品を購入するために、ユーザーは、十分な与信限度額を備えた有効なクレジット カードを示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8edd3-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="8edd3-123">クレームの種類として、クレジット カードの URI があります。</span><span class="sxs-lookup"><span data-stu-id="8edd3-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="8edd3-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="8edd3-124">isOptional</span></span>|<span data-ttu-id="8edd3-125">これが省略可能なクレームかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="8edd3-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="8edd3-126">これが必須のクレームの場合は、この属性を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="8edd3-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="8edd3-127">サービスが必須でない情報を求めるときにこの属性を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8edd3-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="8edd3-128">たとえば、ユーザーに姓、姓、住所を入力する必要があるが、電話番号は省略可能と判断する場合などです。</span><span class="sxs-lookup"><span data-stu-id="8edd3-128">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8edd3-129">子要素</span><span class="sxs-lookup"><span data-stu-id="8edd3-129">Child Elements</span></span>  
 <span data-ttu-id="8edd3-130">[なし] :</span><span class="sxs-lookup"><span data-stu-id="8edd3-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8edd3-131">親要素</span><span class="sxs-lookup"><span data-stu-id="8edd3-131">Parent Elements</span></span>  
  
|<span data-ttu-id="8edd3-132">要素</span><span class="sxs-lookup"><span data-stu-id="8edd3-132">Element</span></span>|<span data-ttu-id="8edd3-133">説明</span><span class="sxs-lookup"><span data-stu-id="8edd3-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8edd3-134">\<要求型要件></span><span class="sxs-lookup"><span data-stu-id="8edd3-134">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="8edd3-135">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="8edd3-135">Specifies a collection of required claim types.</span></span> <span data-ttu-id="8edd3-136">各要素は <xref:System.ServiceModel.Configuration.ClaimTypeElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="8edd3-136">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="8edd3-137">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="8edd3-137">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="8edd3-138">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8edd3-138">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="8edd3-139">このコレクションの要素はそれぞれ、フェデレーション資格情報に表示されると予想される必須の要求および省略可能な要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="8edd3-139">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8edd3-140">解説</span><span class="sxs-lookup"><span data-stu-id="8edd3-140">Remarks</span></span>  
 <span data-ttu-id="8edd3-141">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="8edd3-141">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="8edd3-142">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8edd3-142">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="8edd3-143">この要件はセキュリティ ポリシー内に明記されます。</span><span class="sxs-lookup"><span data-stu-id="8edd3-143">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="8edd3-144">クライアントがフェデレーション サービスの資格情報 (CardSpace など) を要求する場合、クライアントは要件をトークン要求 (RequestSecurityToken) に設定します。これにより、フェデレーション サービスは、要件どおりの資格情報を発行できます。</span><span class="sxs-lookup"><span data-stu-id="8edd3-144">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8edd3-145">例</span><span class="sxs-lookup"><span data-stu-id="8edd3-145">Example</span></span>  
 <span data-ttu-id="8edd3-146">次の構成では、2 つのクレームの種類の要件をセキュリティ バインディングに追加しています。</span><span class="sxs-lookup"><span data-stu-id="8edd3-146">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8edd3-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="8edd3-147">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
