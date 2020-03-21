---
title: <add>の<listeners>要素<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 883eef32172c5a7f900197995b4c57c3d5a84e19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153686"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="5fdc0-102">\<\<ソース>の\<リスナー>の要素>追加</span><span class="sxs-lookup"><span data-stu-id="5fdc0-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="5fdc0-103">トレース ソースの `Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="5fdc0-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5fdc0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5fdc0-105">&nbsp;&nbsp;[**\<診断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="5fdc0-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="5fdc0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ソース>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="5fdc0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="5fdc0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ソース>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="5fdc0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="5fdc0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<リスナー>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="5fdc0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="5fdc0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>を追加する**</span><span class="sxs-lookup"><span data-stu-id="5fdc0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5fdc0-110">構文</span><span class="sxs-lookup"><span data-stu-id="5fdc0-110">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5fdc0-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5fdc0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5fdc0-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5fdc0-113">属性</span><span class="sxs-lookup"><span data-stu-id="5fdc0-113">Attributes</span></span>  
  
|<span data-ttu-id="5fdc0-114">属性</span><span class="sxs-lookup"><span data-stu-id="5fdc0-114">Attribute</span></span>|<span data-ttu-id="5fdc0-115">説明</span><span class="sxs-lookup"><span data-stu-id="5fdc0-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="5fdc0-116">コレクション内`sharedListeners`のリスナーを参照する場合を除き、必須属性は名前で参照するだけで済みます ([例](#example)を参照)。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="5fdc0-117">リスナーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-117">Specifies the type of the listener.</span></span> <span data-ttu-id="5fdc0-118">[「完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」で指定した要件を満たす文字列を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="5fdc0-119">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5fdc0-120">指定したクラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="5fdc0-121">クラス<xref:System.Configuration.ConfigurationException>に文字列を受け取るコンストラクタがない場合は、A がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="5fdc0-122">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5fdc0-123">リスナーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="5fdc0-124">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5fdc0-125">トレース<xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A>リスナーのプロパティ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="5fdc0-126">[カスタム属性]</span><span class="sxs-lookup"><span data-stu-id="5fdc0-126">[custom attributes]</span></span>|<span data-ttu-id="5fdc0-127">省略可能な属性。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="5fdc0-128">そのリスナーのメソッドによって識別されるリスナー固有の<xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A>属性の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="5fdc0-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>は、クラスに固有の追加属性の例<xref:System.Diagnostics.DelimitedListTraceListener>です。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5fdc0-130">子要素</span><span class="sxs-lookup"><span data-stu-id="5fdc0-130">Child Elements</span></span>  
  
|<span data-ttu-id="5fdc0-131">要素</span><span class="sxs-lookup"><span data-stu-id="5fdc0-131">Element</span></span>|<span data-ttu-id="5fdc0-132">説明</span><span class="sxs-lookup"><span data-stu-id="5fdc0-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5fdc0-133">\<フィルター></span><span class="sxs-lookup"><span data-stu-id="5fdc0-133">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="5fdc0-134">トレース ソースの `Listeners` コレクション内のリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5fdc0-135">親要素</span><span class="sxs-lookup"><span data-stu-id="5fdc0-135">Parent Elements</span></span>  
  
|<span data-ttu-id="5fdc0-136">要素</span><span class="sxs-lookup"><span data-stu-id="5fdc0-136">Element</span></span>|<span data-ttu-id="5fdc0-137">説明</span><span class="sxs-lookup"><span data-stu-id="5fdc0-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5fdc0-138">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="5fdc0-139">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="5fdc0-140">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="5fdc0-141">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="5fdc0-142">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fdc0-143">解説</span><span class="sxs-lookup"><span data-stu-id="5fdc0-143">Remarks</span></span>  
 <span data-ttu-id="5fdc0-144">.NET Framework に付属のリスナー クラスは、<xref:System.Diagnostics.TraceListener>クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="5fdc0-145">トレース リスナーの属性を`name`指定しない場合、トレース リスナー<xref:System.Diagnostics.TraceListener.Name%2A>のプロパティは既定で空の文字列 ("") になります。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="5fdc0-146">アプリケーションにリスナーが 1 つしかない場合は、名前を指定せずにリスナーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="5fdc0-147">ただし、アプリケーションに複数のリスナーがある場合は、トレース リスナーごとに一意の名前を<xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType>指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5fdc0-148">同じタイプの複数のトレース リスナーを同じ名前で追加すると、その型と名前のトレース リスナーが 1 つだけ`Listeners`コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="5fdc0-149">ただし、プログラムによって複数の同一のリスナーをコレクション`Listeners`に追加できます。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="5fdc0-150">属性の値は`initializeData`、作成するリスナーのタイプによって異なります。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="5fdc0-151">すべてのトレース リスナーで を指定`initializeData`する必要があるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5fdc0-152">属性を`initializeData`使用すると、コンパイラが "'initializeData' 属性が宣言されていません。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="5fdc0-153">この警告は、属性を認識しない抽象基本クラス<xref:System.Diagnostics.TraceListener>に対して構成設定が検証されるために発生`initializeData`します。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="5fdc0-154">通常、パラメーターを受け取るコンストラクターを持つトレース リスナーの実装では、この警告を無視できます。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="5fdc0-155">次の表は、.NET Framework に含まれるトレース リスナーとその属性の値を`initializeData`示しています。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="5fdc0-156">トレース リスナー クラス</span><span class="sxs-lookup"><span data-stu-id="5fdc0-156">Trace listener class</span></span>|<span data-ttu-id="5fdc0-157">初期化データ属性値</span><span class="sxs-lookup"><span data-stu-id="5fdc0-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="5fdc0-158">コンストラクター`useErrorStream`の<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>値。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="5fdc0-159">この属性`initializeData`を "`true`" に設定すると、トレース出力とデバッグ出力が標準のエラー ストリームに書き込まれます。標準出力ストリームに`false`書き込むには、"" に設定します。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="5fdc0-160"><xref:System.Diagnostics.DelimitedListTraceListener> が出力を書き込むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="5fdc0-161">既存のイベント ログ ソースの名前。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="5fdc0-162">書き込みするファイルの<xref:System.Diagnostics.EventSchemaTraceListener>名前。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="5fdc0-163">書き込みするファイルの<xref:System.Diagnostics.TextWriterTraceListener>名前。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="5fdc0-164">書き込みするファイルの<xref:System.Diagnostics.XmlWriterTraceListener>名前。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="5fdc0-165">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="5fdc0-165">Configuration File</span></span>  
 <span data-ttu-id="5fdc0-166">この要素は、コンピューター構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fdc0-167">例</span><span class="sxs-lookup"><span data-stu-id="5fdc0-167">Example</span></span>  
 <span data-ttu-id="5fdc0-168">次の例は、要素を`<add>`使用して、トレース ソース`console``TraceSourceApp`の`textListener`リスナーと`Listeners`コレクションを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="5fdc0-169">リスナー`textListener`は、myListener.log ファイルにトレース出力を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="5fdc0-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"
        type="System.Diagnostics.TextWriterTraceListener"
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="5fdc0-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fdc0-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="5fdc0-171">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="5fdc0-171">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5fdc0-172">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="5fdc0-172">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
