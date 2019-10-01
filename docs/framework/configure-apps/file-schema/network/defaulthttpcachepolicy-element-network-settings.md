---
title: <defaultHttpCachePolicy> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: f3b029e8b931e976bee85c98dd926e020c5b8743
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698277"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="61594-102">\<defaultHttpCachePolicy> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="61594-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="61594-103">HTTP キャッシュがアクティブかどうか、および既定のキャッシュポリシーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="61594-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
[<span data-ttu-id="61594-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="61594-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="61594-105">&nbsp; @ no__t-1[ **@no__t 47 >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="61594-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="61594-106">&nbsp; @ no__t @ no__t-2 @ no__t-3[ **\<requestcaching >** ](requestcaching-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="61594-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)</span></span>  
<span data-ttu-id="61594-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 **\<defaultHttpCachePolicy >** を行います。</span><span class="sxs-lookup"><span data-stu-id="61594-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultHttpCachePolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61594-108">構文</span><span class="sxs-lookup"><span data-stu-id="61594-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61594-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="61594-109">Attributes and Elements</span></span>  
 <span data-ttu-id="61594-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="61594-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61594-111">属性</span><span class="sxs-lookup"><span data-stu-id="61594-111">Attributes</span></span>  
  
|<span data-ttu-id="61594-112">属性</span><span class="sxs-lookup"><span data-stu-id="61594-112">Attribute</span></span>|<span data-ttu-id="61594-113">説明</span><span class="sxs-lookup"><span data-stu-id="61594-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="61594-114">キャッシュされたオブジェクトを期限切れとしてマークするまでの最大時間間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="61594-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="61594-115">キャッシュされたオブジェクトを期限切れとしてマークするまでの、計算された鮮度時間を超える最大時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="61594-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="61594-116">キャッシュされたオブジェクトが最新であると見なされるための最小時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="61594-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="61594-117">キャッシュポリシーが自動であるかどうか、またはキャッシュをバイパスするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="61594-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="61594-118">既定値は `BypassCache` です。</span><span class="sxs-lookup"><span data-stu-id="61594-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61594-119">子要素</span><span class="sxs-lookup"><span data-stu-id="61594-119">Child Elements</span></span>  
 <span data-ttu-id="61594-120">なし</span><span class="sxs-lookup"><span data-stu-id="61594-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61594-121">親要素</span><span class="sxs-lookup"><span data-stu-id="61594-121">Parent Elements</span></span>  
  
|<span data-ttu-id="61594-122">要素</span><span class="sxs-lookup"><span data-stu-id="61594-122">Element</span></span>|<span data-ttu-id="61594-123">説明</span><span class="sxs-lookup"><span data-stu-id="61594-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61594-124">requestCaching</span><span class="sxs-lookup"><span data-stu-id="61594-124">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="61594-125">ネットワーク要求のキャッシュメカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="61594-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61594-126">コメント</span><span class="sxs-lookup"><span data-stu-id="61594-126">Remarks</span></span>  
 <span data-ttu-id="61594-127">@No__t-0 属性の値は、`BypassCache` または `Default` のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="61594-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="61594-128">@No__t-0、`maximumStale`、`minimumFresh` の各要素の値は、明示的な時間間隔であり、形式は*d*です。*hh*:*mm*:*ss* (日数、時間、分、秒)、または必要に応じて `minValue` または `maxValue` の定数。</span><span class="sxs-lookup"><span data-stu-id="61594-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="61594-129">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="61594-129">Configuration Files</span></span>  
 <span data-ttu-id="61594-130">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="61594-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="61594-131">例</span><span class="sxs-lookup"><span data-stu-id="61594-131">Example</span></span>  
 <span data-ttu-id="61594-132">次の例では、6時間、最長有効期間、および最大4時間の最長時間を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="61594-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="61594-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="61594-133">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="61594-134">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="61594-134">Network Settings Schema</span></span>](index.md)
