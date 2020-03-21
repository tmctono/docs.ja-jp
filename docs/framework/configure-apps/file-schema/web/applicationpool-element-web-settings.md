---
title: <applicationPool> 要素 (Web 設定)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 6feaa801610fa0ffbbf47575f25aff29fa46a66c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152855"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="7ecb9-102">\<applicationPool> 要素 (Web 設定)</span><span class="sxs-lookup"><span data-stu-id="7ecb9-102">\<applicationPool> Element (Web Settings)</span></span>
<span data-ttu-id="7ecb9-103">ASP.NET アプリケーションが IIS 7.0 以降のバージョンで統合モードで実行されている場合に、プロセス全体の動作を管理するためにASP.NETによって使用される構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on IIS 7.0 or a later version.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7ecb9-104">この要素とサポートする機能は、ASP.NET アプリケーションが IIS 7.0 以降のバージョンでホストされている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-104">This element and the feature it supports only work if your ASP.NET application is hosted on IIS 7.0 or later versions.</span></span>  
  
[<span data-ttu-id="7ecb9-105">**\<構成>**</span><span class="sxs-lookup"><span data-stu-id="7ecb9-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="7ecb9-106">&nbsp;&nbsp;[**\<ウェブ>**](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7ecb9-106">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="7ecb9-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<アプリケーションプール>**</span><span class="sxs-lookup"><span data-stu-id="7ecb9-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ecb9-108">構文</span><span class="sxs-lookup"><span data-stu-id="7ecb9-108">Syntax</span></span>  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ecb9-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7ecb9-109">Attributes and Elements</span></span>  

<span data-ttu-id="7ecb9-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ecb9-111">属性</span><span class="sxs-lookup"><span data-stu-id="7ecb9-111">Attributes</span></span>  
  
|<span data-ttu-id="7ecb9-112">属性</span><span class="sxs-lookup"><span data-stu-id="7ecb9-112">Attribute</span></span>|<span data-ttu-id="7ecb9-113">説明</span><span class="sxs-lookup"><span data-stu-id="7ecb9-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="7ecb9-114">CPU ごとに許可ASP.NET同時要求の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="7ecb9-115">各 CPU のアプリケーション プールで実行できる同時スレッドの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="7ecb9-116">これにより、要求を処理するために CPU ごとに使用できるマネージ スレッドの数を制限できるため、ASP.NET同時実行を制御する別の方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="7ecb9-117">既定では、この設定は 0 で、ASP.NETは、CPU ごとに作成できるスレッドの数を制限しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="7ecb9-118">1 つのプロセスでASP.NETにキューに入れることができる要求の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="7ecb9-119">1 つのアプリケーション プールで複数のASP.NETアプリケーションを実行する場合、アプリケーション プール内の任意のアプリケーションに対して行われる要求の累積セットは、この設定の対象となります。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ecb9-120">子要素</span><span class="sxs-lookup"><span data-stu-id="7ecb9-120">Child Elements</span></span>  
 <span data-ttu-id="7ecb9-121">[なし] :</span><span class="sxs-lookup"><span data-stu-id="7ecb9-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ecb9-122">親要素</span><span class="sxs-lookup"><span data-stu-id="7ecb9-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7ecb9-123">要素</span><span class="sxs-lookup"><span data-stu-id="7ecb9-123">Element</span></span>|<span data-ttu-id="7ecb9-124">説明</span><span class="sxs-lookup"><span data-stu-id="7ecb9-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ecb9-125">\<ウェブ></span><span class="sxs-lookup"><span data-stu-id="7ecb9-125">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="7ecb9-126">ASP.NETがホスト アプリケーションと対話する方法に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ecb9-127">解説</span><span class="sxs-lookup"><span data-stu-id="7ecb9-127">Remarks</span></span>  

<span data-ttu-id="7ecb9-128">統合モードで IIS 7.0 以降のバージョンを実行する場合、この要素の組み合わせにより、アプリケーションが IIS アプリケーション プールでホストされている場合に、ASP.NETがスレッドを管理し、要求をキューに格納する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-128">When you run IIS 7.0 or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="7ecb9-129">IIS 6 を実行する場合、またはクラシック モードまたは ISAPI モードで IIS 7.0 を実行した場合、これらの設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-129">If you run IIS 6 or you run IIS 7.0 in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
<span data-ttu-id="7ecb9-130">設定`applicationPool`は、.NET Framework の特定のバージョンで実行されるすべてのアプリケーション プールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="7ecb9-131">設定は、aspnet.config ファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="7ecb9-132">このファイルのバージョンは、.NET Framework のバージョン 2.0 および 4.0 です。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="7ecb9-133">(.NET Framework のバージョン 3.0 および 3.5 は、aspnet.config ファイルをバージョン 2.0 と共有します。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7ecb9-134">Windows 7 で IIS 7.0 を実行する場合は、アプリケーション プールごとに個別の aspnet.config ファイルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-134">If you run IIS 7.0 on Windows 7, you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="7ecb9-135">これにより、各アプリケーション プールのスレッドのパフォーマンスを調整できます。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
<span data-ttu-id="7ecb9-136">この設定`maxConcurrentRequestsPerCPU`では、.NET Framework 4 の既定の設定である "5000" は、実際に CPU あたり 5000 以上の要求がある場合を除き、ASP.NETによって制御される要求調整を効果的にオフにします。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the .NET Framework 4 effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="7ecb9-137">既定の設定は、代わりに、CPU ごとの同時実行を自動的に管理する CLR スレッド プールに依存します。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="7ecb9-138">非同期要求処理を広範に使用するアプリケーション、またはネットワーク I/O でブロックされた長時間の要求が多数あるアプリケーションは、.NET Framework 4 の既定の制限の増加により、恩恵を受けます。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the .NET Framework 4.</span></span> <span data-ttu-id="7ecb9-139">ゼロ`maxConcurrentRequestsPerCPU`に設定すると、ASP.NET要求を処理するためのマネージ スレッドの使用が無効になります。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="7ecb9-140">アプリケーションが IIS アプリケーション プールで実行されている場合、要求は IIS I/O スレッド上にとどまり、したがって同時実行制御は IIS スレッド設定によって制限されます。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
<span data-ttu-id="7ecb9-141">この`requestQueueLimit`設定は、ASP.NETアプリケーションの`requestQueueLimit`Web.config ファイルで設定される[processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100))要素の属性と同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="7ecb9-142">ただし、aspnet.config ファイルの`requestQueueLimit`設定は、Web.config ファイルの`requestQueueLimit`設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="7ecb9-143">つまり、両方の属性が設定されている場合 (既定では true)、aspnet.config ファイルの`requestQueueLimit`設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ecb9-144">例</span><span class="sxs-lookup"><span data-stu-id="7ecb9-144">Example</span></span>  

<span data-ttu-id="7ecb9-145">次の例は、次の状況で aspnet.config ファイルでプロセス全体の動作 ASP.NETを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
- <span data-ttu-id="7ecb9-146">アプリケーションは IIS 7.0 アプリケーション プールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-146">The application is hosted in an IIS 7.0 application pool.</span></span>  
  
- <span data-ttu-id="7ecb9-147">IIS 7.0 は統合モードで実行されています。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-147">IIS 7.0 is running in Integrated mode.</span></span>  
  
- <span data-ttu-id="7ecb9-148">アプリケーションは、.NET Framework 3.5 SP1 またはそれ以降のバージョンを使用しています。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-148">The application is using the .NET Framework 3.5 SP1 or a later version.</span></span>  
  
<span data-ttu-id="7ecb9-149">この例の値はデフォルト値です。</span><span class="sxs-lookup"><span data-stu-id="7ecb9-149">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="7ecb9-150">要素情報</span><span class="sxs-lookup"><span data-stu-id="7ecb9-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ecb9-151">名前空間</span><span class="sxs-lookup"><span data-stu-id="7ecb9-151">Namespace</span></span>||  
|<span data-ttu-id="7ecb9-152">スキーマ名</span><span class="sxs-lookup"><span data-stu-id="7ecb9-152">Schema Name</span></span>||  
|<span data-ttu-id="7ecb9-153">検証ファイル</span><span class="sxs-lookup"><span data-stu-id="7ecb9-153">Validation File</span></span>||  
|<span data-ttu-id="7ecb9-154">空にできる</span><span class="sxs-lookup"><span data-stu-id="7ecb9-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="7ecb9-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ecb9-155">See also</span></span>

- [<span data-ttu-id="7ecb9-156">\<要素> (Web 設定)</span><span class="sxs-lookup"><span data-stu-id="7ecb9-156">\<system.web> Element (Web Settings)</span></span>](system-web-element-web-settings.md)
