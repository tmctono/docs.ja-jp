---
title: <trace> の <listeners> の <add> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: eb3e9cf4a6d138998cfde865cda8ed4146be26d0
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088984"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="ba963-102">\<リスナー > の > 要素を追加 \<\<トレース ></span><span class="sxs-lookup"><span data-stu-id="ba963-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="ba963-103">リスナーを**リスナー**コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="ba963-103">Adds a listener to the **Listeners** collection.</span></span>  

<span data-ttu-id="ba963-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ba963-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ba963-105">&nbsp;&nbsp;[ **\<** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="ba963-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="ba963-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**トレース >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="ba963-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="ba963-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**リスナー >** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="ba963-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="ba963-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**追加 >**</span><span class="sxs-lookup"><span data-stu-id="ba963-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ba963-109">構文</span><span class="sxs-lookup"><span data-stu-id="ba963-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba963-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ba963-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ba963-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba963-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba963-112">属性</span><span class="sxs-lookup"><span data-stu-id="ba963-112">Attributes</span></span>  
  
|<span data-ttu-id="ba963-113">属性</span><span class="sxs-lookup"><span data-stu-id="ba963-113">Attribute</span></span>|<span data-ttu-id="ba963-114">説明</span><span class="sxs-lookup"><span data-stu-id="ba963-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba963-115">**type**</span><span class="sxs-lookup"><span data-stu-id="ba963-115">**type**</span></span>|<span data-ttu-id="ba963-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="ba963-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="ba963-117">リスナーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="ba963-117">Specifies the type of the listener.</span></span> <span data-ttu-id="ba963-118">[「完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」で指定した要件を満たす文字列を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba963-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="ba963-119">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="ba963-119">**initializeData**</span></span>|<span data-ttu-id="ba963-120">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="ba963-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ba963-121">指定したクラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="ba963-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="ba963-122">**name**</span><span class="sxs-lookup"><span data-stu-id="ba963-122">**name**</span></span>|<span data-ttu-id="ba963-123">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="ba963-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ba963-124">リスナーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ba963-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba963-125">子要素</span><span class="sxs-lookup"><span data-stu-id="ba963-125">Child Elements</span></span>  
  
|<span data-ttu-id="ba963-126">要素</span><span class="sxs-lookup"><span data-stu-id="ba963-126">Element</span></span>|<span data-ttu-id="ba963-127">説明</span><span class="sxs-lookup"><span data-stu-id="ba963-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba963-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="ba963-128">\<filter></span></span>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="ba963-129">トレースの `Listeners` コレクション内のリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="ba963-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba963-130">親要素</span><span class="sxs-lookup"><span data-stu-id="ba963-130">Parent Elements</span></span>  
  
|<span data-ttu-id="ba963-131">要素</span><span class="sxs-lookup"><span data-stu-id="ba963-131">Element</span></span>|<span data-ttu-id="ba963-132">説明</span><span class="sxs-lookup"><span data-stu-id="ba963-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ba963-133">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="ba963-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="ba963-134">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ba963-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="ba963-135">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="ba963-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ba963-136">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="ba963-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="ba963-137">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="ba963-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba963-138">Remarks</span><span class="sxs-lookup"><span data-stu-id="ba963-138">Remarks</span></span>  
 <span data-ttu-id="ba963-139"><xref:System.Diagnostics.Debug> クラスと <xref:System.Diagnostics.Trace> クラスは、同じ**Listeners**コレクションを共有します。</span><span class="sxs-lookup"><span data-stu-id="ba963-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="ba963-140">これらのクラスのいずれかのコレクションにリスナーオブジェクトを追加すると、他のクラスは同じリスナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ba963-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="ba963-141">リスナークラスは、<xref:System.Diagnostics.TraceListener>から派生します。</span><span class="sxs-lookup"><span data-stu-id="ba963-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="ba963-142">トレースリスナーの `name` 属性を指定しない場合、トレースリスナーの <xref:System.Diagnostics.TraceListener.Name%2A> は既定で空の文字列 ("") になります。</span><span class="sxs-lookup"><span data-stu-id="ba963-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="ba963-143">アプリケーションにリスナーが1つしかない場合は、名前を指定せずにリスナーを追加し、名前に空の文字列を指定することで削除できます。</span><span class="sxs-lookup"><span data-stu-id="ba963-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="ba963-144">ただし、アプリケーションに複数のリスナーがある場合は、トレースリスナーごとに一意の名前を指定する必要があります。これにより、<xref:System.Diagnostics.Debug.Listeners%2A> コレクションと <xref:System.Diagnostics.Trace.Listeners%2A> コレクション内の個々のトレースリスナーを識別して管理できます。</span><span class="sxs-lookup"><span data-stu-id="ba963-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba963-145">同じ種類の複数のトレースリスナーを同じ名前で追加すると、その型と名前のトレースリスナーが1つだけ `Listeners` コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ba963-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="ba963-146">ただし、複数の同じリスナーを `Listeners` コレクションにプログラムで追加することができます。</span><span class="sxs-lookup"><span data-stu-id="ba963-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="ba963-147">**Initializedata**属性の値は、作成するリスナーの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ba963-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="ba963-148">すべてのトレースリスナーで**Initializedata**を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ba963-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba963-149">`initializeData` 属性を使用すると、"initializeData" 属性が宣言されていないことを示すコンパイラの警告が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ba963-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="ba963-150">この警告は、`initializeData` 属性を認識しない抽象基本クラス <xref:System.Diagnostics.TraceListener>に対して構成設定が検証されるために発生します。</span><span class="sxs-lookup"><span data-stu-id="ba963-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="ba963-151">通常、パラメーターを受け取るコンストラクターを持つトレースリスナーの実装では、この警告を無視できます。</span><span class="sxs-lookup"><span data-stu-id="ba963-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="ba963-152">次の表に、.NET Framework に含まれるトレースリスナーと、 **Initializedata**属性の値について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba963-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="ba963-153">トレースリスナークラス</span><span class="sxs-lookup"><span data-stu-id="ba963-153">Trace listener class</span></span>|<span data-ttu-id="ba963-154">initializeData 属性値</span><span class="sxs-lookup"><span data-stu-id="ba963-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ba963-155"><xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> コンストラクターの `useErrorStream` 値。</span><span class="sxs-lookup"><span data-stu-id="ba963-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="ba963-156">`initializeData` 属性を "`true`" に設定して、トレース出力とデバッグ出力を <xref:System.Console.Error%2A?displayProperty=nameWithType>に書き込みます。 "`false`" を <xref:System.Console.Out%2A?displayProperty=nameWithType>に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="ba963-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ba963-157"><xref:System.Diagnostics.DelimitedListTraceListener> が書き込むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="ba963-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ba963-158">既存のイベントログソースの名前。</span><span class="sxs-lookup"><span data-stu-id="ba963-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ba963-159"><xref:System.Diagnostics.EventSchemaTraceListener> が書き込むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="ba963-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ba963-160"><xref:System.Diagnostics.TextWriterTraceListener> が書き込むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="ba963-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ba963-161"><xref:System.Diagnostics.XmlWriterTraceListener> が書き込むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="ba963-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ba963-162">例</span><span class="sxs-lookup"><span data-stu-id="ba963-162">Example</span></span>  
 <span data-ttu-id="ba963-163">次の例では、> 要素を追加して**リスナーコレクションにリスナー `MyListener`** および `MyEventListener` を追加 **\<** 方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ba963-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="ba963-164">`MyListener` によって `MyListener.log` というファイルが作成され、出力がファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="ba963-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="ba963-165">`MyEventListener` は、イベントログにエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="ba963-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba963-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba963-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="ba963-167">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="ba963-167">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ba963-168">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="ba963-168">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
