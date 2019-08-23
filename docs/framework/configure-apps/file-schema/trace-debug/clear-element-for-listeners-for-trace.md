---
title: <clear> の <listeners> の <trace> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 9816ba0f8e4ddd4c38537eb4e014a4240ff20407
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927180"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="d8d56-102">\<トレース > の\<リスナー \<> の > 要素をクリアします</span><span class="sxs-lookup"><span data-stu-id="d8d56-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="d8d56-103">トレースの `Listeners` コレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="d8d56-103">Clears the `Listeners` collection for trace.</span></span>  
  
 <span data-ttu-id="d8d56-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d8d56-104">\<configuration></span></span>  
<span data-ttu-id="d8d56-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="d8d56-105">\<system.diagnostics></span></span>  
<span data-ttu-id="d8d56-106">\<トレース ></span><span class="sxs-lookup"><span data-stu-id="d8d56-106">\<trace></span></span>  
<span data-ttu-id="d8d56-107">\<リスナー ></span><span class="sxs-lookup"><span data-stu-id="d8d56-107">\<listeners></span></span>  
<span data-ttu-id="d8d56-108">\<clear></span><span class="sxs-lookup"><span data-stu-id="d8d56-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8d56-109">構文</span><span class="sxs-lookup"><span data-stu-id="d8d56-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8d56-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d8d56-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d8d56-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d8d56-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8d56-112">属性</span><span class="sxs-lookup"><span data-stu-id="d8d56-112">Attributes</span></span>  
 <span data-ttu-id="d8d56-113">なし。</span><span class="sxs-lookup"><span data-stu-id="d8d56-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d8d56-114">子要素</span><span class="sxs-lookup"><span data-stu-id="d8d56-114">Child Elements</span></span>  
 <span data-ttu-id="d8d56-115">なし。</span><span class="sxs-lookup"><span data-stu-id="d8d56-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8d56-116">親要素</span><span class="sxs-lookup"><span data-stu-id="d8d56-116">Parent Elements</span></span>  
  
|<span data-ttu-id="d8d56-117">要素</span><span class="sxs-lookup"><span data-stu-id="d8d56-117">Element</span></span>|<span data-ttu-id="d8d56-118">説明</span><span class="sxs-lookup"><span data-stu-id="d8d56-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d8d56-119">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="d8d56-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d8d56-120">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8d56-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="d8d56-121">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="d8d56-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="d8d56-122">メッセージを収集、格納、およびルーティングするリスナーを格納します。</span><span class="sxs-lookup"><span data-stu-id="d8d56-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="d8d56-123">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="d8d56-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8d56-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="d8d56-124">Remarks</span></span>  
 <span data-ttu-id="d8d56-125">要素`<clear>`は、トレースの`Listeners`コレクションからすべてのリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d8d56-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="d8d56-126">要素を使用`<add>`し`<clear>`て、コレクション内に他のアクティブなリスナーが存在しないことを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="d8d56-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="d8d56-127">コレクションは、 `Listeners` <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType>プロパティ ( <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> )でメソッドを呼び出すことで、プログラムによって消去できます。`System.Diagnostics.Trace.Listeners.Clear()`</span><span class="sxs-lookup"><span data-stu-id="d8d56-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="d8d56-128">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8d56-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8d56-129">要素`<clear>`は、、 <xref:System.Diagnostics.DefaultTraceListener> 、 <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>、 `Listeners`および<xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>の各メソッドの動作を変更して、をコレクションから削除します。<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d8d56-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="d8d56-130">通常、 `Assert`メソッド`Fail`またはメソッドを呼び出すと、メッセージボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8d56-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="d8d56-131">ただし、 <xref:System.Diagnostics.DefaultTraceListener>が`Listeners`コレクションに含まれていない場合、メッセージボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="d8d56-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8d56-132">例</span><span class="sxs-lookup"><span data-stu-id="d8d56-132">Example</span></span>  
 <span data-ttu-id="d8d56-133">次の例では、要素を`<clear>`使用し`<add>`て、トレースの`Listeners`コレクションにリスナー `console`を追加する前に、要素を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d8d56-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d8d56-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8d56-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="d8d56-135">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="d8d56-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d8d56-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="d8d56-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="d8d56-137">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="d8d56-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
