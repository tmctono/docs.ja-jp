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
ms.openlocfilehash: 41cabcbce13409b0842cbbd625028b51d32d59d0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926982"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="a5ae4-102">\<sharedListeners > 要素</span><span class="sxs-lookup"><span data-stu-id="a5ae4-102">\<sharedListeners> Element</span></span>
<span data-ttu-id="a5ae4-103">任意の source 要素または trace 要素が参照できるリスナーを含みます。</span><span class="sxs-lookup"><span data-stu-id="a5ae4-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="a5ae4-104">これらのリスナーは、既定ではトレースを受信せず、実行時にこれらのリスナーを取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="a5ae4-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="a5ae4-105">共有リスナーとして識別されるリスナーは、名前を指定してソースまたはトレースに追加できます。</span><span class="sxs-lookup"><span data-stu-id="a5ae4-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
 <span data-ttu-id="a5ae4-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a5ae4-106">\<configuration></span></span>  
<span data-ttu-id="a5ae4-107">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="a5ae4-107">\<system.diagnostics></span></span>  
<span data-ttu-id="a5ae4-108">\<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="a5ae4-108">\<sharedListeners></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ae4-109">構文</span><span class="sxs-lookup"><span data-stu-id="a5ae4-109">Syntax</span></span>  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5ae4-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a5ae4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a5ae4-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5ae4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5ae4-112">属性</span><span class="sxs-lookup"><span data-stu-id="a5ae4-112">Attributes</span></span>  
 <span data-ttu-id="a5ae4-113">なし。</span><span class="sxs-lookup"><span data-stu-id="a5ae4-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a5ae4-114">子要素</span><span class="sxs-lookup"><span data-stu-id="a5ae4-114">Child Elements</span></span>  
  
|<span data-ttu-id="a5ae4-115">要素</span><span class="sxs-lookup"><span data-stu-id="a5ae4-115">Element</span></span>|<span data-ttu-id="a5ae4-116">説明</span><span class="sxs-lookup"><span data-stu-id="a5ae4-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5ae4-117">\<add></span><span class="sxs-lookup"><span data-stu-id="a5ae4-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="a5ae4-118">`sharedListeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a5ae4-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a5ae4-119">親要素</span><span class="sxs-lookup"><span data-stu-id="a5ae4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a5ae4-120">要素</span><span class="sxs-lookup"><span data-stu-id="a5ae4-120">Element</span></span>|<span data-ttu-id="a5ae4-121">説明</span><span class="sxs-lookup"><span data-stu-id="a5ae4-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="a5ae4-122">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a5ae4-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a5ae4-123">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5ae4-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5ae4-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="a5ae4-124">Remarks</span></span>  
 <span data-ttu-id="a5ae4-125">リスナーを共有リスナーコレクションに追加しても、それがアクティブなリスナーになることはありません。</span><span class="sxs-lookup"><span data-stu-id="a5ae4-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="a5ae4-126">トレースソースまたはトレースに追加するには、そのトレース要素の`Listeners`コレクションに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5ae4-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="a5ae4-127">.NET Framework 内のリスナークラスは、 <xref:System.Diagnostics.TraceListener>クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="a5ae4-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="a5ae4-128">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a5ae4-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5ae4-129">例</span><span class="sxs-lookup"><span data-stu-id="a5ae4-129">Example</span></span>  
 <span data-ttu-id="a5ae4-130">次の例は`<sharedListeners>` 、要素を使用し<xref:System.Diagnostics.TraceSource>て、クラスと`console` <xref:System.Diagnostics.Trace>クラスの`Listeners`両方のコレクションにリスナーを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a5ae4-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="a5ae4-131">コンソールトレースリスナーは、 <xref:System.Diagnostics.TraceSource>または<xref:System.Diagnostics.Trace>の呼び出しを通じて、トレース情報をコンソールに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="a5ae4-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a5ae4-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5ae4-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="a5ae4-133">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="a5ae4-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a5ae4-134">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="a5ae4-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
