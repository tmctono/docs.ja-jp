---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 791c5be8aa48db2b17a42a216ad2bf5e7b5a4bc1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189878"
---
# \<caches>

<span data-ttu-id="17da7-101">セッショントークンとトークンリプレイ検出に使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="17da7-101">Registers the caches used for session tokens and token replay detection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**  
  
## <a name="syntax"></a><span data-ttu-id="17da7-102">構文</span><span class="sxs-lookup"><span data-stu-id="17da7-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17da7-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="17da7-103">Attributes and Elements</span></span>  

 <span data-ttu-id="17da7-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="17da7-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17da7-105">属性</span><span class="sxs-lookup"><span data-stu-id="17da7-105">Attributes</span></span>  

 <span data-ttu-id="17da7-106">None</span><span class="sxs-lookup"><span data-stu-id="17da7-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="17da7-107">子要素</span><span class="sxs-lookup"><span data-stu-id="17da7-107">Child Elements</span></span>  
  
|<span data-ttu-id="17da7-108">要素</span><span class="sxs-lookup"><span data-stu-id="17da7-108">Element</span></span>|<span data-ttu-id="17da7-109">説明</span><span class="sxs-lookup"><span data-stu-id="17da7-109">Description</span></span>|  
|-------------|-----------------|  
|[\<sessionSecurityTokenCache>](sessionsecuritytokencache.md)|<span data-ttu-id="17da7-110">セッショントークンのキャッシュをサービスまたはセキュリティトークンハンドラーコレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="17da7-110">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[\<tokenReplayCache>](tokenreplaycache.md)|<span data-ttu-id="17da7-111">トークン再生キャッシュをサービスまたはセキュリティトークンハンドラーコレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="17da7-111">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="17da7-112">親要素</span><span class="sxs-lookup"><span data-stu-id="17da7-112">Parent Elements</span></span>  
  
|<span data-ttu-id="17da7-113">要素</span><span class="sxs-lookup"><span data-stu-id="17da7-113">Element</span></span>|<span data-ttu-id="17da7-114">説明</span><span class="sxs-lookup"><span data-stu-id="17da7-114">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="17da7-115">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="17da7-115">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="17da7-116">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="17da7-116">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17da7-117">解説</span><span class="sxs-lookup"><span data-stu-id="17da7-117">Remarks</span></span>  

 <span data-ttu-id="17da7-118">要素は `<caches>` 、要素の下のサービスレベルで指定することも、 `<identityConfiguration>` 要素の下のセキュリティトークンハンドラーコレクションレベルで指定することもでき `<securityTokenHandlerConfiguration>` ます。</span><span class="sxs-lookup"><span data-stu-id="17da7-118">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="17da7-119">トークンハンドラーコレクションの設定は、サービスで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="17da7-119">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="17da7-120">`<caches>`要素は、クラスによって表され <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> ます。</span><span class="sxs-lookup"><span data-stu-id="17da7-120">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="17da7-121">構成されたキャッシュは、クラスによって表され <xref:System.IdentityModel.Configuration.IdentityModelCaches> ます。</span><span class="sxs-lookup"><span data-stu-id="17da7-121">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17da7-122">例</span><span class="sxs-lookup"><span data-stu-id="17da7-122">Example</span></span>  

 <span data-ttu-id="17da7-123">次の XML は、セッションセキュリティトークン () を保持するためのカスタムキャッシュの構成を示して <xref:System.IdentityModel.Tokens.SessionSecurityToken> います。</span><span class="sxs-lookup"><span data-stu-id="17da7-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="17da7-124">この構成は、サンプルから取得され `ClaimsAwareWebFarm` ます。</span><span class="sxs-lookup"><span data-stu-id="17da7-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
