---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: b1d04280ef993297102d446ba5a7db54e8404dd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750788"
---
# <a name="caches"></a><span data-ttu-id="b16ab-101">\<caches></span><span class="sxs-lookup"><span data-stu-id="b16ab-101">\<caches></span></span>
<span data-ttu-id="b16ab-102">セッション トークンやトークン リプレイ検出のために使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="b16ab-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="b16ab-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b16ab-103">\<system.identityModel></span></span>  
<span data-ttu-id="b16ab-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b16ab-104">\<identityConfiguration></span></span>  
<span data-ttu-id="b16ab-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="b16ab-105">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b16ab-106">構文</span><span class="sxs-lookup"><span data-stu-id="b16ab-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b16ab-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b16ab-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b16ab-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b16ab-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b16ab-109">属性</span><span class="sxs-lookup"><span data-stu-id="b16ab-109">Attributes</span></span>  
 <span data-ttu-id="b16ab-110">なし</span><span class="sxs-lookup"><span data-stu-id="b16ab-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b16ab-111">子要素</span><span class="sxs-lookup"><span data-stu-id="b16ab-111">Child Elements</span></span>  
  
|<span data-ttu-id="b16ab-112">要素</span><span class="sxs-lookup"><span data-stu-id="b16ab-112">Element</span></span>|<span data-ttu-id="b16ab-113">説明</span><span class="sxs-lookup"><span data-stu-id="b16ab-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b16ab-114">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="b16ab-114">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="b16ab-115">サービスまたはセキュリティ トークン ハンドラー コレクションのセッション トークン キャッシュに登録します。</span><span class="sxs-lookup"><span data-stu-id="b16ab-115">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="b16ab-116">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="b16ab-116">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="b16ab-117">トークン再生キャッシュ サービスまたはセキュリティ トークン ハンドラー コレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="b16ab-117">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b16ab-118">親要素</span><span class="sxs-lookup"><span data-stu-id="b16ab-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b16ab-119">要素</span><span class="sxs-lookup"><span data-stu-id="b16ab-119">Element</span></span>|<span data-ttu-id="b16ab-120">説明</span><span class="sxs-lookup"><span data-stu-id="b16ab-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b16ab-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b16ab-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="b16ab-122">サービス レベルの id の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b16ab-122">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="b16ab-123">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b16ab-123">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="b16ab-124">トークン ハンドラー コレクションのセキュリティの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="b16ab-124">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b16ab-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="b16ab-125">Remarks</span></span>  
 <span data-ttu-id="b16ab-126">A`<caches>`下で、サービス レベルで要素を指定することができます、`<identityConfiguration>`要素またはセキュリティ トークン ハンドラー コレクション レベルの下で、`<securityTokenHandlerConfiguration>`要素。</span><span class="sxs-lookup"><span data-stu-id="b16ab-126">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="b16ab-127">トークン ハンドラー コレクションの設定は、サービスに指定されているものをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="b16ab-127">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="b16ab-128">`<caches>`要素が表される、<xref:System.IdentityModel.Configuration.IdentityModelCachesElement>クラス。</span><span class="sxs-lookup"><span data-stu-id="b16ab-128">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="b16ab-129">構成済みのキャッシュがによって表される、<xref:System.IdentityModel.Configuration.IdentityModelCaches>クラス。</span><span class="sxs-lookup"><span data-stu-id="b16ab-129">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b16ab-130">例</span><span class="sxs-lookup"><span data-stu-id="b16ab-130">Example</span></span>  
 <span data-ttu-id="b16ab-131">次の XML はセッション セキュリティ トークンを保持するためのカスタム キャッシュの構成 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>)。</span><span class="sxs-lookup"><span data-stu-id="b16ab-131">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="b16ab-132">構成から取得されますが、`ClaimsAwareWebFarm`サンプル。</span><span class="sxs-lookup"><span data-stu-id="b16ab-132">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
