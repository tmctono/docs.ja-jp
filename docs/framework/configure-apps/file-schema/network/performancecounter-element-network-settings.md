---
title: <performanceCounter> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 58a2bf5118a3a2cd9c33301eca5dcc751c2351bf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74283092"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="cf3ee-102">\<performanceCounter> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="cf3ee-102">\<performanceCounter> Element (Network Settings)</span></span>
<span data-ttu-id="cf3ee-103">ネットワークパフォーマンスカウンターを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-103">Enables or disables networking performance counters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**

## <a name="syntax"></a><span data-ttu-id="cf3ee-104">構文</span><span class="sxs-lookup"><span data-stu-id="cf3ee-104">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf3ee-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cf3ee-105">Attributes and Elements</span></span>  
 <span data-ttu-id="cf3ee-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf3ee-107">属性</span><span class="sxs-lookup"><span data-stu-id="cf3ee-107">Attributes</span></span>  
  
|<span data-ttu-id="cf3ee-108">属性</span><span class="sxs-lookup"><span data-stu-id="cf3ee-108">Attribute</span></span>|<span data-ttu-id="cf3ee-109">説明</span><span class="sxs-lookup"><span data-stu-id="cf3ee-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="cf3ee-110">ネットワークパフォーマンスカウンターを有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-110">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="cf3ee-111">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cf3ee-112">子要素</span><span class="sxs-lookup"><span data-stu-id="cf3ee-112">Child Elements</span></span>  
 <span data-ttu-id="cf3ee-113">なし。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cf3ee-114">親要素</span><span class="sxs-lookup"><span data-stu-id="cf3ee-114">Parent Elements</span></span>  
  
|<span data-ttu-id="cf3ee-115">要素</span><span class="sxs-lookup"><span data-stu-id="cf3ee-115">Element</span></span>|<span data-ttu-id="cf3ee-116">Description</span><span class="sxs-lookup"><span data-stu-id="cf3ee-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf3ee-117">設定</span><span class="sxs-lookup"><span data-stu-id="cf3ee-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="cf3ee-118"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf3ee-119">解説</span><span class="sxs-lookup"><span data-stu-id="cf3ee-119">Remarks</span></span>  
 <span data-ttu-id="cf3ee-120">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-120">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="cf3ee-121">ネットワーク パフォーマンス カウンターは、使用される構成ファイルで有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-121">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="cf3ee-122">すべてのネットワーク パフォーマンス カウンターは、構成ファイル内の 1 つの設定で有効または無効にされます。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-122">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="cf3ee-123">ネットワーク パフォーマンス カウンターを個別に有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-123">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="cf3ee-124">特定のネットワークパフォーマンスカウンターの詳細については、「[ネットワークパフォーマンスカウンター](../../../debug-trace-profile/performance-counters.md#networking-performance-counters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-124">For more information on the specific networking performance counters, see [Networking performance counters](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).</span></span>  
  
 <span data-ttu-id="cf3ee-125">既定値は、ネットワークパフォーマンスカウンターが無効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-125">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="cf3ee-126">プロパティは、 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> 適用可能**な**構成ファイルから enabled 属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-126">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf3ee-127">例</span><span class="sxs-lookup"><span data-stu-id="cf3ee-127">Example</span></span>  
 <span data-ttu-id="cf3ee-128">次の例では、および関連する名前空間を構成して、ネットワークパフォーマンスカウンターを有効にする方法を示し <xref:System.Net> ます。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-128">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf3ee-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf3ee-129">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="cf3ee-130">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="cf3ee-130">Network Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cf3ee-131">ネットワークパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="cf3ee-131">Networking Performance Counters</span></span>](../../../debug-trace-profile/performance-counters.md#networking-performance-counters)
