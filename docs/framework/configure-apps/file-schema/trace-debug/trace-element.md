---
title: <trace> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: fd90d271591a47849b3f70aea50cbe909b6fd613
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920410"
---
# <a name="trace-element"></a><span data-ttu-id="c4121-102">\<トレース > 要素</span><span class="sxs-lookup"><span data-stu-id="c4121-102">\<trace> Element</span></span>
<span data-ttu-id="c4121-103">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="c4121-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="c4121-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c4121-104">\<configuration></span></span>  
<span data-ttu-id="c4121-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="c4121-105">\<system.diagnostics></span></span>  
<span data-ttu-id="c4121-106">\<トレース ></span><span class="sxs-lookup"><span data-stu-id="c4121-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4121-107">構文</span><span class="sxs-lookup"><span data-stu-id="c4121-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4121-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c4121-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c4121-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4121-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4121-110">属性</span><span class="sxs-lookup"><span data-stu-id="c4121-110">Attributes</span></span>  
  
|<span data-ttu-id="c4121-111">属性</span><span class="sxs-lookup"><span data-stu-id="c4121-111">Attribute</span></span>|<span data-ttu-id="c4121-112">説明</span><span class="sxs-lookup"><span data-stu-id="c4121-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="c4121-113">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="c4121-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c4121-114">書き込み操作が行われるたびに、トレースリスナーが出力バッファーを自動的にフラッシュするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4121-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="c4121-115">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="c4121-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c4121-116">インデントするスペースの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4121-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="c4121-117">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="c4121-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c4121-118">グローバルロックを使用する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c4121-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="c4121-119">autoflush 属性</span><span class="sxs-lookup"><span data-stu-id="c4121-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="c4121-120">値</span><span class="sxs-lookup"><span data-stu-id="c4121-120">Value</span></span>|<span data-ttu-id="c4121-121">説明</span><span class="sxs-lookup"><span data-stu-id="c4121-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c4121-122">では、出力バッファーは自動的にはフラッシュされません。</span><span class="sxs-lookup"><span data-stu-id="c4121-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="c4121-123">既定値です。</span><span class="sxs-lookup"><span data-stu-id="c4121-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="c4121-124">出力バッファーを自動的にフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="c4121-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="c4121-125">useGlobalLock 属性</span><span class="sxs-lookup"><span data-stu-id="c4121-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="c4121-126">値</span><span class="sxs-lookup"><span data-stu-id="c4121-126">Value</span></span>|<span data-ttu-id="c4121-127">説明</span><span class="sxs-lookup"><span data-stu-id="c4121-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c4121-128">リスナーがスレッドセーフである場合、はグローバルロックを使用しません。それ以外の場合、はグローバルロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4121-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="c4121-129">は、リスナーがスレッドセーフかどうかに関係なく、グローバルロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4121-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="c4121-130">既定値です。</span><span class="sxs-lookup"><span data-stu-id="c4121-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4121-131">子要素</span><span class="sxs-lookup"><span data-stu-id="c4121-131">Child Elements</span></span>  
  
|<span data-ttu-id="c4121-132">要素</span><span class="sxs-lookup"><span data-stu-id="c4121-132">Element</span></span>|<span data-ttu-id="c4121-133">説明</span><span class="sxs-lookup"><span data-stu-id="c4121-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4121-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="c4121-134">\<listeners></span></span>](listeners-element-for-trace.md)|<span data-ttu-id="c4121-135">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4121-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c4121-136">親要素</span><span class="sxs-lookup"><span data-stu-id="c4121-136">Parent Elements</span></span>  
  
|<span data-ttu-id="c4121-137">要素</span><span class="sxs-lookup"><span data-stu-id="c4121-137">Element</span></span>|<span data-ttu-id="c4121-138">説明</span><span class="sxs-lookup"><span data-stu-id="c4121-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c4121-139">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="c4121-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c4121-140">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4121-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c4121-141">例</span><span class="sxs-lookup"><span data-stu-id="c4121-141">Example</span></span>  
 <span data-ttu-id="c4121-142">次の例では、 `<trace>`要素を使用して、リスナー `MyListener`を`Listeners`コレクションに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c4121-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="c4121-143">`MyListener`という名前`MyListener.log`のファイルを作成し、出力をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="c4121-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="c4121-144">属性がに`false`設定されています。これにより、トレースリスナーがスレッドセーフである場合は、グローバルロックが使用されません。 `useGlobalLock`</span><span class="sxs-lookup"><span data-stu-id="c4121-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="c4121-145">属性はに`true`設定されます。これにより、メソッドが呼び出されて<xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType>いるかどうかに関係なく、トレースリスナーはファイルに書き込みを行います。 `autoflush`</span><span class="sxs-lookup"><span data-stu-id="c4121-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="c4121-146">属性が 0 (ゼロ) に設定されている場合、メソッドの<xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType>呼び出し時にリスナーによって0個の空白がインデントされます。 `indentsize`</span><span class="sxs-lookup"><span data-stu-id="c4121-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4121-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4121-147">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="c4121-148">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="c4121-148">Trace and Debug Settings Schema</span></span>](index.md)
