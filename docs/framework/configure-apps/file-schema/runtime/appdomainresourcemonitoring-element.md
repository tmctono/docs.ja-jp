---
title: <appDomainResourceMonitoring> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154377"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="d6936-102">\<appDomainResourceMonitoring> 要素</span><span class="sxs-lookup"><span data-stu-id="d6936-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="d6936-103">プロセスのライフサイクルにおいて、プロセスのすべてのアプリケーション ドメインの統計を収集するようにランタイムに指示します。</span><span class="sxs-lookup"><span data-stu-id="d6936-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
## <a name="syntax"></a><span data-ttu-id="d6936-104">構文</span><span class="sxs-lookup"><span data-stu-id="d6936-104">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6936-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d6936-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d6936-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6936-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6936-107">属性</span><span class="sxs-lookup"><span data-stu-id="d6936-107">Attributes</span></span>  
  
|<span data-ttu-id="d6936-108">属性</span><span class="sxs-lookup"><span data-stu-id="d6936-108">Attribute</span></span>|<span data-ttu-id="d6936-109">説明</span><span class="sxs-lookup"><span data-stu-id="d6936-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d6936-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="d6936-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="d6936-111">アプリケーションドメインのリソース監視の統計情報をランタイムが収集するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6936-111">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d6936-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="d6936-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="d6936-113">値</span><span class="sxs-lookup"><span data-stu-id="d6936-113">Value</span></span>|<span data-ttu-id="d6936-114">Description</span><span class="sxs-lookup"><span data-stu-id="d6936-114">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="d6936-115">アプリケーションドメインのリソース監視の統計情報が収集されます。</span><span class="sxs-lookup"><span data-stu-id="d6936-115">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="d6936-116">アプリケーションドメインのリソース監視の統計情報は収集されません。</span><span class="sxs-lookup"><span data-stu-id="d6936-116">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6936-117">子要素</span><span class="sxs-lookup"><span data-stu-id="d6936-117">Child Elements</span></span>  
 <span data-ttu-id="d6936-118">なし。</span><span class="sxs-lookup"><span data-stu-id="d6936-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6936-119">親要素</span><span class="sxs-lookup"><span data-stu-id="d6936-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d6936-120">要素</span><span class="sxs-lookup"><span data-stu-id="d6936-120">Element</span></span>|<span data-ttu-id="d6936-121">Description</span><span class="sxs-lookup"><span data-stu-id="d6936-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d6936-122">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="d6936-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d6936-123">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d6936-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6936-124">解説</span><span class="sxs-lookup"><span data-stu-id="d6936-124">Remarks</span></span>  
 <span data-ttu-id="d6936-125">アプリケーションドメインのリソース監視は、マネージアプリケーションドメインクラス、ホスティング[ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)インターフェイス、および Windows イベントトレーシング (ETW) を介して使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6936-125">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="d6936-126">監視が有効になっている場合、プロセス内のすべてのアプリケーションドメインについて、プロセスの実行中に統計が収集されます。</span><span class="sxs-lookup"><span data-stu-id="d6936-126">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="d6936-127">マネージコードからの監視を有効にするには、プロパティを使用し <xref:System.AppDomain.MonitoringIsEnabled%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="d6936-127">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="d6936-128">この構成要素は、.NET Framework 4 以降でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6936-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6936-129">例</span><span class="sxs-lookup"><span data-stu-id="d6936-129">Example</span></span>  
 <span data-ttu-id="d6936-130">次の例は、アプリケーションドメインのリソース監視を有効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d6936-130">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6936-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6936-131">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d6936-132">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="d6936-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d6936-133">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="d6936-133">Configuration File Schema</span></span>](../index.md)
