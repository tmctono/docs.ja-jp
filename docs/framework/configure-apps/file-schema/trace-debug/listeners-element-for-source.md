---
title: <source> の <listeners> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: 0eee325e01b41a15a19e4f40f479596f9d70f73b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153413"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="d6268-102">\<\<ソース>のリスナー>要素</span><span class="sxs-lookup"><span data-stu-id="d6268-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="d6268-103">のコレクション内のリスナーを<xref:System.Diagnostics.TraceSource.Listeners%2A>追加または削除します。 <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="d6268-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="d6268-104">リスナーは、トレース出力をログ、ウィンドウ、テキスト ファイルなどの適切なターゲットに向けます。</span><span class="sxs-lookup"><span data-stu-id="d6268-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[<span data-ttu-id="d6268-105">**\<構成>**</span><span class="sxs-lookup"><span data-stu-id="d6268-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="d6268-106">&nbsp;&nbsp;[**\<診断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="d6268-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="d6268-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ソース>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="d6268-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="d6268-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ソース>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="d6268-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="d6268-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<リスナー>**</span><span class="sxs-lookup"><span data-stu-id="d6268-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6268-110">構文</span><span class="sxs-lookup"><span data-stu-id="d6268-110">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6268-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d6268-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d6268-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6268-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6268-113">属性</span><span class="sxs-lookup"><span data-stu-id="d6268-113">Attributes</span></span>  
 <span data-ttu-id="d6268-114">[なし] :</span><span class="sxs-lookup"><span data-stu-id="d6268-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d6268-115">子要素</span><span class="sxs-lookup"><span data-stu-id="d6268-115">Child Elements</span></span>  
  
|<span data-ttu-id="d6268-116">要素</span><span class="sxs-lookup"><span data-stu-id="d6268-116">Element</span></span>|<span data-ttu-id="d6268-117">説明</span><span class="sxs-lookup"><span data-stu-id="d6268-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6268-118">\<>を追加する</span><span class="sxs-lookup"><span data-stu-id="d6268-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="d6268-119">`Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="d6268-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="d6268-120">\<>を削除する</span><span class="sxs-lookup"><span data-stu-id="d6268-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="d6268-121">`Listeners`コレクションからリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d6268-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="d6268-122">\<クリア></span><span class="sxs-lookup"><span data-stu-id="d6268-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="d6268-123">トレース ソースの `Listeners` コレクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="d6268-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d6268-124">親要素</span><span class="sxs-lookup"><span data-stu-id="d6268-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d6268-125">要素</span><span class="sxs-lookup"><span data-stu-id="d6268-125">Element</span></span>|<span data-ttu-id="d6268-126">説明</span><span class="sxs-lookup"><span data-stu-id="d6268-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d6268-127">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="d6268-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d6268-128">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6268-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="d6268-129">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="d6268-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="d6268-130">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6268-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6268-131">解説</span><span class="sxs-lookup"><span data-stu-id="d6268-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="d6268-132">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="d6268-132">Configuration File</span></span>  
 <span data-ttu-id="d6268-133">この要素は、コンピューター構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6268-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6268-134">例</span><span class="sxs-lookup"><span data-stu-id="d6268-134">Example</span></span>  
 <span data-ttu-id="d6268-135">次の例は、要素を`<listeners>`使用して、ソースにコンソール トレース リスナー`mySource`を追加し、既定のトレース リスナーを削除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d6268-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d6268-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6268-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="d6268-137">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="d6268-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d6268-138">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="d6268-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
