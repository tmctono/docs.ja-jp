---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 4169fe307e9ef7c391500a2292fcc247f435caa9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555888"
---
# \<sessionSecurityTokenCache>
<span data-ttu-id="3ccf8-101">セッショントークンのキャッシュをサービスまたはセキュリティトークンハンドラーコレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="3ccf8-101">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**  
  
## <a name="syntax"></a><span data-ttu-id="3ccf8-102">構文</span><span class="sxs-lookup"><span data-stu-id="3ccf8-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ccf8-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3ccf8-103">Attributes and Elements</span></span>  
 <span data-ttu-id="3ccf8-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ccf8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ccf8-105">属性</span><span class="sxs-lookup"><span data-stu-id="3ccf8-105">Attributes</span></span>  
  
|<span data-ttu-id="3ccf8-106">属性</span><span class="sxs-lookup"><span data-stu-id="3ccf8-106">Attribute</span></span>|<span data-ttu-id="3ccf8-107">説明</span><span class="sxs-lookup"><span data-stu-id="3ccf8-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ccf8-108">type</span><span class="sxs-lookup"><span data-stu-id="3ccf8-108">type</span></span>|<span data-ttu-id="3ccf8-109">クラスから派生する型 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 。</span><span class="sxs-lookup"><span data-stu-id="3ccf8-109">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ccf8-110">子要素</span><span class="sxs-lookup"><span data-stu-id="3ccf8-110">Child Elements</span></span>  
 <span data-ttu-id="3ccf8-111">なし</span><span class="sxs-lookup"><span data-stu-id="3ccf8-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ccf8-112">親要素</span><span class="sxs-lookup"><span data-stu-id="3ccf8-112">Parent Elements</span></span>  
  
|<span data-ttu-id="3ccf8-113">要素</span><span class="sxs-lookup"><span data-stu-id="3ccf8-113">Element</span></span>|<span data-ttu-id="3ccf8-114">説明</span><span class="sxs-lookup"><span data-stu-id="3ccf8-114">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="3ccf8-115">サービスまたはセキュリティトークンハンドラーコレクションによって使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="3ccf8-115">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3ccf8-116">例</span><span class="sxs-lookup"><span data-stu-id="3ccf8-116">Example</span></span>  
 <span data-ttu-id="3ccf8-117">次の XML は、セッションセキュリティトークン () を保持するためのカスタムキャッシュの構成を示して <xref:System.IdentityModel.Tokens.SessionSecurityToken> います。</span><span class="sxs-lookup"><span data-stu-id="3ccf8-117">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="3ccf8-118">この構成は、サンプルから取得され `ClaimsAwareWebFarm` ます。</span><span class="sxs-lookup"><span data-stu-id="3ccf8-118">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="3ccf8-119">このサンプルの詳細については、「 [WIF Code Sample Index](/previous-versions/dotnet/framework/security/wif-code-sample-index)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ccf8-119">For more information about this sample, see [WIF Code Sample Index](/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ccf8-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ccf8-120">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
