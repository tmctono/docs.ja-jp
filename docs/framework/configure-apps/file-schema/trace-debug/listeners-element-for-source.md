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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153413"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="948c8-102">\<source> の \<listeners> 要素</span><span class="sxs-lookup"><span data-stu-id="948c8-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="948c8-103">のコレクション内のリスナーを追加または削除 <xref:System.Diagnostics.TraceSource.Listeners%2A> <xref:System.Diagnostics.TraceSource> します。</span><span class="sxs-lookup"><span data-stu-id="948c8-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="948c8-104">リスナーは、ログ、ウィンドウ、テキストファイルなど、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="948c8-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**  
  
## <a name="syntax"></a><span data-ttu-id="948c8-105">構文</span><span class="sxs-lookup"><span data-stu-id="948c8-105">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="948c8-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="948c8-106">Attributes and Elements</span></span>  
 <span data-ttu-id="948c8-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="948c8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="948c8-108">属性</span><span class="sxs-lookup"><span data-stu-id="948c8-108">Attributes</span></span>  
 <span data-ttu-id="948c8-109">なし。</span><span class="sxs-lookup"><span data-stu-id="948c8-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="948c8-110">子要素</span><span class="sxs-lookup"><span data-stu-id="948c8-110">Child Elements</span></span>  
  
|<span data-ttu-id="948c8-111">要素</span><span class="sxs-lookup"><span data-stu-id="948c8-111">Element</span></span>|<span data-ttu-id="948c8-112">説明</span><span class="sxs-lookup"><span data-stu-id="948c8-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-source.md)|<span data-ttu-id="948c8-113">`Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="948c8-113">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="948c8-114">コレクションからリスナーを削除 `Listeners` します。</span><span class="sxs-lookup"><span data-stu-id="948c8-114">Removes a listener from the `Listeners` collection.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="948c8-115">トレース ソースの `Listeners` コレクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="948c8-115">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="948c8-116">親要素</span><span class="sxs-lookup"><span data-stu-id="948c8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="948c8-117">要素</span><span class="sxs-lookup"><span data-stu-id="948c8-117">Element</span></span>|<span data-ttu-id="948c8-118">説明</span><span class="sxs-lookup"><span data-stu-id="948c8-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="948c8-119">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="948c8-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="948c8-120">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="948c8-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="948c8-121">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="948c8-121">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="948c8-122">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="948c8-122">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="948c8-123">解説</span><span class="sxs-lookup"><span data-stu-id="948c8-123">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="948c8-124">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="948c8-124">Configuration File</span></span>  
 <span data-ttu-id="948c8-125">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="948c8-125">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="948c8-126">例</span><span class="sxs-lookup"><span data-stu-id="948c8-126">Example</span></span>  
 <span data-ttu-id="948c8-127">次の例は、要素を使用して、 `<listeners>` コンソールトレースリスナーをソースに追加し、既定のトレースリスナーを削除する方法を示して `mySource` います。</span><span class="sxs-lookup"><span data-stu-id="948c8-127">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="948c8-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="948c8-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="948c8-129">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="948c8-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="948c8-130">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="948c8-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
