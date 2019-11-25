---
title: <trace> の <listeners> の <clear> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 049b8e7ed17633c0f34b062915afaf719927dad6
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088916"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="4e4a3-102">\<トレース > の \<リスナー > のクリア > 要素を \<します</span><span class="sxs-lookup"><span data-stu-id="4e4a3-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="4e4a3-103">トレースの `Listeners` コレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-103">Clears the `Listeners` collection for trace.</span></span>  

<span data-ttu-id="4e4a3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4e4a3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4e4a3-105">&nbsp;&nbsp;[ **\<** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="4e4a3-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="4e4a3-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**トレース >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="4e4a3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="4e4a3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**リスナー >** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="4e4a3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="4e4a3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**クリア >**</span><span class="sxs-lookup"><span data-stu-id="4e4a3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4e4a3-109">構文</span><span class="sxs-lookup"><span data-stu-id="4e4a3-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e4a3-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4e4a3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4e4a3-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e4a3-112">属性</span><span class="sxs-lookup"><span data-stu-id="4e4a3-112">Attributes</span></span>  
 <span data-ttu-id="4e4a3-113">なし。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4e4a3-114">子要素</span><span class="sxs-lookup"><span data-stu-id="4e4a3-114">Child Elements</span></span>  
 <span data-ttu-id="4e4a3-115">なし。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e4a3-116">親要素</span><span class="sxs-lookup"><span data-stu-id="4e4a3-116">Parent Elements</span></span>  
  
|<span data-ttu-id="4e4a3-117">要素</span><span class="sxs-lookup"><span data-stu-id="4e4a3-117">Element</span></span>|<span data-ttu-id="4e4a3-118">説明</span><span class="sxs-lookup"><span data-stu-id="4e4a3-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4e4a3-119">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4e4a3-120">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="4e4a3-121">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="4e4a3-122">メッセージを収集、格納、およびルーティングするリスナーを格納します。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="4e4a3-123">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e4a3-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="4e4a3-124">Remarks</span></span>  
 <span data-ttu-id="4e4a3-125">`<clear>` 要素は、トレースの `Listeners` コレクションからすべてのリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="4e4a3-126">`<add>` 要素を使用して、コレクション内に他のアクティブなリスナーが存在しないことを特定するには、`<clear>` 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="4e4a3-127"><xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> プロパティ (`System.Diagnostics.Trace.Listeners.Clear()`) で <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> メソッドを呼び出すことによって、`Listeners` コレクションをプログラムでクリアできます。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="4e4a3-128">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4e4a3-129">`<clear>` 要素は `Listeners` コレクションから <xref:System.Diagnostics.DefaultTraceListener> を削除し、<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>、<xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>、<xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>、および <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> の各メソッドの動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="4e4a3-130">`Assert` または `Fail` メソッドを呼び出すと、通常、メッセージボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="4e4a3-131">ただし、<xref:System.Diagnostics.DefaultTraceListener> が `Listeners` コレクションに含まれていない場合、メッセージボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e4a3-132">例</span><span class="sxs-lookup"><span data-stu-id="4e4a3-132">Example</span></span>  
 <span data-ttu-id="4e4a3-133">次の例は、`<add>` 要素を使用してリスナー `console` をトレースの `Listeners` コレクションに追加する前に、`<clear>` 要素を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4e4a3-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="4e4a3-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e4a3-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="4e4a3-135">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="4e4a3-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4e4a3-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="4e4a3-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="4e4a3-137">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="4e4a3-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
