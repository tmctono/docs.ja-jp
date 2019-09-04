---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 80f435b52fd7657c5cd44538028d6080beffe0b5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252156"
---
# <a name="caches"></a><span data-ttu-id="d33c1-101">\<キャッシュ ></span><span class="sxs-lookup"><span data-stu-id="d33c1-101">\<caches></span></span>
<span data-ttu-id="d33c1-102">セッショントークンとトークンリプレイ検出に使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="d33c1-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
<span data-ttu-id="d33c1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d33c1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d33c1-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="d33c1-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="d33c1-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d33c1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="d33c1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<キャッシュ >**</span><span class="sxs-lookup"><span data-stu-id="d33c1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d33c1-107">構文</span><span class="sxs-lookup"><span data-stu-id="d33c1-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d33c1-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d33c1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d33c1-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d33c1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d33c1-110">属性</span><span class="sxs-lookup"><span data-stu-id="d33c1-110">Attributes</span></span>  
 <span data-ttu-id="d33c1-111">なし</span><span class="sxs-lookup"><span data-stu-id="d33c1-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d33c1-112">子要素</span><span class="sxs-lookup"><span data-stu-id="d33c1-112">Child Elements</span></span>  
  
|<span data-ttu-id="d33c1-113">要素</span><span class="sxs-lookup"><span data-stu-id="d33c1-113">Element</span></span>|<span data-ttu-id="d33c1-114">説明</span><span class="sxs-lookup"><span data-stu-id="d33c1-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d33c1-115">\<Sessionsecuritytokencache> ></span><span class="sxs-lookup"><span data-stu-id="d33c1-115">\<sessionSecurityTokenCache></span></span>](sessionsecuritytokencache.md)|<span data-ttu-id="d33c1-116">セッショントークンのキャッシュをサービスまたはセキュリティトークンハンドラーコレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="d33c1-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="d33c1-117">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="d33c1-117">\<tokenReplayCache></span></span>](tokenreplaycache.md)|<span data-ttu-id="d33c1-118">トークン再生キャッシュをサービスまたはセキュリティトークンハンドラーコレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="d33c1-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d33c1-119">親要素</span><span class="sxs-lookup"><span data-stu-id="d33c1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d33c1-120">要素</span><span class="sxs-lookup"><span data-stu-id="d33c1-120">Element</span></span>|<span data-ttu-id="d33c1-121">説明</span><span class="sxs-lookup"><span data-stu-id="d33c1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d33c1-122">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d33c1-122">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="d33c1-123">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="d33c1-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="d33c1-124">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d33c1-124">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="d33c1-125">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="d33c1-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d33c1-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="d33c1-126">Remarks</span></span>  
 <span data-ttu-id="d33c1-127">要素は、要素の`<identityConfiguration>`下のサービスレベルで指定することも、 `<securityTokenHandlerConfiguration>`要素の下のセキュリティトークンハンドラーコレクションレベルで指定することもできます。 `<caches>`</span><span class="sxs-lookup"><span data-stu-id="d33c1-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="d33c1-128">トークンハンドラーコレクションの設定は、サービスで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="d33c1-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="d33c1-129">要素は、 <xref:System.IdentityModel.Configuration.IdentityModelCachesElement>クラスによって表されます。 `<caches>`</span><span class="sxs-lookup"><span data-stu-id="d33c1-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="d33c1-130">構成されたキャッシュは、 <xref:System.IdentityModel.Configuration.IdentityModelCaches>クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="d33c1-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d33c1-131">例</span><span class="sxs-lookup"><span data-stu-id="d33c1-131">Example</span></span>  
 <span data-ttu-id="d33c1-132">次の XML は、セッションセキュリティトークン (<xref:System.IdentityModel.Tokens.SessionSecurityToken>) を保持するためのカスタムキャッシュの構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="d33c1-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="d33c1-133">この構成は、 `ClaimsAwareWebFarm`サンプルから取得されます。</span><span class="sxs-lookup"><span data-stu-id="d33c1-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
