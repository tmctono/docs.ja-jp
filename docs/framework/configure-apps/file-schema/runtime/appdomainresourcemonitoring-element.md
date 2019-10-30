---
title: <appDomainResourceMonitoring> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 991833500cae4d96e9c28f7e94ca366e9b976a9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118255"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="e9076-102">\<appDomainResourceMonitoring > 要素</span><span class="sxs-lookup"><span data-stu-id="e9076-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="e9076-103">プロセスのライフサイクルにおいて、プロセスのすべてのアプリケーション ドメインの統計を収集するようにランタイムに指示します。</span><span class="sxs-lookup"><span data-stu-id="e9076-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
<span data-ttu-id="e9076-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9076-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e9076-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9076-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="e9076-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<appDomainResourceMonitoring >**</span><span class="sxs-lookup"><span data-stu-id="e9076-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9076-107">構文</span><span class="sxs-lookup"><span data-stu-id="e9076-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9076-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e9076-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e9076-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9076-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9076-110">属性</span><span class="sxs-lookup"><span data-stu-id="e9076-110">Attributes</span></span>  
  
|<span data-ttu-id="e9076-111">属性</span><span class="sxs-lookup"><span data-stu-id="e9076-111">Attribute</span></span>|<span data-ttu-id="e9076-112">説明</span><span class="sxs-lookup"><span data-stu-id="e9076-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="e9076-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="e9076-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="e9076-114">アプリケーションドメインのリソース監視の統計情報をランタイムが収集するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9076-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e9076-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="e9076-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="e9076-116">[値]</span><span class="sxs-lookup"><span data-stu-id="e9076-116">Value</span></span>|<span data-ttu-id="e9076-117">説明</span><span class="sxs-lookup"><span data-stu-id="e9076-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="e9076-118">アプリケーションドメインのリソース監視の統計情報が収集されます。</span><span class="sxs-lookup"><span data-stu-id="e9076-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="e9076-119">アプリケーションドメインのリソース監視の統計情報は収集されません。</span><span class="sxs-lookup"><span data-stu-id="e9076-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9076-120">子要素</span><span class="sxs-lookup"><span data-stu-id="e9076-120">Child Elements</span></span>  
 <span data-ttu-id="e9076-121">なし。</span><span class="sxs-lookup"><span data-stu-id="e9076-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9076-122">親要素</span><span class="sxs-lookup"><span data-stu-id="e9076-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e9076-123">要素</span><span class="sxs-lookup"><span data-stu-id="e9076-123">Element</span></span>|<span data-ttu-id="e9076-124">説明</span><span class="sxs-lookup"><span data-stu-id="e9076-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e9076-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="e9076-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e9076-126">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e9076-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9076-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="e9076-127">Remarks</span></span>  
 <span data-ttu-id="e9076-128">アプリケーションドメインのリソース監視は、マネージアプリケーションドメインクラス、ホスティング[ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)インターフェイス、および Windows イベントトレーシング (ETW) を介して使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9076-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="e9076-129">監視が有効になっている場合、プロセス内のすべてのアプリケーションドメインについて、プロセスの実行中に統計が収集されます。</span><span class="sxs-lookup"><span data-stu-id="e9076-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="e9076-130">マネージコードからの監視を有効にするには、<xref:System.AppDomain.MonitoringIsEnabled%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9076-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="e9076-131">この構成要素は、.NET Framework 4 以降でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9076-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9076-132">例</span><span class="sxs-lookup"><span data-stu-id="e9076-132">Example</span></span>  
 <span data-ttu-id="e9076-133">次の例は、アプリケーションドメインのリソース監視を有効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e9076-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9076-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9076-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e9076-135">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="e9076-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e9076-136">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="e9076-136">Configuration File Schema</span></span>](../index.md)
