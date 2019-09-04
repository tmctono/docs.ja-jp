---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: e949b16f76f20191b84bbbbb6e8b019d913316f0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251829"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="c6613-101">\<Sessionsecuritytokencache> ></span><span class="sxs-lookup"><span data-stu-id="c6613-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="c6613-102">セッショントークンのキャッシュをサービスまたはセキュリティトークンハンドラーコレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="c6613-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="c6613-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c6613-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c6613-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="c6613-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="c6613-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c6613-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="c6613-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<キャッシュ >** ](caches.md)</span><span class="sxs-lookup"><span data-stu-id="c6613-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="c6613-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sessionsecuritytokencache> >**</span><span class="sxs-lookup"><span data-stu-id="c6613-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6613-108">構文</span><span class="sxs-lookup"><span data-stu-id="c6613-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6613-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c6613-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c6613-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6613-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6613-111">属性</span><span class="sxs-lookup"><span data-stu-id="c6613-111">Attributes</span></span>  
  
|<span data-ttu-id="c6613-112">属性</span><span class="sxs-lookup"><span data-stu-id="c6613-112">Attribute</span></span>|<span data-ttu-id="c6613-113">説明</span><span class="sxs-lookup"><span data-stu-id="c6613-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6613-114">型</span><span class="sxs-lookup"><span data-stu-id="c6613-114">type</span></span>|<span data-ttu-id="c6613-115"><xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>クラスから派生する型。</span><span class="sxs-lookup"><span data-stu-id="c6613-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6613-116">子要素</span><span class="sxs-lookup"><span data-stu-id="c6613-116">Child Elements</span></span>  
 <span data-ttu-id="c6613-117">なし</span><span class="sxs-lookup"><span data-stu-id="c6613-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6613-118">親要素</span><span class="sxs-lookup"><span data-stu-id="c6613-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c6613-119">要素</span><span class="sxs-lookup"><span data-stu-id="c6613-119">Element</span></span>|<span data-ttu-id="c6613-120">説明</span><span class="sxs-lookup"><span data-stu-id="c6613-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6613-121">\<キャッシュ ></span><span class="sxs-lookup"><span data-stu-id="c6613-121">\<caches></span></span>](caches.md)|<span data-ttu-id="c6613-122">サービスまたはセキュリティトークンハンドラーコレクションによって使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="c6613-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c6613-123">例</span><span class="sxs-lookup"><span data-stu-id="c6613-123">Example</span></span>  
 <span data-ttu-id="c6613-124">次の XML は、セッションセキュリティトークン (<xref:System.IdentityModel.Tokens.SessionSecurityToken>) を保持するためのカスタムキャッシュの構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="c6613-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="c6613-125">この構成は、 `ClaimsAwareWebFarm`サンプルから取得されます。</span><span class="sxs-lookup"><span data-stu-id="c6613-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="c6613-126">このサンプルの詳細については、「 [WIF Code Sample Index](../../../security/wif-code-sample-index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6613-126">For more information about this sample, see [WIF Code Sample Index](../../../security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6613-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6613-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
