---
title: <add><claimTypeRequirements>要素の
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: 920d2b3fa4b51ee56e30863d521214ff66e7fcf2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149245"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="01d8d-102">\<add>\<claimTypeRequirements>要素の</span><span class="sxs-lookup"><span data-stu-id="01d8d-102">\<add> of \<claimTypeRequirements> element</span></span>

<span data-ttu-id="01d8d-103">フェデレーション資格情報に表示されると予想される必須のクレームおよび省略可能なクレームの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="01d8d-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="01d8d-104">たとえば、サービスは、クレームの種類の特定のセットを処理する必要がある受信資格情報について要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="01d8d-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**
  
## <a name="syntax"></a><span data-ttu-id="01d8d-105">構文</span><span class="sxs-lookup"><span data-stu-id="01d8d-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01d8d-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="01d8d-106">Attributes and Elements</span></span>  

 <span data-ttu-id="01d8d-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="01d8d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01d8d-108">属性</span><span class="sxs-lookup"><span data-stu-id="01d8d-108">Attributes</span></span>  
  
|<span data-ttu-id="01d8d-109">属性</span><span class="sxs-lookup"><span data-stu-id="01d8d-109">Attribute</span></span>|<span data-ttu-id="01d8d-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="01d8d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01d8d-111">claimType</span><span class="sxs-lookup"><span data-stu-id="01d8d-111">claimType</span></span>|<span data-ttu-id="01d8d-112">クレームの種類を定義する URI。</span><span class="sxs-lookup"><span data-stu-id="01d8d-112">A URI that defines the type of a claim.</span></span> <span data-ttu-id="01d8d-113">たとえば、Web サイトから製品を購入するために、ユーザーは、十分な与信限度額を備えた有効なクレジット カードを示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d8d-113">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="01d8d-114">クレームの種類として、クレジット カードの URI があります。</span><span class="sxs-lookup"><span data-stu-id="01d8d-114">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="01d8d-115">isOptional</span><span class="sxs-lookup"><span data-stu-id="01d8d-115">isOptional</span></span>|<span data-ttu-id="01d8d-116">これが省略可能なクレームかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="01d8d-116">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="01d8d-117">これが必須のクレームの場合は、この属性を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="01d8d-117">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="01d8d-118">サービスが必須でない情報を求めるときにこの属性を使用できます。</span><span class="sxs-lookup"><span data-stu-id="01d8d-118">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="01d8d-119">たとえば、ユーザーが名、姓、住所を入力する必要があるのに、電話番号は任意であると判断したとします。</span><span class="sxs-lookup"><span data-stu-id="01d8d-119">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01d8d-120">子要素</span><span class="sxs-lookup"><span data-stu-id="01d8d-120">Child Elements</span></span>  

 <span data-ttu-id="01d8d-121">なし。</span><span class="sxs-lookup"><span data-stu-id="01d8d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01d8d-122">親要素</span><span class="sxs-lookup"><span data-stu-id="01d8d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="01d8d-123">要素</span><span class="sxs-lookup"><span data-stu-id="01d8d-123">Element</span></span>|<span data-ttu-id="01d8d-124">説明</span><span class="sxs-lookup"><span data-stu-id="01d8d-124">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="01d8d-125">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="01d8d-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="01d8d-126">各要素は <xref:System.ServiceModel.Configuration.ClaimTypeElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="01d8d-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="01d8d-127">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="01d8d-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="01d8d-128">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d8d-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="01d8d-129">このコレクションの要素はそれぞれ、フェデレーション資格情報に表示されると予想される必須の要求および省略可能な要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="01d8d-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01d8d-130">解説</span><span class="sxs-lookup"><span data-stu-id="01d8d-130">Remarks</span></span>  

 <span data-ttu-id="01d8d-131">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="01d8d-131">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="01d8d-132">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d8d-132">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="01d8d-133">この要件はセキュリティ ポリシー内に明記されます。</span><span class="sxs-lookup"><span data-stu-id="01d8d-133">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="01d8d-134">クライアントがフェデレーション サービスの資格情報 (CardSpace など) を要求する場合、クライアントは要件をトークン要求 (RequestSecurityToken) に設定します。これにより、フェデレーション サービスは、要件どおりの資格情報を発行できます。</span><span class="sxs-lookup"><span data-stu-id="01d8d-134">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01d8d-135">例</span><span class="sxs-lookup"><span data-stu-id="01d8d-135">Example</span></span>  

 <span data-ttu-id="01d8d-136">次の構成では、2 つのクレームの種類の要件をセキュリティ バインディングに追加しています。</span><span class="sxs-lookup"><span data-stu-id="01d8d-136">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="01d8d-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="01d8d-137">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
