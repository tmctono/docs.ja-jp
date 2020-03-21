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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153167"
---
# <a name="trace-element"></a><span data-ttu-id="6adcf-102">\<要素>トレース</span><span class="sxs-lookup"><span data-stu-id="6adcf-102">\<trace> Element</span></span>
<span data-ttu-id="6adcf-103">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="6adcf-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[<span data-ttu-id="6adcf-104">**\<構成>**</span><span class="sxs-lookup"><span data-stu-id="6adcf-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="6adcf-105">&nbsp;&nbsp;[**\<診断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="6adcf-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="6adcf-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<トレース>**</span><span class="sxs-lookup"><span data-stu-id="6adcf-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6adcf-107">構文</span><span class="sxs-lookup"><span data-stu-id="6adcf-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6adcf-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6adcf-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6adcf-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6adcf-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6adcf-110">属性</span><span class="sxs-lookup"><span data-stu-id="6adcf-110">Attributes</span></span>  
  
|<span data-ttu-id="6adcf-111">属性</span><span class="sxs-lookup"><span data-stu-id="6adcf-111">Attribute</span></span>|<span data-ttu-id="6adcf-112">説明</span><span class="sxs-lookup"><span data-stu-id="6adcf-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="6adcf-113">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="6adcf-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6adcf-114">トレース リスナーが書き込み操作のたびに出力バッファーを自動的にフラッシュするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6adcf-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="6adcf-115">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="6adcf-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6adcf-116">インデントするスペースの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6adcf-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="6adcf-117">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="6adcf-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6adcf-118">グローバル ロックを使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6adcf-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="6adcf-119">属性の自動フラッシュ</span><span class="sxs-lookup"><span data-stu-id="6adcf-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="6adcf-120">Value</span><span class="sxs-lookup"><span data-stu-id="6adcf-120">Value</span></span>|<span data-ttu-id="6adcf-121">説明</span><span class="sxs-lookup"><span data-stu-id="6adcf-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="6adcf-122">出力バッファーを自動的にフラッシュしません。</span><span class="sxs-lookup"><span data-stu-id="6adcf-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="6adcf-123">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="6adcf-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="6adcf-124">出力バッファーを自動的にフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="6adcf-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="6adcf-125">使用グローバルロック属性</span><span class="sxs-lookup"><span data-stu-id="6adcf-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="6adcf-126">Value</span><span class="sxs-lookup"><span data-stu-id="6adcf-126">Value</span></span>|<span data-ttu-id="6adcf-127">説明</span><span class="sxs-lookup"><span data-stu-id="6adcf-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="6adcf-128">リスナーがスレッド セーフである場合は、グローバル ロックを使用しません。それ以外の場合は、グローバル ロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="6adcf-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="6adcf-129">リスナーがスレッド セーフかどうかに関係なく、グローバル ロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="6adcf-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="6adcf-130">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="6adcf-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6adcf-131">子要素</span><span class="sxs-lookup"><span data-stu-id="6adcf-131">Child Elements</span></span>  
  
|<span data-ttu-id="6adcf-132">要素</span><span class="sxs-lookup"><span data-stu-id="6adcf-132">Element</span></span>|<span data-ttu-id="6adcf-133">説明</span><span class="sxs-lookup"><span data-stu-id="6adcf-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6adcf-134">\<リスナー></span><span class="sxs-lookup"><span data-stu-id="6adcf-134">\<listeners></span></span>](listeners-element-for-trace.md)|<span data-ttu-id="6adcf-135">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="6adcf-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6adcf-136">親要素</span><span class="sxs-lookup"><span data-stu-id="6adcf-136">Parent Elements</span></span>  
  
|<span data-ttu-id="6adcf-137">要素</span><span class="sxs-lookup"><span data-stu-id="6adcf-137">Element</span></span>|<span data-ttu-id="6adcf-138">説明</span><span class="sxs-lookup"><span data-stu-id="6adcf-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6adcf-139">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="6adcf-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="6adcf-140">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="6adcf-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6adcf-141">例</span><span class="sxs-lookup"><span data-stu-id="6adcf-141">Example</span></span>  
 <span data-ttu-id="6adcf-142">要素を使用してリスナー`<trace>``MyListener`をコレクションに追加する方法を次の例`Listeners`に示します。</span><span class="sxs-lookup"><span data-stu-id="6adcf-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="6adcf-143">`MyListener`という名前`MyListener.log`のファイルを作成し、そのファイルに出力を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="6adcf-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="6adcf-144">この`useGlobalLock`属性は に`false`設定され、トレース リスナーがスレッド セーフである場合にグローバル ロックが使用されません。</span><span class="sxs-lookup"><span data-stu-id="6adcf-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="6adcf-145">属性`autoflush`が に`true`設定され、メソッドが呼び出されるかどうかに関係なく、トレース<xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType>リスナーがファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="6adcf-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="6adcf-146">属性`indentsize`が 0 (ゼロ) に設定され、<xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType>メソッドが呼び出されるとリスナーのインデントが 0 になります。</span><span class="sxs-lookup"><span data-stu-id="6adcf-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6adcf-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="6adcf-147">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="6adcf-148">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="6adcf-148">Trace and Debug Settings Schema</span></span>](index.md)
