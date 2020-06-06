---
title: <remove>のの <listeners> 要素<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: f06973ec30d5061e4a200d6bf7e68adcf6302018
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088845"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="41949-102">\<remove>のの \<listeners> 要素\<trace></span><span class="sxs-lookup"><span data-stu-id="41949-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="41949-103">**リスナーコレクションから**リスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="41949-103">Removes a listener from the **Listeners** collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="41949-104">構文</span><span class="sxs-lookup"><span data-stu-id="41949-104">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41949-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="41949-105">Attributes and Elements</span></span>  
 <span data-ttu-id="41949-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="41949-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41949-107">属性</span><span class="sxs-lookup"><span data-stu-id="41949-107">Attributes</span></span>  
  
|<span data-ttu-id="41949-108">属性</span><span class="sxs-lookup"><span data-stu-id="41949-108">Attribute</span></span>|<span data-ttu-id="41949-109">説明</span><span class="sxs-lookup"><span data-stu-id="41949-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="41949-110">**name**</span><span class="sxs-lookup"><span data-stu-id="41949-110">**name**</span></span>|<span data-ttu-id="41949-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="41949-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="41949-112">**リスナー**コレクションから削除するリスナーの名前。</span><span class="sxs-lookup"><span data-stu-id="41949-112">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41949-113">子要素</span><span class="sxs-lookup"><span data-stu-id="41949-113">Child Elements</span></span>  
 <span data-ttu-id="41949-114">なし。</span><span class="sxs-lookup"><span data-stu-id="41949-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41949-115">親要素</span><span class="sxs-lookup"><span data-stu-id="41949-115">Parent Elements</span></span>  
  
|<span data-ttu-id="41949-116">要素</span><span class="sxs-lookup"><span data-stu-id="41949-116">Element</span></span>|<span data-ttu-id="41949-117">Description</span><span class="sxs-lookup"><span data-stu-id="41949-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="41949-118">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="41949-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="41949-119">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="41949-119">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="41949-120">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="41949-120">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="41949-121">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="41949-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="41949-122">ASP.NET トレース サービスを設定します。</span><span class="sxs-lookup"><span data-stu-id="41949-122">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41949-123">解説</span><span class="sxs-lookup"><span data-stu-id="41949-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="41949-124">コレクションからを削除する <xref:System.Diagnostics.DefaultTraceListener> `Listeners` と、、、、およびの各メソッドの動作が変更され <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="41949-124">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="41949-125">通常、 `Assert` メソッドまたはメソッドを呼び出すと、 `Fail` メッセージボックスが表示されますが、 <xref:System.Diagnostics.DefaultTraceListener> がコレクションに含まれていない場合は、メッセージボックスは表示されません `Listeners` 。</span><span class="sxs-lookup"><span data-stu-id="41949-125">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41949-126">例</span><span class="sxs-lookup"><span data-stu-id="41949-126">Example</span></span>  
 <span data-ttu-id="41949-127">次の例は、トレース**リスナー**コレクションから既定のトレースリスナーを削除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="41949-127">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="41949-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="41949-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="41949-129">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="41949-129">Trace and Debug Settings Schema</span></span>](index.md)
