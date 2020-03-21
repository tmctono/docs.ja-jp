---
title: <filter>用<listeners>の<add>要素<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 0cb668782de263d5f784691f46cb8b74541d942b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153517"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="b6549-102">\<ソース>の\<リスナー>の\<追加>のフィルター>要素\<</span><span class="sxs-lookup"><span data-stu-id="b6549-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="b6549-103">トレース ソースの `Listeners` コレクション内のリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="b6549-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="b6549-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6549-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b6549-105">&nbsp;&nbsp;[**\<診断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6549-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="b6549-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ソース>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6549-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="b6549-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ソース>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6549-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="b6549-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<リスナー>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="b6549-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="b6549-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>を追加する**](add-element-for-listeners-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="b6549-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)</span></span>\
<span data-ttu-id="b6549-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<フィルター>**</span><span class="sxs-lookup"><span data-stu-id="b6549-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b6549-111">構文</span><span class="sxs-lookup"><span data-stu-id="b6549-111">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6549-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b6549-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b6549-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6549-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6549-114">属性</span><span class="sxs-lookup"><span data-stu-id="b6549-114">Attributes</span></span>  
  
|<span data-ttu-id="b6549-115">属性</span><span class="sxs-lookup"><span data-stu-id="b6549-115">Attribute</span></span>|<span data-ttu-id="b6549-116">説明</span><span class="sxs-lookup"><span data-stu-id="b6549-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="b6549-117">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="b6549-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="b6549-118">クラスから継承する必要があるフィルターの型を指定します<xref:System.Diagnostics.TraceFilter>。</span><span class="sxs-lookup"><span data-stu-id="b6549-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="b6549-119">型の名前空間修飾名を使用して、型の<xref:System.Type.FullName%2A>プロパティに対応するか、またはプロパティに対応するアセンブリ情報を含む完全修飾型名を<xref:System.Type.AssemblyQualifiedName%2A>使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6549-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="b6549-120">完全修飾型名の詳細については、「完全修飾[型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6549-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="b6549-121">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="b6549-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b6549-122">指定したフィルター クラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="b6549-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6549-123">子要素</span><span class="sxs-lookup"><span data-stu-id="b6549-123">Child Elements</span></span>  
 <span data-ttu-id="b6549-124">[なし] :</span><span class="sxs-lookup"><span data-stu-id="b6549-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6549-125">親要素</span><span class="sxs-lookup"><span data-stu-id="b6549-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b6549-126">要素</span><span class="sxs-lookup"><span data-stu-id="b6549-126">Element</span></span>|<span data-ttu-id="b6549-127">説明</span><span class="sxs-lookup"><span data-stu-id="b6549-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b6549-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b6549-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b6549-129">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b6549-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="b6549-130">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="b6549-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="b6549-131">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="b6549-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="b6549-132">メッセージを収集、格納、およびルーティングするリスナーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b6549-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="b6549-133">リスナーは、トレース出力を適切なターゲットに送ります。</span><span class="sxs-lookup"><span data-stu-id="b6549-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="b6549-134">トレース ソースの `Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b6549-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6549-135">解説</span><span class="sxs-lookup"><span data-stu-id="b6549-135">Remarks</span></span>  
 <span data-ttu-id="b6549-136">要素`<filter>`は[\<、sharedListeners ](sharedlisteners-element.md) `<add>`>で定義されたリスナーの名前だけでなく、リスナーの型を指定するトレース ソース リスナーの要素に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6549-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="b6549-137">リスナーが[\<sharedListeners>](sharedlisteners-element.md)で定義されている場合は、そのリスナーのフィルターがその要素で定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6549-137">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="b6549-138">この要素は、コンピューター構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6549-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6549-139">例</span><span class="sxs-lookup"><span data-stu-id="b6549-139">Example</span></span>  
 <span data-ttu-id="b6549-140">次の例は、`<filter>`要素を使用して、コレクション内の`console``Listeners`トレース ソース`myTraceSource`のリスナーにフィルターを追加する方法を示しています。 `Error`</span><span class="sxs-lookup"><span data-stu-id="b6549-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b6549-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6549-141">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="b6549-142">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="b6549-142">Trace and Debug Settings Schema</span></span>](index.md)
