---
title: <clear>のの <listeners> 要素<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153543"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="8dedb-102">\<clear>のの \<listeners> 要素\<trace></span><span class="sxs-lookup"><span data-stu-id="8dedb-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="8dedb-103">トレースの `Listeners` コレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="8dedb-103">Clears the `Listeners` collection for trace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="8dedb-104">構文</span><span class="sxs-lookup"><span data-stu-id="8dedb-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8dedb-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8dedb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8dedb-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8dedb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8dedb-107">属性</span><span class="sxs-lookup"><span data-stu-id="8dedb-107">Attributes</span></span>  
 <span data-ttu-id="8dedb-108">なし。</span><span class="sxs-lookup"><span data-stu-id="8dedb-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8dedb-109">子要素</span><span class="sxs-lookup"><span data-stu-id="8dedb-109">Child Elements</span></span>  
 <span data-ttu-id="8dedb-110">[なし] :</span><span class="sxs-lookup"><span data-stu-id="8dedb-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8dedb-111">親要素</span><span class="sxs-lookup"><span data-stu-id="8dedb-111">Parent Elements</span></span>  
  
|<span data-ttu-id="8dedb-112">要素</span><span class="sxs-lookup"><span data-stu-id="8dedb-112">Element</span></span>|<span data-ttu-id="8dedb-113">説明</span><span class="sxs-lookup"><span data-stu-id="8dedb-113">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8dedb-114">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="8dedb-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="8dedb-115">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="8dedb-115">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="8dedb-116">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="8dedb-116">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="8dedb-117">メッセージを収集、格納、およびルーティングするリスナーを格納します。</span><span class="sxs-lookup"><span data-stu-id="8dedb-117">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="8dedb-118">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="8dedb-118">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8dedb-119">解説</span><span class="sxs-lookup"><span data-stu-id="8dedb-119">Remarks</span></span>  
 <span data-ttu-id="8dedb-120">要素は、 `<clear>` トレースのコレクションからすべてのリスナーを削除し `Listeners` ます。</span><span class="sxs-lookup"><span data-stu-id="8dedb-120">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="8dedb-121">要素を使用 `<clear>` して、 `<add>` コレクション内に他のアクティブなリスナーが存在しないことを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="8dedb-121">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="8dedb-122">コレクションは、 `Listeners` <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> プロパティ () でメソッドを呼び出すことで、プログラムによって消去でき <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> `System.Diagnostics.Trace.Listeners.Clear()` ます。</span><span class="sxs-lookup"><span data-stu-id="8dedb-122">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="8dedb-123">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="8dedb-123">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8dedb-124">要素は、、、 `<clear>` <xref:System.Diagnostics.DefaultTraceListener> `Listeners` 、およびの各メソッドの動作を変更して、をコレクションから削除し <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="8dedb-124">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="8dedb-125">通常、 `Assert` メソッドまたはメソッドを呼び出すと `Fail` 、メッセージボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8dedb-125">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="8dedb-126">ただし、 <xref:System.Diagnostics.DefaultTraceListener> がコレクションに含まれていない場合、メッセージボックスは表示されません `Listeners` 。</span><span class="sxs-lookup"><span data-stu-id="8dedb-126">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8dedb-127">例</span><span class="sxs-lookup"><span data-stu-id="8dedb-127">Example</span></span>  
 <span data-ttu-id="8dedb-128">次の例では、要素を使用し `<clear>` て、 `<add>` `console` `Listeners` トレースのコレクションにリスナーを追加する前に、要素を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8dedb-128">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8dedb-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="8dedb-129">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="8dedb-130">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="8dedb-130">Trace and Debug Settings Schema</span></span>](index.md)
- [\<remove>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="8dedb-131">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="8dedb-131">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
