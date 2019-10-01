---
title: <source> の <listeners> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: d7641611e5d8257b49bc6a6abd0a2fadfde66e91
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697299"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="2e9c0-102">\< ソースの @no__t 0listeners > 要素 ></span><span class="sxs-lookup"><span data-stu-id="2e9c0-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="2e9c0-103">@No__t-1 の <xref:System.Diagnostics.TraceSource.Listeners%2A> コレクションのリスナーを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="2e9c0-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="2e9c0-104">リスナーは、ログ、ウィンドウ、テキストファイルなど、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="2e9c0-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[<span data-ttu-id="2e9c0-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="2e9c0-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="2e9c0-106">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e9c0-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="2e9c0-107">&nbsp; @ no__t-1 @ no__t no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e9c0-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="2e9c0-108">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5[ **\<source >** になります。](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e9c0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="2e9c0-109">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 @ no__t-6 @ no__t-7 **\<listeners >** します。</span><span class="sxs-lookup"><span data-stu-id="2e9c0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e9c0-110">構文</span><span class="sxs-lookup"><span data-stu-id="2e9c0-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e9c0-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2e9c0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2e9c0-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e9c0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e9c0-113">属性</span><span class="sxs-lookup"><span data-stu-id="2e9c0-113">Attributes</span></span>  
 <span data-ttu-id="2e9c0-114">[なし] :</span><span class="sxs-lookup"><span data-stu-id="2e9c0-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2e9c0-115">子要素</span><span class="sxs-lookup"><span data-stu-id="2e9c0-115">Child Elements</span></span>  
  
|<span data-ttu-id="2e9c0-116">要素</span><span class="sxs-lookup"><span data-stu-id="2e9c0-116">Element</span></span>|<span data-ttu-id="2e9c0-117">説明</span><span class="sxs-lookup"><span data-stu-id="2e9c0-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e9c0-118">\<add></span><span class="sxs-lookup"><span data-stu-id="2e9c0-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="2e9c0-119">`Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2e9c0-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="2e9c0-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="2e9c0-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="2e9c0-121">@No__t 0 のコレクションからリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2e9c0-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="2e9c0-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="2e9c0-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="2e9c0-123">トレース ソースの `Listeners` コレクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="2e9c0-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2e9c0-124">親要素</span><span class="sxs-lookup"><span data-stu-id="2e9c0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2e9c0-125">要素</span><span class="sxs-lookup"><span data-stu-id="2e9c0-125">Element</span></span>|<span data-ttu-id="2e9c0-126">説明</span><span class="sxs-lookup"><span data-stu-id="2e9c0-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2e9c0-127">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="2e9c0-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2e9c0-128">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e9c0-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="2e9c0-129">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="2e9c0-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="2e9c0-130">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e9c0-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e9c0-131">コメント</span><span class="sxs-lookup"><span data-stu-id="2e9c0-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="2e9c0-132">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="2e9c0-132">Configuration File</span></span>  
 <span data-ttu-id="2e9c0-133">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e9c0-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e9c0-134">例</span><span class="sxs-lookup"><span data-stu-id="2e9c0-134">Example</span></span>  
 <span data-ttu-id="2e9c0-135">次の例は、`<listeners>` 要素を使用して、コンソールトレースリスナーを `mySource` ソースに追加し、既定のトレースリスナーを削除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2e9c0-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e9c0-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e9c0-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="2e9c0-137">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="2e9c0-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2e9c0-138">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="2e9c0-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
