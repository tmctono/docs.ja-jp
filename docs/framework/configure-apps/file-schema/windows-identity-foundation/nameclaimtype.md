---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4bf8ad2f70499edfc72dd9fcd9a5d8a0aafbbc66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251938"
---
# <a name="nameclaimtype"></a><span data-ttu-id="06626-101">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="06626-101">\<nameClaimType></span></span>
<span data-ttu-id="06626-102"><xref:System.Security.Principal.IIdentity.Name%2A>プロパティを指定するクレームの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="06626-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="06626-103">要求の種類は、このトークンハンドラーの<xref:System.Security.Claims.Claim> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>メソッドによって<xref:System.Security.Claims.ClaimsIdentity>返されたオブジェクトのコレクション内のを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="06626-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="06626-104">次に、一致する要求の値が、このトークンハンドラーから<xref:System.Security.Principal.IIdentity>生成されたの名前として設定されます。</span><span class="sxs-lookup"><span data-stu-id="06626-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
<span data-ttu-id="06626-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="06626-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="06626-106">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="06626-106">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="06626-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="06626-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="06626-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="06626-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="06626-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> の追加**](add.md)</span><span class="sxs-lookup"><span data-stu-id="06626-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="06626-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<samlSecurityTokenRequirement >** ](samlsecuritytokenrequirement.md)</span><span class="sxs-lookup"><span data-stu-id="06626-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)</span></span>\
<span data-ttu-id="06626-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<nameClaimType >**</span><span class="sxs-lookup"><span data-stu-id="06626-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06626-112">構文</span><span class="sxs-lookup"><span data-stu-id="06626-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06626-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="06626-113">Attributes and Elements</span></span>  
 <span data-ttu-id="06626-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="06626-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06626-115">属性</span><span class="sxs-lookup"><span data-stu-id="06626-115">Attributes</span></span>  
  
|<span data-ttu-id="06626-116">属性</span><span class="sxs-lookup"><span data-stu-id="06626-116">Attribute</span></span>|<span data-ttu-id="06626-117">説明</span><span class="sxs-lookup"><span data-stu-id="06626-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06626-118">value</span><span class="sxs-lookup"><span data-stu-id="06626-118">value</span></span>|<span data-ttu-id="06626-119"><xref:System.Security.Principal.IIdentity.Name%2A>プロパティに使用するクレームのクレームの種類を表す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="06626-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="06626-120">必須。</span><span class="sxs-lookup"><span data-stu-id="06626-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06626-121">子要素</span><span class="sxs-lookup"><span data-stu-id="06626-121">Child Elements</span></span>  
 <span data-ttu-id="06626-122">なし</span><span class="sxs-lookup"><span data-stu-id="06626-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06626-123">親要素</span><span class="sxs-lookup"><span data-stu-id="06626-123">Parent Elements</span></span>  
  
|<span data-ttu-id="06626-124">要素</span><span class="sxs-lookup"><span data-stu-id="06626-124">Element</span></span>|<span data-ttu-id="06626-125">説明</span><span class="sxs-lookup"><span data-stu-id="06626-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06626-126">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="06626-126">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="06626-127">クラス、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラス、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>またはこれらのクラスの派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="06626-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06626-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="06626-128">Remarks</span></span>  
 <span data-ttu-id="06626-129">要素は、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>オブジェクト<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>が構成から初期化されるときにプロパティを設定します。 `<nameClaimType>`</span><span class="sxs-lookup"><span data-stu-id="06626-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06626-130">例</span><span class="sxs-lookup"><span data-stu-id="06626-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="06626-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="06626-131">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
