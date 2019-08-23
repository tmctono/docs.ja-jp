---
title: <sharedListeners> の <add> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: c4b83834fb7aaf64a696b85bd2c8da47cfba2397
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927215"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="2aa2d-102">\<sharedListeners > の > \<要素の追加</span><span class="sxs-lookup"><span data-stu-id="2aa2d-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="2aa2d-103">`sharedListeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="2aa2d-104">`sharedListeners`[任意\<のソース >](source-element.md)または[ \<トレース >](trace-element.md)が参照できるリスナーのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="2aa2d-105">既定では、 `sharedListeners`コレクション内のリスナーは`Listeners`コレクション内に配置されません。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="2aa2d-106">これらのファイルは、 [ \<ソース >](source-element.md)または[ \<トレース >](trace-element.md)に名前で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="2aa2d-107">実行時にコードで`sharedListeners`コレクション内のリスナーを取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  
  
 <span data-ttu-id="2aa2d-108">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2aa2d-108">\<configuration></span></span>  
<span data-ttu-id="2aa2d-109">&nbsp;&nbsp;\<システム診断 ></span><span class="sxs-lookup"><span data-stu-id="2aa2d-109">&nbsp;&nbsp;\<system.diagnostics></span></span>  
<span data-ttu-id="2aa2d-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners > 要素</span><span class="sxs-lookup"><span data-stu-id="2aa2d-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners> Element</span></span>  
<span data-ttu-id="2aa2d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<> の追加</span><span class="sxs-lookup"><span data-stu-id="2aa2d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aa2d-112">構文</span><span class="sxs-lookup"><span data-stu-id="2aa2d-112">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2aa2d-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2aa2d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2aa2d-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2aa2d-115">属性</span><span class="sxs-lookup"><span data-stu-id="2aa2d-115">Attributes</span></span>  
  
|<span data-ttu-id="2aa2d-116">属性</span><span class="sxs-lookup"><span data-stu-id="2aa2d-116">Attribute</span></span>|<span data-ttu-id="2aa2d-117">説明</span><span class="sxs-lookup"><span data-stu-id="2aa2d-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="2aa2d-118">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="2aa2d-119">共有リスナーを`Listeners`コレクションに追加するために使用されるリスナーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="2aa2d-120">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="2aa2d-121">リスナーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-121">Specifies the type of the listener.</span></span> <span data-ttu-id="2aa2d-122">[「完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」で指定した要件を満たす文字列を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="2aa2d-123">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2aa2d-124">指定したクラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="2aa2d-125">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="2aa2d-126">トレース出力に書き込まれるデータ<xref:System.Diagnostics.TraceOptions>を示す1つ以上の列挙メンバーの文字列形式。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="2aa2d-127">複数の項目は、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="2aa2d-128">既定値は "None" です。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2aa2d-129">子要素</span><span class="sxs-lookup"><span data-stu-id="2aa2d-129">Child Elements</span></span>  
  
|<span data-ttu-id="2aa2d-130">要素</span><span class="sxs-lookup"><span data-stu-id="2aa2d-130">Element</span></span>|<span data-ttu-id="2aa2d-131">説明</span><span class="sxs-lookup"><span data-stu-id="2aa2d-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2aa2d-132">\<filter></span><span class="sxs-lookup"><span data-stu-id="2aa2d-132">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="2aa2d-133">`sharedListeners` コレクションのリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2aa2d-134">親要素</span><span class="sxs-lookup"><span data-stu-id="2aa2d-134">Parent Elements</span></span>  
  
|<span data-ttu-id="2aa2d-135">要素</span><span class="sxs-lookup"><span data-stu-id="2aa2d-135">Element</span></span>|<span data-ttu-id="2aa2d-136">説明</span><span class="sxs-lookup"><span data-stu-id="2aa2d-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2aa2d-137">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2aa2d-138">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="2aa2d-139">任意のソースまたはトレース要素が参照できるリスナーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2aa2d-140">Remarks</span><span class="sxs-lookup"><span data-stu-id="2aa2d-140">Remarks</span></span>  
 <span data-ttu-id="2aa2d-141">.NET Framework に付属しているリスナークラスは、 <xref:System.Diagnostics.TraceListener>クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="2aa2d-142">`name`属性の値は、トレースまたはトレースソースの`Listeners`コレクションに共有リスナーを追加するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="2aa2d-143">`initializeData`属性の値は、作成するリスナーの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="2aa2d-144">すべてのトレースリスナーでを指定`initializeData`する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2aa2d-145">`initializeData`属性を使用すると、"initializedata" 属性が宣言されていないことを示すコンパイラの警告が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="2aa2d-146">この警告は、 <xref:System.Diagnostics.TraceListener> `initializeData`属性を認識しない抽象基本クラスに対して構成設定が検証されるために発生します。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="2aa2d-147">通常、パラメーターを受け取るコンストラクターを持つトレースリスナーの実装では、この警告を無視できます。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="2aa2d-148">次の表に、.NET Framework に含まれているトレースリスナーとその`initializeData`属性の値を示します。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="2aa2d-149">トレースリスナークラス</span><span class="sxs-lookup"><span data-stu-id="2aa2d-149">Trace listener class</span></span>|<span data-ttu-id="2aa2d-150">initializeData 属性値</span><span class="sxs-lookup"><span data-stu-id="2aa2d-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="2aa2d-151">コンストラクターの値`useErrorStream` <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="2aa2d-152">トレース出力`initializeData`およびデバッグ出力`true`を標準エラーストリームに書き込むには、属性を "" に設定します`false`。標準出力ストリームに書き込むには、"" に設定します。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="2aa2d-153">が<xref:System.Diagnostics.DelimitedListTraceListener>書き込むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2aa2d-154">既存のイベントログソースの名前。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2aa2d-155">が<xref:System.Diagnostics.EventSchemaTraceListener>書き込み先となるファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2aa2d-156">が<xref:System.Diagnostics.TextWriterTraceListener>書き込み先となるファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="2aa2d-157">が<xref:System.Diagnostics.XmlWriterTraceListener>書き込み先となるファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="2aa2d-158">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="2aa2d-158">Configuration File</span></span>  
 <span data-ttu-id="2aa2d-159">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aa2d-160">例</span><span class="sxs-lookup"><span data-stu-id="2aa2d-160">Example</span></span>  
 <span data-ttu-id="2aa2d-161">次の例は、要素を`<add>`使用して<xref:System.Diagnostics.TextWriterTraceListener> `textListener`を`sharedListeners`コレクションに追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="2aa2d-162">`textListener`は、トレースソース`Listeners` `TraceSourceApp`のコレクションに名前によって追加されます。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="2aa2d-163">リスナー `textListener`は、トレース出力をファイル mylistener .log に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="2aa2d-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2aa2d-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="2aa2d-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="2aa2d-165">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="2aa2d-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2aa2d-166">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="2aa2d-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
