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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088428"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="e80bb-102">\<defaultFtpCachePolicy> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="e80bb-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="e80bb-103">FTP キャッシュがアクティブかどうか、および既定のキャッシュポリシーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e80bb-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="e80bb-104">構文</span><span class="sxs-lookup"><span data-stu-id="e80bb-104">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e80bb-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e80bb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e80bb-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e80bb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e80bb-107">属性</span><span class="sxs-lookup"><span data-stu-id="e80bb-107">Attributes</span></span>  
  
|<span data-ttu-id="e80bb-108">属性</span><span class="sxs-lookup"><span data-stu-id="e80bb-108">Attribute</span></span>|<span data-ttu-id="e80bb-109">説明</span><span class="sxs-lookup"><span data-stu-id="e80bb-109">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="e80bb-110">FTP キャッシュポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e80bb-110">Specifies the FTP caching policy.</span></span> <span data-ttu-id="e80bb-111">既定値は `Default` です。</span><span class="sxs-lookup"><span data-stu-id="e80bb-111">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="e80bb-112">policyLevel 属性</span><span class="sxs-lookup"><span data-stu-id="e80bb-112">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="e80bb-113">値</span><span class="sxs-lookup"><span data-stu-id="e80bb-113">Value</span></span>|<span data-ttu-id="e80bb-114">Description</span><span class="sxs-lookup"><span data-stu-id="e80bb-114">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="e80bb-115">リソースが最新で、コンテンツの長さが正確で、有効期限、変更、およびコンテンツの長さの属性が存在する場合、キャッシュされたリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="e80bb-115">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="e80bb-116">サーバーからリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="e80bb-116">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="e80bb-117">コンテンツの長さが存在し、エントリのサイズと一致する場合、キャッシュされたリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="e80bb-117">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="e80bb-118">コンテンツの長さが指定され、エントリのサイズと一致する場合に、キャッシュされたリソースを返します。それ以外の場合は、リソースがサーバーからダウンロードされ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="e80bb-118">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="e80bb-119">キャッシュされたリソースのタイムスタンプがサーバー上のリソースのタイムスタンプと同じ場合は、キャッシュされたリソースを返します。それ以外の場合は、リソースがサーバーからダウンロードされ、キャッシュに格納されて、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="e80bb-119">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="e80bb-120">サーバーからリソースをダウンロードし、キャッシュに格納して、リソースを呼び出し元に返します。</span><span class="sxs-lookup"><span data-stu-id="e80bb-120">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="e80bb-121">キャッシュされたリソースが存在する場合は、削除されます。</span><span class="sxs-lookup"><span data-stu-id="e80bb-121">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="e80bb-122">リソースはサーバーからダウンロードされ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="e80bb-122">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="e80bb-123">タイムスタンプがサーバーのリソースのタイムスタンプと同じ場合は、キャッシュされたリソースのコピーを使用して要求に応じます。それ以外の場合は、リソースがサーバーからダウンロードされ、呼び出し元に提示され、キャッシュに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e80bb-123">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e80bb-124">子要素</span><span class="sxs-lookup"><span data-stu-id="e80bb-124">Child Elements</span></span>  
 <span data-ttu-id="e80bb-125">なし。</span><span class="sxs-lookup"><span data-stu-id="e80bb-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e80bb-126">親要素</span><span class="sxs-lookup"><span data-stu-id="e80bb-126">Parent Elements</span></span>  
  
|<span data-ttu-id="e80bb-127">要素</span><span class="sxs-lookup"><span data-stu-id="e80bb-127">Element</span></span>|<span data-ttu-id="e80bb-128">Description</span><span class="sxs-lookup"><span data-stu-id="e80bb-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e80bb-129">Requestcaching></span><span class="sxs-lookup"><span data-stu-id="e80bb-129">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="e80bb-130">ネットワーク要求のキャッシュメカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="e80bb-130">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e80bb-131">解説</span><span class="sxs-lookup"><span data-stu-id="e80bb-131">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="e80bb-132">例</span><span class="sxs-lookup"><span data-stu-id="e80bb-132">Example</span></span>  
 <span data-ttu-id="e80bb-133">次の例は、の FTP キャッシュポリシーを指定する方法を示して `NoCacheNoStore` います。</span><span class="sxs-lookup"><span data-stu-id="e80bb-133">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e80bb-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="e80bb-134">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="e80bb-135">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="e80bb-135">Network Settings Schema</span></span>](index.md)
