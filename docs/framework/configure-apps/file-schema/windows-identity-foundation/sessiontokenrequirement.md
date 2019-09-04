---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 968c48df9e92a1dfbfb6e248b06cf4f97cece8b4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251826"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="2f615-101">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="2f615-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="2f615-102"><xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>クラスまたは派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="2f615-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="2f615-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2f615-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2f615-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="2f615-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="2f615-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="2f615-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="2f615-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="2f615-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="2f615-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> の追加**](add.md)</span><span class="sxs-lookup"><span data-stu-id="2f615-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="2f615-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<sessionTokenRequirement >**</span><span class="sxs-lookup"><span data-stu-id="2f615-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f615-109">構文</span><span class="sxs-lookup"><span data-stu-id="2f615-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f615-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2f615-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2f615-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f615-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f615-112">属性</span><span class="sxs-lookup"><span data-stu-id="2f615-112">Attributes</span></span>  
  
|<span data-ttu-id="2f615-113">属性</span><span class="sxs-lookup"><span data-stu-id="2f615-113">Attribute</span></span>|<span data-ttu-id="2f615-114">説明</span><span class="sxs-lookup"><span data-stu-id="2f615-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f615-115">有効期間</span><span class="sxs-lookup"><span data-stu-id="2f615-115">lifetime</span></span>|<span data-ttu-id="2f615-116">セッショントークンの有効期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f615-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f615-117">子要素</span><span class="sxs-lookup"><span data-stu-id="2f615-117">Child Elements</span></span>  
 <span data-ttu-id="2f615-118">なし</span><span class="sxs-lookup"><span data-stu-id="2f615-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f615-119">親要素</span><span class="sxs-lookup"><span data-stu-id="2f615-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2f615-120">要素</span><span class="sxs-lookup"><span data-stu-id="2f615-120">Element</span></span>|<span data-ttu-id="2f615-121">説明</span><span class="sxs-lookup"><span data-stu-id="2f615-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f615-122">\<add></span><span class="sxs-lookup"><span data-stu-id="2f615-122">\<add></span></span>](add.md)|<span data-ttu-id="2f615-123">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="2f615-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2f615-124">例</span><span class="sxs-lookup"><span data-stu-id="2f615-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
