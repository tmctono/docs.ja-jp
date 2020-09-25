---
title: <add> のの <listeners> 要素 <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: a5abaffbad986785b8879297883da9614f0a8103
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201695"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="80968-102">\<add> のの \<listeners> 要素 \<source></span><span class="sxs-lookup"><span data-stu-id="80968-102">\<add> Element for \<listeners> for \<source></span></span>

<span data-ttu-id="80968-103">トレース ソースの `Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="80968-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="80968-104">構文</span><span class="sxs-lookup"><span data-stu-id="80968-104">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80968-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="80968-105">Attributes and Elements</span></span>  

 <span data-ttu-id="80968-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="80968-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80968-107">属性</span><span class="sxs-lookup"><span data-stu-id="80968-107">Attributes</span></span>  
  
|<span data-ttu-id="80968-108">属性</span><span class="sxs-lookup"><span data-stu-id="80968-108">Attribute</span></span>|<span data-ttu-id="80968-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="80968-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="80968-110">必須属性。コレクション内のリスナーを参照している場合を除き、 `sharedListeners` 名前で参照する必要があります ( [例](#example)を参照)。</span><span class="sxs-lookup"><span data-stu-id="80968-110">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="80968-111">リスナーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="80968-111">Specifies the type of the listener.</span></span> <span data-ttu-id="80968-112">[「完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」で指定した要件を満たす文字列を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80968-112">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="80968-113">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="80968-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="80968-114">指定したクラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="80968-114">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="80968-115"><xref:System.Configuration.ConfigurationException>クラスに文字列を受け取るコンストラクターがない場合は、がスローされます。</span><span class="sxs-lookup"><span data-stu-id="80968-115">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="80968-116">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="80968-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="80968-117">リスナーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="80968-117">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="80968-118">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="80968-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="80968-119"><xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A>トレースリスナーのプロパティ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="80968-119">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="80968-120">[カスタム属性]</span><span class="sxs-lookup"><span data-stu-id="80968-120">[custom attributes]</span></span>|<span data-ttu-id="80968-121">省略可能な属性。</span><span class="sxs-lookup"><span data-stu-id="80968-121">Optional attributes.</span></span><br /><br /> <span data-ttu-id="80968-122">リスナーのメソッドによって識別されるリスナー固有の属性の値を指定し <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="80968-122">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="80968-123"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> は、クラスに固有の追加属性の例です <xref:System.Diagnostics.DelimitedListTraceListener> 。</span><span class="sxs-lookup"><span data-stu-id="80968-123"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80968-124">子要素</span><span class="sxs-lookup"><span data-stu-id="80968-124">Child Elements</span></span>  
  
|<span data-ttu-id="80968-125">要素</span><span class="sxs-lookup"><span data-stu-id="80968-125">Element</span></span>|<span data-ttu-id="80968-126">説明</span><span class="sxs-lookup"><span data-stu-id="80968-126">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="80968-127">トレース ソースの `Listeners` コレクション内のリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="80968-127">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80968-128">親要素</span><span class="sxs-lookup"><span data-stu-id="80968-128">Parent Elements</span></span>  
  
|<span data-ttu-id="80968-129">要素</span><span class="sxs-lookup"><span data-stu-id="80968-129">Element</span></span>|<span data-ttu-id="80968-130">説明</span><span class="sxs-lookup"><span data-stu-id="80968-130">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="80968-131">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="80968-131">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="80968-132">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="80968-132">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="80968-133">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="80968-133">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="80968-134">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="80968-134">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="80968-135">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="80968-135">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80968-136">解説</span><span class="sxs-lookup"><span data-stu-id="80968-136">Remarks</span></span>  

 <span data-ttu-id="80968-137">.NET Framework に付属しているリスナークラスは、クラスから派生し <xref:System.Diagnostics.TraceListener> ます。</span><span class="sxs-lookup"><span data-stu-id="80968-137">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="80968-138">トレースリスナーの属性を指定しない場合 `name` 、 <xref:System.Diagnostics.TraceListener.Name%2A> トレースリスナーのプロパティの既定値は空の文字列 ("") になります。</span><span class="sxs-lookup"><span data-stu-id="80968-138">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="80968-139">アプリケーションにリスナーが1つしかない場合は、名前を指定せずに追加することができます。名前に空の文字列を指定することで削除できます。</span><span class="sxs-lookup"><span data-stu-id="80968-139">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="80968-140">ただし、アプリケーションに複数のリスナーがある場合は、各トレースリスナーに対して一意の名前を指定する必要があります。これにより、コレクション内の個々のトレースリスナーを識別して管理することができ <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="80968-140">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80968-141">同じ種類の複数のトレースリスナーを同じ名前で追加すると、その型と名前のトレースリスナーは1つだけになり、コレクションに追加され `Listeners` ます。</span><span class="sxs-lookup"><span data-stu-id="80968-141">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="80968-142">ただし、プログラムを使用して複数の同じリスナーをコレクションに追加することはでき `Listeners` ます。</span><span class="sxs-lookup"><span data-stu-id="80968-142">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="80968-143">属性の値は、 `initializeData` 作成するリスナーの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="80968-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="80968-144">すべてのトレースリスナーでを指定する必要はありません `initializeData` 。</span><span class="sxs-lookup"><span data-stu-id="80968-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80968-145">属性を使用すると、 `initializeData` "initializeData" 属性が宣言されていないことを示すコンパイラの警告が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="80968-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="80968-146">この警告は、属性を認識しない抽象基本クラスに対して構成設定が検証されるために発生し <xref:System.Diagnostics.TraceListener> `initializeData` ます。</span><span class="sxs-lookup"><span data-stu-id="80968-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="80968-147">通常、パラメーターを受け取るコンストラクターを持つトレースリスナーの実装では、この警告を無視できます。</span><span class="sxs-lookup"><span data-stu-id="80968-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="80968-148">次の表に、.NET Framework に含まれているトレースリスナーとその属性の値を示し `initializeData` ます。</span><span class="sxs-lookup"><span data-stu-id="80968-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="80968-149">トレースリスナークラス</span><span class="sxs-lookup"><span data-stu-id="80968-149">Trace listener class</span></span>|<span data-ttu-id="80968-150">initializeData 属性値</span><span class="sxs-lookup"><span data-stu-id="80968-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="80968-151">`useErrorStream`コンストラクターの値 <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 。</span><span class="sxs-lookup"><span data-stu-id="80968-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="80968-152">`initializeData`トレース出力およびデバッグ出力を標準エラーストリームに書き込むには、属性を "" に設定します `true` 。 `false` 標準出力ストリームに書き込むには、"" に設定します。</span><span class="sxs-lookup"><span data-stu-id="80968-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="80968-153"><xref:System.Diagnostics.DelimitedListTraceListener> が出力を書き込むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="80968-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="80968-154">既存のイベント ログ ソースの名前。</span><span class="sxs-lookup"><span data-stu-id="80968-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="80968-155">が書き込み先となるファイルの名前 <xref:System.Diagnostics.EventSchemaTraceListener> 。</span><span class="sxs-lookup"><span data-stu-id="80968-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="80968-156">が書き込み先となるファイルの名前 <xref:System.Diagnostics.TextWriterTraceListener> 。</span><span class="sxs-lookup"><span data-stu-id="80968-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="80968-157">が書き込み先となるファイルの名前 <xref:System.Diagnostics.XmlWriterTraceListener> 。</span><span class="sxs-lookup"><span data-stu-id="80968-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="80968-158">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="80968-158">Configuration File</span></span>  

 <span data-ttu-id="80968-159">この要素は、マシン構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="80968-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80968-160">例</span><span class="sxs-lookup"><span data-stu-id="80968-160">Example</span></span>  

 <span data-ttu-id="80968-161">次の例では、要素を使用して、 `<add>` リスナー `console` およびを `textListener` `Listeners` トレースソースのコレクションに追加する方法を示し `TraceSourceApp` ます。</span><span class="sxs-lookup"><span data-stu-id="80968-161">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="80968-162">リスナーは、 `textListener` トレース出力をファイル myListener .log に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="80968-162">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80968-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="80968-163">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="80968-164">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="80968-164">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="80968-165">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="80968-165">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
