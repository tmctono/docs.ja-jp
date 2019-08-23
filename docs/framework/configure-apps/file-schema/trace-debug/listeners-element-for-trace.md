---
title: <trace> の <listeners> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: e4550d4c4cd9ff37c5937ad366cccf91387c0e3f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927021"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="91207-102">\<トレース > の\<リスナー > 要素</span><span class="sxs-lookup"><span data-stu-id="91207-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="91207-103">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="91207-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="91207-104">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="91207-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
 <span data-ttu-id="91207-105">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="91207-105">\<configuration> Element</span></span>  
<span data-ttu-id="91207-106">\<system. diagnostics > 要素</span><span class="sxs-lookup"><span data-stu-id="91207-106">\<system.diagnostics> Element</span></span>  
<span data-ttu-id="91207-107">\<トレース > 要素</span><span class="sxs-lookup"><span data-stu-id="91207-107">\<trace> Element</span></span>  
<span data-ttu-id="91207-108">\<トレース > の\<リスナー > 要素</span><span class="sxs-lookup"><span data-stu-id="91207-108">\<listeners> Element for \<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91207-109">構文</span><span class="sxs-lookup"><span data-stu-id="91207-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91207-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="91207-110">Attributes and Elements</span></span>  
 <span data-ttu-id="91207-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="91207-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91207-112">属性</span><span class="sxs-lookup"><span data-stu-id="91207-112">Attributes</span></span>  
 <span data-ttu-id="91207-113">なし。</span><span class="sxs-lookup"><span data-stu-id="91207-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="91207-114">子要素</span><span class="sxs-lookup"><span data-stu-id="91207-114">Child Elements</span></span>  
  
|<span data-ttu-id="91207-115">要素</span><span class="sxs-lookup"><span data-stu-id="91207-115">Element</span></span>|<span data-ttu-id="91207-116">説明</span><span class="sxs-lookup"><span data-stu-id="91207-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91207-117">\<add></span><span class="sxs-lookup"><span data-stu-id="91207-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="91207-118">`Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="91207-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="91207-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="91207-119">\<clear></span></span>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="91207-120">トレースの `Listeners` コレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="91207-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="91207-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="91207-121">\<remove></span></span>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="91207-122">`Listeners`コレクションからリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="91207-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91207-123">親要素</span><span class="sxs-lookup"><span data-stu-id="91207-123">Parent Elements</span></span>  
  
|<span data-ttu-id="91207-124">要素</span><span class="sxs-lookup"><span data-stu-id="91207-124">Element</span></span>|<span data-ttu-id="91207-125">説明</span><span class="sxs-lookup"><span data-stu-id="91207-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="91207-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="91207-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="91207-127">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="91207-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="91207-128">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="91207-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91207-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="91207-129">Remarks</span></span>  
 <span data-ttu-id="91207-130">クラス<xref:System.Diagnostics.Debug>と<xref:System.Diagnostics.Trace>クラスは、同じ**Listeners**コレクションを共有します。</span><span class="sxs-lookup"><span data-stu-id="91207-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="91207-131">これらのクラスのいずれかのコレクションにリスナーオブジェクトを追加すると、他のクラスは同じリスナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="91207-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="91207-132">.NET Framework に付属しているリスナークラスは、 <xref:System.Diagnostics.TraceListener>クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="91207-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="91207-133">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="91207-133">Configuration File</span></span>  
 <span data-ttu-id="91207-134">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="91207-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91207-135">例</span><span class="sxs-lookup"><span data-stu-id="91207-135">Example</span></span>  
 <span data-ttu-id="91207-136">次の例では、listeners  **\<>** 要素を使用してリスナー `MyListener`および`MyEventListener`リスナーコレクションに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="91207-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="91207-137">`MyListener`という名前`MyListener.log`のファイルを作成し、その出力をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="91207-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="91207-138">`MyEventListener`イベントログにエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="91207-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"   
          type="System.Diagnostics.TextWriterTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"   
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="91207-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="91207-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="91207-140">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="91207-140">Trace and Debug Settings Schema</span></span>](index.md)
