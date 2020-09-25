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
ms.openlocfilehash: 4859f3a9e6de4f1bf8a56212bfe01f94d66f5650
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190242"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="f23a8-102">\<performanceCounter> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="f23a8-102">\<performanceCounter> Element (Network Settings)</span></span>

<span data-ttu-id="f23a8-103">ネットワークパフォーマンスカウンターを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="f23a8-103">Enables or disables networking performance counters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**

## <a name="syntax"></a><span data-ttu-id="f23a8-104">構文</span><span class="sxs-lookup"><span data-stu-id="f23a8-104">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f23a8-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f23a8-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f23a8-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f23a8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f23a8-107">属性</span><span class="sxs-lookup"><span data-stu-id="f23a8-107">Attributes</span></span>  
  
|<span data-ttu-id="f23a8-108">属性</span><span class="sxs-lookup"><span data-stu-id="f23a8-108">Attribute</span></span>|<span data-ttu-id="f23a8-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="f23a8-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f23a8-110">ネットワークパフォーマンスカウンターを有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f23a8-110">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="f23a8-111">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="f23a8-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f23a8-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f23a8-112">Child Elements</span></span>  

 <span data-ttu-id="f23a8-113">なし。</span><span class="sxs-lookup"><span data-stu-id="f23a8-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f23a8-114">親要素</span><span class="sxs-lookup"><span data-stu-id="f23a8-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f23a8-115">要素</span><span class="sxs-lookup"><span data-stu-id="f23a8-115">Element</span></span>|<span data-ttu-id="f23a8-116">説明</span><span class="sxs-lookup"><span data-stu-id="f23a8-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f23a8-117">設定</span><span class="sxs-lookup"><span data-stu-id="f23a8-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="f23a8-118"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="f23a8-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f23a8-119">解説</span><span class="sxs-lookup"><span data-stu-id="f23a8-119">Remarks</span></span>  

 <span data-ttu-id="f23a8-120">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f23a8-120">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="f23a8-121">ネットワーク パフォーマンス カウンターは、使用される構成ファイルで有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23a8-121">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="f23a8-122">すべてのネットワーク パフォーマンス カウンターは、構成ファイル内の 1 つの設定で有効または無効にされます。</span><span class="sxs-lookup"><span data-stu-id="f23a8-122">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="f23a8-123">ネットワーク パフォーマンス カウンターを個別に有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f23a8-123">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="f23a8-124">特定のネットワークパフォーマンスカウンターの詳細については、「 [ネットワークパフォーマンスカウンター](../../../debug-trace-profile/performance-counters.md#networking-performance-counters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f23a8-124">For more information on the specific networking performance counters, see [Networking performance counters](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).</span></span>  
  
 <span data-ttu-id="f23a8-125">既定値は、ネットワークパフォーマンスカウンターが無効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="f23a8-125">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="f23a8-126">プロパティは、 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> 適用可能 **な** 構成ファイルから enabled 属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="f23a8-126">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f23a8-127">例</span><span class="sxs-lookup"><span data-stu-id="f23a8-127">Example</span></span>  

 <span data-ttu-id="f23a8-128">次の例では、および関連する名前空間を構成して、ネットワークパフォーマンスカウンターを有効にする方法を示し <xref:System.Net> ます。</span><span class="sxs-lookup"><span data-stu-id="f23a8-128">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f23a8-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="f23a8-129">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f23a8-130">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f23a8-130">Network Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f23a8-131">ネットワークパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="f23a8-131">Networking Performance Counters</span></span>](../../../debug-trace-profile/performance-counters.md#networking-performance-counters)
