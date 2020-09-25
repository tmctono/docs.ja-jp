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
ms.openlocfilehash: 4120c57fbb65da1c124414cbe9cfba7ae64388f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190320"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="0f074-102">\<defaultHttpCachePolicy> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="0f074-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>

<span data-ttu-id="0f074-103">HTTP キャッシュがアクティブかどうか、および既定のキャッシュポリシーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0f074-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultHttpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="0f074-104">構文</span><span class="sxs-lookup"><span data-stu-id="0f074-104">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f074-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0f074-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0f074-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f074-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f074-107">属性</span><span class="sxs-lookup"><span data-stu-id="0f074-107">Attributes</span></span>  
  
|<span data-ttu-id="0f074-108">属性</span><span class="sxs-lookup"><span data-stu-id="0f074-108">Attribute</span></span>|<span data-ttu-id="0f074-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="0f074-109">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="0f074-110">キャッシュされたオブジェクトを期限切れとしてマークするまでの最大時間間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="0f074-110">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="0f074-111">キャッシュされたオブジェクトを期限切れとしてマークするまでの、計算された鮮度時間を超える最大時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="0f074-111">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="0f074-112">キャッシュされたオブジェクトが最新であると見なされるための最小時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="0f074-112">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="0f074-113">キャッシュポリシーが自動であるかどうか、またはキャッシュをバイパスするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f074-113">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="0f074-114">既定値は `BypassCache` です。</span><span class="sxs-lookup"><span data-stu-id="0f074-114">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f074-115">子要素</span><span class="sxs-lookup"><span data-stu-id="0f074-115">Child Elements</span></span>  

 <span data-ttu-id="0f074-116">None</span><span class="sxs-lookup"><span data-stu-id="0f074-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f074-117">親要素</span><span class="sxs-lookup"><span data-stu-id="0f074-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0f074-118">要素</span><span class="sxs-lookup"><span data-stu-id="0f074-118">Element</span></span>|<span data-ttu-id="0f074-119">説明</span><span class="sxs-lookup"><span data-stu-id="0f074-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f074-120">Requestcaching></span><span class="sxs-lookup"><span data-stu-id="0f074-120">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="0f074-121">ネットワーク要求のキャッシュメカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="0f074-121">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f074-122">解説</span><span class="sxs-lookup"><span data-stu-id="0f074-122">Remarks</span></span>  

 <span data-ttu-id="0f074-123">属性の値 `policyLevel` がまたはのいずれか `BypassCache` `Default` です。</span><span class="sxs-lookup"><span data-stu-id="0f074-123">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="0f074-124">`maximumAge`、、およびの各要素の値 `maximumStale` は、明示的な時間間隔であり、形式は `minimumFresh` *d*です。*hh*:*mm*:*ss* (日数、時間、分、秒)、または必要に応じ `minValue` て定数または `maxValue` 。</span><span class="sxs-lookup"><span data-stu-id="0f074-124">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0f074-125">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="0f074-125">Configuration Files</span></span>  

 <span data-ttu-id="0f074-126">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f074-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f074-127">例</span><span class="sxs-lookup"><span data-stu-id="0f074-127">Example</span></span>  

 <span data-ttu-id="0f074-128">次の例では、6時間、最長有効期間、および最大4時間の最長時間を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0f074-128">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0f074-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f074-129">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="0f074-130">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="0f074-130">Network Settings Schema</span></span>](index.md)
