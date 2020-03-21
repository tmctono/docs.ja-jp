---
title: <filter>の<add>要素<sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: 6fb52cdfa5792ab6059b60d8dbb91c107cd666ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153454"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="095d2-102">\<共有リスナー>の\<追加>の\<フィルター>要素</span><span class="sxs-lookup"><span data-stu-id="095d2-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="095d2-103">`sharedListeners` コレクションのリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="095d2-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  

<span data-ttu-id="095d2-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="095d2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="095d2-105">&nbsp;&nbsp;[**\<診断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="095d2-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="095d2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<共有リスナー>**](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="095d2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>\
<span data-ttu-id="095d2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>を追加する**](add-element-for-sharedlisteners.md)</span><span class="sxs-lookup"><span data-stu-id="095d2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)</span></span>\
<span data-ttu-id="095d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<フィルター>**</span><span class="sxs-lookup"><span data-stu-id="095d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="095d2-109">構文</span><span class="sxs-lookup"><span data-stu-id="095d2-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="095d2-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="095d2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="095d2-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="095d2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="095d2-112">属性</span><span class="sxs-lookup"><span data-stu-id="095d2-112">Attributes</span></span>  
  
|<span data-ttu-id="095d2-113">属性</span><span class="sxs-lookup"><span data-stu-id="095d2-113">Attribute</span></span>|<span data-ttu-id="095d2-114">説明</span><span class="sxs-lookup"><span data-stu-id="095d2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="095d2-115">**型**</span><span class="sxs-lookup"><span data-stu-id="095d2-115">**type**</span></span>|<span data-ttu-id="095d2-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="095d2-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="095d2-117">フィルタの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="095d2-117">Specifies the type of the filter.</span></span> <span data-ttu-id="095d2-118">型の完全名 (<xref:System.Type.FullName%2A?displayProperty=nameWithType>プロパティの形式) のみを使用するか、アセンブリ情報を含む完全修飾型名 (プロパティの形式) を<xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>使用できます。</span><span class="sxs-lookup"><span data-stu-id="095d2-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="095d2-119">完全修飾型名の作成については、「完全修飾[型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="095d2-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="095d2-120">**初期化データ**</span><span class="sxs-lookup"><span data-stu-id="095d2-120">**initializeData**</span></span>|<span data-ttu-id="095d2-121">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="095d2-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="095d2-122">指定したクラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="095d2-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="095d2-123">子要素</span><span class="sxs-lookup"><span data-stu-id="095d2-123">Child Elements</span></span>  
 <span data-ttu-id="095d2-124">[なし] :</span><span class="sxs-lookup"><span data-stu-id="095d2-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="095d2-125">親要素</span><span class="sxs-lookup"><span data-stu-id="095d2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="095d2-126">要素</span><span class="sxs-lookup"><span data-stu-id="095d2-126">Element</span></span>|<span data-ttu-id="095d2-127">説明</span><span class="sxs-lookup"><span data-stu-id="095d2-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="095d2-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="095d2-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="095d2-129">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="095d2-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="095d2-130">任意のソースまたはトレース要素が参照できるリスナーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="095d2-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="095d2-131">リスナーを**sharedListeners**コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="095d2-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="095d2-132">解説</span><span class="sxs-lookup"><span data-stu-id="095d2-132">Remarks</span></span>  
 <span data-ttu-id="095d2-133">`<add>`リスナーが`<sharedListeners>`要素の要素で定義されている場合、そのリスナーのフィルターは、要素の子要素で`<filter>`定義する`<add>`必要があります。</span><span class="sxs-lookup"><span data-stu-id="095d2-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="095d2-134">この要素は、コンピューター構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="095d2-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="095d2-135">例</span><span class="sxs-lookup"><span data-stu-id="095d2-135">Example</span></span>  
 <span data-ttu-id="095d2-136">要素を使用してコレクション内の`<filter>`トレース リスナー`console`にフィルターを追加する方法を次の`sharedListeners`例に示します。</span><span class="sxs-lookup"><span data-stu-id="095d2-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="095d2-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="095d2-137">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="095d2-138">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="095d2-138">Trace and Debug Settings Schema</span></span>](index.md)
