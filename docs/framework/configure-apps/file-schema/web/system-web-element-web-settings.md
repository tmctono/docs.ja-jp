---
title: <system.web> 要素 (Web 設定)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: c8b01ec217fc1b6b91ccf36c8667922b57f26852
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185588"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="03b11-102">\<system.web> 要素 (Web 設定)</span><span class="sxs-lookup"><span data-stu-id="03b11-102">\<system.web> Element (Web Settings)</span></span>

<span data-ttu-id="03b11-103">ASP.NET ホスティングレイヤーがプロセス全体の動作をどのように管理するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="03b11-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
## <a name="syntax"></a><span data-ttu-id="03b11-104">構文</span><span class="sxs-lookup"><span data-stu-id="03b11-104">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03b11-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="03b11-105">Attributes and Elements</span></span>  

<span data-ttu-id="03b11-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="03b11-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03b11-107">属性</span><span class="sxs-lookup"><span data-stu-id="03b11-107">Attributes</span></span>  

<span data-ttu-id="03b11-108">なし。</span><span class="sxs-lookup"><span data-stu-id="03b11-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03b11-109">子要素</span><span class="sxs-lookup"><span data-stu-id="03b11-109">Child Elements</span></span>  
  
|<span data-ttu-id="03b11-110">要素</span><span class="sxs-lookup"><span data-stu-id="03b11-110">Element</span></span>|<span data-ttu-id="03b11-111">説明</span><span class="sxs-lookup"><span data-stu-id="03b11-111">Description</span></span>|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|<span data-ttu-id="03b11-112">aspnet.config ファイル内の IIS アプリケーションプールの構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="03b11-112">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03b11-113">親要素</span><span class="sxs-lookup"><span data-stu-id="03b11-113">Parent Elements</span></span>  
  
|<span data-ttu-id="03b11-114">要素</span><span class="sxs-lookup"><span data-stu-id="03b11-114">Element</span></span>|<span data-ttu-id="03b11-115">説明</span><span class="sxs-lookup"><span data-stu-id="03b11-115">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="03b11-116">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="03b11-116">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03b11-117">解説</span><span class="sxs-lookup"><span data-stu-id="03b11-117">Remarks</span></span>  

<span data-ttu-id="03b11-118">`system.web`要素とその子 `applicationPool` 要素が .NET FRAMEWORK 3.5 SP1 の .NET Framework に追加されました。</span><span class="sxs-lookup"><span data-stu-id="03b11-118">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="03b11-119">IIS 7.0 以降のバージョンを統合モードで実行すると、この要素の組み合わせによって、ASP.NET がどのようにスレッドを管理し、ASP.NET が IIS アプリケーションプールでホストされている場合の要求をキューに配置するかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="03b11-119">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="03b11-120">IIS 7.0 以降のバージョンをクラシックモードまたは ISAPI モードで実行した場合、これらの設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="03b11-120">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03b11-121">例</span><span class="sxs-lookup"><span data-stu-id="03b11-121">Example</span></span>  

<span data-ttu-id="03b11-122">次の例では、IIS アプリケーションプールで ASP.NET がホストされている場合に、aspnet.config ファイルに ASP.NET プロセス全体の動作を構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="03b11-122">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="03b11-123">この例では、IIS が統合モードで実行されており、アプリケーションが .NET Framework 3.5 SP1 以降のバージョンを使用していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="03b11-123">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="03b11-124">この動作は、.NET Framework 3.5 SP1 より前のバージョンの .NET Framework では発生しません。</span><span class="sxs-lookup"><span data-stu-id="03b11-124">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="03b11-125">この例の値は既定値です。</span><span class="sxs-lookup"><span data-stu-id="03b11-125">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="03b11-126">要素情報</span><span class="sxs-lookup"><span data-stu-id="03b11-126">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="03b11-127">名前空間</span><span class="sxs-lookup"><span data-stu-id="03b11-127">Namespace</span></span>||  
|<span data-ttu-id="03b11-128">スキーマ名</span><span class="sxs-lookup"><span data-stu-id="03b11-128">Schema Name</span></span>||  
|<span data-ttu-id="03b11-129">検証ファイル</span><span class="sxs-lookup"><span data-stu-id="03b11-129">Validation File</span></span>||  
|<span data-ttu-id="03b11-130">空にすることができます</span><span class="sxs-lookup"><span data-stu-id="03b11-130">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="03b11-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="03b11-131">See also</span></span>

- [<span data-ttu-id="03b11-132">\<applicationPool> 要素 (Web 設定)</span><span class="sxs-lookup"><span data-stu-id="03b11-132">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
