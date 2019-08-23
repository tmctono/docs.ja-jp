---
title: <remove> の <listeners> の <source> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: edd27dd262004aead7db4d81db8ecab0e831dac1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926993"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="8cc94-102">\<ソース > の\<リスナー \<> の > 要素を削除します</span><span class="sxs-lookup"><span data-stu-id="8cc94-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="8cc94-103">トレース ソースの `Listeners` コレクションからリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="8cc94-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="8cc94-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8cc94-104">\<configuration></span></span>  
<span data-ttu-id="8cc94-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="8cc94-105">\<system.diagnostics></span></span>  
<span data-ttu-id="8cc94-106">\<ソース ></span><span class="sxs-lookup"><span data-stu-id="8cc94-106">\<sources></span></span>  
<span data-ttu-id="8cc94-107">\<ソース ></span><span class="sxs-lookup"><span data-stu-id="8cc94-107">\<source></span></span>  
<span data-ttu-id="8cc94-108">\<リスナー ></span><span class="sxs-lookup"><span data-stu-id="8cc94-108">\<listeners></span></span>  
<span data-ttu-id="8cc94-109">\<remove></span><span class="sxs-lookup"><span data-stu-id="8cc94-109">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cc94-110">構文</span><span class="sxs-lookup"><span data-stu-id="8cc94-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8cc94-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8cc94-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8cc94-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8cc94-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8cc94-113">属性</span><span class="sxs-lookup"><span data-stu-id="8cc94-113">Attributes</span></span>  
  
|<span data-ttu-id="8cc94-114">属性</span><span class="sxs-lookup"><span data-stu-id="8cc94-114">Attribute</span></span>|<span data-ttu-id="8cc94-115">説明</span><span class="sxs-lookup"><span data-stu-id="8cc94-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="8cc94-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="8cc94-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="8cc94-117">`Listeners`コレクションから削除するリスナーの名前。</span><span class="sxs-lookup"><span data-stu-id="8cc94-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8cc94-118">子要素</span><span class="sxs-lookup"><span data-stu-id="8cc94-118">Child Elements</span></span>  
 <span data-ttu-id="8cc94-119">なし。</span><span class="sxs-lookup"><span data-stu-id="8cc94-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8cc94-120">親要素</span><span class="sxs-lookup"><span data-stu-id="8cc94-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8cc94-121">要素</span><span class="sxs-lookup"><span data-stu-id="8cc94-121">Element</span></span>|<span data-ttu-id="8cc94-122">説明</span><span class="sxs-lookup"><span data-stu-id="8cc94-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8cc94-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="8cc94-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="8cc94-124">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="8cc94-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="8cc94-125">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="8cc94-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="8cc94-126">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="8cc94-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="8cc94-127">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8cc94-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cc94-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="8cc94-128">Remarks</span></span>  
 <span data-ttu-id="8cc94-129">要素`<remove>`は、指定されたリスナー `Listeners`をトレースソースのコレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="8cc94-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="8cc94-130">インスタンスの`Listeners` <xref:System.Diagnostics.TraceSource.Listeners%2A>プロパティ<xref:System.Diagnostics.TraceListenerCollection.Remove%2A>に対してメソッドを呼び出すことによって、プログラムによってトレースソースのコレクションから要素を削除できます。 <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="8cc94-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="8cc94-131">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="8cc94-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cc94-132">例</span><span class="sxs-lookup"><span data-stu-id="8cc94-132">Example</span></span>  
 <span data-ttu-id="8cc94-133">次の例では、要素を`<remove>`使用し`<add>`て、リスナー `console`をトレースソース`TraceSourceApp`の`Listeners`コレクションに追加する前に、要素を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8cc94-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8cc94-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="8cc94-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="8cc94-135">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="8cc94-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8cc94-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="8cc94-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="8cc94-137">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="8cc94-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
