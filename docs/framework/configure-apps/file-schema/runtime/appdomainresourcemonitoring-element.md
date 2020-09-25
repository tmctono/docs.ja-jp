---
title: <appDomainResourceMonitoring> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 9ecf2e382b5d483377df871835793219b3f74760
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170273"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="70a93-102">\<appDomainResourceMonitoring> 要素</span><span class="sxs-lookup"><span data-stu-id="70a93-102">\<appDomainResourceMonitoring> Element</span></span>

<span data-ttu-id="70a93-103">プロセスのライフサイクルにおいて、プロセスのすべてのアプリケーション ドメインの統計を収集するようにランタイムに指示します。</span><span class="sxs-lookup"><span data-stu-id="70a93-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
## <a name="syntax"></a><span data-ttu-id="70a93-104">構文</span><span class="sxs-lookup"><span data-stu-id="70a93-104">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70a93-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="70a93-105">Attributes and Elements</span></span>  

 <span data-ttu-id="70a93-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="70a93-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70a93-107">属性</span><span class="sxs-lookup"><span data-stu-id="70a93-107">Attributes</span></span>  
  
|<span data-ttu-id="70a93-108">属性</span><span class="sxs-lookup"><span data-stu-id="70a93-108">Attribute</span></span>|<span data-ttu-id="70a93-109">説明</span><span class="sxs-lookup"><span data-stu-id="70a93-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="70a93-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="70a93-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="70a93-111">アプリケーションドメインのリソース監視の統計情報をランタイムが収集するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="70a93-111">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="70a93-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="70a93-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="70a93-113">値</span><span class="sxs-lookup"><span data-stu-id="70a93-113">Value</span></span>|<span data-ttu-id="70a93-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="70a93-114">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="70a93-115">アプリケーションドメインのリソース監視の統計情報が収集されます。</span><span class="sxs-lookup"><span data-stu-id="70a93-115">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="70a93-116">アプリケーションドメインのリソース監視の統計情報は収集されません。</span><span class="sxs-lookup"><span data-stu-id="70a93-116">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70a93-117">子要素</span><span class="sxs-lookup"><span data-stu-id="70a93-117">Child Elements</span></span>  

 <span data-ttu-id="70a93-118">なし。</span><span class="sxs-lookup"><span data-stu-id="70a93-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70a93-119">親要素</span><span class="sxs-lookup"><span data-stu-id="70a93-119">Parent Elements</span></span>  
  
|<span data-ttu-id="70a93-120">要素</span><span class="sxs-lookup"><span data-stu-id="70a93-120">Element</span></span>|<span data-ttu-id="70a93-121">説明</span><span class="sxs-lookup"><span data-stu-id="70a93-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="70a93-122">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="70a93-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="70a93-123">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="70a93-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70a93-124">解説</span><span class="sxs-lookup"><span data-stu-id="70a93-124">Remarks</span></span>  

 <span data-ttu-id="70a93-125">アプリケーションドメインのリソース監視は、マネージアプリケーションドメインクラス、ホスティング [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) インターフェイス、および Windows イベントトレーシング (ETW) を介して使用できます。</span><span class="sxs-lookup"><span data-stu-id="70a93-125">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="70a93-126">監視が有効になっている場合、プロセス内のすべてのアプリケーションドメインについて、プロセスの実行中に統計が収集されます。</span><span class="sxs-lookup"><span data-stu-id="70a93-126">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="70a93-127">マネージコードからの監視を有効にするには、プロパティを使用し <xref:System.AppDomain.MonitoringIsEnabled%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="70a93-127">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="70a93-128">この構成要素は、.NET Framework 4 以降でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="70a93-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70a93-129">例</span><span class="sxs-lookup"><span data-stu-id="70a93-129">Example</span></span>  

 <span data-ttu-id="70a93-130">次の例は、アプリケーションドメインのリソース監視を有効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="70a93-130">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="70a93-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="70a93-131">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="70a93-132">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="70a93-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="70a93-133">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="70a93-133">Configuration File Schema</span></span>](../index.md)
