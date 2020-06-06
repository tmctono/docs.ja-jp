---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: ade55a5b26826633faf2e7ef7598a4071d613bbc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152542"
---
# \<sessionTokenRequirement>
<span data-ttu-id="f94b8-101"><xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>クラスまたは派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="f94b8-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="f94b8-102">構文</span><span class="sxs-lookup"><span data-stu-id="f94b8-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f94b8-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f94b8-103">Attributes and Elements</span></span>  
 <span data-ttu-id="f94b8-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f94b8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f94b8-105">属性</span><span class="sxs-lookup"><span data-stu-id="f94b8-105">Attributes</span></span>  
  
|<span data-ttu-id="f94b8-106">属性</span><span class="sxs-lookup"><span data-stu-id="f94b8-106">Attribute</span></span>|<span data-ttu-id="f94b8-107">説明</span><span class="sxs-lookup"><span data-stu-id="f94b8-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f94b8-108">有効期間</span><span class="sxs-lookup"><span data-stu-id="f94b8-108">lifetime</span></span>|<span data-ttu-id="f94b8-109">セッショントークンの有効期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f94b8-109">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f94b8-110">子要素</span><span class="sxs-lookup"><span data-stu-id="f94b8-110">Child Elements</span></span>  
 <span data-ttu-id="f94b8-111">なし</span><span class="sxs-lookup"><span data-stu-id="f94b8-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f94b8-112">親要素</span><span class="sxs-lookup"><span data-stu-id="f94b8-112">Parent Elements</span></span>  
  
|<span data-ttu-id="f94b8-113">要素</span><span class="sxs-lookup"><span data-stu-id="f94b8-113">Element</span></span>|<span data-ttu-id="f94b8-114">Description</span><span class="sxs-lookup"><span data-stu-id="f94b8-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="f94b8-115">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f94b8-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f94b8-116">例</span><span class="sxs-lookup"><span data-stu-id="f94b8-116">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
