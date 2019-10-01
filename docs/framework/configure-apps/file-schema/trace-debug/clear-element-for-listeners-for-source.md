---
title: <source> の <listeners> の <clear> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 05c20040ef59f4dee6b15bbe0b0369281b532754
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697185"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="360b9-102">\<source > の \< リスナー > の @no__t 0clear > 要素</span><span class="sxs-lookup"><span data-stu-id="360b9-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="360b9-103">トレース ソースの `Listeners` コレクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="360b9-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="360b9-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="360b9-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="360b9-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="360b9-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="360b9-106">&nbsp; @ no__t-1 @ no__t no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="360b9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="360b9-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5[ **\<source >** になります。](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="360b9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="360b9-108">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listeners** (&) >](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="360b9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="360b9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="360b9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="360b9-110">構文</span><span class="sxs-lookup"><span data-stu-id="360b9-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="360b9-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="360b9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="360b9-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="360b9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="360b9-113">属性</span><span class="sxs-lookup"><span data-stu-id="360b9-113">Attributes</span></span>  
 <span data-ttu-id="360b9-114">[なし] :</span><span class="sxs-lookup"><span data-stu-id="360b9-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="360b9-115">子要素</span><span class="sxs-lookup"><span data-stu-id="360b9-115">Child Elements</span></span>  
 <span data-ttu-id="360b9-116">なし。</span><span class="sxs-lookup"><span data-stu-id="360b9-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="360b9-117">親要素</span><span class="sxs-lookup"><span data-stu-id="360b9-117">Parent Elements</span></span>  
  
|<span data-ttu-id="360b9-118">要素</span><span class="sxs-lookup"><span data-stu-id="360b9-118">Element</span></span>|<span data-ttu-id="360b9-119">説明</span><span class="sxs-lookup"><span data-stu-id="360b9-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="360b9-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="360b9-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="360b9-121">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="360b9-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="360b9-122">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="360b9-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="360b9-123">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="360b9-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="360b9-124">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="360b9-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="360b9-125">コメント</span><span class="sxs-lookup"><span data-stu-id="360b9-125">Remarks</span></span>  
 <span data-ttu-id="360b9-126">@No__t-0 要素は、<xref:System.Diagnostics.DefaultTraceListener> を含む、トレースソースの `Listeners` コレクションからすべてのリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="360b9-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="360b9-127">@No__t-1 要素を使用して、コレクション内に他のアクティブなリスナーが存在しないことを特定するには、`<clear>` 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="360b9-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="360b9-128">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="360b9-128">Configuration File</span></span>  
 <span data-ttu-id="360b9-129">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="360b9-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="360b9-130">例</span><span class="sxs-lookup"><span data-stu-id="360b9-130">Example</span></span>  
 <span data-ttu-id="360b9-131">次の例では、`<clear>` の要素を使用してから、`<add>` の要素を使用してリスナー `console` と @no__t をトレースソースの @no__t 4 コレクションに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="360b9-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="360b9-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="360b9-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="360b9-133">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="360b9-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="360b9-134">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="360b9-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
