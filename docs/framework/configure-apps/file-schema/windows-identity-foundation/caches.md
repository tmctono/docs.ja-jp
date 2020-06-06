---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 80f435b52fd7657c5cd44538028d6080beffe0b5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252156"
---
# \<caches>
<span data-ttu-id="1382e-101">セッショントークンとトークンリプレイ検出に使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="1382e-101">Registers the caches used for session tokens and token replay detection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**  
  
## <a name="syntax"></a><span data-ttu-id="1382e-102">構文</span><span class="sxs-lookup"><span data-stu-id="1382e-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1382e-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1382e-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1382e-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1382e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1382e-105">属性</span><span class="sxs-lookup"><span data-stu-id="1382e-105">Attributes</span></span>  
 <span data-ttu-id="1382e-106">なし</span><span class="sxs-lookup"><span data-stu-id="1382e-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1382e-107">子要素</span><span class="sxs-lookup"><span data-stu-id="1382e-107">Child Elements</span></span>  
  
|<span data-ttu-id="1382e-108">要素</span><span class="sxs-lookup"><span data-stu-id="1382e-108">Element</span></span>|<span data-ttu-id="1382e-109">説明</span><span class="sxs-lookup"><span data-stu-id="1382e-109">Description</span></span>|  
|-------------|-----------------|  
|[\<sessionSecurityTokenCache>](sessionsecuritytokencache.md)|<span data-ttu-id="1382e-110">セッショントークンのキャッシュをサービスまたはセキュリティトークンハンドラーコレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="1382e-110">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[\<tokenReplayCache>](tokenreplaycache.md)|<span data-ttu-id="1382e-111">トークン再生キャッシュをサービスまたはセキュリティトークンハンドラーコレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="1382e-111">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1382e-112">親要素</span><span class="sxs-lookup"><span data-stu-id="1382e-112">Parent Elements</span></span>  
  
|<span data-ttu-id="1382e-113">要素</span><span class="sxs-lookup"><span data-stu-id="1382e-113">Element</span></span>|<span data-ttu-id="1382e-114">説明</span><span class="sxs-lookup"><span data-stu-id="1382e-114">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="1382e-115">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="1382e-115">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="1382e-116">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="1382e-116">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1382e-117">解説</span><span class="sxs-lookup"><span data-stu-id="1382e-117">Remarks</span></span>  
 <span data-ttu-id="1382e-118">要素は `<caches>` 、要素の下のサービスレベルで指定することも、 `<identityConfiguration>` 要素の下のセキュリティトークンハンドラーコレクションレベルで指定することもでき `<securityTokenHandlerConfiguration>` ます。</span><span class="sxs-lookup"><span data-stu-id="1382e-118">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="1382e-119">トークンハンドラーコレクションの設定は、サービスで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="1382e-119">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="1382e-120">`<caches>`要素は、クラスによって表され <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> ます。</span><span class="sxs-lookup"><span data-stu-id="1382e-120">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="1382e-121">構成されたキャッシュは、クラスによって表され <xref:System.IdentityModel.Configuration.IdentityModelCaches> ます。</span><span class="sxs-lookup"><span data-stu-id="1382e-121">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1382e-122">例</span><span class="sxs-lookup"><span data-stu-id="1382e-122">Example</span></span>  
 <span data-ttu-id="1382e-123">次の XML は、セッションセキュリティトークン () を保持するためのカスタムキャッシュの構成を示して <xref:System.IdentityModel.Tokens.SessionSecurityToken> います。</span><span class="sxs-lookup"><span data-stu-id="1382e-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="1382e-124">この構成は、サンプルから取得され `ClaimsAwareWebFarm` ます。</span><span class="sxs-lookup"><span data-stu-id="1382e-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
