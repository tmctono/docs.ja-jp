---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 8c7b7c9b42ac72b878aed4e12298dc3655f1e707
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115597"
---
# <a name="roleclaimtype"></a><span data-ttu-id="c8e92-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="c8e92-101">\<roleClaimType></span></span>
<span data-ttu-id="c8e92-102">コレクション内のロールの種類の要求を定義する要求の種類を指定します<xref:System.Security.Claims.ClaimsIdentity>によって返されるオブジェクト、<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>トークン ハンドラーのメソッド。</span><span class="sxs-lookup"><span data-stu-id="c8e92-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="c8e92-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c8e92-103">\<system.identityModel></span></span>  
<span data-ttu-id="c8e92-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c8e92-104">\<identityConfiguration></span></span>  
<span data-ttu-id="c8e92-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="c8e92-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="c8e92-106">\<add></span><span class="sxs-lookup"><span data-stu-id="c8e92-106">\<add></span></span>  
<span data-ttu-id="c8e92-107">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="c8e92-107">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="c8e92-108">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="c8e92-108">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8e92-109">構文</span><span class="sxs-lookup"><span data-stu-id="c8e92-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8e92-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c8e92-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c8e92-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8e92-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8e92-112">属性</span><span class="sxs-lookup"><span data-stu-id="c8e92-112">Attributes</span></span>  
  
|<span data-ttu-id="c8e92-113">属性</span><span class="sxs-lookup"><span data-stu-id="c8e92-113">Attribute</span></span>|<span data-ttu-id="c8e92-114">説明</span><span class="sxs-lookup"><span data-stu-id="c8e92-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8e92-115">値</span><span class="sxs-lookup"><span data-stu-id="c8e92-115">value</span></span>|<span data-ttu-id="c8e92-116">ロール要求の種類を使用する要求の要求の種類を表す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="c8e92-116">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8e92-117">子要素</span><span class="sxs-lookup"><span data-stu-id="c8e92-117">Child Elements</span></span>  
 <span data-ttu-id="c8e92-118">なし</span><span class="sxs-lookup"><span data-stu-id="c8e92-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8e92-119">親要素</span><span class="sxs-lookup"><span data-stu-id="c8e92-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c8e92-120">要素</span><span class="sxs-lookup"><span data-stu-id="c8e92-120">Element</span></span>|<span data-ttu-id="c8e92-121">説明</span><span class="sxs-lookup"><span data-stu-id="c8e92-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8e92-122">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="c8e92-122">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="c8e92-123">構成を提供、<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>クラス、<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラス、またはこれらのクラスのいずれかの派生クラス。</span><span class="sxs-lookup"><span data-stu-id="c8e92-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8e92-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8e92-124">Remarks</span></span>  
 <span data-ttu-id="c8e92-125">`<roleClaimType>`要素セット、<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>プロパティと、<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>構成からオブジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="c8e92-125">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8e92-126">例</span><span class="sxs-lookup"><span data-stu-id="c8e92-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8e92-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8e92-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
