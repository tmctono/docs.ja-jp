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
ms.openlocfilehash: f0ede5f9dc19e9589afc888e7fcd01785bc1840c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174031"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="b20f1-102">\<sharedListeners> の \<add> 要素</span><span class="sxs-lookup"><span data-stu-id="b20f1-102">\<add> Element for \<sharedListeners></span></span>

<span data-ttu-id="b20f1-103">`sharedListeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b20f1-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="b20f1-104">`sharedListeners`[\<source>](source-element.md)またはが参照できるリスナーのコレクションです [\<trace>](trace-element.md) 。</span><span class="sxs-lookup"><span data-stu-id="b20f1-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="b20f1-105">既定では、コレクション内のリスナー `sharedListeners` はコレクション内に配置されません `Listeners` 。</span><span class="sxs-lookup"><span data-stu-id="b20f1-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="b20f1-106">これらは、またはに名前で追加する必要があり [\<source>](source-element.md) [\<trace>](trace-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="b20f1-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="b20f1-107">実行時にコードでコレクション内のリスナーを取得することはできません `sharedListeners` 。</span><span class="sxs-lookup"><span data-stu-id="b20f1-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="b20f1-108">構文</span><span class="sxs-lookup"><span data-stu-id="b20f1-108">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b20f1-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b20f1-109">Attributes and Elements</span></span>  

 <span data-ttu-id="b20f1-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b20f1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b20f1-111">属性</span><span class="sxs-lookup"><span data-stu-id="b20f1-111">Attributes</span></span>  
  
|<span data-ttu-id="b20f1-112">属性</span><span class="sxs-lookup"><span data-stu-id="b20f1-112">Attribute</span></span>|<span data-ttu-id="b20f1-113">説明</span><span class="sxs-lookup"><span data-stu-id="b20f1-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="b20f1-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="b20f1-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="b20f1-115">共有リスナーをコレクションに追加するために使用されるリスナーの名前を指定し `Listeners` ます。</span><span class="sxs-lookup"><span data-stu-id="b20f1-115">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="b20f1-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="b20f1-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="b20f1-117">リスナーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="b20f1-117">Specifies the type of the listener.</span></span> <span data-ttu-id="b20f1-118">[「完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」で指定した要件を満たす文字列を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b20f1-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="b20f1-119">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="b20f1-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b20f1-120">指定したクラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="b20f1-120">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="b20f1-121">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="b20f1-121">Optional attribute.</span></span><br/><br/><span data-ttu-id="b20f1-122"><xref:System.Diagnostics.TraceOptions>トレース出力に書き込まれるデータを示す1つ以上の列挙メンバーの文字列形式。</span><span class="sxs-lookup"><span data-stu-id="b20f1-122">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="b20f1-123">複数の項目は、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="b20f1-123">Multiple items are separated by commas.</span></span> <span data-ttu-id="b20f1-124">既定値は "None" です。</span><span class="sxs-lookup"><span data-stu-id="b20f1-124">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b20f1-125">子要素</span><span class="sxs-lookup"><span data-stu-id="b20f1-125">Child Elements</span></span>  
  
|<span data-ttu-id="b20f1-126">要素</span><span class="sxs-lookup"><span data-stu-id="b20f1-126">Element</span></span>|<span data-ttu-id="b20f1-127">説明</span><span class="sxs-lookup"><span data-stu-id="b20f1-127">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="b20f1-128">`sharedListeners` コレクションのリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="b20f1-128">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b20f1-129">親要素</span><span class="sxs-lookup"><span data-stu-id="b20f1-129">Parent Elements</span></span>  
  
|<span data-ttu-id="b20f1-130">要素</span><span class="sxs-lookup"><span data-stu-id="b20f1-130">Element</span></span>|<span data-ttu-id="b20f1-131">説明</span><span class="sxs-lookup"><span data-stu-id="b20f1-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b20f1-132">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b20f1-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b20f1-133">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b20f1-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="b20f1-134">任意のソースまたはトレース要素が参照できるリスナーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="b20f1-134">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b20f1-135">解説</span><span class="sxs-lookup"><span data-stu-id="b20f1-135">Remarks</span></span>  

 <span data-ttu-id="b20f1-136">.NET Framework に付属しているリスナークラスは、クラスから派生し <xref:System.Diagnostics.TraceListener> ます。</span><span class="sxs-lookup"><span data-stu-id="b20f1-136">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="b20f1-137">属性の値 `name` は、 `Listeners` トレースまたはトレースソースのコレクションに共有リスナーを追加するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b20f1-137">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="b20f1-138">属性の値は、 `initializeData` 作成するリスナーの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b20f1-138">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="b20f1-139">すべてのトレースリスナーでを指定する必要はありません `initializeData` 。</span><span class="sxs-lookup"><span data-stu-id="b20f1-139">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b20f1-140">属性を使用すると、 `initializeData` "initializeData" 属性が宣言されていないことを示すコンパイラの警告が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="b20f1-140">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="b20f1-141">この警告は、属性を認識しない抽象基本クラスに対して構成設定が検証されるために発生し <xref:System.Diagnostics.TraceListener> `initializeData` ます。</span><span class="sxs-lookup"><span data-stu-id="b20f1-141">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="b20f1-142">通常、パラメーターを受け取るコンストラクターを持つトレースリスナーの実装では、この警告を無視できます。</span><span class="sxs-lookup"><span data-stu-id="b20f1-142">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="b20f1-143">次の表に、.NET Framework に含まれているトレースリスナーとその属性の値を示し `initializeData` ます。</span><span class="sxs-lookup"><span data-stu-id="b20f1-143">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="b20f1-144">トレースリスナークラス</span><span class="sxs-lookup"><span data-stu-id="b20f1-144">Trace listener class</span></span>|<span data-ttu-id="b20f1-145">initializeData 属性値</span><span class="sxs-lookup"><span data-stu-id="b20f1-145">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="b20f1-146">`useErrorStream`コンストラクターの値 <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b20f1-146">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="b20f1-147">`initializeData`トレース出力およびデバッグ出力を標準エラーストリームに書き込むには、属性を "" に設定します `true` 。 `false` 標準出力ストリームに書き込むには、"" に設定します。</span><span class="sxs-lookup"><span data-stu-id="b20f1-147">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="b20f1-148"><xref:System.Diagnostics.DelimitedListTraceListener> が出力を書き込むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="b20f1-148">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="b20f1-149">既存のイベント ログ ソースの名前。</span><span class="sxs-lookup"><span data-stu-id="b20f1-149">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="b20f1-150">が書き込み先となるファイルの名前 <xref:System.Diagnostics.EventSchemaTraceListener> 。</span><span class="sxs-lookup"><span data-stu-id="b20f1-150">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="b20f1-151">が書き込み先となるファイルの名前 <xref:System.Diagnostics.TextWriterTraceListener> 。</span><span class="sxs-lookup"><span data-stu-id="b20f1-151">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="b20f1-152">が書き込み先となるファイルの名前 <xref:System.Diagnostics.XmlWriterTraceListener> 。</span><span class="sxs-lookup"><span data-stu-id="b20f1-152">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="b20f1-153">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="b20f1-153">Configuration File</span></span>  

 <span data-ttu-id="b20f1-154">この要素は、マシン構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b20f1-154">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b20f1-155">例</span><span class="sxs-lookup"><span data-stu-id="b20f1-155">Example</span></span>  

 <span data-ttu-id="b20f1-156">次の例は、要素を使用してをコレクションに追加する方法を示して `<add>` <xref:System.Diagnostics.TextWriterTraceListener> `textListener` `sharedListeners` います。</span><span class="sxs-lookup"><span data-stu-id="b20f1-156">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="b20f1-157">`textListener` は、トレースソースのコレクションに名前によって追加され `Listeners` `TraceSourceApp` ます。</span><span class="sxs-lookup"><span data-stu-id="b20f1-157">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="b20f1-158">リスナーは、 `textListener` トレース出力をファイル myListener .log に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="b20f1-158">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b20f1-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="b20f1-159">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="b20f1-160">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="b20f1-160">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b20f1-161">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="b20f1-161">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
