---
title: <clear> の <listeners> の <trace> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 97b18f9d6baa618b0f535955b232e2119c758b11
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701321"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="1420f-102">\<クリア > 要素の\<リスナー > の\<トレース ></span><span class="sxs-lookup"><span data-stu-id="1420f-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="1420f-103">トレースの `Listeners` コレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="1420f-103">Clears the `Listeners` collection for trace.</span></span>  
  
 <span data-ttu-id="1420f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1420f-104">\<configuration></span></span>  
<span data-ttu-id="1420f-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="1420f-105">\<system.diagnostics></span></span>  
<span data-ttu-id="1420f-106">\<トレース ></span><span class="sxs-lookup"><span data-stu-id="1420f-106">\<trace></span></span>  
<span data-ttu-id="1420f-107">\<listeners></span><span class="sxs-lookup"><span data-stu-id="1420f-107">\<listeners></span></span>  
<span data-ttu-id="1420f-108">\<clear></span><span class="sxs-lookup"><span data-stu-id="1420f-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1420f-109">構文</span><span class="sxs-lookup"><span data-stu-id="1420f-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1420f-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1420f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1420f-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1420f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1420f-112">属性</span><span class="sxs-lookup"><span data-stu-id="1420f-112">Attributes</span></span>  
 <span data-ttu-id="1420f-113">なし。</span><span class="sxs-lookup"><span data-stu-id="1420f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1420f-114">子要素</span><span class="sxs-lookup"><span data-stu-id="1420f-114">Child Elements</span></span>  
 <span data-ttu-id="1420f-115">なし。</span><span class="sxs-lookup"><span data-stu-id="1420f-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1420f-116">親要素</span><span class="sxs-lookup"><span data-stu-id="1420f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1420f-117">要素</span><span class="sxs-lookup"><span data-stu-id="1420f-117">Element</span></span>|<span data-ttu-id="1420f-118">説明</span><span class="sxs-lookup"><span data-stu-id="1420f-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1420f-119">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="1420f-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="1420f-120">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="1420f-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="1420f-121">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="1420f-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="1420f-122">収集、格納、およびメッセージをルーティングするリスナーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1420f-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="1420f-123">リスナーでは、適切なターゲットのトレースを出力します。</span><span class="sxs-lookup"><span data-stu-id="1420f-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1420f-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="1420f-124">Remarks</span></span>  
 <span data-ttu-id="1420f-125">`<clear>`要素からすべてのリスナーを削除して、`Listeners`トレースのコレクション。</span><span class="sxs-lookup"><span data-stu-id="1420f-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="1420f-126">使用することができます、`<clear>`要素を使用する前に、`<add>`要素をコレクション内の他のアクティブなリスナーが存在しないことを特定します。</span><span class="sxs-lookup"><span data-stu-id="1420f-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="1420f-127">オフにすることができます、`Listeners`呼び出すことによってプログラムでのコレクション、<xref:System.Diagnostics.TraceListenerCollection.Clear%2A>メソッドを<xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType>プロパティ (`System.Diagnostics.Trace.Listeners.Clear()`)。</span><span class="sxs-lookup"><span data-stu-id="1420f-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="1420f-128">この要素は、マシン構成ファイル (Machine.config) と、アプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1420f-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1420f-129">`<clear>`要素は、削除、<xref:System.Diagnostics.DefaultTraceListener>から、`Listeners`の動作を変更するコレクション、 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>、 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>、 <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>、および<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="1420f-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="1420f-130">呼び出す、`Assert`または`Fail`メソッドは、通常、メッセージ ボックスの表示になります。</span><span class="sxs-lookup"><span data-stu-id="1420f-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="1420f-131">場合、メッセージ ボックスが表示されません、<xref:System.Diagnostics.DefaultTraceListener>内にない、`Listeners`コレクション。</span><span class="sxs-lookup"><span data-stu-id="1420f-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1420f-132">例</span><span class="sxs-lookup"><span data-stu-id="1420f-132">Example</span></span>  
 <span data-ttu-id="1420f-133">次の例は、使用する方法を示します、`<clear>`要素を使用する前に、`<add>`リスナーを追加する要素`console`を`Listeners`トレースのコレクション。</span><span class="sxs-lookup"><span data-stu-id="1420f-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1420f-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="1420f-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="1420f-135">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="1420f-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="1420f-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="1420f-136">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="1420f-137">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="1420f-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
