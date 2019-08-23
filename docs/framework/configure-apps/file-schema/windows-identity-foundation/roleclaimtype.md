---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0ce2e06ee895d09de193bac1fe7038e71794dda4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942541"
---
# <a name="roleclaimtype"></a><span data-ttu-id="0ac50-101">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="0ac50-101">\<roleClaimType></span></span>
<span data-ttu-id="0ac50-102">トークンハンドラーの<xref:System.Security.Claims.ClaimsIdentity> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>メソッドによって返されるオブジェクトのコレクション内でのロールの種類の要求を定義する要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ac50-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="0ac50-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="0ac50-103">\<system.identityModel></span></span>  
<span data-ttu-id="0ac50-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="0ac50-104">\<identityConfiguration></span></span>  
<span data-ttu-id="0ac50-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="0ac50-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="0ac50-106">\<add></span><span class="sxs-lookup"><span data-stu-id="0ac50-106">\<add></span></span>  
<span data-ttu-id="0ac50-107">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="0ac50-107">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="0ac50-108">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="0ac50-108">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ac50-109">構文</span><span class="sxs-lookup"><span data-stu-id="0ac50-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ac50-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0ac50-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0ac50-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ac50-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ac50-112">属性</span><span class="sxs-lookup"><span data-stu-id="0ac50-112">Attributes</span></span>  
  
|<span data-ttu-id="0ac50-113">属性</span><span class="sxs-lookup"><span data-stu-id="0ac50-113">Attribute</span></span>|<span data-ttu-id="0ac50-114">説明</span><span class="sxs-lookup"><span data-stu-id="0ac50-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0ac50-115">value</span><span class="sxs-lookup"><span data-stu-id="0ac50-115">value</span></span>|<span data-ttu-id="0ac50-116">ロール要求の種類に使用するクレームのクレームの種類を表す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="0ac50-116">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ac50-117">子要素</span><span class="sxs-lookup"><span data-stu-id="0ac50-117">Child Elements</span></span>  
 <span data-ttu-id="0ac50-118">なし</span><span class="sxs-lookup"><span data-stu-id="0ac50-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ac50-119">親要素</span><span class="sxs-lookup"><span data-stu-id="0ac50-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0ac50-120">要素</span><span class="sxs-lookup"><span data-stu-id="0ac50-120">Element</span></span>|<span data-ttu-id="0ac50-121">説明</span><span class="sxs-lookup"><span data-stu-id="0ac50-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ac50-122">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="0ac50-122">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="0ac50-123">クラス、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラス、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>またはこれらのクラスの派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="0ac50-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ac50-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="0ac50-124">Remarks</span></span>  
 <span data-ttu-id="0ac50-125">要素は、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>オブジェクト<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>が構成から初期化されるときにプロパティを設定します。 `<roleClaimType>`</span><span class="sxs-lookup"><span data-stu-id="0ac50-125">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ac50-126">例</span><span class="sxs-lookup"><span data-stu-id="0ac50-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ac50-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ac50-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
