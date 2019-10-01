---
title: <trace> の <listeners> の <clear> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 0361580724351f8f42d058d5e20354e3335bac2f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699378"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="35b7e-102">\<trace @no__t の \< リスナー > の > 要素</span><span class="sxs-lookup"><span data-stu-id="35b7e-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="35b7e-103">トレースの `Listeners` コレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="35b7e-103">Clears the `Listeners` collection for trace.</span></span>  
  
[<span data-ttu-id="35b7e-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="35b7e-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="35b7e-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="35b7e-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="35b7e-106">&nbsp; @ no__t-1 @ no__t @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="35b7e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="35b7e-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5[ **\<listeners >** します。](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="35b7e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="35b7e-108">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 @ no__t-6 @ no__t-7 **\<clear > を削除**します。</span><span class="sxs-lookup"><span data-stu-id="35b7e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35b7e-109">構文</span><span class="sxs-lookup"><span data-stu-id="35b7e-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35b7e-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="35b7e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="35b7e-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="35b7e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35b7e-112">属性</span><span class="sxs-lookup"><span data-stu-id="35b7e-112">Attributes</span></span>  
 <span data-ttu-id="35b7e-113">[なし] :</span><span class="sxs-lookup"><span data-stu-id="35b7e-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="35b7e-114">子要素</span><span class="sxs-lookup"><span data-stu-id="35b7e-114">Child Elements</span></span>  
 <span data-ttu-id="35b7e-115">なし。</span><span class="sxs-lookup"><span data-stu-id="35b7e-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35b7e-116">親要素</span><span class="sxs-lookup"><span data-stu-id="35b7e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="35b7e-117">要素</span><span class="sxs-lookup"><span data-stu-id="35b7e-117">Element</span></span>|<span data-ttu-id="35b7e-118">説明</span><span class="sxs-lookup"><span data-stu-id="35b7e-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="35b7e-119">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="35b7e-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="35b7e-120">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="35b7e-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="35b7e-121">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="35b7e-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="35b7e-122">メッセージを収集、格納、およびルーティングするリスナーを格納します。</span><span class="sxs-lookup"><span data-stu-id="35b7e-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="35b7e-123">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="35b7e-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35b7e-124">コメント</span><span class="sxs-lookup"><span data-stu-id="35b7e-124">Remarks</span></span>  
 <span data-ttu-id="35b7e-125">@No__t-0 要素は、トレースの `Listeners` コレクションからすべてのリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="35b7e-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="35b7e-126">@No__t-1 要素を使用して、コレクション内に他のアクティブなリスナーが存在しないことを特定するには、`<clear>` 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="35b7e-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="35b7e-127">@No__t-2 プロパティの <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> メソッド (`System.Diagnostics.Trace.Listeners.Clear()`) を呼び出すことで、プログラムによって @no__t 0 のコレクションを消去できます。</span><span class="sxs-lookup"><span data-stu-id="35b7e-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="35b7e-128">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="35b7e-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35b7e-129">@No__t-0 要素は、`Listeners` コレクションから <xref:System.Diagnostics.DefaultTraceListener> を削除し、<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>、@no__t 4、<xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>、および @no__t 6 の各メソッドの動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="35b7e-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="35b7e-130">通常、`Assert` または `Fail` メソッドを呼び出すと、メッセージボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35b7e-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="35b7e-131">ただし、<xref:System.Diagnostics.DefaultTraceListener> が `Listeners` コレクションに含まれていない場合、メッセージボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="35b7e-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35b7e-132">例</span><span class="sxs-lookup"><span data-stu-id="35b7e-132">Example</span></span>  
 <span data-ttu-id="35b7e-133">次の例では、`<clear>` の要素を使用して、`<add>` の要素を使用してリスナー `console` をトレースの `Listeners` コレクションに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="35b7e-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="35b7e-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="35b7e-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="35b7e-135">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="35b7e-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="35b7e-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="35b7e-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="35b7e-137">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="35b7e-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
