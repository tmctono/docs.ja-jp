---
title: <trace> の <listeners> の <remove> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 56d1e56514aed98d5f3b9f7363e461af6ac68a8c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697212"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="0f4eb-102">\<trace > の \< リスナーの > 要素を削除 @no__t</span><span class="sxs-lookup"><span data-stu-id="0f4eb-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="0f4eb-103">**リスナーコレクションから**リスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0f4eb-103">Removes a listener from the **Listeners** collection.</span></span>  
  
[<span data-ttu-id="0f4eb-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="0f4eb-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="0f4eb-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f4eb-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="0f4eb-106">&nbsp; @ no__t-1 @ no__t @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f4eb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="0f4eb-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5[ **\<listeners >** します。](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="0f4eb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="0f4eb-108">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 @ no__t-6 @ no__t-7 **\<remove を削除**します。</span><span class="sxs-lookup"><span data-stu-id="0f4eb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f4eb-109">構文</span><span class="sxs-lookup"><span data-stu-id="0f4eb-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f4eb-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0f4eb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0f4eb-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f4eb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f4eb-112">属性</span><span class="sxs-lookup"><span data-stu-id="0f4eb-112">Attributes</span></span>  
  
|<span data-ttu-id="0f4eb-113">属性</span><span class="sxs-lookup"><span data-stu-id="0f4eb-113">Attribute</span></span>|<span data-ttu-id="0f4eb-114">説明</span><span class="sxs-lookup"><span data-stu-id="0f4eb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0f4eb-115">**name**</span><span class="sxs-lookup"><span data-stu-id="0f4eb-115">**name**</span></span>|<span data-ttu-id="0f4eb-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="0f4eb-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="0f4eb-117">**リスナー**コレクションから削除するリスナーの名前。</span><span class="sxs-lookup"><span data-stu-id="0f4eb-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f4eb-118">子要素</span><span class="sxs-lookup"><span data-stu-id="0f4eb-118">Child Elements</span></span>  
 <span data-ttu-id="0f4eb-119">なし。</span><span class="sxs-lookup"><span data-stu-id="0f4eb-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f4eb-120">親要素</span><span class="sxs-lookup"><span data-stu-id="0f4eb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0f4eb-121">要素</span><span class="sxs-lookup"><span data-stu-id="0f4eb-121">Element</span></span>|<span data-ttu-id="0f4eb-122">説明</span><span class="sxs-lookup"><span data-stu-id="0f4eb-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0f4eb-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="0f4eb-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="0f4eb-124">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f4eb-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="0f4eb-125">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="0f4eb-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="0f4eb-126">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f4eb-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="0f4eb-127">ASP.NET トレースサービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="0f4eb-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f4eb-128">コメント</span><span class="sxs-lookup"><span data-stu-id="0f4eb-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f4eb-129">@No__t-0 を `Listeners` のコレクションから削除すると、<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>、<xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>、@no__t 4、および @no__t 5 の各メソッドの動作が変更されます。</span><span class="sxs-lookup"><span data-stu-id="0f4eb-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="0f4eb-130">通常、`Assert` または `Fail` メソッドを呼び出すと、メッセージボックスが表示されますが、<xref:System.Diagnostics.DefaultTraceListener> が @no__t 3 コレクションに含まれていない場合、メッセージボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="0f4eb-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f4eb-131">例</span><span class="sxs-lookup"><span data-stu-id="0f4eb-131">Example</span></span>  
 <span data-ttu-id="0f4eb-132">次の例は、トレース**リスナー**コレクションから既定のトレースリスナーを削除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0f4eb-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f4eb-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f4eb-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="0f4eb-134">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="0f4eb-134">Trace and Debug Settings Schema</span></span>](index.md)
