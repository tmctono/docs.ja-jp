---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: fed8964e03b80e365fdc5eafd45b4fc372a6e352
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944252"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="8b950-101">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="8b950-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="8b950-102"><xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>クラスまたは派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="8b950-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="8b950-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="8b950-103">\<system.identityModel></span></span>  
<span data-ttu-id="8b950-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="8b950-104">\<identityConfiguration></span></span>  
<span data-ttu-id="8b950-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="8b950-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="8b950-106">\<add></span><span class="sxs-lookup"><span data-stu-id="8b950-106">\<add></span></span>  
<span data-ttu-id="8b950-107">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="8b950-107">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b950-108">構文</span><span class="sxs-lookup"><span data-stu-id="8b950-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b950-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8b950-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8b950-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b950-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b950-111">属性</span><span class="sxs-lookup"><span data-stu-id="8b950-111">Attributes</span></span>  
  
|<span data-ttu-id="8b950-112">属性</span><span class="sxs-lookup"><span data-stu-id="8b950-112">Attribute</span></span>|<span data-ttu-id="8b950-113">説明</span><span class="sxs-lookup"><span data-stu-id="8b950-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8b950-114">メンバーシップ Providername</span><span class="sxs-lookup"><span data-stu-id="8b950-114">membershipProviderName</span></span>|<span data-ttu-id="8b950-115"><xref:System.Web.Security.MembershipProvider>セキュリティトークンハンドラーによって使用されるを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b950-115">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b950-116">子要素</span><span class="sxs-lookup"><span data-stu-id="8b950-116">Child Elements</span></span>  
 <span data-ttu-id="8b950-117">なし</span><span class="sxs-lookup"><span data-stu-id="8b950-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8b950-118">親要素</span><span class="sxs-lookup"><span data-stu-id="8b950-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8b950-119">要素</span><span class="sxs-lookup"><span data-stu-id="8b950-119">Element</span></span>|<span data-ttu-id="8b950-120">説明</span><span class="sxs-lookup"><span data-stu-id="8b950-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b950-121">\<add></span><span class="sxs-lookup"><span data-stu-id="8b950-121">\<add></span></span>](add.md)|<span data-ttu-id="8b950-122">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="8b950-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b950-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="8b950-123">Remarks</span></span>  
 <span data-ttu-id="8b950-124">要素は、 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>オブジェクト<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A>が構成から初期化されるときにプロパティを設定します。 `<userNameSecurityTokenHandlerRequirement>`</span><span class="sxs-lookup"><span data-stu-id="8b950-124">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b950-125">例</span><span class="sxs-lookup"><span data-stu-id="8b950-125">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
