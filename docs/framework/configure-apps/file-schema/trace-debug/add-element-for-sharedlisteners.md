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
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153608"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="34ff9-102">\<共有リスナー>>\<要素を追加します</span><span class="sxs-lookup"><span data-stu-id="34ff9-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="34ff9-103">`sharedListeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="34ff9-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="34ff9-104">`sharedListeners`は、[\<ソース>](source-element.md)または[\<トレース>](trace-element.md)が参照できるリスナーのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="34ff9-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="34ff9-105">既定では、コレクション内の`sharedListeners`リスナーはコレクションに`Listeners`配置されません。</span><span class="sxs-lookup"><span data-stu-id="34ff9-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="34ff9-106">ソース[\<>](source-element.md)または[\<トレース>](trace-element.md)に名前で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ff9-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="34ff9-107">実行時に、コレクション内のリスナーを`sharedListeners`コードで取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="34ff9-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  

<span data-ttu-id="34ff9-108">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="34ff9-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="34ff9-109">&nbsp;&nbsp;[**\<診断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="34ff9-109">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="34ff9-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<共有リスナー>**](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="34ff9-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>\
<span data-ttu-id="34ff9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>を追加する**</span><span class="sxs-lookup"><span data-stu-id="34ff9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="34ff9-112">構文</span><span class="sxs-lookup"><span data-stu-id="34ff9-112">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34ff9-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="34ff9-113">Attributes and Elements</span></span>  
 <span data-ttu-id="34ff9-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="34ff9-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34ff9-115">属性</span><span class="sxs-lookup"><span data-stu-id="34ff9-115">Attributes</span></span>  
  
|<span data-ttu-id="34ff9-116">属性</span><span class="sxs-lookup"><span data-stu-id="34ff9-116">Attribute</span></span>|<span data-ttu-id="34ff9-117">説明</span><span class="sxs-lookup"><span data-stu-id="34ff9-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="34ff9-118">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="34ff9-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="34ff9-119">共有リスナーをコレクションに追加するために使用されるリスナーの名前を`Listeners`指定します。</span><span class="sxs-lookup"><span data-stu-id="34ff9-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="34ff9-120">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="34ff9-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="34ff9-121">リスナーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="34ff9-121">Specifies the type of the listener.</span></span> <span data-ttu-id="34ff9-122">[「完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」で指定した要件を満たす文字列を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ff9-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="34ff9-123">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="34ff9-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="34ff9-124">指定したクラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="34ff9-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="34ff9-125">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="34ff9-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="34ff9-126">トレース出力に書き込む<xref:System.Diagnostics.TraceOptions>データを示す 1 つ以上の列挙型メンバーの文字列表現。</span><span class="sxs-lookup"><span data-stu-id="34ff9-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="34ff9-127">複数の項目はコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="34ff9-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="34ff9-128">デフォルト値は「なし」です。</span><span class="sxs-lookup"><span data-stu-id="34ff9-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="34ff9-129">子要素</span><span class="sxs-lookup"><span data-stu-id="34ff9-129">Child Elements</span></span>  
  
|<span data-ttu-id="34ff9-130">要素</span><span class="sxs-lookup"><span data-stu-id="34ff9-130">Element</span></span>|<span data-ttu-id="34ff9-131">説明</span><span class="sxs-lookup"><span data-stu-id="34ff9-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34ff9-132">\<フィルター></span><span class="sxs-lookup"><span data-stu-id="34ff9-132">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="34ff9-133">`sharedListeners` コレクションのリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="34ff9-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="34ff9-134">親要素</span><span class="sxs-lookup"><span data-stu-id="34ff9-134">Parent Elements</span></span>  
  
|<span data-ttu-id="34ff9-135">要素</span><span class="sxs-lookup"><span data-stu-id="34ff9-135">Element</span></span>|<span data-ttu-id="34ff9-136">説明</span><span class="sxs-lookup"><span data-stu-id="34ff9-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="34ff9-137">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="34ff9-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="34ff9-138">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="34ff9-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="34ff9-139">任意のソースまたはトレース要素が参照できるリスナーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="34ff9-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34ff9-140">解説</span><span class="sxs-lookup"><span data-stu-id="34ff9-140">Remarks</span></span>  
 <span data-ttu-id="34ff9-141">.NET Framework に付属のリスナー クラスは、<xref:System.Diagnostics.TraceListener>クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="34ff9-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="34ff9-142">この属性の`name`値は、共有リスナーをトレースまたはトレース・ソース`Listeners`のコレクションに追加するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="34ff9-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="34ff9-143">属性の値は`initializeData`、作成するリスナーのタイプによって異なります。</span><span class="sxs-lookup"><span data-stu-id="34ff9-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="34ff9-144">すべてのトレース リスナーで を指定`initializeData`する必要があるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="34ff9-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34ff9-145">属性を`initializeData`使用すると、コンパイラが "'initializeData' 属性が宣言されていません。</span><span class="sxs-lookup"><span data-stu-id="34ff9-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="34ff9-146">この警告は、属性を認識しない抽象基本クラス<xref:System.Diagnostics.TraceListener>に対して構成設定が検証されるために発生`initializeData`します。</span><span class="sxs-lookup"><span data-stu-id="34ff9-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="34ff9-147">通常、パラメーターを受け取るコンストラクターを持つトレース リスナーの実装では、この警告を無視できます。</span><span class="sxs-lookup"><span data-stu-id="34ff9-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="34ff9-148">次の表は、.NET Framework に含まれるトレース リスナーとその属性の値を`initializeData`示しています。</span><span class="sxs-lookup"><span data-stu-id="34ff9-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="34ff9-149">トレース リスナー クラス</span><span class="sxs-lookup"><span data-stu-id="34ff9-149">Trace listener class</span></span>|<span data-ttu-id="34ff9-150">初期化データ属性値</span><span class="sxs-lookup"><span data-stu-id="34ff9-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="34ff9-151">コンストラクター`useErrorStream`の<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>値。</span><span class="sxs-lookup"><span data-stu-id="34ff9-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="34ff9-152">この属性`initializeData`を "`true`" に設定すると、トレース出力とデバッグ出力が標準のエラー ストリームに書き込まれます。標準出力ストリームに`false`書き込むには、"" に設定します。</span><span class="sxs-lookup"><span data-stu-id="34ff9-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="34ff9-153"><xref:System.Diagnostics.DelimitedListTraceListener> が出力を書き込むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="34ff9-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="34ff9-154">既存のイベント ログ ソースの名前。</span><span class="sxs-lookup"><span data-stu-id="34ff9-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="34ff9-155">書き込みするファイルの<xref:System.Diagnostics.EventSchemaTraceListener>名前。</span><span class="sxs-lookup"><span data-stu-id="34ff9-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="34ff9-156">書き込みするファイルの<xref:System.Diagnostics.TextWriterTraceListener>名前。</span><span class="sxs-lookup"><span data-stu-id="34ff9-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="34ff9-157">書き込みするファイルの<xref:System.Diagnostics.XmlWriterTraceListener>名前。</span><span class="sxs-lookup"><span data-stu-id="34ff9-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="34ff9-158">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="34ff9-158">Configuration File</span></span>  
 <span data-ttu-id="34ff9-159">この要素は、コンピューター構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="34ff9-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34ff9-160">例</span><span class="sxs-lookup"><span data-stu-id="34ff9-160">Example</span></span>  
 <span data-ttu-id="34ff9-161">要素`<add>`を使用して コレクションに追加する方法を<xref:System.Diagnostics.TextWriterTraceListener>`textListener`次の`sharedListeners`例に示します。</span><span class="sxs-lookup"><span data-stu-id="34ff9-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="34ff9-162">`textListener`は、トレース ソースの`Listeners`コレクションに名前で追加`TraceSourceApp`されます。</span><span class="sxs-lookup"><span data-stu-id="34ff9-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="34ff9-163">リスナー`textListener`は、myListener.log ファイルにトレース出力を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="34ff9-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="34ff9-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="34ff9-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="34ff9-165">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="34ff9-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="34ff9-166">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="34ff9-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
