---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0f651377346b1f14a4226128cd5cf7059543adca
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251911"
---
# \<roleClaimType>
<span data-ttu-id="9a55c-101"><xref:System.Security.Claims.ClaimsIdentity>トークンハンドラーのメソッドによって返されるオブジェクトのコレクション内でのロールの種類の要求を定義する要求の種類を指定し <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="9a55c-101">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="9a55c-102">構文</span><span class="sxs-lookup"><span data-stu-id="9a55c-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a55c-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9a55c-103">Attributes and Elements</span></span>  
 <span data-ttu-id="9a55c-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a55c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a55c-105">属性</span><span class="sxs-lookup"><span data-stu-id="9a55c-105">Attributes</span></span>  
  
|<span data-ttu-id="9a55c-106">属性</span><span class="sxs-lookup"><span data-stu-id="9a55c-106">Attribute</span></span>|<span data-ttu-id="9a55c-107">説明</span><span class="sxs-lookup"><span data-stu-id="9a55c-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a55c-108">value</span><span class="sxs-lookup"><span data-stu-id="9a55c-108">value</span></span>|<span data-ttu-id="9a55c-109">ロール要求の種類に使用するクレームのクレームの種類を表す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="9a55c-109">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a55c-110">子要素</span><span class="sxs-lookup"><span data-stu-id="9a55c-110">Child Elements</span></span>  
 <span data-ttu-id="9a55c-111">なし</span><span class="sxs-lookup"><span data-stu-id="9a55c-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a55c-112">親要素</span><span class="sxs-lookup"><span data-stu-id="9a55c-112">Parent Elements</span></span>  
  
|<span data-ttu-id="9a55c-113">要素</span><span class="sxs-lookup"><span data-stu-id="9a55c-113">Element</span></span>|<span data-ttu-id="9a55c-114">Description</span><span class="sxs-lookup"><span data-stu-id="9a55c-114">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="9a55c-115">クラス、クラス、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> またはこれらのクラスの派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="9a55c-115">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a55c-116">解説</span><span class="sxs-lookup"><span data-stu-id="9a55c-116">Remarks</span></span>  
 <span data-ttu-id="9a55c-117">要素は、 `<roleClaimType>` <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> オブジェクトが構成から初期化されるときにプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="9a55c-117">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a55c-118">例</span><span class="sxs-lookup"><span data-stu-id="9a55c-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a55c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a55c-119">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
