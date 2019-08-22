---
title: <requestCaching> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: 2a3d0b182acad2351ed095934ca97c6194d344fc
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659131"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="a9274-102">\<requestCaching> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="a9274-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="a9274-103">ネットワーク要求のキャッシュメカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="a9274-103">Controls the caching mechanism for network requests.</span></span>  
  
 <span data-ttu-id="a9274-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a9274-104">\<configuration></span></span>  
<span data-ttu-id="a9274-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a9274-105">\<system.net></span></span>  
<span data-ttu-id="a9274-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="a9274-106">\<requestCaching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9274-107">構文</span><span class="sxs-lookup"><span data-stu-id="a9274-107">Syntax</span></span>  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9274-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a9274-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a9274-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9274-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9274-110">属性</span><span class="sxs-lookup"><span data-stu-id="a9274-110">Attributes</span></span>  
  
|<span data-ttu-id="a9274-111">属性</span><span class="sxs-lookup"><span data-stu-id="a9274-111">Attribute</span></span>|<span data-ttu-id="a9274-112">説明</span><span class="sxs-lookup"><span data-stu-id="a9274-112">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="a9274-113">キャッシュがさまざまなユーザーの情報の分離を提供するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9274-113">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="a9274-114">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="a9274-114">The default value is `true`.</span></span> <span data-ttu-id="a9274-115">中間層アプリケーションの`false`場合は、この値をにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9274-115">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="a9274-116">すべての Web 応答に対してキャッシュを無効にし、プログラムでオーバーライドすることはできないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9274-116">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="a9274-117"><xref:System.Net.Cache.RequestCacheLevel> 列挙値の値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="a9274-117">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="a9274-118">既定値は `BypassCache` です。</span><span class="sxs-lookup"><span data-stu-id="a9274-118">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="a9274-119">コンテンツが期限切れとしてマークされるまでの既定の時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9274-119">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="a9274-120">policyLevel 属性</span><span class="sxs-lookup"><span data-stu-id="a9274-120">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="a9274-121">値</span><span class="sxs-lookup"><span data-stu-id="a9274-121">Value</span></span>|<span data-ttu-id="a9274-122">説明</span><span class="sxs-lookup"><span data-stu-id="a9274-122">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="a9274-123">リソースが最新で、コンテンツの長さが正確で、有効期限、変更、およびコンテンツの長さの属性が存在する場合、キャッシュされたリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="a9274-123">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="a9274-124">サーバーからリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="a9274-124">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="a9274-125">コンテンツの長さが存在し、エントリのサイズと一致する場合、キャッシュされたリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="a9274-125">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="a9274-126">コンテンツの長さが指定され、エントリのサイズと一致する場合に、キャッシュされたリソースを返します。それ以外の場合は、リソースがサーバーからダウンロードされ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="a9274-126">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="a9274-127">キャッシュされたリソースのタイムスタンプがサーバー上のリソースのタイムスタンプと同じ場合は、キャッシュされたリソースを返します。それ以外の場合は、リソースがサーバーからダウンロードされ、キャッシュに格納されて、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="a9274-127">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="a9274-128">サーバーからリソースをダウンロードし、キャッシュに格納して、リソースを呼び出し元に返します。</span><span class="sxs-lookup"><span data-stu-id="a9274-128">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="a9274-129">キャッシュされたリソースが存在する場合は、削除されます。</span><span class="sxs-lookup"><span data-stu-id="a9274-129">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="a9274-130">リソースはサーバーからダウンロードされ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="a9274-130">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="a9274-131">タイムスタンプがサーバー上のリソースのタイムスタンプと同じ場合は、リソースのキャッシュされたコピーを使用して要求を満たします。それ以外の場合、リソースはサーバーからダウンロードされ、呼び出し元に渡され、キャッシュに格納されます。</span><span class="sxs-lookup"><span data-stu-id="a9274-131">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9274-132">子要素</span><span class="sxs-lookup"><span data-stu-id="a9274-132">Child Elements</span></span>  
  
|<span data-ttu-id="a9274-133">要素</span><span class="sxs-lookup"><span data-stu-id="a9274-133">Element</span></span>|<span data-ttu-id="a9274-134">説明</span><span class="sxs-lookup"><span data-stu-id="a9274-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9274-135">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="a9274-135">defaultHttpCachePolicy</span></span>](defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="a9274-136">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a9274-136">Optional element.</span></span><br /><br /> <span data-ttu-id="a9274-137">HTTP キャッシュがアクティブかどうか、および既定のキャッシュポリシーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a9274-137">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="a9274-138">\<defaultFtpCachePolicy> 要素 (ネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="a9274-138">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="a9274-139">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a9274-139">Optional element.</span></span><br /><br /> <span data-ttu-id="a9274-140">FTP キャッシュがアクティブでかどうかし、既定のキャッシュ ポリシーを記述について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9274-140">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a9274-141">親要素</span><span class="sxs-lookup"><span data-stu-id="a9274-141">Parent Elements</span></span>  
  
|<span data-ttu-id="a9274-142">要素</span><span class="sxs-lookup"><span data-stu-id="a9274-142">Element</span></span>|<span data-ttu-id="a9274-143">説明</span><span class="sxs-lookup"><span data-stu-id="a9274-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9274-144">system.net</span><span class="sxs-lookup"><span data-stu-id="a9274-144">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="a9274-145">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9274-145">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a9274-146">例</span><span class="sxs-lookup"><span data-stu-id="a9274-146">Example</span></span>  
 <span data-ttu-id="a9274-147">次の例では、すべてのキャッシュを無効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a9274-147">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9274-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9274-148">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="a9274-149">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a9274-149">Network Settings Schema</span></span>](index.md)
