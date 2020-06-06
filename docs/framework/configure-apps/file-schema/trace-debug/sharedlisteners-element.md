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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153322"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="186e7-102">\<sharedListeners> 要素</span><span class="sxs-lookup"><span data-stu-id="186e7-102">\<sharedListeners> Element</span></span>
<span data-ttu-id="186e7-103">任意の source 要素または trace 要素が参照できるリスナーを含みます。</span><span class="sxs-lookup"><span data-stu-id="186e7-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="186e7-104">これらのリスナーは、既定ではトレースを受信せず、実行時にこれらのリスナーを取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="186e7-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="186e7-105">共有リスナーとして識別されるリスナーは、名前を指定してソースまたはトレースに追加できます。</span><span class="sxs-lookup"><span data-stu-id="186e7-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**  
  
## <a name="syntax"></a><span data-ttu-id="186e7-106">構文</span><span class="sxs-lookup"><span data-stu-id="186e7-106">Syntax</span></span>  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="186e7-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="186e7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="186e7-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="186e7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="186e7-109">属性</span><span class="sxs-lookup"><span data-stu-id="186e7-109">Attributes</span></span>  
 <span data-ttu-id="186e7-110">なし。</span><span class="sxs-lookup"><span data-stu-id="186e7-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="186e7-111">子要素</span><span class="sxs-lookup"><span data-stu-id="186e7-111">Child Elements</span></span>  
  
|<span data-ttu-id="186e7-112">要素</span><span class="sxs-lookup"><span data-stu-id="186e7-112">Element</span></span>|<span data-ttu-id="186e7-113">説明</span><span class="sxs-lookup"><span data-stu-id="186e7-113">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="186e7-114">`sharedListeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="186e7-114">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="186e7-115">親要素</span><span class="sxs-lookup"><span data-stu-id="186e7-115">Parent Elements</span></span>  
  
|<span data-ttu-id="186e7-116">要素</span><span class="sxs-lookup"><span data-stu-id="186e7-116">Element</span></span>|<span data-ttu-id="186e7-117">説明</span><span class="sxs-lookup"><span data-stu-id="186e7-117">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="186e7-118">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="186e7-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="186e7-119">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="186e7-119">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="186e7-120">解説</span><span class="sxs-lookup"><span data-stu-id="186e7-120">Remarks</span></span>  
 <span data-ttu-id="186e7-121">リスナーを共有リスナーコレクションに追加しても、それがアクティブなリスナーになることはありません。</span><span class="sxs-lookup"><span data-stu-id="186e7-121">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="186e7-122">トレースソースまたはトレースに追加するには、そのトレース要素のコレクションに追加する必要があり `Listeners` ます。</span><span class="sxs-lookup"><span data-stu-id="186e7-122">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="186e7-123">.NET Framework 内のリスナークラスは、クラスから派生し <xref:System.Diagnostics.TraceListener> ます。</span><span class="sxs-lookup"><span data-stu-id="186e7-123">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="186e7-124">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="186e7-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="186e7-125">例</span><span class="sxs-lookup"><span data-stu-id="186e7-125">Example</span></span>  
 <span data-ttu-id="186e7-126">次の例は、要素を使用し `<sharedListeners>` `console` て、 `Listeners` クラスとクラスの両方のコレクションにリスナーを追加する方法を示して <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace> います。</span><span class="sxs-lookup"><span data-stu-id="186e7-126">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="186e7-127">コンソールトレースリスナーは、またはの呼び出しを通じて、トレース情報をコンソールに書き込み <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace> ます。</span><span class="sxs-lookup"><span data-stu-id="186e7-127">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="186e7-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="186e7-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="186e7-129">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="186e7-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="186e7-130">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="186e7-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
