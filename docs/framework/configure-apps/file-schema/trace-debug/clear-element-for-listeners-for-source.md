---
title: <clear>の<listeners>要素<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 7f9ddd93d27c3619119702c82c9e8752dab1af7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153582"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="b92ee-102">\<ソース>の\<リスナー>の>要素\<をクリア</span><span class="sxs-lookup"><span data-stu-id="b92ee-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="b92ee-103">トレース ソースの `Listeners` コレクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="b92ee-103">Clears the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="b92ee-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b92ee-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b92ee-105">&nbsp;&nbsp;[**\<診断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="b92ee-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="b92ee-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ソース>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="b92ee-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="b92ee-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ソース>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="b92ee-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="b92ee-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<リスナー>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="b92ee-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="b92ee-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<クリア>**</span><span class="sxs-lookup"><span data-stu-id="b92ee-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b92ee-110">構文</span><span class="sxs-lookup"><span data-stu-id="b92ee-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b92ee-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b92ee-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b92ee-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b92ee-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b92ee-113">属性</span><span class="sxs-lookup"><span data-stu-id="b92ee-113">Attributes</span></span>  
 <span data-ttu-id="b92ee-114">[なし] :</span><span class="sxs-lookup"><span data-stu-id="b92ee-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b92ee-115">子要素</span><span class="sxs-lookup"><span data-stu-id="b92ee-115">Child Elements</span></span>  
 <span data-ttu-id="b92ee-116">[なし] :</span><span class="sxs-lookup"><span data-stu-id="b92ee-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b92ee-117">親要素</span><span class="sxs-lookup"><span data-stu-id="b92ee-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b92ee-118">要素</span><span class="sxs-lookup"><span data-stu-id="b92ee-118">Element</span></span>|<span data-ttu-id="b92ee-119">説明</span><span class="sxs-lookup"><span data-stu-id="b92ee-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b92ee-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b92ee-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b92ee-121">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b92ee-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="b92ee-122">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="b92ee-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="b92ee-123">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="b92ee-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="b92ee-124">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b92ee-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b92ee-125">解説</span><span class="sxs-lookup"><span data-stu-id="b92ee-125">Remarks</span></span>  
 <span data-ttu-id="b92ee-126">要素`<clear>`は、トレース ソースの`Listeners`コレクションからすべてのリスナーを削除します。 <xref:System.Diagnostics.DefaultTraceListener></span><span class="sxs-lookup"><span data-stu-id="b92ee-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="b92ee-127">要素を`<clear>`使用する前に要素を`<add>`使用して、コレクション内に他のアクティブなリスナーがないことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b92ee-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="b92ee-128">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="b92ee-128">Configuration File</span></span>  
 <span data-ttu-id="b92ee-129">この要素は、コンピューター構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b92ee-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b92ee-130">例</span><span class="sxs-lookup"><span data-stu-id="b92ee-130">Example</span></span>  
 <span data-ttu-id="b92ee-131">`<clear>`次の例では、`<add>`要素を使用して、トレース ソースのリスナー`console`と`textListener``Listeners`コレクションを追加する前に、要素を使用`TraceSourceApp`する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b92ee-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b92ee-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="b92ee-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="b92ee-133">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="b92ee-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b92ee-134">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="b92ee-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
