---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 5863c01e97e7f5fb6fe07c43174c0d6cb7a0a25d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251748"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="b4f14-101">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="b4f14-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="b4f14-102"><xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>クラスまたは派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="b4f14-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="b4f14-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b4f14-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b4f14-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="b4f14-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="b4f14-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b4f14-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="b4f14-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="b4f14-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="b4f14-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> の追加**](add.md)</span><span class="sxs-lookup"><span data-stu-id="b4f14-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="b4f14-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<userNameSecurityTokenHandlerRequirement >**</span><span class="sxs-lookup"><span data-stu-id="b4f14-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f14-109">構文</span><span class="sxs-lookup"><span data-stu-id="b4f14-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4f14-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b4f14-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b4f14-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b4f14-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4f14-112">属性</span><span class="sxs-lookup"><span data-stu-id="b4f14-112">Attributes</span></span>  
  
|<span data-ttu-id="b4f14-113">属性</span><span class="sxs-lookup"><span data-stu-id="b4f14-113">Attribute</span></span>|<span data-ttu-id="b4f14-114">説明</span><span class="sxs-lookup"><span data-stu-id="b4f14-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b4f14-115">メンバーシップ Providername</span><span class="sxs-lookup"><span data-stu-id="b4f14-115">membershipProviderName</span></span>|<span data-ttu-id="b4f14-116"><xref:System.Web.Security.MembershipProvider>セキュリティトークンハンドラーによって使用されるを指定します。</span><span class="sxs-lookup"><span data-stu-id="b4f14-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4f14-117">子要素</span><span class="sxs-lookup"><span data-stu-id="b4f14-117">Child Elements</span></span>  
 <span data-ttu-id="b4f14-118">なし</span><span class="sxs-lookup"><span data-stu-id="b4f14-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4f14-119">親要素</span><span class="sxs-lookup"><span data-stu-id="b4f14-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b4f14-120">要素</span><span class="sxs-lookup"><span data-stu-id="b4f14-120">Element</span></span>|<span data-ttu-id="b4f14-121">説明</span><span class="sxs-lookup"><span data-stu-id="b4f14-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4f14-122">\<add></span><span class="sxs-lookup"><span data-stu-id="b4f14-122">\<add></span></span>](add.md)|<span data-ttu-id="b4f14-123">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="b4f14-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4f14-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="b4f14-124">Remarks</span></span>  
 <span data-ttu-id="b4f14-125">要素は、 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>オブジェクト<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A>が構成から初期化されるときにプロパティを設定します。 `<userNameSecurityTokenHandlerRequirement>`</span><span class="sxs-lookup"><span data-stu-id="b4f14-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4f14-126">例</span><span class="sxs-lookup"><span data-stu-id="b4f14-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
