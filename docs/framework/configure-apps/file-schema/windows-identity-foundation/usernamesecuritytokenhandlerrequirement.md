---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 18769794da8528f085c567264827db5aa6b214f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790456"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="78a04-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="78a04-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="78a04-102">構成を提供、<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>クラスまたは派生クラス。</span><span class="sxs-lookup"><span data-stu-id="78a04-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="78a04-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="78a04-103">\<system.identityModel></span></span>  
<span data-ttu-id="78a04-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="78a04-104">\<identityConfiguration></span></span>  
<span data-ttu-id="78a04-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="78a04-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="78a04-106">\<add></span><span class="sxs-lookup"><span data-stu-id="78a04-106">\<add></span></span>  
<span data-ttu-id="78a04-107">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="78a04-107">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a04-108">構文</span><span class="sxs-lookup"><span data-stu-id="78a04-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78a04-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="78a04-109">Attributes and Elements</span></span>  
 <span data-ttu-id="78a04-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="78a04-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78a04-111">属性</span><span class="sxs-lookup"><span data-stu-id="78a04-111">Attributes</span></span>  
  
|<span data-ttu-id="78a04-112">属性</span><span class="sxs-lookup"><span data-stu-id="78a04-112">Attribute</span></span>|<span data-ttu-id="78a04-113">説明</span><span class="sxs-lookup"><span data-stu-id="78a04-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78a04-114">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="78a04-114">membershipProviderName</span></span>|<span data-ttu-id="78a04-115">指定します、<xref:System.Web.Security.MembershipProvider>でセキュリティ トークン ハンドラーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78a04-115">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78a04-116">子要素</span><span class="sxs-lookup"><span data-stu-id="78a04-116">Child Elements</span></span>  
 <span data-ttu-id="78a04-117">なし</span><span class="sxs-lookup"><span data-stu-id="78a04-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78a04-118">親要素</span><span class="sxs-lookup"><span data-stu-id="78a04-118">Parent Elements</span></span>  
  
|<span data-ttu-id="78a04-119">要素</span><span class="sxs-lookup"><span data-stu-id="78a04-119">Element</span></span>|<span data-ttu-id="78a04-120">説明</span><span class="sxs-lookup"><span data-stu-id="78a04-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78a04-121">\<add></span><span class="sxs-lookup"><span data-stu-id="78a04-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="78a04-122">トークン ハンドラー コレクションには、指定したセキュリティ トークン ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="78a04-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78a04-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="78a04-123">Remarks</span></span>  
 <span data-ttu-id="78a04-124">`<userNameSecurityTokenHandlerRequirement>`要素セット、<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A>プロパティと、<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>構成からオブジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="78a04-124">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78a04-125">例</span><span class="sxs-lookup"><span data-stu-id="78a04-125">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
