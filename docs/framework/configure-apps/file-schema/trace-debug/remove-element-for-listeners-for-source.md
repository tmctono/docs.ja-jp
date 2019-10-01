---
title: <source> の <listeners> の <remove> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 4a11308278f755ec8271477352d91d8797d105c5
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699499"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="20216-102">\<source の > \< リスナーの > 要素を削除 @no__t</span><span class="sxs-lookup"><span data-stu-id="20216-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="20216-103">トレース ソースの `Listeners` コレクションからリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="20216-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="20216-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="20216-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="20216-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="20216-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="20216-106">&nbsp; @ no__t-1 @ no__t no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="20216-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="20216-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5[ **\<source >** になります。](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="20216-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="20216-108">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listeners** (&) >](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="20216-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="20216-109">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 **&nbsp;1remove > を削除**します。</span><span class="sxs-lookup"><span data-stu-id="20216-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20216-110">構文</span><span class="sxs-lookup"><span data-stu-id="20216-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20216-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="20216-111">Attributes and Elements</span></span>  
 <span data-ttu-id="20216-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="20216-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20216-113">属性</span><span class="sxs-lookup"><span data-stu-id="20216-113">Attributes</span></span>  
  
|<span data-ttu-id="20216-114">属性</span><span class="sxs-lookup"><span data-stu-id="20216-114">Attribute</span></span>|<span data-ttu-id="20216-115">説明</span><span class="sxs-lookup"><span data-stu-id="20216-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="20216-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="20216-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="20216-117">@No__t 0 のコレクションから削除するリスナーの名前。</span><span class="sxs-lookup"><span data-stu-id="20216-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20216-118">子要素</span><span class="sxs-lookup"><span data-stu-id="20216-118">Child Elements</span></span>  
 <span data-ttu-id="20216-119">なし。</span><span class="sxs-lookup"><span data-stu-id="20216-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="20216-120">親要素</span><span class="sxs-lookup"><span data-stu-id="20216-120">Parent Elements</span></span>  
  
|<span data-ttu-id="20216-121">要素</span><span class="sxs-lookup"><span data-stu-id="20216-121">Element</span></span>|<span data-ttu-id="20216-122">説明</span><span class="sxs-lookup"><span data-stu-id="20216-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="20216-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="20216-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="20216-124">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="20216-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="20216-125">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="20216-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="20216-126">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="20216-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="20216-127">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="20216-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20216-128">コメント</span><span class="sxs-lookup"><span data-stu-id="20216-128">Remarks</span></span>  
 <span data-ttu-id="20216-129">@No__t-0 要素は、指定されたリスナーをトレースソースの `Listeners` コレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="20216-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="20216-130">@No__t-3 インスタンスの <xref:System.Diagnostics.TraceSource.Listeners%2A> プロパティで <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> メソッドを呼び出すことによって、トレースソースの `Listeners` コレクションからプログラムを使用して要素を削除できます。</span><span class="sxs-lookup"><span data-stu-id="20216-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="20216-131">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="20216-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20216-132">例</span><span class="sxs-lookup"><span data-stu-id="20216-132">Example</span></span>  
 <span data-ttu-id="20216-133">次の例では、`<remove>` の要素を使用して、`<add>` の要素を使用してリスナー `console` をトレース @no__t ソースの `Listeners` コレクションに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="20216-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="20216-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="20216-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="20216-135">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="20216-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="20216-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="20216-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="20216-137">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="20216-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
