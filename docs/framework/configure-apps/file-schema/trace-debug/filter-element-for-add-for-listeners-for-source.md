---
title: <filter>のの <add> 要素 <listeners><source>
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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153517"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="ba860-102">\<filter>のの \<add> 要素 \<listeners>\<source></span><span class="sxs-lookup"><span data-stu-id="ba860-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="ba860-103">トレース ソースの `Listeners` コレクション内のリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="ba860-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="ba860-104">構文</span><span class="sxs-lookup"><span data-stu-id="ba860-104">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba860-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ba860-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ba860-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba860-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba860-107">属性</span><span class="sxs-lookup"><span data-stu-id="ba860-107">Attributes</span></span>  
  
|<span data-ttu-id="ba860-108">属性</span><span class="sxs-lookup"><span data-stu-id="ba860-108">Attribute</span></span>|<span data-ttu-id="ba860-109">説明</span><span class="sxs-lookup"><span data-stu-id="ba860-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="ba860-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="ba860-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="ba860-111">フィルターの種類を指定します。この型はクラスから継承する必要があり <xref:System.Diagnostics.TraceFilter> ます。</span><span class="sxs-lookup"><span data-stu-id="ba860-111">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="ba860-112">型の名前空間で修飾された名前を使用できます。これは、型のプロパティに対応し <xref:System.Type.FullName%2A> ます。または、プロパティに対応するアセンブリ情報を含む完全修飾型名を使用することもでき <xref:System.Type.AssemblyQualifiedName%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="ba860-112">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="ba860-113">完全修飾型名の詳細については、「[完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba860-113">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="ba860-114">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="ba860-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ba860-115">指定されたフィルタークラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="ba860-115">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba860-116">子要素</span><span class="sxs-lookup"><span data-stu-id="ba860-116">Child Elements</span></span>  
 <span data-ttu-id="ba860-117">なし。</span><span class="sxs-lookup"><span data-stu-id="ba860-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba860-118">親要素</span><span class="sxs-lookup"><span data-stu-id="ba860-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ba860-119">要素</span><span class="sxs-lookup"><span data-stu-id="ba860-119">Element</span></span>|<span data-ttu-id="ba860-120">Description</span><span class="sxs-lookup"><span data-stu-id="ba860-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ba860-121">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="ba860-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ba860-122">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="ba860-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="ba860-123">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="ba860-123">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="ba860-124">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="ba860-124">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="ba860-125">メッセージを収集、格納、およびルーティングするリスナーを格納します。</span><span class="sxs-lookup"><span data-stu-id="ba860-125">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="ba860-126">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="ba860-126">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="ba860-127">トレース ソースの `Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ba860-127">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba860-128">解説</span><span class="sxs-lookup"><span data-stu-id="ba860-128">Remarks</span></span>  
 <span data-ttu-id="ba860-129">`<filter>`要素は `<add>` 、で定義されているリスナーの名前だけでなく、リスナーの種類を指定するトレースソースリスナーの要素に格納されている必要があり [\<sharedListeners>](sharedlisteners-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="ba860-129">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="ba860-130">リスナーがで定義されている場合は [\<sharedListeners>](sharedlisteners-element.md) 、そのリスナーのフィルターをその要素で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba860-130">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="ba860-131">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ba860-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba860-132">例</span><span class="sxs-lookup"><span data-stu-id="ba860-132">Example</span></span>  
 <span data-ttu-id="ba860-133">次の例では、要素を使用して、フィルター `<filter>` `console` `Listeners` イベントレベルをとして指定し、トレースソースのコレクション内のリスナーにフィルターを追加する方法を示し `myTraceSource` `Error` ます。</span><span class="sxs-lookup"><span data-stu-id="ba860-133">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ba860-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba860-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="ba860-135">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="ba860-135">Trace and Debug Settings Schema</span></span>](index.md)
