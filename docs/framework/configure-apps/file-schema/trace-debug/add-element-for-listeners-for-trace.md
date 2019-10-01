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
ms.openlocfilehash: d89a77107e7aff65b007a69c23af34771146570c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697333"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="600f2-102">\<trace > の \< リスナーの > 要素を追加し @no__t</span><span class="sxs-lookup"><span data-stu-id="600f2-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="600f2-103">リスナーを**リスナー**コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="600f2-103">Adds a listener to the **Listeners** collection.</span></span>  
  
[<span data-ttu-id="600f2-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="600f2-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="600f2-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="600f2-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="600f2-106">&nbsp; @ no__t-1 @ no__t @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="600f2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="600f2-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5[ **\<listeners >** します。](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="600f2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="600f2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="600f2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="600f2-109">構文</span><span class="sxs-lookup"><span data-stu-id="600f2-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="600f2-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="600f2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="600f2-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="600f2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="600f2-112">属性</span><span class="sxs-lookup"><span data-stu-id="600f2-112">Attributes</span></span>  
  
|<span data-ttu-id="600f2-113">属性</span><span class="sxs-lookup"><span data-stu-id="600f2-113">Attribute</span></span>|<span data-ttu-id="600f2-114">説明</span><span class="sxs-lookup"><span data-stu-id="600f2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="600f2-115">**type**</span><span class="sxs-lookup"><span data-stu-id="600f2-115">**type**</span></span>|<span data-ttu-id="600f2-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="600f2-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="600f2-117">リスナーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="600f2-117">Specifies the type of the listener.</span></span> <span data-ttu-id="600f2-118">[「完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」で指定した要件を満たす文字列を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="600f2-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="600f2-119">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="600f2-119">**initializeData**</span></span>|<span data-ttu-id="600f2-120">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="600f2-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="600f2-121">指定したクラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="600f2-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="600f2-122">**name**</span><span class="sxs-lookup"><span data-stu-id="600f2-122">**name**</span></span>|<span data-ttu-id="600f2-123">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="600f2-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="600f2-124">リスナーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="600f2-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="600f2-125">子要素</span><span class="sxs-lookup"><span data-stu-id="600f2-125">Child Elements</span></span>  
  
|<span data-ttu-id="600f2-126">要素</span><span class="sxs-lookup"><span data-stu-id="600f2-126">Element</span></span>|<span data-ttu-id="600f2-127">説明</span><span class="sxs-lookup"><span data-stu-id="600f2-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="600f2-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="600f2-128">\<filter></span></span>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="600f2-129">トレースの @no__t 0 コレクションのリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="600f2-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="600f2-130">親要素</span><span class="sxs-lookup"><span data-stu-id="600f2-130">Parent Elements</span></span>  
  
|<span data-ttu-id="600f2-131">要素</span><span class="sxs-lookup"><span data-stu-id="600f2-131">Element</span></span>|<span data-ttu-id="600f2-132">説明</span><span class="sxs-lookup"><span data-stu-id="600f2-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="600f2-133">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="600f2-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="600f2-134">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="600f2-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="600f2-135">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="600f2-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="600f2-136">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="600f2-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="600f2-137">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="600f2-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="600f2-138">コメント</span><span class="sxs-lookup"><span data-stu-id="600f2-138">Remarks</span></span>  
 <span data-ttu-id="600f2-139">@No__t-0 および <xref:System.Diagnostics.Trace> クラスは、同じ**リスナー**コレクションを共有します。</span><span class="sxs-lookup"><span data-stu-id="600f2-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="600f2-140">これらのクラスのいずれかのコレクションにリスナーオブジェクトを追加すると、他のクラスは同じリスナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="600f2-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="600f2-141">リスナークラスは @no__t 0 から派生します。</span><span class="sxs-lookup"><span data-stu-id="600f2-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="600f2-142">トレースリスナーの @no__t 0 の属性を指定しない場合、トレースリスナーの <xref:System.Diagnostics.TraceListener.Name%2A> は既定で空の文字列 ("") になります。</span><span class="sxs-lookup"><span data-stu-id="600f2-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="600f2-143">アプリケーションにリスナーが1つしかない場合は、名前を指定せずにリスナーを追加し、名前に空の文字列を指定することで削除できます。</span><span class="sxs-lookup"><span data-stu-id="600f2-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="600f2-144">ただし、アプリケーションに複数のリスナーがある場合は、トレースリスナーごとに一意の名前を指定する必要があります。これにより、<xref:System.Diagnostics.Debug.Listeners%2A> および <xref:System.Diagnostics.Trace.Listeners%2A> のコレクション内の個々のトレースリスナーを識別して管理できます。</span><span class="sxs-lookup"><span data-stu-id="600f2-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="600f2-145">同じ種類の複数のトレースリスナーを同じ名前で追加すると、その型と名前のトレースリスナーが1つだけ `Listeners` コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="600f2-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="600f2-146">ただし、複数の同じリスナーを @no__t 0 のコレクションにプログラムで追加することができます。</span><span class="sxs-lookup"><span data-stu-id="600f2-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="600f2-147">**Initializedata**属性の値は、作成するリスナーの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="600f2-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="600f2-148">すべてのトレースリスナーで**Initializedata**を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="600f2-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="600f2-149">@No__t-0 属性を使用すると、"initializeData" 属性が宣言されていないことを示すコンパイラの警告が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="600f2-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="600f2-150">この警告は、構成設定が抽象基本クラスに対して検証されるために発生します。この <xref:System.Diagnostics.TraceListener> は、`initializeData` 属性を認識しません。</span><span class="sxs-lookup"><span data-stu-id="600f2-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="600f2-151">通常、パラメーターを受け取るコンストラクターを持つトレースリスナーの実装では、この警告を無視できます。</span><span class="sxs-lookup"><span data-stu-id="600f2-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="600f2-152">次の表に、.NET Framework に含まれるトレースリスナーと、 **Initializedata**属性の値について説明します。</span><span class="sxs-lookup"><span data-stu-id="600f2-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="600f2-153">トレースリスナークラス</span><span class="sxs-lookup"><span data-stu-id="600f2-153">Trace listener class</span></span>|<span data-ttu-id="600f2-154">initializeData 属性値</span><span class="sxs-lookup"><span data-stu-id="600f2-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="600f2-155">@No__t-1 コンストラクターの @no__t 0 値。</span><span class="sxs-lookup"><span data-stu-id="600f2-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="600f2-156">トレース出力とデバッグ出力を <xref:System.Console.Error%2A?displayProperty=nameWithType> に書き込むには、`initializeData` 属性を "`true`" に設定します。"`false`" を <xref:System.Console.Out%2A?displayProperty=nameWithType> に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="600f2-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="600f2-157">@No__t の書き込み先のファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="600f2-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="600f2-158">既存のイベントログソースの名前。</span><span class="sxs-lookup"><span data-stu-id="600f2-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="600f2-159">@No__t が書き込み先となるファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="600f2-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="600f2-160">@No__t が書き込み先となるファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="600f2-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="600f2-161">@No__t が書き込み先となるファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="600f2-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="600f2-162">例</span><span class="sxs-lookup"><span data-stu-id="600f2-162">Example</span></span>  
 <span data-ttu-id="600f2-163">次の例は、使用する方法を示します **\<追加 >** リスナーを追加する要素`MyListener`と`MyEventListener`を**リスナー**コレクション。</span><span class="sxs-lookup"><span data-stu-id="600f2-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="600f2-164">`MyListener` `MyListener.log` という名前のファイルを作成し、出力をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="600f2-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="600f2-165">`MyEventListener` を入力すると、イベントログにエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="600f2-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="600f2-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="600f2-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="600f2-167">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="600f2-167">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="600f2-168">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="600f2-168">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
