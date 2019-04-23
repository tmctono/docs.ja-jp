---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 5c68fe618f965f364a3716c3bc65de5e165b12ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207800"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="d4bf3-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="d4bf3-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="d4bf3-102">サービスまたはセキュリティ トークン ハンドラー コレクションのセッション トークン キャッシュに登録します。</span><span class="sxs-lookup"><span data-stu-id="d4bf3-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="d4bf3-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d4bf3-103">\<system.identityModel></span></span>  
<span data-ttu-id="d4bf3-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d4bf3-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d4bf3-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="d4bf3-105">\<caches></span></span>  
<span data-ttu-id="d4bf3-106">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="d4bf3-106">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4bf3-107">構文</span><span class="sxs-lookup"><span data-stu-id="d4bf3-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4bf3-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d4bf3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d4bf3-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4bf3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4bf3-110">属性</span><span class="sxs-lookup"><span data-stu-id="d4bf3-110">Attributes</span></span>  
  
|<span data-ttu-id="d4bf3-111">属性</span><span class="sxs-lookup"><span data-stu-id="d4bf3-111">Attribute</span></span>|<span data-ttu-id="d4bf3-112">説明</span><span class="sxs-lookup"><span data-stu-id="d4bf3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d4bf3-113">型</span><span class="sxs-lookup"><span data-stu-id="d4bf3-113">type</span></span>|<span data-ttu-id="d4bf3-114">派生した型、<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>クラス。</span><span class="sxs-lookup"><span data-stu-id="d4bf3-114">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4bf3-115">子要素</span><span class="sxs-lookup"><span data-stu-id="d4bf3-115">Child Elements</span></span>  
 <span data-ttu-id="d4bf3-116">なし</span><span class="sxs-lookup"><span data-stu-id="d4bf3-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4bf3-117">親要素</span><span class="sxs-lookup"><span data-stu-id="d4bf3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d4bf3-118">要素</span><span class="sxs-lookup"><span data-stu-id="d4bf3-118">Element</span></span>|<span data-ttu-id="d4bf3-119">説明</span><span class="sxs-lookup"><span data-stu-id="d4bf3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4bf3-120">\<caches></span><span class="sxs-lookup"><span data-stu-id="d4bf3-120">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="d4bf3-121">サービスまたはセキュリティ トークン ハンドラー コレクションで使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="d4bf3-121">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d4bf3-122">例</span><span class="sxs-lookup"><span data-stu-id="d4bf3-122">Example</span></span>  
 <span data-ttu-id="d4bf3-123">次の XML はセッション セキュリティ トークンを保持するためのカスタム キャッシュの構成 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>)。</span><span class="sxs-lookup"><span data-stu-id="d4bf3-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="d4bf3-124">構成から取得されますが、`ClaimsAwareWebFarm`サンプル。</span><span class="sxs-lookup"><span data-stu-id="d4bf3-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="d4bf3-125">このサンプルの詳細については、次を参照してください。 [WIF コード サンプル インデックス](../../../../../docs/framework/security/wif-code-sample-index.md)します。</span><span class="sxs-lookup"><span data-stu-id="d4bf3-125">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4bf3-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4bf3-126">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
