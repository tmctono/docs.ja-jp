---
title: <trace> の <listeners> の <remove> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: f06973ec30d5061e4a200d6bf7e68adcf6302018
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088845"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="fb68d-102">\<トレース > の \<リスナー > の > 要素を削除 \<には</span><span class="sxs-lookup"><span data-stu-id="fb68d-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="fb68d-103">**リスナーコレクションから**リスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fb68d-103">Removes a listener from the **Listeners** collection.</span></span>  

<span data-ttu-id="fb68d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fb68d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fb68d-105">&nbsp;&nbsp;[ **\<** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="fb68d-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="fb68d-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**トレース >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="fb68d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="fb68d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**リスナー >** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="fb68d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="fb68d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**削除 >**</span><span class="sxs-lookup"><span data-stu-id="fb68d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fb68d-109">構文</span><span class="sxs-lookup"><span data-stu-id="fb68d-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb68d-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fb68d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fb68d-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb68d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb68d-112">属性</span><span class="sxs-lookup"><span data-stu-id="fb68d-112">Attributes</span></span>  
  
|<span data-ttu-id="fb68d-113">属性</span><span class="sxs-lookup"><span data-stu-id="fb68d-113">Attribute</span></span>|<span data-ttu-id="fb68d-114">説明</span><span class="sxs-lookup"><span data-stu-id="fb68d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb68d-115">**name**</span><span class="sxs-lookup"><span data-stu-id="fb68d-115">**name**</span></span>|<span data-ttu-id="fb68d-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="fb68d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="fb68d-117">**リスナー**コレクションから削除するリスナーの名前。</span><span class="sxs-lookup"><span data-stu-id="fb68d-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fb68d-118">子要素</span><span class="sxs-lookup"><span data-stu-id="fb68d-118">Child Elements</span></span>  
 <span data-ttu-id="fb68d-119">なし。</span><span class="sxs-lookup"><span data-stu-id="fb68d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fb68d-120">親要素</span><span class="sxs-lookup"><span data-stu-id="fb68d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="fb68d-121">要素</span><span class="sxs-lookup"><span data-stu-id="fb68d-121">Element</span></span>|<span data-ttu-id="fb68d-122">説明</span><span class="sxs-lookup"><span data-stu-id="fb68d-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fb68d-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="fb68d-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="fb68d-124">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb68d-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="fb68d-125">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="fb68d-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="fb68d-126">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb68d-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="fb68d-127">ASP.NET トレースサービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="fb68d-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb68d-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="fb68d-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fb68d-129">`Listeners` コレクションから <xref:System.Diagnostics.DefaultTraceListener> を削除すると、<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>、<xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>、<xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>、および <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> の各メソッドの動作が変更されます。</span><span class="sxs-lookup"><span data-stu-id="fb68d-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="fb68d-130">`Assert` または `Fail` メソッドを呼び出すと、通常、メッセージボックスが表示されますが、<xref:System.Diagnostics.DefaultTraceListener> が `Listeners` コレクションに含まれていない場合は、メッセージボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="fb68d-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb68d-131">例</span><span class="sxs-lookup"><span data-stu-id="fb68d-131">Example</span></span>  
 <span data-ttu-id="fb68d-132">次の例は、トレース**リスナー**コレクションから既定のトレースリスナーを削除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fb68d-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fb68d-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb68d-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="fb68d-134">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="fb68d-134">Trace and Debug Settings Schema</span></span>](index.md)
