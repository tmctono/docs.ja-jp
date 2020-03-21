---
title: <sharedListeners> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: 69f15cc9583b397017ac30a0c567914495867c18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153322"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="fedc1-102">\<共有リスナー>要素</span><span class="sxs-lookup"><span data-stu-id="fedc1-102">\<sharedListeners> Element</span></span>
<span data-ttu-id="fedc1-103">任意の source 要素または trace 要素が参照できるリスナーを含みます。</span><span class="sxs-lookup"><span data-stu-id="fedc1-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="fedc1-104">これらのリスナーは、既定ではトレースを受信せず、実行時にこれらのリスナーを取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="fedc1-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="fedc1-105">共有リスナーとして識別されたリスナーは、ソースまたはトレースに名前で追加できます。</span><span class="sxs-lookup"><span data-stu-id="fedc1-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[<span data-ttu-id="fedc1-106">**\<構成>**</span><span class="sxs-lookup"><span data-stu-id="fedc1-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="fedc1-107">&nbsp;&nbsp;[**\<診断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="fedc1-107">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="fedc1-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<共有リスナー>**</span><span class="sxs-lookup"><span data-stu-id="fedc1-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fedc1-109">構文</span><span class="sxs-lookup"><span data-stu-id="fedc1-109">Syntax</span></span>  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fedc1-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fedc1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fedc1-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fedc1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fedc1-112">属性</span><span class="sxs-lookup"><span data-stu-id="fedc1-112">Attributes</span></span>  
 <span data-ttu-id="fedc1-113">[なし] :</span><span class="sxs-lookup"><span data-stu-id="fedc1-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fedc1-114">子要素</span><span class="sxs-lookup"><span data-stu-id="fedc1-114">Child Elements</span></span>  
  
|<span data-ttu-id="fedc1-115">要素</span><span class="sxs-lookup"><span data-stu-id="fedc1-115">Element</span></span>|<span data-ttu-id="fedc1-116">説明</span><span class="sxs-lookup"><span data-stu-id="fedc1-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fedc1-117">\<>を追加する</span><span class="sxs-lookup"><span data-stu-id="fedc1-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="fedc1-118">`sharedListeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fedc1-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fedc1-119">親要素</span><span class="sxs-lookup"><span data-stu-id="fedc1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fedc1-120">要素</span><span class="sxs-lookup"><span data-stu-id="fedc1-120">Element</span></span>|<span data-ttu-id="fedc1-121">説明</span><span class="sxs-lookup"><span data-stu-id="fedc1-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="fedc1-122">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="fedc1-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="fedc1-123">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="fedc1-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fedc1-124">解説</span><span class="sxs-lookup"><span data-stu-id="fedc1-124">Remarks</span></span>  
 <span data-ttu-id="fedc1-125">共有リスナーコレクションにリスナーを追加しても、アクティブなリスナーにはなっていません。</span><span class="sxs-lookup"><span data-stu-id="fedc1-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="fedc1-126">トレース ソースまたはトレース要素の`Listeners`コレクションに追加することによって、トレース ソースまたはトレースに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fedc1-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="fedc1-127">.NET Framework のリスナー クラスは、<xref:System.Diagnostics.TraceListener>クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="fedc1-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="fedc1-128">この要素は、コンピューター構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="fedc1-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fedc1-129">例</span><span class="sxs-lookup"><span data-stu-id="fedc1-129">Example</span></span>  
 <span data-ttu-id="fedc1-130">次の例は、要素を使用`<sharedListeners>`して、 クラスと`console`<xref:System.Diagnostics.Trace>クラス`Listeners`の両方のリスナー<xref:System.Diagnostics.TraceSource>をコレクションに追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fedc1-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="fedc1-131">コンソール トレース リスナーは、<xref:System.Diagnostics.TraceSource>または<xref:System.Diagnostics.Trace>への呼び出しを通じてトレース情報をコンソールに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="fedc1-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="fedc1-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="fedc1-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="fedc1-133">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="fedc1-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fedc1-134">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="fedc1-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
