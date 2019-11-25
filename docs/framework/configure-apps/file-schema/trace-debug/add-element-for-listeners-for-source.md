---
title: <source> の <listeners> の <add> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: c32205310f9fc451a5a55a943f925ee52f65c8a8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089000"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="58f03-102">\<ソース \<の \<リスナー > の > 要素を追加します</span><span class="sxs-lookup"><span data-stu-id="58f03-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="58f03-103">トレース ソースの `Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="58f03-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="58f03-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="58f03-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="58f03-105">&nbsp;&nbsp;[ **\<** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="58f03-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="58f03-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**ソース**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="58f03-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="58f03-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**ソース >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="58f03-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="58f03-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**リスナー >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="58f03-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="58f03-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**追加 >**</span><span class="sxs-lookup"><span data-stu-id="58f03-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="58f03-110">構文</span><span class="sxs-lookup"><span data-stu-id="58f03-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58f03-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="58f03-111">Attributes and Elements</span></span>  
 <span data-ttu-id="58f03-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="58f03-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58f03-113">属性</span><span class="sxs-lookup"><span data-stu-id="58f03-113">Attributes</span></span>  
  
|<span data-ttu-id="58f03-114">属性</span><span class="sxs-lookup"><span data-stu-id="58f03-114">Attribute</span></span>|<span data-ttu-id="58f03-115">説明</span><span class="sxs-lookup"><span data-stu-id="58f03-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="58f03-116">必須属性。 `sharedListeners` コレクション内のリスナーを参照している場合を除き、名前で参照する必要があります ([例](#example)を参照)。</span><span class="sxs-lookup"><span data-stu-id="58f03-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="58f03-117">リスナーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="58f03-117">Specifies the type of the listener.</span></span> <span data-ttu-id="58f03-118">[「完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」で指定した要件を満たす文字列を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58f03-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="58f03-119">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="58f03-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="58f03-120">指定したクラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="58f03-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="58f03-121">クラスに文字列を受け取るコンストラクターがない場合、<xref:System.Configuration.ConfigurationException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="58f03-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="58f03-122">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="58f03-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="58f03-123">リスナーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="58f03-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="58f03-124">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="58f03-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="58f03-125">トレースリスナーの <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> プロパティ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="58f03-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="58f03-126">[カスタム属性]</span><span class="sxs-lookup"><span data-stu-id="58f03-126">[custom attributes]</span></span>|<span data-ttu-id="58f03-127">省略可能な属性。</span><span class="sxs-lookup"><span data-stu-id="58f03-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="58f03-128">リスナーの <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> メソッドによって識別されるリスナー固有の属性の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="58f03-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="58f03-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> は、<xref:System.Diagnostics.DelimitedListTraceListener> クラスに固有の追加属性の例です。</span><span class="sxs-lookup"><span data-stu-id="58f03-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58f03-130">子要素</span><span class="sxs-lookup"><span data-stu-id="58f03-130">Child Elements</span></span>  
  
|<span data-ttu-id="58f03-131">要素</span><span class="sxs-lookup"><span data-stu-id="58f03-131">Element</span></span>|<span data-ttu-id="58f03-132">説明</span><span class="sxs-lookup"><span data-stu-id="58f03-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58f03-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="58f03-133">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="58f03-134">トレース ソースの `Listeners` コレクション内のリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="58f03-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58f03-135">親要素</span><span class="sxs-lookup"><span data-stu-id="58f03-135">Parent Elements</span></span>  
  
|<span data-ttu-id="58f03-136">要素</span><span class="sxs-lookup"><span data-stu-id="58f03-136">Element</span></span>|<span data-ttu-id="58f03-137">説明</span><span class="sxs-lookup"><span data-stu-id="58f03-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="58f03-138">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="58f03-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="58f03-139">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="58f03-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="58f03-140">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="58f03-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="58f03-141">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="58f03-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="58f03-142">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="58f03-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58f03-143">Remarks</span><span class="sxs-lookup"><span data-stu-id="58f03-143">Remarks</span></span>  
 <span data-ttu-id="58f03-144">.NET Framework に付属しているリスナークラスは、<xref:System.Diagnostics.TraceListener> クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="58f03-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="58f03-145">トレースリスナーの `name` 属性を指定しない場合、トレースリスナーの <xref:System.Diagnostics.TraceListener.Name%2A> プロパティの既定値は空の文字列 ("") になります。</span><span class="sxs-lookup"><span data-stu-id="58f03-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="58f03-146">アプリケーションにリスナーが1つしかない場合は、名前を指定せずに追加することができます。名前に空の文字列を指定することで削除できます。</span><span class="sxs-lookup"><span data-stu-id="58f03-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="58f03-147">ただし、アプリケーションに複数のリスナーがある場合は、トレースリスナーごとに一意の名前を指定する必要があります。これにより、<xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> コレクション内の個々のトレースリスナーを識別および管理できます。</span><span class="sxs-lookup"><span data-stu-id="58f03-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58f03-148">同じ種類の複数のトレースリスナーを同じ名前で追加すると、その型と名前のトレースリスナーが1つだけ `Listeners` コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="58f03-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="58f03-149">ただし、複数の同じリスナーを `Listeners` コレクションにプログラムで追加することができます。</span><span class="sxs-lookup"><span data-stu-id="58f03-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="58f03-150">`initializeData` 属性の値は、作成するリスナーの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="58f03-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="58f03-151">すべてのトレースリスナーで `initializeData`を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="58f03-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58f03-152">`initializeData` 属性を使用すると、"initializeData" 属性が宣言されていないことを示すコンパイラの警告が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="58f03-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="58f03-153">この警告は、`initializeData` 属性を認識しない抽象基本クラス <xref:System.Diagnostics.TraceListener>に対して構成設定が検証されるために発生します。</span><span class="sxs-lookup"><span data-stu-id="58f03-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="58f03-154">通常、パラメーターを受け取るコンストラクターを持つトレースリスナーの実装では、この警告を無視できます。</span><span class="sxs-lookup"><span data-stu-id="58f03-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="58f03-155">次の表に、.NET Framework に含まれているトレースリスナーと、それらの `initializeData` 属性の値を示します。</span><span class="sxs-lookup"><span data-stu-id="58f03-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="58f03-156">トレースリスナークラス</span><span class="sxs-lookup"><span data-stu-id="58f03-156">Trace listener class</span></span>|<span data-ttu-id="58f03-157">initializeData 属性値</span><span class="sxs-lookup"><span data-stu-id="58f03-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="58f03-158"><xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> コンストラクターの `useErrorStream` 値。</span><span class="sxs-lookup"><span data-stu-id="58f03-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="58f03-159">トレース出力とデバッグ出力を標準エラーストリームに書き込むには、`initializeData` 属性を "`true`" に設定します。標準出力ストリームに書き込むには、"`false`" に設定します。</span><span class="sxs-lookup"><span data-stu-id="58f03-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="58f03-160"><xref:System.Diagnostics.DelimitedListTraceListener> が書き込むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="58f03-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="58f03-161">既存のイベントログソースの名前。</span><span class="sxs-lookup"><span data-stu-id="58f03-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="58f03-162"><xref:System.Diagnostics.EventSchemaTraceListener> が書き込むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="58f03-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="58f03-163"><xref:System.Diagnostics.TextWriterTraceListener> が書き込むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="58f03-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="58f03-164"><xref:System.Diagnostics.XmlWriterTraceListener> が書き込むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="58f03-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="58f03-165">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="58f03-165">Configuration File</span></span>  
 <span data-ttu-id="58f03-166">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="58f03-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58f03-167">例</span><span class="sxs-lookup"><span data-stu-id="58f03-167">Example</span></span>  
 <span data-ttu-id="58f03-168">次の例では、`<add>` 要素を使用して、トレースソース `TraceSourceApp`の `Listeners` コレクションにリスナー `console` と `textListener` を追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="58f03-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="58f03-169">`textListener` リスナーは、トレース出力をファイル myListener .log に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="58f03-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="58f03-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="58f03-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="58f03-171">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="58f03-171">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="58f03-172">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="58f03-172">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
