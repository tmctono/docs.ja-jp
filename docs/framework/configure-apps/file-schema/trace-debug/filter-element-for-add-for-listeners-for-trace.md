---
title: <trace> の <listeners> の <add> の <filter> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: f6b1ec99c5aab8e85df7f1920aca32f49a5be066
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699358"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="3fb53-102">\<trace > 用の \< add > の \<filter > 要素</span><span class="sxs-lookup"><span data-stu-id="3fb53-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="3fb53-103">トレースの @no__t 0 コレクションのリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="3fb53-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
[<span data-ttu-id="3fb53-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="3fb53-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="3fb53-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="3fb53-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="3fb53-106">&nbsp; @ no__t-1 @ no__t @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="3fb53-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="3fb53-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5[ **\<listeners >** します。](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="3fb53-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="3fb53-108">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t @ no__t-6 @ no__t-7[ **&nbsp;0add > を追加**します。](add-element-for-listeners-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="3fb53-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)</span></span>  
<span data-ttu-id="3fb53-109">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t @ no__t @ no__t @ no__t-7 @ no__t-8 @-9 **&nbsp;1filter > を選択**します。</span><span class="sxs-lookup"><span data-stu-id="3fb53-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fb53-110">構文</span><span class="sxs-lookup"><span data-stu-id="3fb53-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fb53-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3fb53-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3fb53-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3fb53-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fb53-113">属性</span><span class="sxs-lookup"><span data-stu-id="3fb53-113">Attributes</span></span>  
  
|<span data-ttu-id="3fb53-114">属性</span><span class="sxs-lookup"><span data-stu-id="3fb53-114">Attribute</span></span>|<span data-ttu-id="3fb53-115">説明</span><span class="sxs-lookup"><span data-stu-id="3fb53-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="3fb53-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="3fb53-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="3fb53-117">フィルターの種類を指定します。この型は、<xref:System.Diagnostics.TraceFilter> クラスから継承する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fb53-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="3fb53-118">型の名前空間で修飾された名前を使用できます。これは、型の @no__t 0 のプロパティに対応します。または、<xref:System.Type.AssemblyQualifiedName%2A> プロパティに対応するアセンブリ情報を含む完全修飾型名を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3fb53-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="3fb53-119">完全修飾型名の詳細については、「[完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fb53-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="3fb53-120">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3fb53-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3fb53-121">指定されたフィルタークラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="3fb53-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3fb53-122">子要素</span><span class="sxs-lookup"><span data-stu-id="3fb53-122">Child Elements</span></span>  
 <span data-ttu-id="3fb53-123">なし。</span><span class="sxs-lookup"><span data-stu-id="3fb53-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3fb53-124">親要素</span><span class="sxs-lookup"><span data-stu-id="3fb53-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3fb53-125">要素</span><span class="sxs-lookup"><span data-stu-id="3fb53-125">Element</span></span>|<span data-ttu-id="3fb53-126">説明</span><span class="sxs-lookup"><span data-stu-id="3fb53-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3fb53-127">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="3fb53-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="3fb53-128">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="3fb53-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="3fb53-129">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="3fb53-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="3fb53-130">メッセージを収集、格納、およびルーティングするリスナーを格納します。</span><span class="sxs-lookup"><span data-stu-id="3fb53-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="3fb53-131">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="3fb53-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="3fb53-132">`Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3fb53-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fb53-133">コメント</span><span class="sxs-lookup"><span data-stu-id="3fb53-133">Remarks</span></span>  
 <span data-ttu-id="3fb53-134">@No__t-0 要素は、 [\<sharedListeners >](sharedlisteners-element.md)で定義されているリスナーの名前だけでなく、リスナーの種類を指定するトレースリスナーの `<add>` 要素に格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fb53-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="3fb53-135">リスナーが[@no__t 1sharedListeners >](sharedlisteners-element.md)で定義されている場合は、そのリスナーのフィルターをその要素で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fb53-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="3fb53-136">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3fb53-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fb53-137">例</span><span class="sxs-lookup"><span data-stu-id="3fb53-137">Example</span></span>  
 <span data-ttu-id="3fb53-138">次の例では、`<filter>` 要素を使用して、トレースの `Listeners` コレクションにある `console` のリスナーにフィルターを追加し、フィルターイベントレベルを `Error` に指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3fb53-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3fb53-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="3fb53-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="3fb53-140">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="3fb53-140">Trace and Debug Settings Schema</span></span>](index.md)
