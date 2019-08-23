---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 9be3bf980c3756678d26d8652271113d4daaba43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943711"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="cee21-101">\<Sessionsecuritytokencache> ></span><span class="sxs-lookup"><span data-stu-id="cee21-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="cee21-102">セッショントークンのキャッシュをサービスまたはセキュリティトークンハンドラーコレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="cee21-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="cee21-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="cee21-103">\<system.identityModel></span></span>  
<span data-ttu-id="cee21-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="cee21-104">\<identityConfiguration></span></span>  
<span data-ttu-id="cee21-105">\<キャッシュ ></span><span class="sxs-lookup"><span data-stu-id="cee21-105">\<caches></span></span>  
<span data-ttu-id="cee21-106">\<Sessionsecuritytokencache> ></span><span class="sxs-lookup"><span data-stu-id="cee21-106">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cee21-107">構文</span><span class="sxs-lookup"><span data-stu-id="cee21-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cee21-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cee21-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cee21-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cee21-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cee21-110">属性</span><span class="sxs-lookup"><span data-stu-id="cee21-110">Attributes</span></span>  
  
|<span data-ttu-id="cee21-111">属性</span><span class="sxs-lookup"><span data-stu-id="cee21-111">Attribute</span></span>|<span data-ttu-id="cee21-112">説明</span><span class="sxs-lookup"><span data-stu-id="cee21-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cee21-113">型</span><span class="sxs-lookup"><span data-stu-id="cee21-113">type</span></span>|<span data-ttu-id="cee21-114"><xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>クラスから派生する型。</span><span class="sxs-lookup"><span data-stu-id="cee21-114">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cee21-115">子要素</span><span class="sxs-lookup"><span data-stu-id="cee21-115">Child Elements</span></span>  
 <span data-ttu-id="cee21-116">なし</span><span class="sxs-lookup"><span data-stu-id="cee21-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cee21-117">親要素</span><span class="sxs-lookup"><span data-stu-id="cee21-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cee21-118">要素</span><span class="sxs-lookup"><span data-stu-id="cee21-118">Element</span></span>|<span data-ttu-id="cee21-119">説明</span><span class="sxs-lookup"><span data-stu-id="cee21-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cee21-120">\<キャッシュ ></span><span class="sxs-lookup"><span data-stu-id="cee21-120">\<caches></span></span>](caches.md)|<span data-ttu-id="cee21-121">サービスまたはセキュリティトークンハンドラーコレクションによって使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="cee21-121">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cee21-122">例</span><span class="sxs-lookup"><span data-stu-id="cee21-122">Example</span></span>  
 <span data-ttu-id="cee21-123">次の XML は、セッションセキュリティトークン (<xref:System.IdentityModel.Tokens.SessionSecurityToken>) を保持するためのカスタムキャッシュの構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="cee21-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="cee21-124">この構成は、 `ClaimsAwareWebFarm`サンプルから取得されます。</span><span class="sxs-lookup"><span data-stu-id="cee21-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="cee21-125">このサンプルの詳細については、「 [WIF Code Sample Index](../../../security/wif-code-sample-index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cee21-125">For more information about this sample, see [WIF Code Sample Index](../../../security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cee21-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="cee21-126">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
