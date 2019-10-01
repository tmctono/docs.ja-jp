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
ms.openlocfilehash: 3fe6b19d0055aafad859b55960800d9786d7fa08
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698000"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="133ed-102">\<performanceCounter > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="133ed-102">\<performanceCounter> Element (Network Settings)</span></span>
<span data-ttu-id="133ed-103">ネットワークパフォーマンスカウンターを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="133ed-103">Enables or disables networking performance counters.</span></span>  
  
[<span data-ttu-id="133ed-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="133ed-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="133ed-105">&nbsp; @ no__t-1[ **@no__t 47 >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="133ed-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="133ed-106">&nbsp; @ no__t @ no__t @no__t @ no__t-3[ **-6 設定 >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="133ed-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="133ed-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 **\<performanceCounters >** を行います。</span><span class="sxs-lookup"><span data-stu-id="133ed-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="133ed-108">構文</span><span class="sxs-lookup"><span data-stu-id="133ed-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="133ed-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="133ed-109">Attributes and Elements</span></span>  
 <span data-ttu-id="133ed-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="133ed-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="133ed-111">属性</span><span class="sxs-lookup"><span data-stu-id="133ed-111">Attributes</span></span>  
  
|<span data-ttu-id="133ed-112">属性</span><span class="sxs-lookup"><span data-stu-id="133ed-112">Attribute</span></span>|<span data-ttu-id="133ed-113">説明</span><span class="sxs-lookup"><span data-stu-id="133ed-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="133ed-114">ネットワークパフォーマンスカウンターを有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="133ed-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="133ed-115">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="133ed-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="133ed-116">子要素</span><span class="sxs-lookup"><span data-stu-id="133ed-116">Child Elements</span></span>  
 <span data-ttu-id="133ed-117">なし。</span><span class="sxs-lookup"><span data-stu-id="133ed-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="133ed-118">親要素</span><span class="sxs-lookup"><span data-stu-id="133ed-118">Parent Elements</span></span>  
  
|<span data-ttu-id="133ed-119">要素</span><span class="sxs-lookup"><span data-stu-id="133ed-119">Element</span></span>|<span data-ttu-id="133ed-120">説明</span><span class="sxs-lookup"><span data-stu-id="133ed-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="133ed-121">settings</span><span class="sxs-lookup"><span data-stu-id="133ed-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="133ed-122"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="133ed-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="133ed-123">コメント</span><span class="sxs-lookup"><span data-stu-id="133ed-123">Remarks</span></span>  
 <span data-ttu-id="133ed-124">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="133ed-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="133ed-125">ネットワーク パフォーマンス カウンターは、使用される構成ファイルで有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="133ed-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="133ed-126">すべてのネットワーク パフォーマンス カウンターは、構成ファイル内の 1 つの設定で有効または無効にされます。</span><span class="sxs-lookup"><span data-stu-id="133ed-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="133ed-127">ネットワーク パフォーマンス カウンターを個別に有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="133ed-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="133ed-128">特定のネットワークパフォーマンスカウンターの詳細については、「[ネットワークパフォーマンスカウンター](../../../debug-trace-profile/performance-counters.md#networking)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="133ed-128">For more information on the specific networking performance counters, see [Networking Performance Counters](../../../debug-trace-profile/performance-counters.md#networking).</span></span>  
  
 <span data-ttu-id="133ed-129">既定値は、ネットワークパフォーマンスカウンターが無効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="133ed-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="133ed-130">@No__t-0 プロパティは、適用可能な構成ファイルから**enabled**属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="133ed-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="133ed-131">例</span><span class="sxs-lookup"><span data-stu-id="133ed-131">Example</span></span>  
 <span data-ttu-id="133ed-132">次の例では、<xref:System.Net> および関連する名前空間を構成して、ネットワークパフォーマンスカウンターを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="133ed-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="133ed-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="133ed-133">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="133ed-134">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="133ed-134">Network Settings Schema</span></span>](index.md)
- [<span data-ttu-id="133ed-135">ネットワークパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="133ed-135">Networking Performance Counters</span></span>](../../../debug-trace-profile/performance-counters.md#networking)
