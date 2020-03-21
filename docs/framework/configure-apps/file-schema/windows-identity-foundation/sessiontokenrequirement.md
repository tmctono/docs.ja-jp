---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: ade55a5b26826633faf2e7ef7598a4071d613bbc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152542"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="ae683-101">\<>の要件</span><span class="sxs-lookup"><span data-stu-id="ae683-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="ae683-102">クラスまたは派生クラス<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>の構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="ae683-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="ae683-103">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ae683-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ae683-104">&nbsp;&nbsp;[**\<>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="ae683-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="ae683-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<id構成>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="ae683-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="ae683-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="ae683-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="ae683-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>を追加する**](add.md)</span><span class="sxs-lookup"><span data-stu-id="ae683-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="ae683-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>要件**</span><span class="sxs-lookup"><span data-stu-id="ae683-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae683-109">構文</span><span class="sxs-lookup"><span data-stu-id="ae683-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae683-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ae683-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ae683-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae683-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae683-112">属性</span><span class="sxs-lookup"><span data-stu-id="ae683-112">Attributes</span></span>  
  
|<span data-ttu-id="ae683-113">属性</span><span class="sxs-lookup"><span data-stu-id="ae683-113">Attribute</span></span>|<span data-ttu-id="ae683-114">説明</span><span class="sxs-lookup"><span data-stu-id="ae683-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae683-115">有効期間</span><span class="sxs-lookup"><span data-stu-id="ae683-115">lifetime</span></span>|<span data-ttu-id="ae683-116">セッション トークンの有効期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae683-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae683-117">子要素</span><span class="sxs-lookup"><span data-stu-id="ae683-117">Child Elements</span></span>  
 <span data-ttu-id="ae683-118">なし</span><span class="sxs-lookup"><span data-stu-id="ae683-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae683-119">親要素</span><span class="sxs-lookup"><span data-stu-id="ae683-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ae683-120">要素</span><span class="sxs-lookup"><span data-stu-id="ae683-120">Element</span></span>|<span data-ttu-id="ae683-121">説明</span><span class="sxs-lookup"><span data-stu-id="ae683-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae683-122">\<>を追加する</span><span class="sxs-lookup"><span data-stu-id="ae683-122">\<add></span></span>](add.md)|<span data-ttu-id="ae683-123">指定したセキュリティ トークン ハンドラーをトークン ハンドラー コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="ae683-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ae683-124">例</span><span class="sxs-lookup"><span data-stu-id="ae683-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
