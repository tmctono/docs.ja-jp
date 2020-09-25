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
ms.openlocfilehash: 7e249e59423740b36e42f59fae8854412d01a0cc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173849"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="6a563-102">\<sharedListeners> 要素</span><span class="sxs-lookup"><span data-stu-id="6a563-102">\<sharedListeners> Element</span></span>

<span data-ttu-id="6a563-103">任意の source 要素または trace 要素が参照できるリスナーを含みます。</span><span class="sxs-lookup"><span data-stu-id="6a563-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="6a563-104">これらのリスナーは、既定ではトレースを受信せず、実行時にこれらのリスナーを取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="6a563-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="6a563-105">共有リスナーとして識別されるリスナーは、名前を指定してソースまたはトレースに追加できます。</span><span class="sxs-lookup"><span data-stu-id="6a563-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**  
  
## <a name="syntax"></a><span data-ttu-id="6a563-106">構文</span><span class="sxs-lookup"><span data-stu-id="6a563-106">Syntax</span></span>  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a563-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6a563-107">Attributes and Elements</span></span>  

 <span data-ttu-id="6a563-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a563-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a563-109">属性</span><span class="sxs-lookup"><span data-stu-id="6a563-109">Attributes</span></span>  

 <span data-ttu-id="6a563-110">なし。</span><span class="sxs-lookup"><span data-stu-id="6a563-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6a563-111">子要素</span><span class="sxs-lookup"><span data-stu-id="6a563-111">Child Elements</span></span>  
  
|<span data-ttu-id="6a563-112">要素</span><span class="sxs-lookup"><span data-stu-id="6a563-112">Element</span></span>|<span data-ttu-id="6a563-113">説明</span><span class="sxs-lookup"><span data-stu-id="6a563-113">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="6a563-114">`sharedListeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="6a563-114">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a563-115">親要素</span><span class="sxs-lookup"><span data-stu-id="6a563-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6a563-116">要素</span><span class="sxs-lookup"><span data-stu-id="6a563-116">Element</span></span>|<span data-ttu-id="6a563-117">説明</span><span class="sxs-lookup"><span data-stu-id="6a563-117">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="6a563-118">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="6a563-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="6a563-119">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a563-119">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a563-120">解説</span><span class="sxs-lookup"><span data-stu-id="6a563-120">Remarks</span></span>  

 <span data-ttu-id="6a563-121">リスナーを共有リスナーコレクションに追加しても、それがアクティブなリスナーになることはありません。</span><span class="sxs-lookup"><span data-stu-id="6a563-121">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="6a563-122">トレースソースまたはトレースに追加するには、そのトレース要素のコレクションに追加する必要があり `Listeners` ます。</span><span class="sxs-lookup"><span data-stu-id="6a563-122">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="6a563-123">.NET Framework 内のリスナークラスは、クラスから派生し <xref:System.Diagnostics.TraceListener> ます。</span><span class="sxs-lookup"><span data-stu-id="6a563-123">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="6a563-124">この要素は、マシン構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="6a563-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a563-125">例</span><span class="sxs-lookup"><span data-stu-id="6a563-125">Example</span></span>  

 <span data-ttu-id="6a563-126">次の例は、要素を使用し `<sharedListeners>` `console` て、 `Listeners` クラスとクラスの両方のコレクションにリスナーを追加する方法を示して <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace> います。</span><span class="sxs-lookup"><span data-stu-id="6a563-126">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="6a563-127">コンソールトレースリスナーは、またはの呼び出しを通じて、トレース情報をコンソールに書き込み <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace> ます。</span><span class="sxs-lookup"><span data-stu-id="6a563-127">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6a563-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a563-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="6a563-129">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="6a563-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6a563-130">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="6a563-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
