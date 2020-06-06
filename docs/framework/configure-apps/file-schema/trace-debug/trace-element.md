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
ms.openlocfilehash: 7d8a989219d84e8604e767456c84c0092bc73b22
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153167"
---
# <a name="trace-element"></a><span data-ttu-id="90ad6-102">\<trace> 要素</span><span class="sxs-lookup"><span data-stu-id="90ad6-102">\<trace> Element</span></span>
<span data-ttu-id="90ad6-103">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="90ad6-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**  
  
## <a name="syntax"></a><span data-ttu-id="90ad6-104">構文</span><span class="sxs-lookup"><span data-stu-id="90ad6-104">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90ad6-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="90ad6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="90ad6-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="90ad6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90ad6-107">属性</span><span class="sxs-lookup"><span data-stu-id="90ad6-107">Attributes</span></span>  
  
|<span data-ttu-id="90ad6-108">属性</span><span class="sxs-lookup"><span data-stu-id="90ad6-108">Attribute</span></span>|<span data-ttu-id="90ad6-109">説明</span><span class="sxs-lookup"><span data-stu-id="90ad6-109">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="90ad6-110">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="90ad6-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="90ad6-111">書き込み操作が行われるたびに、トレースリスナーが出力バッファーを自動的にフラッシュするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="90ad6-111">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="90ad6-112">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="90ad6-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="90ad6-113">インデントするスペースの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="90ad6-113">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="90ad6-114">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="90ad6-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="90ad6-115">グローバルロックを使用する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="90ad6-115">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="90ad6-116">autoflush 属性</span><span class="sxs-lookup"><span data-stu-id="90ad6-116">autoflush Attribute</span></span>  
  
|<span data-ttu-id="90ad6-117">値</span><span class="sxs-lookup"><span data-stu-id="90ad6-117">Value</span></span>|<span data-ttu-id="90ad6-118">Description</span><span class="sxs-lookup"><span data-stu-id="90ad6-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="90ad6-119">では、出力バッファーは自動的にはフラッシュされません。</span><span class="sxs-lookup"><span data-stu-id="90ad6-119">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="90ad6-120">既定値です。</span><span class="sxs-lookup"><span data-stu-id="90ad6-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="90ad6-121">出力バッファーを自動的にフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="90ad6-121">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="90ad6-122">useGlobalLock 属性</span><span class="sxs-lookup"><span data-stu-id="90ad6-122">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="90ad6-123">値</span><span class="sxs-lookup"><span data-stu-id="90ad6-123">Value</span></span>|<span data-ttu-id="90ad6-124">Description</span><span class="sxs-lookup"><span data-stu-id="90ad6-124">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="90ad6-125">リスナーがスレッドセーフである場合、はグローバルロックを使用しません。それ以外の場合、はグローバルロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="90ad6-125">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="90ad6-126">は、リスナーがスレッドセーフかどうかに関係なく、グローバルロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="90ad6-126">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="90ad6-127">既定値です。</span><span class="sxs-lookup"><span data-stu-id="90ad6-127">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90ad6-128">子要素</span><span class="sxs-lookup"><span data-stu-id="90ad6-128">Child Elements</span></span>  
  
|<span data-ttu-id="90ad6-129">要素</span><span class="sxs-lookup"><span data-stu-id="90ad6-129">Element</span></span>|<span data-ttu-id="90ad6-130">Description</span><span class="sxs-lookup"><span data-stu-id="90ad6-130">Description</span></span>|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-trace.md)|<span data-ttu-id="90ad6-131">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="90ad6-131">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="90ad6-132">親要素</span><span class="sxs-lookup"><span data-stu-id="90ad6-132">Parent Elements</span></span>  
  
|<span data-ttu-id="90ad6-133">要素</span><span class="sxs-lookup"><span data-stu-id="90ad6-133">Element</span></span>|<span data-ttu-id="90ad6-134">Description</span><span class="sxs-lookup"><span data-stu-id="90ad6-134">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="90ad6-135">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="90ad6-135">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="90ad6-136">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="90ad6-136">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="90ad6-137">例</span><span class="sxs-lookup"><span data-stu-id="90ad6-137">Example</span></span>  
 <span data-ttu-id="90ad6-138">次の例では、要素を使用して、リスナーをコレクションに追加する方法を示し `<trace>` `MyListener` `Listeners` ます。</span><span class="sxs-lookup"><span data-stu-id="90ad6-138">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="90ad6-139">`MyListener`という名前のファイルを作成 `MyListener.log` し、出力をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="90ad6-139">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="90ad6-140">`useGlobalLock`属性がに設定されてい `false` ます。これにより、トレースリスナーがスレッドセーフである場合は、グローバルロックが使用されません。</span><span class="sxs-lookup"><span data-stu-id="90ad6-140">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="90ad6-141">`autoflush`属性はに設定されます `true` 。これにより、メソッドが呼び出されているかどうかに関係なく、トレースリスナーはファイルに書き込みを <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> 行います。</span><span class="sxs-lookup"><span data-stu-id="90ad6-141">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="90ad6-142">`indentsize`属性が 0 (ゼロ) に設定されている場合、メソッドの呼び出し時にリスナーによって0個の空白がインデントされ <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="90ad6-142">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="90ad6-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="90ad6-143">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="90ad6-144">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="90ad6-144">Trace and Debug Settings Schema</span></span>](index.md)
