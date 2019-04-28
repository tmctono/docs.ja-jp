---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 5202e162a7eb5fc4e36d6a6c0a2c18af48872a69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791600"
---
# <a name="nameclaimtype"></a><span data-ttu-id="5093c-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="5093c-101">\<nameClaimType></span></span>
<span data-ttu-id="5093c-102">設定を指定するクレームの種類、<xref:System.Security.Principal.IIdentity.Name%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5093c-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="5093c-103">要求の種類が検索に使用される、<xref:System.Security.Claims.Claim>のコレクションで<xref:System.Security.Claims.ClaimsIdentity>によって返されるオブジェクト、<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>このトークン ハンドラーのメソッド。</span><span class="sxs-lookup"><span data-stu-id="5093c-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="5093c-104">名前と一致するクレームの値が設定し、<xref:System.Security.Principal.IIdentity>このトークン ハンドラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="5093c-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="5093c-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="5093c-105">\<system.identityModel></span></span>  
<span data-ttu-id="5093c-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5093c-106">\<identityConfiguration></span></span>  
<span data-ttu-id="5093c-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="5093c-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="5093c-108">\<add></span><span class="sxs-lookup"><span data-stu-id="5093c-108">\<add></span></span>  
<span data-ttu-id="5093c-109">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="5093c-109">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="5093c-110">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="5093c-110">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5093c-111">構文</span><span class="sxs-lookup"><span data-stu-id="5093c-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5093c-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5093c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5093c-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5093c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5093c-114">属性</span><span class="sxs-lookup"><span data-stu-id="5093c-114">Attributes</span></span>  
  
|<span data-ttu-id="5093c-115">属性</span><span class="sxs-lookup"><span data-stu-id="5093c-115">Attribute</span></span>|<span data-ttu-id="5093c-116">説明</span><span class="sxs-lookup"><span data-stu-id="5093c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5093c-117">値</span><span class="sxs-lookup"><span data-stu-id="5093c-117">value</span></span>|<span data-ttu-id="5093c-118">使用する要求の要求の種類を表す URI を指定する文字列、<xref:System.Security.Principal.IIdentity.Name%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5093c-118">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="5093c-119">必須。</span><span class="sxs-lookup"><span data-stu-id="5093c-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5093c-120">子要素</span><span class="sxs-lookup"><span data-stu-id="5093c-120">Child Elements</span></span>  
 <span data-ttu-id="5093c-121">なし</span><span class="sxs-lookup"><span data-stu-id="5093c-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5093c-122">親要素</span><span class="sxs-lookup"><span data-stu-id="5093c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5093c-123">要素</span><span class="sxs-lookup"><span data-stu-id="5093c-123">Element</span></span>|<span data-ttu-id="5093c-124">説明</span><span class="sxs-lookup"><span data-stu-id="5093c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5093c-125">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="5093c-125">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="5093c-126">構成を提供、<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>クラス、<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラス、またはこれらのクラスのいずれかの派生クラス。</span><span class="sxs-lookup"><span data-stu-id="5093c-126">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5093c-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="5093c-127">Remarks</span></span>  
 <span data-ttu-id="5093c-128">`<nameClaimType>`要素セット、<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>プロパティと、<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>構成からオブジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="5093c-128">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5093c-129">例</span><span class="sxs-lookup"><span data-stu-id="5093c-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5093c-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="5093c-130">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
