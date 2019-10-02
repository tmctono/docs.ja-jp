---
title: <source> の <listeners> の <add> の <filter> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: ec288685f47c8a35e2371c31d359b604a4967196
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697168"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="fe7fc-102">\<source @no__t の >-2listeners @no__t の \< add > の > 要素</span><span class="sxs-lookup"><span data-stu-id="fe7fc-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="fe7fc-103">トレース ソースの `Listeners` コレクション内のリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="fe7fc-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="fe7fc-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="fe7fc-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="fe7fc-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="fe7fc-106">&nbsp; @ no__t-1 @ no__t no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="fe7fc-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="fe7fc-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5[ **\<source >** になります。](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="fe7fc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="fe7fc-108">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listeners** (&) >](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="fe7fc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="fe7fc-109">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9[ **&nbsp;2add > を追加**します。](add-element-for-listeners-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="fe7fc-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)</span></span>  
<span data-ttu-id="fe7fc-110">&nbsp; @ no__t @ no__t @ no__t @ no__t @ no__t @ no__t @ no__t-7 @ no__t-6 @ no__t-9 @ no__t-10 @-11 **&nbsp;3filter > を選択**して、フィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe7fc-111">構文</span><span class="sxs-lookup"><span data-stu-id="fe7fc-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe7fc-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fe7fc-112">Attributes and Elements</span></span>  
 <span data-ttu-id="fe7fc-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe7fc-114">属性</span><span class="sxs-lookup"><span data-stu-id="fe7fc-114">Attributes</span></span>  
  
|<span data-ttu-id="fe7fc-115">属性</span><span class="sxs-lookup"><span data-stu-id="fe7fc-115">Attribute</span></span>|<span data-ttu-id="fe7fc-116">説明</span><span class="sxs-lookup"><span data-stu-id="fe7fc-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="fe7fc-117">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="fe7fc-118">フィルターの種類を指定します。この型は、<xref:System.Diagnostics.TraceFilter> クラスから継承する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="fe7fc-119">型の名前空間で修飾された名前を使用できます。これは、型の @no__t 0 のプロパティに対応します。または、<xref:System.Type.AssemblyQualifiedName%2A> プロパティに対応するアセンブリ情報を含む完全修飾型名を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="fe7fc-120">完全修飾型名の詳細については、「[完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="fe7fc-121">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fe7fc-122">指定されたフィルタークラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe7fc-123">子要素</span><span class="sxs-lookup"><span data-stu-id="fe7fc-123">Child Elements</span></span>  
 <span data-ttu-id="fe7fc-124">なし。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe7fc-125">親要素</span><span class="sxs-lookup"><span data-stu-id="fe7fc-125">Parent Elements</span></span>  
  
|<span data-ttu-id="fe7fc-126">要素</span><span class="sxs-lookup"><span data-stu-id="fe7fc-126">Element</span></span>|<span data-ttu-id="fe7fc-127">説明</span><span class="sxs-lookup"><span data-stu-id="fe7fc-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fe7fc-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="fe7fc-129">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="fe7fc-130">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="fe7fc-131">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="fe7fc-132">メッセージを収集、格納、およびルーティングするリスナーを格納します。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="fe7fc-133">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="fe7fc-134">トレース ソースの `Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe7fc-135">コメント</span><span class="sxs-lookup"><span data-stu-id="fe7fc-135">Remarks</span></span>  
 <span data-ttu-id="fe7fc-136">@No__t-0 要素は、 [\<sharedListeners >](sharedlisteners-element.md)で定義されているリスナーの名前だけでなく、リスナーの種類を指定するトレースソースリスナーの `<add>` 要素に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="fe7fc-137">リスナーが[@no__t 1sharedListeners >](sharedlisteners-element.md)で定義されている場合は、そのリスナーのフィルターをその要素で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-137">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="fe7fc-138">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe7fc-139">例</span><span class="sxs-lookup"><span data-stu-id="fe7fc-139">Example</span></span>  
 <span data-ttu-id="fe7fc-140">次の例では、`<filter>` 要素を使用して、トレース @no__t ソースの `Listeners` コレクションのリスナー `console` にフィルターを追加し、フィルターイベントレベルを `Error` に指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fe7fc-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe7fc-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe7fc-141">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="fe7fc-142">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="fe7fc-142">Trace and Debug Settings Schema</span></span>](index.md)
