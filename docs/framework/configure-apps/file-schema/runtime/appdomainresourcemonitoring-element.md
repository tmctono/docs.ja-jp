---
title: <appDomainResourceMonitoring> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154377"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="64d31-102">\<要素>リソースの監視</span><span class="sxs-lookup"><span data-stu-id="64d31-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="64d31-103">プロセスのライフサイクルにおいて、プロセスのすべてのアプリケーション ドメインの統計を収集するようにランタイムに指示します。</span><span class="sxs-lookup"><span data-stu-id="64d31-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
<span data-ttu-id="64d31-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="64d31-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="64d31-105">&nbsp;&nbsp;[**\<ランタイム>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="64d31-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="64d31-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<>の監視**</span><span class="sxs-lookup"><span data-stu-id="64d31-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64d31-107">構文</span><span class="sxs-lookup"><span data-stu-id="64d31-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64d31-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="64d31-108">Attributes and Elements</span></span>  
 <span data-ttu-id="64d31-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="64d31-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64d31-110">属性</span><span class="sxs-lookup"><span data-stu-id="64d31-110">Attributes</span></span>  
  
|<span data-ttu-id="64d31-111">属性</span><span class="sxs-lookup"><span data-stu-id="64d31-111">Attribute</span></span>|<span data-ttu-id="64d31-112">説明</span><span class="sxs-lookup"><span data-stu-id="64d31-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="64d31-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="64d31-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="64d31-114">ランタイムがアプリケーション ドメインリソース監視の統計を収集するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="64d31-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="64d31-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="64d31-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="64d31-116">Value</span><span class="sxs-lookup"><span data-stu-id="64d31-116">Value</span></span>|<span data-ttu-id="64d31-117">説明</span><span class="sxs-lookup"><span data-stu-id="64d31-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="64d31-118">アプリケーション ドメインリソース監視の統計が収集されます。</span><span class="sxs-lookup"><span data-stu-id="64d31-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="64d31-119">アプリケーション ドメインリソースの監視の統計は収集されません。</span><span class="sxs-lookup"><span data-stu-id="64d31-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64d31-120">子要素</span><span class="sxs-lookup"><span data-stu-id="64d31-120">Child Elements</span></span>  
 <span data-ttu-id="64d31-121">[なし] :</span><span class="sxs-lookup"><span data-stu-id="64d31-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64d31-122">親要素</span><span class="sxs-lookup"><span data-stu-id="64d31-122">Parent Elements</span></span>  
  
|<span data-ttu-id="64d31-123">要素</span><span class="sxs-lookup"><span data-stu-id="64d31-123">Element</span></span>|<span data-ttu-id="64d31-124">説明</span><span class="sxs-lookup"><span data-stu-id="64d31-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="64d31-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="64d31-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="64d31-126">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="64d31-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64d31-127">解説</span><span class="sxs-lookup"><span data-stu-id="64d31-127">Remarks</span></span>  
 <span data-ttu-id="64d31-128">アプリケーション ドメイン リソースの監視は、マネージ アプリケーション ドメイン クラス、ホストする[ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)インターフェイス、および Windows のイベント トレース (ETW) を通じて使用できます。</span><span class="sxs-lookup"><span data-stu-id="64d31-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="64d31-129">監視が有効な場合、プロセスの有効期間中に、プロセス内のすべてのアプリケーション ドメインに関する統計が収集されます。</span><span class="sxs-lookup"><span data-stu-id="64d31-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="64d31-130">マネージ コードからの監視を有効にするには、<xref:System.AppDomain.MonitoringIsEnabled%2A>プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="64d31-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="64d31-131">この構成要素は、.NET Framework 4 以降でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="64d31-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64d31-132">例</span><span class="sxs-lookup"><span data-stu-id="64d31-132">Example</span></span>  
 <span data-ttu-id="64d31-133">アプリケーション ドメインのリソース監視を有効にする方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="64d31-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="64d31-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="64d31-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="64d31-135">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="64d31-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="64d31-136">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="64d31-136">Configuration File Schema</span></span>](../index.md)
