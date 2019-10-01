---
title: <trace> の <listeners> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: 84b67532825372e7f69d86e1ef6060f4263587eb
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699348"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="23d18-102">\< トレース > の @no__t 0listeners > 要素</span><span class="sxs-lookup"><span data-stu-id="23d18-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="23d18-103">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="23d18-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="23d18-104">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="23d18-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
[<span data-ttu-id="23d18-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="23d18-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="23d18-106">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="23d18-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="23d18-107">&nbsp; @ no__t-1 @ no__t @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="23d18-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="23d18-108">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 **\<listeners >** を行います。</span><span class="sxs-lookup"><span data-stu-id="23d18-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d18-109">構文</span><span class="sxs-lookup"><span data-stu-id="23d18-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23d18-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="23d18-110">Attributes and Elements</span></span>  
 <span data-ttu-id="23d18-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="23d18-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23d18-112">属性</span><span class="sxs-lookup"><span data-stu-id="23d18-112">Attributes</span></span>  
 <span data-ttu-id="23d18-113">[なし] :</span><span class="sxs-lookup"><span data-stu-id="23d18-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="23d18-114">子要素</span><span class="sxs-lookup"><span data-stu-id="23d18-114">Child Elements</span></span>  
  
|<span data-ttu-id="23d18-115">要素</span><span class="sxs-lookup"><span data-stu-id="23d18-115">Element</span></span>|<span data-ttu-id="23d18-116">説明</span><span class="sxs-lookup"><span data-stu-id="23d18-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23d18-117">\<add></span><span class="sxs-lookup"><span data-stu-id="23d18-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="23d18-118">`Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="23d18-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="23d18-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="23d18-119">\<clear></span></span>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="23d18-120">トレースの `Listeners` コレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="23d18-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="23d18-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="23d18-121">\<remove></span></span>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="23d18-122">@No__t 0 のコレクションからリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="23d18-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23d18-123">親要素</span><span class="sxs-lookup"><span data-stu-id="23d18-123">Parent Elements</span></span>  
  
|<span data-ttu-id="23d18-124">要素</span><span class="sxs-lookup"><span data-stu-id="23d18-124">Element</span></span>|<span data-ttu-id="23d18-125">説明</span><span class="sxs-lookup"><span data-stu-id="23d18-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="23d18-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="23d18-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="23d18-127">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="23d18-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="23d18-128">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="23d18-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23d18-129">コメント</span><span class="sxs-lookup"><span data-stu-id="23d18-129">Remarks</span></span>  
 <span data-ttu-id="23d18-130">@No__t-0 および <xref:System.Diagnostics.Trace> クラスは、同じ**リスナー**コレクションを共有します。</span><span class="sxs-lookup"><span data-stu-id="23d18-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="23d18-131">これらのクラスのいずれかのコレクションにリスナーオブジェクトを追加すると、他のクラスは同じリスナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="23d18-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="23d18-132">.NET Framework に付属しているリスナークラスは、@no__t 0 クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="23d18-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="23d18-133">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="23d18-133">Configuration File</span></span>  
 <span data-ttu-id="23d18-134">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="23d18-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23d18-135">例</span><span class="sxs-lookup"><span data-stu-id="23d18-135">Example</span></span>  
 <span data-ttu-id="23d18-136">次の例では、 **\<listeners >** 要素を使用してリスナー `MyListener` と @no__t を**リスナー**コレクションに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="23d18-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="23d18-137">`MyListener` `MyListener.log` という名前のファイルを作成し、出力をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="23d18-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="23d18-138">`MyEventListener` を入力すると、イベントログにエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="23d18-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="23d18-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="23d18-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="23d18-140">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="23d18-140">Trace and Debug Settings Schema</span></span>](index.md)
