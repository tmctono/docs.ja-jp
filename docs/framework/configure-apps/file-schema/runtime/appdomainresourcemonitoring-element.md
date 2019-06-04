---
title: <appDomainResourceMonitoring> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad0ae023215eeb1f42f9351369ee77d41d537b88
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487729"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="57e28-102">\<appDomainResourceMonitoring > 要素</span><span class="sxs-lookup"><span data-stu-id="57e28-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="57e28-103">プロセスのライフサイクルにおいて、プロセスのすべてのアプリケーション ドメインの統計を収集するようにランタイムに指示します。</span><span class="sxs-lookup"><span data-stu-id="57e28-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="57e28-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="57e28-104">\<configuration></span></span>  
<span data-ttu-id="57e28-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="57e28-105">\<runtime></span></span>  
<span data-ttu-id="57e28-106">\<appDomainResourceMonitoring ></span><span class="sxs-lookup"><span data-stu-id="57e28-106">\<appDomainResourceMonitoring></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57e28-107">構文</span><span class="sxs-lookup"><span data-stu-id="57e28-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57e28-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="57e28-108">Attributes and Elements</span></span>  
 <span data-ttu-id="57e28-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="57e28-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57e28-110">属性</span><span class="sxs-lookup"><span data-stu-id="57e28-110">Attributes</span></span>  
  
|<span data-ttu-id="57e28-111">属性</span><span class="sxs-lookup"><span data-stu-id="57e28-111">Attribute</span></span>|<span data-ttu-id="57e28-112">説明</span><span class="sxs-lookup"><span data-stu-id="57e28-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="57e28-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="57e28-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="57e28-114">ランタイムがアプリケーション ドメインのリソースの監視に関する統計を収集するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="57e28-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="57e28-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="57e28-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="57e28-116">値</span><span class="sxs-lookup"><span data-stu-id="57e28-116">Value</span></span>|<span data-ttu-id="57e28-117">説明</span><span class="sxs-lookup"><span data-stu-id="57e28-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="57e28-118">アプリケーション ドメインのリソース監視の統計情報が収集されます。</span><span class="sxs-lookup"><span data-stu-id="57e28-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="57e28-119">アプリケーション ドメインのリソース監視の統計情報は収集されません。</span><span class="sxs-lookup"><span data-stu-id="57e28-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57e28-120">子要素</span><span class="sxs-lookup"><span data-stu-id="57e28-120">Child Elements</span></span>  
 <span data-ttu-id="57e28-121">なし。</span><span class="sxs-lookup"><span data-stu-id="57e28-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="57e28-122">親要素</span><span class="sxs-lookup"><span data-stu-id="57e28-122">Parent Elements</span></span>  
  
|<span data-ttu-id="57e28-123">要素</span><span class="sxs-lookup"><span data-stu-id="57e28-123">Element</span></span>|<span data-ttu-id="57e28-124">説明</span><span class="sxs-lookup"><span data-stu-id="57e28-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="57e28-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="57e28-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="57e28-126">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="57e28-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57e28-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="57e28-127">Remarks</span></span>  
 <span data-ttu-id="57e28-128">アプリケーション ドメインのリソースの監視をホスト、管理対象のアプリケーション ドメイン クラスを利用[ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)インターフェイスと event tracing for Windows (ETW)。</span><span class="sxs-lookup"><span data-stu-id="57e28-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="57e28-129">監視を有効にすると、プロセスの実行中のプロセス内のすべてのアプリケーション ドメインの統計情報が収集されます。</span><span class="sxs-lookup"><span data-stu-id="57e28-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="57e28-130">マネージ コードからの監視を有効にするには使用、<xref:System.AppDomain.MonitoringIsEnabled%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="57e28-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="57e28-131">この構成要素は、以降、.NET Framework 4 でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="57e28-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57e28-132">例</span><span class="sxs-lookup"><span data-stu-id="57e28-132">Example</span></span>  
 <span data-ttu-id="57e28-133">次の例では、アプリケーション ドメインのリソースの監視を有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="57e28-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="57e28-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="57e28-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="57e28-135">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="57e28-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="57e28-136">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="57e28-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
