---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4ffc19366d91e4a14ee0f931d7009ede390cc097
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165027"
---
# \<nameClaimType>

<span data-ttu-id="7c125-101">プロパティを指定するクレームの種類を設定し <xref:System.Security.Principal.IIdentity.Name%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="7c125-101">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="7c125-102">要求の種類は、 <xref:System.Security.Claims.Claim> <xref:System.Security.Claims.ClaimsIdentity> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> このトークンハンドラーのメソッドによって返されたオブジェクトのコレクション内のを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7c125-102">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="7c125-103">次に、一致する要求の値が、 <xref:System.Security.Principal.IIdentity> このトークンハンドラーから生成されたの名前として設定されます。</span><span class="sxs-lookup"><span data-stu-id="7c125-103">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="7c125-104">構文</span><span class="sxs-lookup"><span data-stu-id="7c125-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c125-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7c125-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7c125-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7c125-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c125-107">属性</span><span class="sxs-lookup"><span data-stu-id="7c125-107">Attributes</span></span>  
  
|<span data-ttu-id="7c125-108">属性</span><span class="sxs-lookup"><span data-stu-id="7c125-108">Attribute</span></span>|<span data-ttu-id="7c125-109">説明</span><span class="sxs-lookup"><span data-stu-id="7c125-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7c125-110">value</span><span class="sxs-lookup"><span data-stu-id="7c125-110">value</span></span>|<span data-ttu-id="7c125-111">プロパティに使用するクレームのクレームの種類を表す URI を指定する文字列 <xref:System.Security.Principal.IIdentity.Name%2A> 。</span><span class="sxs-lookup"><span data-stu-id="7c125-111">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="7c125-112">必須。</span><span class="sxs-lookup"><span data-stu-id="7c125-112">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c125-113">子要素</span><span class="sxs-lookup"><span data-stu-id="7c125-113">Child Elements</span></span>  

 <span data-ttu-id="7c125-114">None</span><span class="sxs-lookup"><span data-stu-id="7c125-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7c125-115">親要素</span><span class="sxs-lookup"><span data-stu-id="7c125-115">Parent Elements</span></span>  
  
|<span data-ttu-id="7c125-116">要素</span><span class="sxs-lookup"><span data-stu-id="7c125-116">Element</span></span>|<span data-ttu-id="7c125-117">説明</span><span class="sxs-lookup"><span data-stu-id="7c125-117">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="7c125-118">クラス、クラス、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> またはこれらのクラスの派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="7c125-118">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c125-119">解説</span><span class="sxs-lookup"><span data-stu-id="7c125-119">Remarks</span></span>  

 <span data-ttu-id="7c125-120">要素は、 `<nameClaimType>` <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> オブジェクトが構成から初期化されるときにプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7c125-120">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c125-121">例</span><span class="sxs-lookup"><span data-stu-id="7c125-121">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c125-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c125-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
