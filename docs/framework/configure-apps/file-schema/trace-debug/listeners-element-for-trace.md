---
title: <trace> の <listeners> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: fd12be1b775d7611ef3f16d23147470313bf9866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153374"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="9ffbd-102">\<トレース>の\<リスナー>要素</span><span class="sxs-lookup"><span data-stu-id="9ffbd-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="9ffbd-103">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="9ffbd-104">リスナーは、トレース出力を適切なターゲットに送ります。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-104">Listeners direct the tracing output to an appropriate target.</span></span>  

<span data-ttu-id="9ffbd-105">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9ffbd-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9ffbd-106">&nbsp;&nbsp;[**\<診断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="9ffbd-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="9ffbd-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<トレース>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="9ffbd-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="9ffbd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<リスナー>**</span><span class="sxs-lookup"><span data-stu-id="9ffbd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9ffbd-109">構文</span><span class="sxs-lookup"><span data-stu-id="9ffbd-109">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ffbd-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9ffbd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9ffbd-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ffbd-112">属性</span><span class="sxs-lookup"><span data-stu-id="9ffbd-112">Attributes</span></span>  
 <span data-ttu-id="9ffbd-113">[なし] :</span><span class="sxs-lookup"><span data-stu-id="9ffbd-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9ffbd-114">子要素</span><span class="sxs-lookup"><span data-stu-id="9ffbd-114">Child Elements</span></span>  
  
|<span data-ttu-id="9ffbd-115">要素</span><span class="sxs-lookup"><span data-stu-id="9ffbd-115">Element</span></span>|<span data-ttu-id="9ffbd-116">説明</span><span class="sxs-lookup"><span data-stu-id="9ffbd-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ffbd-117">\<>を追加する</span><span class="sxs-lookup"><span data-stu-id="9ffbd-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="9ffbd-118">`Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="9ffbd-119">\<クリア></span><span class="sxs-lookup"><span data-stu-id="9ffbd-119">\<clear></span></span>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="9ffbd-120">トレースの `Listeners` コレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="9ffbd-121">\<>を削除する</span><span class="sxs-lookup"><span data-stu-id="9ffbd-121">\<remove></span></span>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="9ffbd-122">`Listeners`コレクションからリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ffbd-123">親要素</span><span class="sxs-lookup"><span data-stu-id="9ffbd-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9ffbd-124">要素</span><span class="sxs-lookup"><span data-stu-id="9ffbd-124">Element</span></span>|<span data-ttu-id="9ffbd-125">説明</span><span class="sxs-lookup"><span data-stu-id="9ffbd-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9ffbd-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="9ffbd-127">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="9ffbd-128">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ffbd-129">解説</span><span class="sxs-lookup"><span data-stu-id="9ffbd-129">Remarks</span></span>  
 <span data-ttu-id="9ffbd-130">と<xref:System.Diagnostics.Debug><xref:System.Diagnostics.Trace>クラスは同じ**Listeners**コレクションを共有します。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="9ffbd-131">これらのクラスの 1 つでリスナー オブジェクトをコレクションに追加すると、もう一方のクラスは同じリスナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="9ffbd-132">.NET Framework に付属のリスナー クラスは、<xref:System.Diagnostics.TraceListener>クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="9ffbd-133">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="9ffbd-133">Configuration File</span></span>  
 <span data-ttu-id="9ffbd-134">この要素は、コンピューター構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ffbd-135">例</span><span class="sxs-lookup"><span data-stu-id="9ffbd-135">Example</span></span>  
 <span data-ttu-id="9ffbd-136">次の例は、**\<リスナー>** 要素を使用してリスナーと`MyListener``MyEventListener` **Listeners**コレクションを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="9ffbd-137">`MyListener`と呼ばれる`MyListener.log`ファイルを作成し、そのファイルに出力を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="9ffbd-138">`MyEventListener`は、イベント ログにエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="9ffbd-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9ffbd-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ffbd-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="9ffbd-140">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="9ffbd-140">Trace and Debug Settings Schema</span></span>](index.md)
