---
title: <filter>用<listeners>の<add>要素<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: b6c2c2bf7fe953a75f9d8129039ef33b4d8a3f56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153467"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="b9f33-102">\<トレース>のリスナー \<>の追加\<>のフィルター>要素\<</span><span class="sxs-lookup"><span data-stu-id="b9f33-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="b9f33-103">`Listeners`コレクション内のトレースのリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="b9f33-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

<span data-ttu-id="b9f33-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b9f33-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b9f33-105">&nbsp;&nbsp;[**\<診断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="b9f33-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="b9f33-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<トレース>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="b9f33-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="b9f33-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<リスナー>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="b9f33-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="b9f33-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>を追加する**](add-element-for-listeners-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="b9f33-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)</span></span>\
<span data-ttu-id="b9f33-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<フィルター>**</span><span class="sxs-lookup"><span data-stu-id="b9f33-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b9f33-110">構文</span><span class="sxs-lookup"><span data-stu-id="b9f33-110">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9f33-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b9f33-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b9f33-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9f33-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9f33-113">属性</span><span class="sxs-lookup"><span data-stu-id="b9f33-113">Attributes</span></span>  
  
|<span data-ttu-id="b9f33-114">属性</span><span class="sxs-lookup"><span data-stu-id="b9f33-114">Attribute</span></span>|<span data-ttu-id="b9f33-115">説明</span><span class="sxs-lookup"><span data-stu-id="b9f33-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="b9f33-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="b9f33-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="b9f33-117">クラスから継承する必要があるフィルターの型を指定します<xref:System.Diagnostics.TraceFilter>。</span><span class="sxs-lookup"><span data-stu-id="b9f33-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="b9f33-118">型の名前空間修飾名を使用して、型の<xref:System.Type.FullName%2A>プロパティに対応するか、またはプロパティに対応するアセンブリ情報を含む完全修飾型名を<xref:System.Type.AssemblyQualifiedName%2A>使用できます。</span><span class="sxs-lookup"><span data-stu-id="b9f33-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="b9f33-119">完全修飾型名の詳細については、「完全修飾[型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9f33-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="b9f33-120">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="b9f33-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b9f33-121">指定したフィルター クラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="b9f33-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9f33-122">子要素</span><span class="sxs-lookup"><span data-stu-id="b9f33-122">Child Elements</span></span>  
 <span data-ttu-id="b9f33-123">[なし] :</span><span class="sxs-lookup"><span data-stu-id="b9f33-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9f33-124">親要素</span><span class="sxs-lookup"><span data-stu-id="b9f33-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b9f33-125">要素</span><span class="sxs-lookup"><span data-stu-id="b9f33-125">Element</span></span>|<span data-ttu-id="b9f33-126">説明</span><span class="sxs-lookup"><span data-stu-id="b9f33-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b9f33-127">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b9f33-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b9f33-128">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9f33-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="b9f33-129">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="b9f33-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="b9f33-130">メッセージを収集、格納、およびルーティングするリスナーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b9f33-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="b9f33-131">リスナーは、トレース出力を適切なターゲットに送ります。</span><span class="sxs-lookup"><span data-stu-id="b9f33-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="b9f33-132">`Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b9f33-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9f33-133">解説</span><span class="sxs-lookup"><span data-stu-id="b9f33-133">Remarks</span></span>  
 <span data-ttu-id="b9f33-134">要素`<filter>`は[\<、sharedListeners ](sharedlisteners-element.md) `<add>`>で定義されたリスナーの名前だけでなく、リスナーの型を指定するトレース リスナーの要素に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9f33-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="b9f33-135">リスナーが[\<sharedListeners>](sharedlisteners-element.md)で定義されている場合は、そのリスナーのフィルターがその要素で定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9f33-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="b9f33-136">この要素は、コンピューター構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b9f33-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9f33-137">例</span><span class="sxs-lookup"><span data-stu-id="b9f33-137">Example</span></span>  
 <span data-ttu-id="b9f33-138">次の`<filter>`例では、要素を使用して、コレクション内のトレース用の`console`リスナーに`Listeners`フィルターを追加し、フィルター イベント レベルを`Error`として指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b9f33-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9f33-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9f33-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="b9f33-140">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="b9f33-140">Trace and Debug Settings Schema</span></span>](index.md)
