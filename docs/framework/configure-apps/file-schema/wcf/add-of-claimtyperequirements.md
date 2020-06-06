---
title: <add> の <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 6ba935f7f6dae0e4d9e6581f53a50c684efcbed3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153088"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="0d1fc-102">\<add> の \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="0d1fc-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="0d1fc-103">フェデレーション資格情報に表示されると予想される必須のクレームおよび省略可能なクレームの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="0d1fc-104">たとえば、サービスは、クレームの種類の特定のセットを処理する必要がある受信資格情報について要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="0d1fc-105">構文</span><span class="sxs-lookup"><span data-stu-id="0d1fc-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d1fc-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0d1fc-106">Attributes and Elements</span></span>  
 <span data-ttu-id="0d1fc-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d1fc-108">属性</span><span class="sxs-lookup"><span data-stu-id="0d1fc-108">Attributes</span></span>  
  
|<span data-ttu-id="0d1fc-109">属性</span><span class="sxs-lookup"><span data-stu-id="0d1fc-109">Attribute</span></span>|<span data-ttu-id="0d1fc-110">説明</span><span class="sxs-lookup"><span data-stu-id="0d1fc-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d1fc-111">claimType</span><span class="sxs-lookup"><span data-stu-id="0d1fc-111">claimType</span></span>|<span data-ttu-id="0d1fc-112">クレームの種類を定義する URI。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-112">A URI that defines the type of a claim.</span></span> <span data-ttu-id="0d1fc-113">たとえば、Web サイトから製品を購入するために、ユーザーは、十分な与信限度額を備えた有効なクレジット カードを示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-113">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="0d1fc-114">クレームの種類として、クレジット カードの URI があります。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-114">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="0d1fc-115">isOptional</span><span class="sxs-lookup"><span data-stu-id="0d1fc-115">isOptional</span></span>|<span data-ttu-id="0d1fc-116">これが省略可能なクレームかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-116">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="0d1fc-117">これが必須のクレームの場合は、この属性を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-117">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="0d1fc-118">サービスが必須でない情報を求めるときにこの属性を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-118">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="0d1fc-119">たとえば、ユーザーが名、姓、住所を入力する必要があるのに、電話番号は任意であると判断したとします。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-119">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d1fc-120">子要素</span><span class="sxs-lookup"><span data-stu-id="0d1fc-120">Child Elements</span></span>  
 <span data-ttu-id="0d1fc-121">なし。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0d1fc-122">親要素</span><span class="sxs-lookup"><span data-stu-id="0d1fc-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0d1fc-123">要素</span><span class="sxs-lookup"><span data-stu-id="0d1fc-123">Element</span></span>|<span data-ttu-id="0d1fc-124">Description</span><span class="sxs-lookup"><span data-stu-id="0d1fc-124">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="0d1fc-125">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-125">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="0d1fc-126">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-126">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="0d1fc-127">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-127">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="0d1fc-128">このコレクションの要素はそれぞれ、フェデレーション資格情報に表示されると予想される必須の要求および省略可能な要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-128">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d1fc-129">解説</span><span class="sxs-lookup"><span data-stu-id="0d1fc-129">Remarks</span></span>  
 <span data-ttu-id="0d1fc-130">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-130">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="0d1fc-131">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-131">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="0d1fc-132">この要件はセキュリティ ポリシー内に明記されます。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-132">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="0d1fc-133">クライアントがフェデレーション サービスの資格情報 (CardSpace など) を要求する場合、クライアントは要件をトークン要求 (RequestSecurityToken) に設定します。これにより、フェデレーション サービスは、要件どおりの資格情報を発行できます。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-133">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d1fc-134">例</span><span class="sxs-lookup"><span data-stu-id="0d1fc-134">Example</span></span>  
 <span data-ttu-id="0d1fc-135">次の構成では、2 つのクレームの種類の要件をセキュリティ バインディングに追加しています。</span><span class="sxs-lookup"><span data-stu-id="0d1fc-135">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0d1fc-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d1fc-136">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<claimTypeRequirements>](claimtyperequirements-element.md)
- [<span data-ttu-id="0d1fc-137">バインド</span><span class="sxs-lookup"><span data-stu-id="0d1fc-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0d1fc-138">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="0d1fc-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0d1fc-139">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="0d1fc-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="0d1fc-140">方法: SecurityBindingElement を使用してカスタム バインドを作成する</span><span class="sxs-lookup"><span data-stu-id="0d1fc-140">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="0d1fc-141">カスタム バインディング セキュリティ</span><span class="sxs-lookup"><span data-stu-id="0d1fc-141">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
