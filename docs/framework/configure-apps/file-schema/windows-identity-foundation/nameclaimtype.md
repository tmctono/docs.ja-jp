---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 47366c5bb2bd9228268fce3ae6e1fb5ad457dab1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942621"
---
# <a name="nameclaimtype"></a><span data-ttu-id="87339-101">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="87339-101">\<nameClaimType></span></span>
<span data-ttu-id="87339-102"><xref:System.Security.Principal.IIdentity.Name%2A>プロパティを指定するクレームの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="87339-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="87339-103">要求の種類は、このトークンハンドラーの<xref:System.Security.Claims.Claim> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>メソッドによって<xref:System.Security.Claims.ClaimsIdentity>返されたオブジェクトのコレクション内のを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="87339-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="87339-104">次に、一致する要求の値が、このトークンハンドラーから<xref:System.Security.Principal.IIdentity>生成されたの名前として設定されます。</span><span class="sxs-lookup"><span data-stu-id="87339-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="87339-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="87339-105">\<system.identityModel></span></span>  
<span data-ttu-id="87339-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="87339-106">\<identityConfiguration></span></span>  
<span data-ttu-id="87339-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="87339-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="87339-108">\<add></span><span class="sxs-lookup"><span data-stu-id="87339-108">\<add></span></span>  
<span data-ttu-id="87339-109">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="87339-109">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="87339-110">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="87339-110">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87339-111">構文</span><span class="sxs-lookup"><span data-stu-id="87339-111">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87339-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="87339-112">Attributes and Elements</span></span>  
 <span data-ttu-id="87339-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="87339-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87339-114">属性</span><span class="sxs-lookup"><span data-stu-id="87339-114">Attributes</span></span>  
  
|<span data-ttu-id="87339-115">属性</span><span class="sxs-lookup"><span data-stu-id="87339-115">Attribute</span></span>|<span data-ttu-id="87339-116">説明</span><span class="sxs-lookup"><span data-stu-id="87339-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87339-117">value</span><span class="sxs-lookup"><span data-stu-id="87339-117">value</span></span>|<span data-ttu-id="87339-118"><xref:System.Security.Principal.IIdentity.Name%2A>プロパティに使用するクレームのクレームの種類を表す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="87339-118">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="87339-119">必須。</span><span class="sxs-lookup"><span data-stu-id="87339-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87339-120">子要素</span><span class="sxs-lookup"><span data-stu-id="87339-120">Child Elements</span></span>  
 <span data-ttu-id="87339-121">なし</span><span class="sxs-lookup"><span data-stu-id="87339-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87339-122">親要素</span><span class="sxs-lookup"><span data-stu-id="87339-122">Parent Elements</span></span>  
  
|<span data-ttu-id="87339-123">要素</span><span class="sxs-lookup"><span data-stu-id="87339-123">Element</span></span>|<span data-ttu-id="87339-124">説明</span><span class="sxs-lookup"><span data-stu-id="87339-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87339-125">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="87339-125">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="87339-126">クラス、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラス、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>またはこれらのクラスの派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="87339-126">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87339-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="87339-127">Remarks</span></span>  
 <span data-ttu-id="87339-128">要素は、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>オブジェクト<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>が構成から初期化されるときにプロパティを設定します。 `<nameClaimType>`</span><span class="sxs-lookup"><span data-stu-id="87339-128">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87339-129">例</span><span class="sxs-lookup"><span data-stu-id="87339-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="87339-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="87339-130">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
