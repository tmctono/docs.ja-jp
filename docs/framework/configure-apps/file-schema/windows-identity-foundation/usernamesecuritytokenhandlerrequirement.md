---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: a49b41c04c8f184188b62e04c3b232bd33752fca
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185523"
---
# \<userNameSecurityTokenHandlerRequirement>

<span data-ttu-id="070e1-101"><xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>クラスまたは派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="070e1-101">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="070e1-102">構文</span><span class="sxs-lookup"><span data-stu-id="070e1-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="070e1-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="070e1-103">Attributes and Elements</span></span>  

 <span data-ttu-id="070e1-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="070e1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="070e1-105">属性</span><span class="sxs-lookup"><span data-stu-id="070e1-105">Attributes</span></span>  
  
|<span data-ttu-id="070e1-106">属性</span><span class="sxs-lookup"><span data-stu-id="070e1-106">Attribute</span></span>|<span data-ttu-id="070e1-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="070e1-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="070e1-108">メンバーシップ Providername</span><span class="sxs-lookup"><span data-stu-id="070e1-108">membershipProviderName</span></span>|<span data-ttu-id="070e1-109"><xref:System.Web.Security.MembershipProvider>セキュリティトークンハンドラーによって使用されるを指定します。</span><span class="sxs-lookup"><span data-stu-id="070e1-109">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="070e1-110">子要素</span><span class="sxs-lookup"><span data-stu-id="070e1-110">Child Elements</span></span>  

 <span data-ttu-id="070e1-111">None</span><span class="sxs-lookup"><span data-stu-id="070e1-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="070e1-112">親要素</span><span class="sxs-lookup"><span data-stu-id="070e1-112">Parent Elements</span></span>  
  
|<span data-ttu-id="070e1-113">要素</span><span class="sxs-lookup"><span data-stu-id="070e1-113">Element</span></span>|<span data-ttu-id="070e1-114">説明</span><span class="sxs-lookup"><span data-stu-id="070e1-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="070e1-115">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="070e1-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="070e1-116">解説</span><span class="sxs-lookup"><span data-stu-id="070e1-116">Remarks</span></span>  

 <span data-ttu-id="070e1-117">要素は、 `<userNameSecurityTokenHandlerRequirement>` <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> オブジェクトが構成から初期化されるときにプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="070e1-117">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="070e1-118">例</span><span class="sxs-lookup"><span data-stu-id="070e1-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
