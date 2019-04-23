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
ms.openlocfilehash: af290e4b9258a08425a15e297ff538502edea916
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164854"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="88983-102">\<requestCaching > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="88983-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="88983-103">ネットワーク要求のキャッシュ メカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="88983-103">Controls the caching mechanism for network requests.</span></span>  
  
 <span data-ttu-id="88983-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="88983-104">\<configuration></span></span>  
<span data-ttu-id="88983-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="88983-105">\<system.net></span></span>  
<span data-ttu-id="88983-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="88983-106">\<requestCaching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88983-107">構文</span><span class="sxs-lookup"><span data-stu-id="88983-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88983-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="88983-108">Attributes and Elements</span></span>  
 <span data-ttu-id="88983-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="88983-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88983-110">属性</span><span class="sxs-lookup"><span data-stu-id="88983-110">Attributes</span></span>  
  
|<span data-ttu-id="88983-111">属性</span><span class="sxs-lookup"><span data-stu-id="88983-111">Attribute</span></span>|<span data-ttu-id="88983-112">説明</span><span class="sxs-lookup"><span data-stu-id="88983-112">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="88983-113">キャッシュが別のユーザーの情報との間の分離を提供するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="88983-113">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="88983-114">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="88983-114">The default value is `true`.</span></span> <span data-ttu-id="88983-115">この値は`false`中間層アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="88983-115">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="88983-116">キャッシュは、すべての Web 応答の無効になり、プログラムでオーバーライドされることはできませんを指定します。</span><span class="sxs-lookup"><span data-stu-id="88983-116">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="88983-117"><xref:System.Net.Cache.RequestCacheLevel> 列挙値の値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="88983-117">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="88983-118">既定値は `BypassCache` です。</span><span class="sxs-lookup"><span data-stu-id="88983-118">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="88983-119">その後、コンテンツを期限切れとマークが既定の時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="88983-119">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="88983-120">policyLevel 属性</span><span class="sxs-lookup"><span data-stu-id="88983-120">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="88983-121">[値]</span><span class="sxs-lookup"><span data-stu-id="88983-121">Value</span></span>|<span data-ttu-id="88983-122">説明</span><span class="sxs-lookup"><span data-stu-id="88983-122">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="88983-123">リソースに新しいもコンテンツの長さは正確では、有効期限、変更、およびコンテンツの長さの属性が存在する場合は、キャッシュされたリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="88983-123">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="88983-124">サーバーからリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="88983-124">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="88983-125">コンテンツの長さが存在し、エントリのサイズと一致する場合は、キャッシュされたリソースを返します。</span><span class="sxs-lookup"><span data-stu-id="88983-125">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="88983-126">コンテンツの長さが指定されたエントリのサイズと一致する場合、キャッシュされたリソースを返しますそれ以外の場合、リソースはサーバーからダウンロードされ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="88983-126">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="88983-127">キャッシュされたリソースのタイムスタンプが、サーバー上のリソースのタイムスタンプと同じである場合、キャッシュされたリソースを返しますそれ以外の場合、リソースは、キャッシュに格納されているサーバーからダウンロードされ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="88983-127">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="88983-128">サーバーからリソースをダウンロード、キャッシュに格納およびリソースを呼び出し元に返します。</span><span class="sxs-lookup"><span data-stu-id="88983-128">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="88983-129">キャッシュされたリソースが存在する場合は削除されます。</span><span class="sxs-lookup"><span data-stu-id="88983-129">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="88983-130">リソースは、サーバーからがダウンロードされ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="88983-130">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="88983-131">タイムスタンプが、サーバー上のリソースのタイムスタンプと同じである場合は、リソースのキャッシュされたコピーを使用して、要求に応じます。それ以外の場合、リソースの呼び出し元に表示される、サーバーからダウンロードし、キャッシュに格納されます。</span><span class="sxs-lookup"><span data-stu-id="88983-131">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88983-132">子要素</span><span class="sxs-lookup"><span data-stu-id="88983-132">Child Elements</span></span>  
  
|<span data-ttu-id="88983-133">要素</span><span class="sxs-lookup"><span data-stu-id="88983-133">Element</span></span>|<span data-ttu-id="88983-134">説明</span><span class="sxs-lookup"><span data-stu-id="88983-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88983-135">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="88983-135">defaultHttpCachePolicy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="88983-136">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="88983-136">Optional element.</span></span><br /><br /> <span data-ttu-id="88983-137">HTTP キャッシュがアクティブでかどうかし、既定のキャッシュ ポリシーの記述について説明します。</span><span class="sxs-lookup"><span data-stu-id="88983-137">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="88983-138">\<defaultFtpCachePolicy> 要素 (ネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="88983-138">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="88983-139">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="88983-139">Optional element.</span></span><br /><br /> <span data-ttu-id="88983-140">FTP キャッシュがアクティブでかどうかし、既定のキャッシュ ポリシーを記述について説明します。</span><span class="sxs-lookup"><span data-stu-id="88983-140">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="88983-141">親要素</span><span class="sxs-lookup"><span data-stu-id="88983-141">Parent Elements</span></span>  
  
|<span data-ttu-id="88983-142">要素</span><span class="sxs-lookup"><span data-stu-id="88983-142">Element</span></span>|<span data-ttu-id="88983-143">説明</span><span class="sxs-lookup"><span data-stu-id="88983-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88983-144">system.net</span><span class="sxs-lookup"><span data-stu-id="88983-144">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="88983-145">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="88983-145">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="88983-146">例</span><span class="sxs-lookup"><span data-stu-id="88983-146">Example</span></span>  
 <span data-ttu-id="88983-147">次の例では、すべてのキャッシュを無効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="88983-147">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="88983-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="88983-148">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="88983-149">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="88983-149">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
