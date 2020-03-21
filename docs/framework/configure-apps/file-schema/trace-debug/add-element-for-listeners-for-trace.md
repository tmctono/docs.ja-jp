---
title: <add>の<listeners>要素<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: c64673908dc9afe67d97c08f93e5b9d9533bd34d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153673"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="25e3d-102">\<トレース>に>\<リスナーの>要素\<を追加します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="25e3d-103">**リスナー**をリスナー コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-103">Adds a listener to the **Listeners** collection.</span></span>  

<span data-ttu-id="25e3d-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="25e3d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="25e3d-105">&nbsp;&nbsp;[**\<診断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="25e3d-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="25e3d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<トレース>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="25e3d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="25e3d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<リスナー>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="25e3d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="25e3d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>を追加する**</span><span class="sxs-lookup"><span data-stu-id="25e3d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="25e3d-109">構文</span><span class="sxs-lookup"><span data-stu-id="25e3d-109">Syntax</span></span>  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25e3d-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="25e3d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="25e3d-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25e3d-112">属性</span><span class="sxs-lookup"><span data-stu-id="25e3d-112">Attributes</span></span>  
  
|<span data-ttu-id="25e3d-113">属性</span><span class="sxs-lookup"><span data-stu-id="25e3d-113">Attribute</span></span>|<span data-ttu-id="25e3d-114">説明</span><span class="sxs-lookup"><span data-stu-id="25e3d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="25e3d-115">**型**</span><span class="sxs-lookup"><span data-stu-id="25e3d-115">**type**</span></span>|<span data-ttu-id="25e3d-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="25e3d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="25e3d-117">リスナーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-117">Specifies the type of the listener.</span></span> <span data-ttu-id="25e3d-118">[「完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」で指定した要件を満たす文字列を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25e3d-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="25e3d-119">**初期化データ**</span><span class="sxs-lookup"><span data-stu-id="25e3d-119">**initializeData**</span></span>|<span data-ttu-id="25e3d-120">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="25e3d-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="25e3d-121">指定したクラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="25e3d-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="25e3d-122">**name**</span><span class="sxs-lookup"><span data-stu-id="25e3d-122">**name**</span></span>|<span data-ttu-id="25e3d-123">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="25e3d-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="25e3d-124">リスナーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25e3d-125">子要素</span><span class="sxs-lookup"><span data-stu-id="25e3d-125">Child Elements</span></span>  
  
|<span data-ttu-id="25e3d-126">要素</span><span class="sxs-lookup"><span data-stu-id="25e3d-126">Element</span></span>|<span data-ttu-id="25e3d-127">説明</span><span class="sxs-lookup"><span data-stu-id="25e3d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25e3d-128">\<フィルター></span><span class="sxs-lookup"><span data-stu-id="25e3d-128">\<filter></span></span>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="25e3d-129">`Listeners`コレクション内のトレースのリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="25e3d-130">親要素</span><span class="sxs-lookup"><span data-stu-id="25e3d-130">Parent Elements</span></span>  
  
|<span data-ttu-id="25e3d-131">要素</span><span class="sxs-lookup"><span data-stu-id="25e3d-131">Element</span></span>|<span data-ttu-id="25e3d-132">説明</span><span class="sxs-lookup"><span data-stu-id="25e3d-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="25e3d-133">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="25e3d-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="25e3d-134">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="25e3d-135">リスナーは、トレース出力を適切なターゲットに送ります。</span><span class="sxs-lookup"><span data-stu-id="25e3d-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="25e3d-136">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="25e3d-137">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25e3d-138">解説</span><span class="sxs-lookup"><span data-stu-id="25e3d-138">Remarks</span></span>  
 <span data-ttu-id="25e3d-139">と<xref:System.Diagnostics.Debug><xref:System.Diagnostics.Trace>クラスは同じ**Listeners**コレクションを共有します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="25e3d-140">これらのクラスの 1 つでリスナー オブジェクトをコレクションに追加すると、もう一方のクラスは同じリスナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="25e3d-141">リスナー クラスは から<xref:System.Diagnostics.TraceListener>派生します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="25e3d-142">トレース リスナーの属性を`name`指定しない場合、トレース リスナー<xref:System.Diagnostics.TraceListener.Name%2A>の既定のは空の文字列 ("") になります。</span><span class="sxs-lookup"><span data-stu-id="25e3d-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="25e3d-143">アプリケーションにリスナーが 1 つしかない場合は、名前を指定せずにリスナーを追加し、名前に空の文字列を指定して削除できます。</span><span class="sxs-lookup"><span data-stu-id="25e3d-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="25e3d-144">ただし、アプリケーションに複数のリスナーがある場合は、トレース リスナーごとに一意の名前を<xref:System.Diagnostics.Debug.Listeners%2A><xref:System.Diagnostics.Trace.Listeners%2A>指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25e3d-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25e3d-145">同じタイプの複数のトレース リスナーを同じ名前で追加すると、その型と名前のトレース リスナーが 1 つだけ`Listeners`コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="25e3d-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="25e3d-146">ただし、プログラムによって複数の同一のリスナーをコレクション`Listeners`に追加できます。</span><span class="sxs-lookup"><span data-stu-id="25e3d-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="25e3d-147">**initializeData**属性の値は、作成するリスナーのタイプによって異なります。</span><span class="sxs-lookup"><span data-stu-id="25e3d-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="25e3d-148">すべてのトレース リスナーで**initializeData**を指定する必要があるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="25e3d-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25e3d-149">属性を`initializeData`使用すると、コンパイラが "'initializeData' 属性が宣言されていません。</span><span class="sxs-lookup"><span data-stu-id="25e3d-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="25e3d-150">この警告は、属性を認識しない抽象基本クラス<xref:System.Diagnostics.TraceListener>に対して構成設定が検証されるために発生`initializeData`します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="25e3d-151">通常、パラメーターを受け取るコンストラクターを持つトレース リスナーの実装では、この警告を無視できます。</span><span class="sxs-lookup"><span data-stu-id="25e3d-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="25e3d-152">次の表は、.NET Framework に含まれるトレース リスナーと **、initializeData**属性の値を示しています。</span><span class="sxs-lookup"><span data-stu-id="25e3d-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="25e3d-153">トレース リスナー クラス</span><span class="sxs-lookup"><span data-stu-id="25e3d-153">Trace listener class</span></span>|<span data-ttu-id="25e3d-154">初期化データ属性値</span><span class="sxs-lookup"><span data-stu-id="25e3d-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="25e3d-155">コンストラクター`useErrorStream`の<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>値。</span><span class="sxs-lookup"><span data-stu-id="25e3d-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="25e3d-156">この属性`initializeData`を "`true`" に設定して、トレース<xref:System.Console.Error%2A?displayProperty=nameWithType>出力とデバッグ出力をに書き込みます。"`false`" に<xref:System.Console.Out%2A?displayProperty=nameWithType>書き込むには、</span><span class="sxs-lookup"><span data-stu-id="25e3d-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="25e3d-157"><xref:System.Diagnostics.DelimitedListTraceListener> が出力を書き込むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="25e3d-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="25e3d-158">既存のイベント ログ ソースの名前。</span><span class="sxs-lookup"><span data-stu-id="25e3d-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="25e3d-159">書き込みするファイルの<xref:System.Diagnostics.EventSchemaTraceListener>名前。</span><span class="sxs-lookup"><span data-stu-id="25e3d-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="25e3d-160">書き込みするファイルの<xref:System.Diagnostics.TextWriterTraceListener>名前。</span><span class="sxs-lookup"><span data-stu-id="25e3d-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="25e3d-161">書き込みするファイルの<xref:System.Diagnostics.XmlWriterTraceListener>名前。</span><span class="sxs-lookup"><span data-stu-id="25e3d-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="25e3d-162">例</span><span class="sxs-lookup"><span data-stu-id="25e3d-162">Example</span></span>  
 <span data-ttu-id="25e3d-163">次の例では**\<、>** 要素を追加してリスナーと`MyListener``MyEventListener` **Listeners**コレクションに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="25e3d-164">`MyListener`と呼ばれる`MyListener.log`ファイルを作成し、そのファイルに出力を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="25e3d-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="25e3d-165">`MyEventListener`は、イベント ログにエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="25e3d-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="25e3d-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="25e3d-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="25e3d-167">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="25e3d-167">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="25e3d-168">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="25e3d-168">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
