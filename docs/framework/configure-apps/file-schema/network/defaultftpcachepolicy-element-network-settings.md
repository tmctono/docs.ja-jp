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
ms.openlocfilehash: fd1649edbf7a2c8546992019df667f27df68e02c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698316"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="3f00c-102">\<defaultFtpCachePolicy> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="3f00c-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="3f00c-103">FTP キャッシュがアクティブでかどうかし、既定のキャッシュ ポリシーを記述について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f00c-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
[<span data-ttu-id="3f00c-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="3f00c-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="3f00c-105">&nbsp; @ no__t-1[ **@no__t 47 >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3f00c-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="3f00c-106">&nbsp; @ no__t @ no__t-2 @ no__t-3[ **\<requestcaching >** ](requestcaching-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3f00c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)</span></span>  
<span data-ttu-id="3f00c-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 **\<defaultFtpCachePolicy >** を行います。</span><span class="sxs-lookup"><span data-stu-id="3f00c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f00c-108">構文</span><span class="sxs-lookup"><span data-stu-id="3f00c-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f00c-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3f00c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3f00c-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f00c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f00c-111">属性</span><span class="sxs-lookup"><span data-stu-id="3f00c-111">Attributes</span></span>  
  
|<span data-ttu-id="3f00c-112">属性</span><span class="sxs-lookup"><span data-stu-id="3f00c-112">Attribute</span></span>|<span data-ttu-id="3f00c-113">説明</span><span class="sxs-lookup"><span data-stu-id="3f00c-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="3f00c-114">FTP キャッシュポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f00c-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="3f00c-115">既定値は `Default` です。</span><span class="sxs-lookup"><span data-stu-id="3f00c-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="3f00c-116">policyLevel 属性</span><span class="sxs-lookup"><span data-stu-id="3f00c-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="3f00c-117">値</span><span class="sxs-lookup"><span data-stu-id="3f00c-117">Value</span></span>|<span data-ttu-id="3f00c-118">説明</span><span class="sxs-lookup"><span data-stu-id="3f00c-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="3f00c-119">リソースが最新で、コンテンツの長さが正確で、有効期限、変更、およびコンテンツの長さの属性が存在する場合、キャッシュされたリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="3f00c-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="3f00c-120">サーバーからリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="3f00c-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="3f00c-121">コンテンツの長さが存在し、エントリのサイズと一致する場合、キャッシュされたリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="3f00c-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="3f00c-122">コンテンツの長さが指定され、エントリのサイズと一致する場合に、キャッシュされたリソースを返します。それ以外の場合は、リソースがサーバーからダウンロードされ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="3f00c-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="3f00c-123">キャッシュされたリソースのタイムスタンプがサーバー上のリソースのタイムスタンプと同じ場合は、キャッシュされたリソースを返します。それ以外の場合は、リソースがサーバーからダウンロードされ、キャッシュに格納されて、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="3f00c-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="3f00c-124">サーバーからリソースをダウンロードし、キャッシュに格納して、リソースを呼び出し元に返します。</span><span class="sxs-lookup"><span data-stu-id="3f00c-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="3f00c-125">キャッシュされたリソースが存在する場合は、削除されます。</span><span class="sxs-lookup"><span data-stu-id="3f00c-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="3f00c-126">リソースはサーバーからダウンロードされ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="3f00c-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="3f00c-127">タイムスタンプがサーバー上のリソースのタイムスタンプと同じ場合は、リソースのキャッシュされたコピーを使用して要求を満たします。それ以外の場合は、リソースがサーバーからダウンロードされ、呼び出し元に提示されて、キャッシュに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3f00c-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f00c-128">子要素</span><span class="sxs-lookup"><span data-stu-id="3f00c-128">Child Elements</span></span>  
 <span data-ttu-id="3f00c-129">なし。</span><span class="sxs-lookup"><span data-stu-id="3f00c-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f00c-130">親要素</span><span class="sxs-lookup"><span data-stu-id="3f00c-130">Parent Elements</span></span>  
  
|<span data-ttu-id="3f00c-131">要素</span><span class="sxs-lookup"><span data-stu-id="3f00c-131">Element</span></span>|<span data-ttu-id="3f00c-132">説明</span><span class="sxs-lookup"><span data-stu-id="3f00c-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f00c-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="3f00c-133">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="3f00c-134">ネットワーク要求のキャッシュメカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="3f00c-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f00c-135">コメント</span><span class="sxs-lookup"><span data-stu-id="3f00c-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f00c-136">例</span><span class="sxs-lookup"><span data-stu-id="3f00c-136">Example</span></span>  
 <span data-ttu-id="3f00c-137">次の例では、`NoCacheNoStore` の FTP キャッシュポリシーを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3f00c-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3f00c-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f00c-138">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="3f00c-139">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="3f00c-139">Network Settings Schema</span></span>](index.md)
