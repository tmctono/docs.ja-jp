---
title: < diagnostics > 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: f3b4238a8d7028d47122a420526b38ee4f327332
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926945"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="de59d-102">\<system. diagnostics > 要素</span><span class="sxs-lookup"><span data-stu-id="de59d-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="de59d-103">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="de59d-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="de59d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="de59d-104">\<configuration></span></span>  
<span data-ttu-id="de59d-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="de59d-105">\<system.diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de59d-106">構文</span><span class="sxs-lookup"><span data-stu-id="de59d-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de59d-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="de59d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="de59d-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="de59d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de59d-109">属性</span><span class="sxs-lookup"><span data-stu-id="de59d-109">Attributes</span></span>  
 <span data-ttu-id="de59d-110">なし。</span><span class="sxs-lookup"><span data-stu-id="de59d-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="de59d-111">子要素</span><span class="sxs-lookup"><span data-stu-id="de59d-111">Child Elements</span></span>  
  
|<span data-ttu-id="de59d-112">要素</span><span class="sxs-lookup"><span data-stu-id="de59d-112">Element</span></span>|<span data-ttu-id="de59d-113">説明</span><span class="sxs-lookup"><span data-stu-id="de59d-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de59d-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="de59d-114">\<assert></span></span>](assert-element.md)|<span data-ttu-id="de59d-115"><xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> メソッドの呼び出し時にメッセージ ボックスを表示するかどうかを指定し、メッセージの書き込み先のファイルの名前も指定します。</span><span class="sxs-lookup"><span data-stu-id="de59d-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="de59d-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="de59d-116">\<performanceCounters></span></span>](performancecounters-element.md)|<span data-ttu-id="de59d-117">パフォーマンス カウンターが共有するグローバル メモリのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="de59d-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="de59d-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="de59d-118">\<sharedListeners></span></span>](sharedlisteners-element.md)|<span data-ttu-id="de59d-119">任意の source 要素または trace 要素が参照できるリスナーを含みます。</span><span class="sxs-lookup"><span data-stu-id="de59d-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="de59d-120">共有リスナーとして識別されるリスナーは、名前を指定してソースまたはトレースに追加できます。</span><span class="sxs-lookup"><span data-stu-id="de59d-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="de59d-121">\<sources></span><span class="sxs-lookup"><span data-stu-id="de59d-121">\<sources></span></span>](sources-element.md)|<span data-ttu-id="de59d-122">トレースメッセージを開始するトレースソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="de59d-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="de59d-123">\<switches></span><span class="sxs-lookup"><span data-stu-id="de59d-123">\<switches></span></span>](switches-element.md)|<span data-ttu-id="de59d-124">トレーススイッチと、トレーススイッチが設定されているレベルを格納します。</span><span class="sxs-lookup"><span data-stu-id="de59d-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="de59d-125">\<trace></span><span class="sxs-lookup"><span data-stu-id="de59d-125">\<trace></span></span>](trace-element.md)|<span data-ttu-id="de59d-126">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="de59d-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="de59d-127">親要素</span><span class="sxs-lookup"><span data-stu-id="de59d-127">Parent Elements</span></span>  
  
|<span data-ttu-id="de59d-128">要素</span><span class="sxs-lookup"><span data-stu-id="de59d-128">Element</span></span>|<span data-ttu-id="de59d-129">説明</span><span class="sxs-lookup"><span data-stu-id="de59d-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="de59d-130">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="de59d-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="de59d-131">例</span><span class="sxs-lookup"><span data-stu-id="de59d-131">Example</span></span>  
 <span data-ttu-id="de59d-132">次の例は、トレーススイッチとトレースリスナーを、  **\<システムの診断 >** 要素内に埋め込む方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="de59d-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="de59d-133">トレース`General`スイッチが<xref:System.Diagnostics.TraceLevel>レベルに設定されています。</span><span class="sxs-lookup"><span data-stu-id="de59d-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="de59d-134">トレースリスナー `myListener`は、という`MyListener.log`ファイルを作成し、ファイルに出力を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="de59d-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de59d-135">.NET Framework バージョン 2.0 では、スイッチの値を指定するためにテキストを使用できます。</span><span class="sxs-lookup"><span data-stu-id="de59d-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="de59d-136">たとえば、 `true` `Error`に対してを指定<xref:System.Diagnostics.TraceSwitch>したり、のような列挙値を表すテキストを使用したりできます。<xref:System.Diagnostics.BooleanSwitch></span><span class="sxs-lookup"><span data-stu-id="de59d-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="de59d-137">`<add name="myTraceSwitch" value="Error" />` という行は、`<add name="myTraceSwitch" value="1" />` と同じです。</span><span class="sxs-lookup"><span data-stu-id="de59d-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de59d-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="de59d-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="de59d-139">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="de59d-139">Trace and Debug Settings Schema</span></span>](index.md)
