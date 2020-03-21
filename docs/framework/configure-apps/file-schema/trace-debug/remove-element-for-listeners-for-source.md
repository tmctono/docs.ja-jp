---
title: <remove>の<listeners>要素<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 657e6db2af9b99b3bbf03afc6aab02c58a830f2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153336"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="b7841-102">\<ソース>>の\<リスナー>要素を\<削除します</span><span class="sxs-lookup"><span data-stu-id="b7841-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="b7841-103">トレース ソースの `Listeners` コレクションからリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b7841-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="b7841-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b7841-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b7841-105">&nbsp;&nbsp;[**\<診断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="b7841-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="b7841-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ソース>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="b7841-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="b7841-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ソース>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="b7841-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="b7841-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<リスナー>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="b7841-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="b7841-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>を削除する**</span><span class="sxs-lookup"><span data-stu-id="b7841-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b7841-110">構文</span><span class="sxs-lookup"><span data-stu-id="b7841-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7841-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b7841-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b7841-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7841-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7841-113">属性</span><span class="sxs-lookup"><span data-stu-id="b7841-113">Attributes</span></span>  
  
|<span data-ttu-id="b7841-114">属性</span><span class="sxs-lookup"><span data-stu-id="b7841-114">Attribute</span></span>|<span data-ttu-id="b7841-115">説明</span><span class="sxs-lookup"><span data-stu-id="b7841-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="b7841-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="b7841-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="b7841-117">コレクションから削除するリスナーの`Listeners`名前。</span><span class="sxs-lookup"><span data-stu-id="b7841-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7841-118">子要素</span><span class="sxs-lookup"><span data-stu-id="b7841-118">Child Elements</span></span>  
 <span data-ttu-id="b7841-119">[なし] :</span><span class="sxs-lookup"><span data-stu-id="b7841-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7841-120">親要素</span><span class="sxs-lookup"><span data-stu-id="b7841-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b7841-121">要素</span><span class="sxs-lookup"><span data-stu-id="b7841-121">Element</span></span>|<span data-ttu-id="b7841-122">説明</span><span class="sxs-lookup"><span data-stu-id="b7841-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b7841-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b7841-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b7841-124">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7841-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="b7841-125">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="b7841-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="b7841-126">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7841-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="b7841-127">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7841-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7841-128">解説</span><span class="sxs-lookup"><span data-stu-id="b7841-128">Remarks</span></span>  
 <span data-ttu-id="b7841-129">要素`<remove>`は、トレース ソースの`Listeners`コレクションから指定されたリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b7841-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="b7841-130">インスタンスのプロパティ`Listeners`のメソッドを呼び出すことによって、トレース ソースの<xref:System.Diagnostics.TraceListenerCollection.Remove%2A>コレクションから要素を<xref:System.Diagnostics.TraceSource.Listeners%2A><xref:System.Diagnostics.TraceSource>プログラムで削除できます。</span><span class="sxs-lookup"><span data-stu-id="b7841-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="b7841-131">この要素は、コンピューター構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7841-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7841-132">例</span><span class="sxs-lookup"><span data-stu-id="b7841-132">Example</span></span>  
 <span data-ttu-id="b7841-133">次`<remove>`の例は、`<add>`要素を使用してトレース ソース`console``Listeners``TraceSourceApp`のコレクションにリスナーを追加する前に、要素を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b7841-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="b7841-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7841-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="b7841-135">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="b7841-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b7841-136">\<クリア></span><span class="sxs-lookup"><span data-stu-id="b7841-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="b7841-137">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="b7841-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
