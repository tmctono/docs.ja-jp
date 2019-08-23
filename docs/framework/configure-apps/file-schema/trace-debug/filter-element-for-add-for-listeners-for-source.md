---
title: <filter> の <add> の <listeners> の <source> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 0d25d0b955a94986147922914068c8a1cf2d96c4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920520"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="83756-102">\<ソース > の\< \<リスナー>のadd>の>要素をフィルター処理します\<</span><span class="sxs-lookup"><span data-stu-id="83756-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="83756-103">トレース ソースの `Listeners` コレクション内のリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="83756-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="83756-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="83756-104">\<configuration></span></span>  
<span data-ttu-id="83756-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="83756-105">\<system.diagnostics></span></span>  
<span data-ttu-id="83756-106">\<ソース ></span><span class="sxs-lookup"><span data-stu-id="83756-106">\<sources></span></span>  
<span data-ttu-id="83756-107">\<ソース ></span><span class="sxs-lookup"><span data-stu-id="83756-107">\<source></span></span>  
<span data-ttu-id="83756-108">\<リスナー ></span><span class="sxs-lookup"><span data-stu-id="83756-108">\<listeners></span></span>  
<span data-ttu-id="83756-109">\<add></span><span class="sxs-lookup"><span data-stu-id="83756-109">\<add></span></span>  
<span data-ttu-id="83756-110">\<フィルター ></span><span class="sxs-lookup"><span data-stu-id="83756-110">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83756-111">構文</span><span class="sxs-lookup"><span data-stu-id="83756-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83756-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="83756-112">Attributes and Elements</span></span>  
 <span data-ttu-id="83756-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="83756-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83756-114">属性</span><span class="sxs-lookup"><span data-stu-id="83756-114">Attributes</span></span>  
  
|<span data-ttu-id="83756-115">属性</span><span class="sxs-lookup"><span data-stu-id="83756-115">Attribute</span></span>|<span data-ttu-id="83756-116">説明</span><span class="sxs-lookup"><span data-stu-id="83756-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="83756-117">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="83756-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="83756-118">フィルターの種類を指定します。この型は<xref:System.Diagnostics.TraceFilter>クラスから継承する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83756-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="83756-119">型の名前空間で修飾された名前を使用できます。これは、 <xref:System.Type.FullName%2A>型のプロパティに対応します。または、 <xref:System.Type.AssemblyQualifiedName%2A>プロパティに対応するアセンブリ情報を含む完全修飾型名を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="83756-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="83756-120">完全修飾型名の詳細については、「[完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83756-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="83756-121">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="83756-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="83756-122">指定されたフィルタークラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="83756-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83756-123">子要素</span><span class="sxs-lookup"><span data-stu-id="83756-123">Child Elements</span></span>  
 <span data-ttu-id="83756-124">なし。</span><span class="sxs-lookup"><span data-stu-id="83756-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83756-125">親要素</span><span class="sxs-lookup"><span data-stu-id="83756-125">Parent Elements</span></span>  
  
|<span data-ttu-id="83756-126">要素</span><span class="sxs-lookup"><span data-stu-id="83756-126">Element</span></span>|<span data-ttu-id="83756-127">説明</span><span class="sxs-lookup"><span data-stu-id="83756-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="83756-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="83756-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="83756-129">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="83756-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="83756-130">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="83756-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="83756-131">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="83756-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="83756-132">メッセージを収集、格納、およびルーティングするリスナーを格納します。</span><span class="sxs-lookup"><span data-stu-id="83756-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="83756-133">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="83756-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="83756-134">トレース ソースの `Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="83756-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83756-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="83756-135">Remarks</span></span>  
 <span data-ttu-id="83756-136">要素`<filter>`は、 `<add>` [sharedListeners > で定義されているリスナーの名前だけでなく、リスナーの種類を指定するトレースソースリスナーの要素に含まれている必要があります。 \<](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="83756-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="83756-137">リスナーが[ \<sharedListeners >](sharedlisteners-element.md)で定義されている場合は、そのリスナーのフィルターをその要素で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83756-137">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="83756-138">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="83756-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83756-139">例</span><span class="sxs-lookup"><span data-stu-id="83756-139">Example</span></span>  
 <span data-ttu-id="83756-140">次の例では`<filter>` 、要素を使用して、フィルターイベントレベルをとして`Error`指定し、トレース`myTraceSource`ソースの`Listeners`コレクション内のリスナー `console`にフィルターを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="83756-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="83756-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="83756-141">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="83756-142">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="83756-142">Trace and Debug Settings Schema</span></span>](index.md)
