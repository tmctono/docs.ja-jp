---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: a0db10ceb75a470dbf799d717b2059355dd104bb
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646067"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="e0d91-101">\<></span><span class="sxs-lookup"><span data-stu-id="e0d91-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="e0d91-102">サービスまたはセキュリティ トークン ハンドラーコレクションを使用して、セッション トークンのキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="e0d91-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="e0d91-103">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e0d91-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e0d91-104">&nbsp;&nbsp;[**\<>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="e0d91-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="e0d91-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<id構成>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="e0d91-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="e0d91-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<キャッシュ>**](caches.md)</span><span class="sxs-lookup"><span data-stu-id="e0d91-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="e0d91-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>**</span><span class="sxs-lookup"><span data-stu-id="e0d91-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0d91-108">構文</span><span class="sxs-lookup"><span data-stu-id="e0d91-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0d91-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e0d91-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e0d91-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0d91-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0d91-111">属性</span><span class="sxs-lookup"><span data-stu-id="e0d91-111">Attributes</span></span>  
  
|<span data-ttu-id="e0d91-112">属性</span><span class="sxs-lookup"><span data-stu-id="e0d91-112">Attribute</span></span>|<span data-ttu-id="e0d91-113">説明</span><span class="sxs-lookup"><span data-stu-id="e0d91-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0d91-114">type</span><span class="sxs-lookup"><span data-stu-id="e0d91-114">type</span></span>|<span data-ttu-id="e0d91-115">クラスから派生する<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>型。</span><span class="sxs-lookup"><span data-stu-id="e0d91-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0d91-116">子要素</span><span class="sxs-lookup"><span data-stu-id="e0d91-116">Child Elements</span></span>  
 <span data-ttu-id="e0d91-117">なし</span><span class="sxs-lookup"><span data-stu-id="e0d91-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0d91-118">親要素</span><span class="sxs-lookup"><span data-stu-id="e0d91-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e0d91-119">要素</span><span class="sxs-lookup"><span data-stu-id="e0d91-119">Element</span></span>|<span data-ttu-id="e0d91-120">説明</span><span class="sxs-lookup"><span data-stu-id="e0d91-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0d91-121">\<キャッシュ></span><span class="sxs-lookup"><span data-stu-id="e0d91-121">\<caches></span></span>](caches.md)|<span data-ttu-id="e0d91-122">サービスまたはセキュリティ トークン ハンドラーのコレクションで使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="e0d91-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e0d91-123">例</span><span class="sxs-lookup"><span data-stu-id="e0d91-123">Example</span></span>  
 <span data-ttu-id="e0d91-124">次の XML は、セッション セキュリティ トークン ( )<xref:System.IdentityModel.Tokens.SessionSecurityToken>を保持するためのカスタム キャッシュの構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="e0d91-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="e0d91-125">構成はサンプルから取得されます`ClaimsAwareWebFarm`。</span><span class="sxs-lookup"><span data-stu-id="e0d91-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="e0d91-126">このサンプルの詳細については、「 [WIF コード サンプル インデックス](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0d91-126">For more information about this sample, see [WIF Code Sample Index](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0d91-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0d91-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
