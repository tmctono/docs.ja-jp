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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153374"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="46364-102">\<trace> の \<listeners> 要素</span><span class="sxs-lookup"><span data-stu-id="46364-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="46364-103">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="46364-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="46364-104">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="46364-104">Listeners direct the tracing output to an appropriate target.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**

## <a name="syntax"></a><span data-ttu-id="46364-105">構文</span><span class="sxs-lookup"><span data-stu-id="46364-105">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46364-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="46364-106">Attributes and Elements</span></span>  
 <span data-ttu-id="46364-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="46364-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46364-108">属性</span><span class="sxs-lookup"><span data-stu-id="46364-108">Attributes</span></span>  
 <span data-ttu-id="46364-109">なし。</span><span class="sxs-lookup"><span data-stu-id="46364-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="46364-110">子要素</span><span class="sxs-lookup"><span data-stu-id="46364-110">Child Elements</span></span>  
  
|<span data-ttu-id="46364-111">要素</span><span class="sxs-lookup"><span data-stu-id="46364-111">Element</span></span>|<span data-ttu-id="46364-112">説明</span><span class="sxs-lookup"><span data-stu-id="46364-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="46364-113">`Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="46364-113">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="46364-114">トレースの `Listeners` コレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="46364-114">Clears the `Listeners` collection for trace.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="46364-115">コレクションからリスナーを削除 `Listeners` します。</span><span class="sxs-lookup"><span data-stu-id="46364-115">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="46364-116">親要素</span><span class="sxs-lookup"><span data-stu-id="46364-116">Parent Elements</span></span>  
  
|<span data-ttu-id="46364-117">要素</span><span class="sxs-lookup"><span data-stu-id="46364-117">Element</span></span>|<span data-ttu-id="46364-118">説明</span><span class="sxs-lookup"><span data-stu-id="46364-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="46364-119">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="46364-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="46364-120">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="46364-120">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="46364-121">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="46364-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46364-122">解説</span><span class="sxs-lookup"><span data-stu-id="46364-122">Remarks</span></span>  
 <span data-ttu-id="46364-123"><xref:System.Diagnostics.Debug>クラスと <xref:System.Diagnostics.Trace> クラスは、同じ**Listeners**コレクションを共有します。</span><span class="sxs-lookup"><span data-stu-id="46364-123">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="46364-124">これらのクラスのいずれかのコレクションにリスナーオブジェクトを追加すると、他のクラスは同じリスナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="46364-124">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="46364-125">.NET Framework に付属しているリスナークラスは、クラスから派生し <xref:System.Diagnostics.TraceListener> ます。</span><span class="sxs-lookup"><span data-stu-id="46364-125">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="46364-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="46364-126">Configuration File</span></span>  
 <span data-ttu-id="46364-127">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="46364-127">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46364-128">例</span><span class="sxs-lookup"><span data-stu-id="46364-128">Example</span></span>  
 <span data-ttu-id="46364-129">次の例は、要素を使用して **\<listeners>** リスナー `MyListener` および `MyEventListener` **リスナー**コレクションに追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="46364-129">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="46364-130">`MyListener`という名前のファイルを作成し、その `MyListener.log` 出力をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="46364-130">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="46364-131">`MyEventListener`イベントログにエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="46364-131">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="46364-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="46364-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="46364-133">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="46364-133">Trace and Debug Settings Schema</span></span>](index.md)
