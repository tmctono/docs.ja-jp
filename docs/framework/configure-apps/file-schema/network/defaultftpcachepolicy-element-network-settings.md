---
title: <defaultFtpCachePolicy> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: 9261a430642cb4d5ac4507835bd0fd3561bd8c02
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088428"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="7e7b9-102">\<defaultFtpCachePolicy > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="7e7b9-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="7e7b9-103">FTP キャッシュがアクティブかどうか、および既定のキャッシュポリシーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  

<span data-ttu-id="7e7b9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7e7b9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7e7b9-105">&nbsp;&nbsp;[ **\<system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7e7b9-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="7e7b9-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<requestcaching >** ](requestcaching-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7e7b9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)</span></span>\
<span data-ttu-id="7e7b9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**defaultFtpCachePolicy >**</span><span class="sxs-lookup"><span data-stu-id="7e7b9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7e7b9-108">構文</span><span class="sxs-lookup"><span data-stu-id="7e7b9-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e7b9-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7e7b9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7e7b9-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e7b9-111">属性</span><span class="sxs-lookup"><span data-stu-id="7e7b9-111">Attributes</span></span>  
  
|<span data-ttu-id="7e7b9-112">属性</span><span class="sxs-lookup"><span data-stu-id="7e7b9-112">Attribute</span></span>|<span data-ttu-id="7e7b9-113">説明</span><span class="sxs-lookup"><span data-stu-id="7e7b9-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="7e7b9-114">FTP キャッシュポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="7e7b9-115">既定値は `Default`です。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="7e7b9-116">policyLevel 属性</span><span class="sxs-lookup"><span data-stu-id="7e7b9-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="7e7b9-117">[値]</span><span class="sxs-lookup"><span data-stu-id="7e7b9-117">Value</span></span>|<span data-ttu-id="7e7b9-118">説明</span><span class="sxs-lookup"><span data-stu-id="7e7b9-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="7e7b9-119">リソースが最新で、コンテンツの長さが正確で、有効期限、変更、およびコンテンツの長さの属性が存在する場合、キャッシュされたリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="7e7b9-120">サーバーからリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="7e7b9-121">コンテンツの長さが存在し、エントリのサイズと一致する場合、キャッシュされたリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="7e7b9-122">コンテンツの長さが指定され、エントリのサイズと一致する場合に、キャッシュされたリソースを返します。それ以外の場合は、リソースがサーバーからダウンロードされ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="7e7b9-123">キャッシュされたリソースのタイムスタンプがサーバー上のリソースのタイムスタンプと同じ場合は、キャッシュされたリソースを返します。それ以外の場合は、リソースがサーバーからダウンロードされ、キャッシュに格納されて、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="7e7b9-124">サーバーからリソースをダウンロードし、キャッシュに格納して、リソースを呼び出し元に返します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="7e7b9-125">キャッシュされたリソースが存在する場合は、削除されます。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="7e7b9-126">リソースはサーバーからダウンロードされ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="7e7b9-127">タイムスタンプがサーバー上のリソースのタイムスタンプと同じ場合は、リソースのキャッシュされたコピーを使用して要求を満たします。それ以外の場合は、リソースがサーバーからダウンロードされ、呼び出し元に提示されて、キャッシュに格納されます。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e7b9-128">子要素</span><span class="sxs-lookup"><span data-stu-id="7e7b9-128">Child Elements</span></span>  
 <span data-ttu-id="7e7b9-129">なし。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e7b9-130">親要素</span><span class="sxs-lookup"><span data-stu-id="7e7b9-130">Parent Elements</span></span>  
  
|<span data-ttu-id="7e7b9-131">要素</span><span class="sxs-lookup"><span data-stu-id="7e7b9-131">Element</span></span>|<span data-ttu-id="7e7b9-132">説明</span><span class="sxs-lookup"><span data-stu-id="7e7b9-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e7b9-133">Requestcaching></span><span class="sxs-lookup"><span data-stu-id="7e7b9-133">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="7e7b9-134">ネットワーク要求のキャッシュメカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e7b9-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="7e7b9-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e7b9-136">例</span><span class="sxs-lookup"><span data-stu-id="7e7b9-136">Example</span></span>  
 <span data-ttu-id="7e7b9-137">次の例は、`NoCacheNoStore`の FTP キャッシュポリシーを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7e7b9-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e7b9-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e7b9-138">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="7e7b9-139">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="7e7b9-139">Network Settings Schema</span></span>](index.md)
