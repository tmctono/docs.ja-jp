---
title: <clear> の <listeners> の <source> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 768d51a74b4c31d1250d2f5d6517f760f886e0a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920558"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="f18de-102">\<ソース > の\<リスナー \<> の > 要素をクリアします</span><span class="sxs-lookup"><span data-stu-id="f18de-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="f18de-103">トレース ソースの `Listeners` コレクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="f18de-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="f18de-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f18de-104">\<configuration></span></span>  
<span data-ttu-id="f18de-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="f18de-105">\<system.diagnostics></span></span>  
<span data-ttu-id="f18de-106">\<ソース ></span><span class="sxs-lookup"><span data-stu-id="f18de-106">\<sources></span></span>  
<span data-ttu-id="f18de-107">\<ソース ></span><span class="sxs-lookup"><span data-stu-id="f18de-107">\<source></span></span>  
<span data-ttu-id="f18de-108">\<リスナー ></span><span class="sxs-lookup"><span data-stu-id="f18de-108">\<listeners></span></span>  
<span data-ttu-id="f18de-109">\<clear></span><span class="sxs-lookup"><span data-stu-id="f18de-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f18de-110">構文</span><span class="sxs-lookup"><span data-stu-id="f18de-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f18de-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f18de-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f18de-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f18de-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f18de-113">属性</span><span class="sxs-lookup"><span data-stu-id="f18de-113">Attributes</span></span>  
 <span data-ttu-id="f18de-114">なし。</span><span class="sxs-lookup"><span data-stu-id="f18de-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f18de-115">子要素</span><span class="sxs-lookup"><span data-stu-id="f18de-115">Child Elements</span></span>  
 <span data-ttu-id="f18de-116">なし。</span><span class="sxs-lookup"><span data-stu-id="f18de-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f18de-117">親要素</span><span class="sxs-lookup"><span data-stu-id="f18de-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f18de-118">要素</span><span class="sxs-lookup"><span data-stu-id="f18de-118">Element</span></span>|<span data-ttu-id="f18de-119">説明</span><span class="sxs-lookup"><span data-stu-id="f18de-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f18de-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="f18de-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f18de-121">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f18de-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="f18de-122">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="f18de-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="f18de-123">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="f18de-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="f18de-124">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f18de-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f18de-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="f18de-125">Remarks</span></span>  
 <span data-ttu-id="f18de-126">要素`<clear>`は`Listeners` 、<xref:System.Diagnostics.DefaultTraceListener>を含む、トレースソースのコレクションからすべてのリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="f18de-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="f18de-127">要素を使用`<add>`し`<clear>`て、コレクション内に他のアクティブなリスナーが存在しないことを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="f18de-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="f18de-128">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="f18de-128">Configuration File</span></span>  
 <span data-ttu-id="f18de-129">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f18de-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f18de-130">例</span><span class="sxs-lookup"><span data-stu-id="f18de-130">Example</span></span>  
 <span data-ttu-id="f18de-131">次の例では、要素を`<clear>`使用し`<add>`て`console`リスナー `textListener`を追加してから、トレースソース`Listeners` `TraceSourceApp`のコレクションに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f18de-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f18de-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="f18de-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="f18de-133">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="f18de-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f18de-134">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="f18de-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
