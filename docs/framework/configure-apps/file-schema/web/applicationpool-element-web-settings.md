---
title: <applicationPool> 要素 (Web 設定)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: c88f4e5407e550047eaf0f5c8d0d2924da611e93
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699223"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="6f417-102">\<applicationPool > 要素 (Web 設定)</span><span class="sxs-lookup"><span data-stu-id="6f417-102">\<applicationPool> Element (Web Settings)</span></span>
<span data-ttu-id="6f417-103">ASP.NET アプリケーションが IIS 7.0 以降のバージョンで統合モードで実行されている場合に、プロセス全体の動作を管理するために ASP.NET によって使用される構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f417-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on IIS 7.0 or a later version.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6f417-104">この要素とサポートされる機能は、ASP.NET アプリケーションが IIS 7.0 以降のバージョンでホストされている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="6f417-104">This element and the feature it supports only work if your ASP.NET application is hosted on IIS 7.0 or later versions.</span></span>  
  
[<span data-ttu-id="6f417-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="6f417-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="6f417-106">&nbsp; @ no__t[ **@no__t 47 >** ](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6f417-106">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="6f417-107">&nbsp; @ no__t-1 @ no__t @ no__t-3 **\<applicationPool >**</span><span class="sxs-lookup"><span data-stu-id="6f417-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f417-108">構文</span><span class="sxs-lookup"><span data-stu-id="6f417-108">Syntax</span></span>  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f417-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6f417-109">Attributes and Elements</span></span>  

<span data-ttu-id="6f417-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f417-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f417-111">属性</span><span class="sxs-lookup"><span data-stu-id="6f417-111">Attributes</span></span>  
  
|<span data-ttu-id="6f417-112">属性</span><span class="sxs-lookup"><span data-stu-id="6f417-112">Attribute</span></span>|<span data-ttu-id="6f417-113">説明</span><span class="sxs-lookup"><span data-stu-id="6f417-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="6f417-114">CPU ごとに ASP.NET が許可する同時要求の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f417-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="6f417-115">CPU ごとにアプリケーションプールに対して同時に実行できるスレッドの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f417-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="6f417-116">これにより、要求を処理するために CPU ごとに使用できるマネージスレッドの数を制限できるため、ASP.NET concurrency を制御する別の方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="6f417-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="6f417-117">既定では、この設定は0です。これは、ASP.NET が CPU ごとに作成できるスレッドの数を制限しないことを意味します。ただし、CLR スレッドプールでは、作成可能なスレッドの数も制限されます。</span><span class="sxs-lookup"><span data-stu-id="6f417-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="6f417-118">1つのプロセスで ASP.NET のキューに入れることができる要求の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f417-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="6f417-119">複数の ASP.NET アプリケーションが1つのアプリケーションプールで実行される場合、アプリケーションプール内のアプリケーションに対して行われる要求の累積セットは、この設定の対象となります。</span><span class="sxs-lookup"><span data-stu-id="6f417-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f417-120">子要素</span><span class="sxs-lookup"><span data-stu-id="6f417-120">Child Elements</span></span>  
 <span data-ttu-id="6f417-121">なし。</span><span class="sxs-lookup"><span data-stu-id="6f417-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f417-122">親要素</span><span class="sxs-lookup"><span data-stu-id="6f417-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6f417-123">要素</span><span class="sxs-lookup"><span data-stu-id="6f417-123">Element</span></span>|<span data-ttu-id="6f417-124">説明</span><span class="sxs-lookup"><span data-stu-id="6f417-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f417-125">\<system.web ></span><span class="sxs-lookup"><span data-stu-id="6f417-125">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="6f417-126">ASP.NET がホストアプリケーションと対話する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f417-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f417-127">コメント</span><span class="sxs-lookup"><span data-stu-id="6f417-127">Remarks</span></span>  

<span data-ttu-id="6f417-128">IIS 7.0 以降のバージョンを統合モードで実行する場合、この要素の組み合わせを使用して、アプリケーションが IIS アプリケーションプールでホストされている場合に、ASP.NET がスレッドを管理し、要求をキューに配置する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6f417-128">When you run IIS 7.0 or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="6f417-129">IIS 6 を実行した場合、またはクラシックモードまたは ISAPI モードで IIS 7.0 を実行している場合、これらの設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="6f417-129">If you run IIS 6 or you run IIS 7.0 in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
<span data-ttu-id="6f417-130">@No__t-0 の設定は、.NET Framework の特定のバージョンで実行されるすべてのアプリケーションプールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6f417-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="6f417-131">設定は、aspnet ファイルに格納されています。</span><span class="sxs-lookup"><span data-stu-id="6f417-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="6f417-132">.NET Framework のバージョン2.0 および4.0 では、このファイルのバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="6f417-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="6f417-133">(.NET Framework のバージョン3.0 および3.5 は、aspnet .config ファイルをバージョン2.0 で共有します)。</span><span class="sxs-lookup"><span data-stu-id="6f417-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6f417-134">@No__t-0 で IIS 7.0 を実行している場合は、アプリケーションプールごとに個別の aspnet .config ファイルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="6f417-134">If you run IIS 7.0 on [!INCLUDE[win7](../../../../../includes/win7-md.md)], you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="6f417-135">これにより、各アプリケーションプールのスレッドのパフォーマンスを調整できます。</span><span class="sxs-lookup"><span data-stu-id="6f417-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
<span data-ttu-id="6f417-136">@No__t-0 設定の場合、.NET Framework 4 の既定の設定 "5000" は、ASP.NET によって制御される要求の調整を無効にします (CPU あたりの要求が実際に5000以上の場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="6f417-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the .NET Framework 4 effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="6f417-137">既定の設定は、CPU ごとの同時実行制御を自動的に管理する CLR スレッドプールに依存します。</span><span class="sxs-lookup"><span data-stu-id="6f417-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="6f417-138">非同期要求処理を広範囲にわたって使用するアプリケーションや、ネットワーク i/o でブロックされている実行時間の長い要求が多数あるアプリケーションでは、.NET Framework 4 の既定の制限値を増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="6f417-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the .NET Framework 4.</span></span> <span data-ttu-id="6f417-139">@No__t-0 を0に設定すると、ASP.NET 要求を処理するためのマネージスレッドの使用がオフになります。</span><span class="sxs-lookup"><span data-stu-id="6f417-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="6f417-140">アプリケーションが IIS アプリケーションプールで実行されている場合、要求は IIS の i/o スレッドにとどまります。そのため、同時実行は IIS スレッド設定によって制限されます。</span><span class="sxs-lookup"><span data-stu-id="6f417-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
<span data-ttu-id="6f417-141">@No__t 0 の設定は、ASP.NET アプリケーションの web.config ファイルで設定されている[processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100))要素の `requestQueueLimit` 属性と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="6f417-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="6f417-142">ただし、aspnet ファイルの @no__t 0 の設定は、web.config ファイルの `requestQueueLimit` 設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="6f417-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="6f417-143">つまり、両方の属性が設定されている場合 (既定では true)、aspnet ファイルの @no__t 0 の設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="6f417-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f417-144">例</span><span class="sxs-lookup"><span data-stu-id="6f417-144">Example</span></span>  

<span data-ttu-id="6f417-145">次の例は、次のような場合に、ASP.NET ファイルでプロセス全体の動作を構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6f417-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
- <span data-ttu-id="6f417-146">アプリケーションは、IIS 7.0 アプリケーションプールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="6f417-146">The application is hosted in an IIS 7.0 application pool.</span></span>  
  
- <span data-ttu-id="6f417-147">IIS 7.0 は統合モードで実行されています。</span><span class="sxs-lookup"><span data-stu-id="6f417-147">IIS 7.0 is running in Integrated mode.</span></span>  
  
- <span data-ttu-id="6f417-148">アプリケーションで .NET Framework 3.5 SP1 以降のバージョンが使用されています。</span><span class="sxs-lookup"><span data-stu-id="6f417-148">The application is using the .NET Framework 3.5 SP1 or a later version.</span></span>  
  
<span data-ttu-id="6f417-149">この例の値は既定値です。</span><span class="sxs-lookup"><span data-stu-id="6f417-149">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="6f417-150">要素情報</span><span class="sxs-lookup"><span data-stu-id="6f417-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6f417-151">Namespace</span><span class="sxs-lookup"><span data-stu-id="6f417-151">Namespace</span></span>||  
|<span data-ttu-id="6f417-152">[スキーマ名]</span><span class="sxs-lookup"><span data-stu-id="6f417-152">Schema Name</span></span>||  
|<span data-ttu-id="6f417-153">検証ファイル</span><span class="sxs-lookup"><span data-stu-id="6f417-153">Validation File</span></span>||  
|<span data-ttu-id="6f417-154">空にすることができます</span><span class="sxs-lookup"><span data-stu-id="6f417-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="6f417-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f417-155">See also</span></span>

- [<span data-ttu-id="6f417-156">\<system.web> 要素 (Web 設定)</span><span class="sxs-lookup"><span data-stu-id="6f417-156">\<system.web> Element (Web Settings)</span></span>](system-web-element-web-settings.md)
