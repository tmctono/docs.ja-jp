---
title: <filter>のの <add> 要素 <listeners><trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: d856fc742bc2dca51095ce0866dcbfdaadadf64d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176111"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="71345-102">\<filter>のの \<add> 要素 \<listeners>\<trace></span><span class="sxs-lookup"><span data-stu-id="71345-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>

<span data-ttu-id="71345-103">トレースのコレクションのリスナーにフィルターを追加し `Listeners` ます。</span><span class="sxs-lookup"><span data-stu-id="71345-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="71345-104">構文</span><span class="sxs-lookup"><span data-stu-id="71345-104">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71345-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="71345-105">Attributes and Elements</span></span>  

 <span data-ttu-id="71345-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="71345-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71345-107">属性</span><span class="sxs-lookup"><span data-stu-id="71345-107">Attributes</span></span>  
  
|<span data-ttu-id="71345-108">属性</span><span class="sxs-lookup"><span data-stu-id="71345-108">Attribute</span></span>|<span data-ttu-id="71345-109">説明</span><span class="sxs-lookup"><span data-stu-id="71345-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="71345-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="71345-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="71345-111">フィルターの種類を指定します。この型はクラスから継承する必要があり <xref:System.Diagnostics.TraceFilter> ます。</span><span class="sxs-lookup"><span data-stu-id="71345-111">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="71345-112">型の名前空間で修飾された名前を使用できます。これは、型のプロパティに対応し <xref:System.Type.FullName%2A> ます。または、プロパティに対応するアセンブリ情報を含む完全修飾型名を使用することもでき <xref:System.Type.AssemblyQualifiedName%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="71345-112">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="71345-113">完全修飾型名の詳細については、「 [完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71345-113">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="71345-114">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="71345-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="71345-115">指定されたフィルタークラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="71345-115">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71345-116">子要素</span><span class="sxs-lookup"><span data-stu-id="71345-116">Child Elements</span></span>  

 <span data-ttu-id="71345-117">なし。</span><span class="sxs-lookup"><span data-stu-id="71345-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71345-118">親要素</span><span class="sxs-lookup"><span data-stu-id="71345-118">Parent Elements</span></span>  
  
|<span data-ttu-id="71345-119">要素</span><span class="sxs-lookup"><span data-stu-id="71345-119">Element</span></span>|<span data-ttu-id="71345-120">説明</span><span class="sxs-lookup"><span data-stu-id="71345-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="71345-121">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="71345-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="71345-122">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="71345-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="71345-123">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="71345-123">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="71345-124">メッセージを収集、格納、およびルーティングするリスナーを格納します。</span><span class="sxs-lookup"><span data-stu-id="71345-124">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="71345-125">リスナーは、適切なターゲットにトレース出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="71345-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="71345-126">`Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="71345-126">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71345-127">解説</span><span class="sxs-lookup"><span data-stu-id="71345-127">Remarks</span></span>  

 <span data-ttu-id="71345-128">`<filter>`要素は `<add>` 、で定義されているリスナーの名前だけでなく、リスナーの種類を指定するトレースリスナーの要素に格納されている必要があり [\<sharedListeners>](sharedlisteners-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="71345-128">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="71345-129">リスナーがで定義されている場合は [\<sharedListeners>](sharedlisteners-element.md) 、そのリスナーのフィルターをその要素で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71345-129">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="71345-130">この要素は、マシン構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="71345-130">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71345-131">例</span><span class="sxs-lookup"><span data-stu-id="71345-131">Example</span></span>  

 <span data-ttu-id="71345-132">次の例では、要素を使用して、フィルター `<filter>` `console` `Listeners` イベントレベルをとして指定し、トレースのコレクション内のリスナーにフィルターを追加する方法を示し `Error` ます。</span><span class="sxs-lookup"><span data-stu-id="71345-132">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="71345-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="71345-133">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="71345-134">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="71345-134">Trace and Debug Settings Schema</span></span>](index.md)
