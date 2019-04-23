---
title: <source> の <listeners> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: b15a30fb6d356f92312bf33bc1964c7922ba1383
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089654"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="e529b-102">\<リスナー > 要素の\<ソース ></span><span class="sxs-lookup"><span data-stu-id="e529b-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="e529b-103">追加または内のリスナーを削除します、<xref:System.Diagnostics.TraceSource.Listeners%2A>のコレクションを<xref:System.Diagnostics.TraceSource>します。</span><span class="sxs-lookup"><span data-stu-id="e529b-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="e529b-104">ログ、ウィンドウ、またはテキスト ファイルなど、適切なターゲットへのトレース出力をリスナーに指示します。</span><span class="sxs-lookup"><span data-stu-id="e529b-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="e529b-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e529b-105">\<configuration></span></span>  
<span data-ttu-id="e529b-106">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="e529b-106">\<system.diagnostics></span></span>  
<span data-ttu-id="e529b-107">\<ソース ></span><span class="sxs-lookup"><span data-stu-id="e529b-107">\<sources></span></span>  
<span data-ttu-id="e529b-108">\<ソース ></span><span class="sxs-lookup"><span data-stu-id="e529b-108">\<source></span></span>  
<span data-ttu-id="e529b-109">\<リスナー > 要素</span><span class="sxs-lookup"><span data-stu-id="e529b-109">\<listeners> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e529b-110">構文</span><span class="sxs-lookup"><span data-stu-id="e529b-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e529b-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e529b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e529b-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e529b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e529b-113">属性</span><span class="sxs-lookup"><span data-stu-id="e529b-113">Attributes</span></span>  
 <span data-ttu-id="e529b-114">なし。</span><span class="sxs-lookup"><span data-stu-id="e529b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e529b-115">子要素</span><span class="sxs-lookup"><span data-stu-id="e529b-115">Child Elements</span></span>  
  
|<span data-ttu-id="e529b-116">要素</span><span class="sxs-lookup"><span data-stu-id="e529b-116">Element</span></span>|<span data-ttu-id="e529b-117">説明</span><span class="sxs-lookup"><span data-stu-id="e529b-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e529b-118">\<add></span><span class="sxs-lookup"><span data-stu-id="e529b-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|<span data-ttu-id="e529b-119">`Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="e529b-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="e529b-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="e529b-120">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|<span data-ttu-id="e529b-121">リスナーを削除、`Listeners`コレクション。</span><span class="sxs-lookup"><span data-stu-id="e529b-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="e529b-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="e529b-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|<span data-ttu-id="e529b-123">トレース ソースの `Listeners` コレクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="e529b-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e529b-124">親要素</span><span class="sxs-lookup"><span data-stu-id="e529b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e529b-125">要素</span><span class="sxs-lookup"><span data-stu-id="e529b-125">Element</span></span>|<span data-ttu-id="e529b-126">説明</span><span class="sxs-lookup"><span data-stu-id="e529b-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e529b-127">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="e529b-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e529b-128">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="e529b-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="e529b-129">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="e529b-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="e529b-130">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="e529b-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e529b-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="e529b-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="e529b-132">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="e529b-132">Configuration File</span></span>  
 <span data-ttu-id="e529b-133">この要素は、マシン構成ファイル (Machine.config) と、アプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e529b-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e529b-134">例</span><span class="sxs-lookup"><span data-stu-id="e529b-134">Example</span></span>  
 <span data-ttu-id="e529b-135">次の例は、使用する方法を示します、`<listeners>`コンソール トレース リスナーを追加する要素、`mySource`ソースおよび既定のトレース リスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e529b-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e529b-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="e529b-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="e529b-137">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="e529b-137">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="e529b-138">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="e529b-138">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
