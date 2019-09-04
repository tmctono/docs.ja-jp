---
title: <gcServer> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa03179df1cd2595b4be428106dd3ec10b309317
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252548"
---
# <a name="gcserver-element"></a><span data-ttu-id="f393e-102">\<gcServer > 要素</span><span class="sxs-lookup"><span data-stu-id="f393e-102">\<gcServer> Element</span></span>
<span data-ttu-id="f393e-103">共通言語ランタイムがサーバーのガベージ コレクションを実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f393e-103">Specifies whether the common language runtime runs server garbage collection.</span></span>  
  
<span data-ttu-id="f393e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f393e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f393e-105">&nbsp;&nbsp;[ **\<ランタイム >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="f393e-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="f393e-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<gcServer>**</span><span class="sxs-lookup"><span data-stu-id="f393e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcServer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f393e-107">構文</span><span class="sxs-lookup"><span data-stu-id="f393e-107">Syntax</span></span>  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f393e-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f393e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f393e-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f393e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f393e-110">属性</span><span class="sxs-lookup"><span data-stu-id="f393e-110">Attributes</span></span>  
  
|<span data-ttu-id="f393e-111">属性</span><span class="sxs-lookup"><span data-stu-id="f393e-111">Attribute</span></span>|<span data-ttu-id="f393e-112">説明</span><span class="sxs-lookup"><span data-stu-id="f393e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f393e-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="f393e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f393e-114">ランタイムがサーバーのガベージ コレクションを実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f393e-114">Specifies whether the runtime runs server garbage collection.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f393e-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="f393e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="f393e-116">値</span><span class="sxs-lookup"><span data-stu-id="f393e-116">Value</span></span>|<span data-ttu-id="f393e-117">説明</span><span class="sxs-lookup"><span data-stu-id="f393e-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="f393e-118">サーバーのガベージ コレクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="f393e-118">Does not run server garbage collection.</span></span> <span data-ttu-id="f393e-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="f393e-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="f393e-120">サーバーのガベージ コレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="f393e-120">Runs server garbage collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f393e-121">子要素</span><span class="sxs-lookup"><span data-stu-id="f393e-121">Child Elements</span></span>  
 <span data-ttu-id="f393e-122">なし。</span><span class="sxs-lookup"><span data-stu-id="f393e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f393e-123">親要素</span><span class="sxs-lookup"><span data-stu-id="f393e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f393e-124">要素</span><span class="sxs-lookup"><span data-stu-id="f393e-124">Element</span></span>|<span data-ttu-id="f393e-125">説明</span><span class="sxs-lookup"><span data-stu-id="f393e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f393e-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="f393e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f393e-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f393e-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f393e-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="f393e-128">Remarks</span></span>  
 <span data-ttu-id="f393e-129">共通言語ランタイム (CLR) は、2 種類のガベージ コレクションをサポートしています。1 つはワークステーション ガベージ コレクションで、すべてのシステムで使用できるものです。もう 1 つはサーバー ガベージ コレクションで、マルチプロセッサ システムで使用できるものです。</span><span class="sxs-lookup"><span data-stu-id="f393e-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="f393e-130">`<gcServer>` 要素を使用して、CLR によって実行されるガベージ コレクションの種類を制御します。</span><span class="sxs-lookup"><span data-stu-id="f393e-130">You use the `<gcServer>` element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="f393e-131"><xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> プロパティを使用して、サーバー ガベージ コレクションが有効かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f393e-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>  
  
 <span data-ttu-id="f393e-132">シングル プロセッサ コンピューターの場合、既定のワークステーション ガベージ コレクションが催促のオプションです。</span><span class="sxs-lookup"><span data-stu-id="f393e-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="f393e-133">2 つのプロセッサを搭載するコンピューターで、ワークステーションかサーバーのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f393e-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="f393e-134">3 つ以上のプロセッサでは、サーバー ガベージ コレクションが最速のオプションです。</span><span class="sxs-lookup"><span data-stu-id="f393e-134">Server garbage collection should be the fastest option for more than two processors.</span></span>  
  
 <span data-ttu-id="f393e-135">この要素は、アプリケーション構成ファイルでのみ使用できます。要素がマシン構成ファイルにある場合には無視されます。</span><span class="sxs-lookup"><span data-stu-id="f393e-135">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f393e-136">.NET Framework 4 以前のバージョンでは、サーバー ガベージ コレクションを有効にすると同時実行ガベージ コレクションが使用できません。</span><span class="sxs-lookup"><span data-stu-id="f393e-136">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="f393e-137">.NET Framework 4.5 以降では、サーバーのガベージコレクションは同時に実行されます。</span><span class="sxs-lookup"><span data-stu-id="f393e-137">Starting with the .NET Framework 4.5, server garbage collection is concurrent.</span></span> <span data-ttu-id="f393e-138">非同時サーバーガベージコレクションを使用するには、 `<gcServer>`要素を`true`に`false` [ \<設定し、gcConcurrent > 要素](gcconcurrent-element.md)をに設定します。</span><span class="sxs-lookup"><span data-stu-id="f393e-138">To use non-concurrent server garbage collection, set the `<gcServer>` element to `true` and the [\<gcConcurrent> element](gcconcurrent-element.md) to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f393e-139">例</span><span class="sxs-lookup"><span data-stu-id="f393e-139">Example</span></span>  
 <span data-ttu-id="f393e-140">サーバー ガベージ コレクションを有効にする方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="f393e-140">The following example enables server garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f393e-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="f393e-141">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f393e-142">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f393e-142">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f393e-143">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="f393e-143">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f393e-144">同時実行ガベージコレクションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="f393e-144">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
