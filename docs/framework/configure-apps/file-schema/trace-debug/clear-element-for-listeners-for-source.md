---
title: <clear> の <listeners> の <source> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 63d3bb272fcdbee2c59b0569c85f8183cdac8666
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673786"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="d4aa4-102">\<クリア > 要素の\<リスナー > の\<ソース ></span><span class="sxs-lookup"><span data-stu-id="d4aa4-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="d4aa4-103">トレース ソースの `Listeners` コレクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="d4aa4-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="d4aa4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d4aa4-104">\<configuration></span></span>  
<span data-ttu-id="d4aa4-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="d4aa4-105">\<system.diagnostics></span></span>  
<span data-ttu-id="d4aa4-106">\<ソース ></span><span class="sxs-lookup"><span data-stu-id="d4aa4-106">\<sources></span></span>  
<span data-ttu-id="d4aa4-107">\<ソース ></span><span class="sxs-lookup"><span data-stu-id="d4aa4-107">\<source></span></span>  
<span data-ttu-id="d4aa4-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="d4aa4-108">\<listeners></span></span>  
<span data-ttu-id="d4aa4-109">\<clear></span><span class="sxs-lookup"><span data-stu-id="d4aa4-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4aa4-110">構文</span><span class="sxs-lookup"><span data-stu-id="d4aa4-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4aa4-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d4aa4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d4aa4-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4aa4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4aa4-113">属性</span><span class="sxs-lookup"><span data-stu-id="d4aa4-113">Attributes</span></span>  
 <span data-ttu-id="d4aa4-114">なし。</span><span class="sxs-lookup"><span data-stu-id="d4aa4-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d4aa4-115">子要素</span><span class="sxs-lookup"><span data-stu-id="d4aa4-115">Child Elements</span></span>  
 <span data-ttu-id="d4aa4-116">なし。</span><span class="sxs-lookup"><span data-stu-id="d4aa4-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4aa4-117">親要素</span><span class="sxs-lookup"><span data-stu-id="d4aa4-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d4aa4-118">要素</span><span class="sxs-lookup"><span data-stu-id="d4aa4-118">Element</span></span>|<span data-ttu-id="d4aa4-119">説明</span><span class="sxs-lookup"><span data-stu-id="d4aa4-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d4aa4-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="d4aa4-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d4aa4-121">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4aa4-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="d4aa4-122">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="d4aa4-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="d4aa4-123">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4aa4-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="d4aa4-124">収集、格納、およびメッセージをルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4aa4-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4aa4-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="d4aa4-125">Remarks</span></span>  
 <span data-ttu-id="d4aa4-126">`<clear>`要素からすべてのリスナーを削除して、`Listeners`トレース ソースのコレクションを含む、 <xref:System.Diagnostics.DefaultTraceListener>。</span><span class="sxs-lookup"><span data-stu-id="d4aa4-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="d4aa4-127">使用することができます、`<clear>`要素を使用する前に、`<add>`要素をコレクション内の他のアクティブなリスナーが存在しないことを特定します。</span><span class="sxs-lookup"><span data-stu-id="d4aa4-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="d4aa4-128">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="d4aa4-128">Configuration File</span></span>  
 <span data-ttu-id="d4aa4-129">この要素は、マシン構成ファイル (Machine.config) と、アプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4aa4-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4aa4-130">例</span><span class="sxs-lookup"><span data-stu-id="d4aa4-130">Example</span></span>  
 <span data-ttu-id="d4aa4-131">次の例は、使用する方法を示します、`<clear>`要素を使用する前に、`<add>`リスナーを追加する要素`console`と`textListener`を`Listeners`トレース ソースのコレクション`TraceSourceApp`します。</span><span class="sxs-lookup"><span data-stu-id="d4aa4-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="d4aa4-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4aa4-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="d4aa4-133">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="d4aa4-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="d4aa4-134">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="d4aa4-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
