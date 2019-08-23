---
title: <filter> の <add> の <listeners> の <trace> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: afde5381a7dd7dfe6a1a9d238a2029511bd9bae2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927135"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="a2a1d-102">\<トレース > の\< \<リスナー>のadd>のフィルター>\<要素</span><span class="sxs-lookup"><span data-stu-id="a2a1d-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="a2a1d-103">トレースの`Listeners`コレクションのリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
 <span data-ttu-id="a2a1d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a2a1d-104">\<configuration></span></span>  
<span data-ttu-id="a2a1d-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="a2a1d-105">\<system.diagnostics></span></span>  
<span data-ttu-id="a2a1d-106">\<トレース ></span><span class="sxs-lookup"><span data-stu-id="a2a1d-106">\<trace></span></span>  
<span data-ttu-id="a2a1d-107">\<リスナー ></span><span class="sxs-lookup"><span data-stu-id="a2a1d-107">\<listeners></span></span>  
<span data-ttu-id="a2a1d-108">\<add></span><span class="sxs-lookup"><span data-stu-id="a2a1d-108">\<add></span></span>  
<span data-ttu-id="a2a1d-109">\<フィルター ></span><span class="sxs-lookup"><span data-stu-id="a2a1d-109">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2a1d-110">構文</span><span class="sxs-lookup"><span data-stu-id="a2a1d-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2a1d-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a2a1d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a2a1d-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2a1d-113">属性</span><span class="sxs-lookup"><span data-stu-id="a2a1d-113">Attributes</span></span>  
  
|<span data-ttu-id="a2a1d-114">属性</span><span class="sxs-lookup"><span data-stu-id="a2a1d-114">Attribute</span></span>|<span data-ttu-id="a2a1d-115">説明</span><span class="sxs-lookup"><span data-stu-id="a2a1d-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="a2a1d-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="a2a1d-117">フィルターの種類を指定します。この型は<xref:System.Diagnostics.TraceFilter>クラスから継承する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="a2a1d-118">型の名前空間で修飾された名前を使用できます。これは、 <xref:System.Type.FullName%2A>型のプロパティに対応します。または、 <xref:System.Type.AssemblyQualifiedName%2A>プロパティに対応するアセンブリ情報を含む完全修飾型名を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="a2a1d-119">完全修飾型名の詳細については、「[完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="a2a1d-120">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a2a1d-121">指定されたフィルタークラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2a1d-122">子要素</span><span class="sxs-lookup"><span data-stu-id="a2a1d-122">Child Elements</span></span>  
 <span data-ttu-id="a2a1d-123">なし。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2a1d-124">親要素</span><span class="sxs-lookup"><span data-stu-id="a2a1d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a2a1d-125">要素</span><span class="sxs-lookup"><span data-stu-id="a2a1d-125">Element</span></span>|<span data-ttu-id="a2a1d-126">説明</span><span class="sxs-lookup"><span data-stu-id="a2a1d-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a2a1d-127">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a2a1d-128">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="a2a1d-129">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="a2a1d-130">メッセージを収集、格納、およびルーティングするリスナーを格納します。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="a2a1d-131">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="a2a1d-132">`Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2a1d-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="a2a1d-133">Remarks</span></span>  
 <span data-ttu-id="a2a1d-134">要素`<filter>`は、 `<add>` [sharedListeners > で定義されているリスナーの名前だけでなく、リスナーの種類を指定するトレースリスナーの要素に含まれている必要があります。 \<](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="a2a1d-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="a2a1d-135">リスナーが[ \<sharedListeners >](sharedlisteners-element.md)で定義されている場合は、そのリスナーのフィルターをその要素で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="a2a1d-136">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2a1d-137">例</span><span class="sxs-lookup"><span data-stu-id="a2a1d-137">Example</span></span>  
 <span data-ttu-id="a2a1d-138">次の`<filter>`例では、要素を使用して、フィルターイベントレベルをとして`Error`指定し、トレースの`Listeners`コレクション内のリスナー `console`にフィルターを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a2a1d-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a2a1d-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2a1d-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="a2a1d-140">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="a2a1d-140">Trace and Debug Settings Schema</span></span>](index.md)
