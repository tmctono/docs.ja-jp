---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 254d34149892abeaf31b9227f7567eb0a66ec0b6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943677"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="0956b-101">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="0956b-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="0956b-102"><xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>クラスまたは派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="0956b-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="0956b-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="0956b-103">\<system.identityModel></span></span>  
<span data-ttu-id="0956b-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="0956b-104">\<identityConfiguration></span></span>  
<span data-ttu-id="0956b-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="0956b-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="0956b-106">\<add></span><span class="sxs-lookup"><span data-stu-id="0956b-106">\<add></span></span>  
<span data-ttu-id="0956b-107">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="0956b-107">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0956b-108">構文</span><span class="sxs-lookup"><span data-stu-id="0956b-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0956b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0956b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0956b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0956b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0956b-111">属性</span><span class="sxs-lookup"><span data-stu-id="0956b-111">Attributes</span></span>  
  
|<span data-ttu-id="0956b-112">属性</span><span class="sxs-lookup"><span data-stu-id="0956b-112">Attribute</span></span>|<span data-ttu-id="0956b-113">説明</span><span class="sxs-lookup"><span data-stu-id="0956b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0956b-114">有効期間</span><span class="sxs-lookup"><span data-stu-id="0956b-114">lifetime</span></span>|<span data-ttu-id="0956b-115">セッショントークンの有効期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="0956b-115">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0956b-116">子要素</span><span class="sxs-lookup"><span data-stu-id="0956b-116">Child Elements</span></span>  
 <span data-ttu-id="0956b-117">なし</span><span class="sxs-lookup"><span data-stu-id="0956b-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0956b-118">親要素</span><span class="sxs-lookup"><span data-stu-id="0956b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0956b-119">要素</span><span class="sxs-lookup"><span data-stu-id="0956b-119">Element</span></span>|<span data-ttu-id="0956b-120">説明</span><span class="sxs-lookup"><span data-stu-id="0956b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0956b-121">\<add></span><span class="sxs-lookup"><span data-stu-id="0956b-121">\<add></span></span>](add.md)|<span data-ttu-id="0956b-122">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="0956b-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0956b-123">例</span><span class="sxs-lookup"><span data-stu-id="0956b-123">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
