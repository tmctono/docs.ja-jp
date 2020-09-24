---
title: <clear> のの <listeners> 要素 <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: d3e76496c82b508feabf8a46cf7bce7e3d54e8cf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149284"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="73abb-102">\<clear> のの \<listeners> 要素 \<source></span><span class="sxs-lookup"><span data-stu-id="73abb-102">\<clear> Element for \<listeners> for \<source></span></span>

<span data-ttu-id="73abb-103">トレース ソースの `Listeners` コレクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="73abb-103">Clears the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="73abb-104">構文</span><span class="sxs-lookup"><span data-stu-id="73abb-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73abb-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="73abb-105">Attributes and Elements</span></span>  

 <span data-ttu-id="73abb-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="73abb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73abb-107">属性</span><span class="sxs-lookup"><span data-stu-id="73abb-107">Attributes</span></span>  

 <span data-ttu-id="73abb-108">なし。</span><span class="sxs-lookup"><span data-stu-id="73abb-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="73abb-109">子要素</span><span class="sxs-lookup"><span data-stu-id="73abb-109">Child Elements</span></span>  

 <span data-ttu-id="73abb-110">なし。</span><span class="sxs-lookup"><span data-stu-id="73abb-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73abb-111">親要素</span><span class="sxs-lookup"><span data-stu-id="73abb-111">Parent Elements</span></span>  
  
|<span data-ttu-id="73abb-112">要素</span><span class="sxs-lookup"><span data-stu-id="73abb-112">Element</span></span>|<span data-ttu-id="73abb-113">説明</span><span class="sxs-lookup"><span data-stu-id="73abb-113">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="73abb-114">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="73abb-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="73abb-115">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="73abb-115">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="73abb-116">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="73abb-116">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="73abb-117">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="73abb-117">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="73abb-118">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="73abb-118">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73abb-119">解説</span><span class="sxs-lookup"><span data-stu-id="73abb-119">Remarks</span></span>  

 <span data-ttu-id="73abb-120">`<clear>`要素は、を含む、 `Listeners` トレースソースのコレクションからすべてのリスナーを削除し <xref:System.Diagnostics.DefaultTraceListener> ます。</span><span class="sxs-lookup"><span data-stu-id="73abb-120">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="73abb-121">要素を使用 `<clear>` して、 `<add>` コレクション内に他のアクティブなリスナーが存在しないことを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="73abb-121">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="73abb-122">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="73abb-122">Configuration File</span></span>  

 <span data-ttu-id="73abb-123">この要素は、マシン構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="73abb-123">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73abb-124">例</span><span class="sxs-lookup"><span data-stu-id="73abb-124">Example</span></span>  

 <span data-ttu-id="73abb-125">次の例では、要素を使用し `<clear>` てリスナーを追加してから、 `<add>` `console` `textListener` `Listeners` トレースソースのコレクションに追加 `TraceSourceApp` する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="73abb-125">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73abb-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="73abb-126">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="73abb-127">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="73abb-127">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="73abb-128">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="73abb-128">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
