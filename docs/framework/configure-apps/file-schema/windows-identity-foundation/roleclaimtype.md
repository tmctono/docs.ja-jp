---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0f651377346b1f14a4226128cd5cf7059543adca
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251911"
---
# <a name="roleclaimtype"></a><span data-ttu-id="00182-101">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="00182-101">\<roleClaimType></span></span>
<span data-ttu-id="00182-102">トークンハンドラーの<xref:System.Security.Claims.ClaimsIdentity> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>メソッドによって返されるオブジェクトのコレクション内でのロールの種類の要求を定義する要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="00182-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
<span data-ttu-id="00182-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="00182-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="00182-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="00182-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="00182-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="00182-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="00182-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="00182-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="00182-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> の追加**](add.md)</span><span class="sxs-lookup"><span data-stu-id="00182-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="00182-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<samlSecurityTokenRequirement >** ](samlsecuritytokenrequirement.md)</span><span class="sxs-lookup"><span data-stu-id="00182-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)</span></span>\
<span data-ttu-id="00182-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<roleClaimType >**</span><span class="sxs-lookup"><span data-stu-id="00182-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00182-110">構文</span><span class="sxs-lookup"><span data-stu-id="00182-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00182-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="00182-111">Attributes and Elements</span></span>  
 <span data-ttu-id="00182-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="00182-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00182-113">属性</span><span class="sxs-lookup"><span data-stu-id="00182-113">Attributes</span></span>  
  
|<span data-ttu-id="00182-114">属性</span><span class="sxs-lookup"><span data-stu-id="00182-114">Attribute</span></span>|<span data-ttu-id="00182-115">説明</span><span class="sxs-lookup"><span data-stu-id="00182-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00182-116">value</span><span class="sxs-lookup"><span data-stu-id="00182-116">value</span></span>|<span data-ttu-id="00182-117">ロール要求の種類に使用するクレームのクレームの種類を表す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="00182-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00182-118">子要素</span><span class="sxs-lookup"><span data-stu-id="00182-118">Child Elements</span></span>  
 <span data-ttu-id="00182-119">なし</span><span class="sxs-lookup"><span data-stu-id="00182-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00182-120">親要素</span><span class="sxs-lookup"><span data-stu-id="00182-120">Parent Elements</span></span>  
  
|<span data-ttu-id="00182-121">要素</span><span class="sxs-lookup"><span data-stu-id="00182-121">Element</span></span>|<span data-ttu-id="00182-122">説明</span><span class="sxs-lookup"><span data-stu-id="00182-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00182-123">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="00182-123">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="00182-124">クラス、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラス、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>またはこれらのクラスの派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="00182-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00182-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="00182-125">Remarks</span></span>  
 <span data-ttu-id="00182-126">要素は、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>オブジェクト<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>が構成から初期化されるときにプロパティを設定します。 `<roleClaimType>`</span><span class="sxs-lookup"><span data-stu-id="00182-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00182-127">例</span><span class="sxs-lookup"><span data-stu-id="00182-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="00182-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="00182-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
