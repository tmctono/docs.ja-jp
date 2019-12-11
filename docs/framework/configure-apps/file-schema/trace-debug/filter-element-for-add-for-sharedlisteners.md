---
title: <sharedListeners> の <add> の <filter> 要素
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
ms.openlocfilehash: e04ecd773bd6aa7791858711edbd72128dc391ea
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088878"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="c0237-102">\<sharedListeners> の \<add> の \<filter> 要素</span><span class="sxs-lookup"><span data-stu-id="c0237-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="c0237-103">`sharedListeners` コレクションのリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="c0237-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  

<span data-ttu-id="c0237-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c0237-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c0237-105">&nbsp;&nbsp;[ **\<system.diagnostics>** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="c0237-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="c0237-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sharedListeners>** ](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="c0237-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>\
<span data-ttu-id="c0237-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<add>** ](add-element-for-sharedlisteners.md)</span><span class="sxs-lookup"><span data-stu-id="c0237-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)</span></span>\
<span data-ttu-id="c0237-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<filter>**</span><span class="sxs-lookup"><span data-stu-id="c0237-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c0237-109">構文</span><span class="sxs-lookup"><span data-stu-id="c0237-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0237-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c0237-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c0237-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0237-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0237-112">属性</span><span class="sxs-lookup"><span data-stu-id="c0237-112">Attributes</span></span>  
  
|<span data-ttu-id="c0237-113">属性</span><span class="sxs-lookup"><span data-stu-id="c0237-113">Attribute</span></span>|<span data-ttu-id="c0237-114">説明</span><span class="sxs-lookup"><span data-stu-id="c0237-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0237-115">**type**</span><span class="sxs-lookup"><span data-stu-id="c0237-115">**type**</span></span>|<span data-ttu-id="c0237-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="c0237-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="c0237-117">フィルターの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0237-117">Specifies the type of the filter.</span></span> <span data-ttu-id="c0237-118">(<xref:System.Type.FullName%2A?displayProperty=nameWithType> プロパティの形式で) 型の完全な名前のみを使用することも、アセンブリ情報を含む完全修飾型名 (<xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> プロパティの形式) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0237-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="c0237-119">完全修飾型名の作成の詳細については、「[完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0237-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="c0237-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="c0237-120">**initializeData**</span></span>|<span data-ttu-id="c0237-121">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="c0237-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c0237-122">指定したクラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="c0237-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0237-123">子要素</span><span class="sxs-lookup"><span data-stu-id="c0237-123">Child Elements</span></span>  
 <span data-ttu-id="c0237-124">なし。</span><span class="sxs-lookup"><span data-stu-id="c0237-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0237-125">親要素</span><span class="sxs-lookup"><span data-stu-id="c0237-125">Parent Elements</span></span>  
  
|<span data-ttu-id="c0237-126">要素</span><span class="sxs-lookup"><span data-stu-id="c0237-126">Element</span></span>|<span data-ttu-id="c0237-127">説明</span><span class="sxs-lookup"><span data-stu-id="c0237-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c0237-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="c0237-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c0237-129">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0237-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="c0237-130">任意のソースまたはトレース要素が参照できるリスナーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="c0237-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="c0237-131">リスナーを**sharedListeners**コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="c0237-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0237-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0237-132">Remarks</span></span>  
 <span data-ttu-id="c0237-133">リスナーが `<sharedListeners>` 要素の `<add>` 要素で定義されている場合は、そのリスナーのフィルターを `<add>` 要素の子である `<filter>` 要素で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0237-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="c0237-134">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0237-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0237-135">例</span><span class="sxs-lookup"><span data-stu-id="c0237-135">Example</span></span>  
 <span data-ttu-id="c0237-136">次の例は、`<filter>` 要素を使用して、`sharedListeners` コレクション内のトレースリスナー `console` にフィルターを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c0237-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c0237-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0237-137">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="c0237-138">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="c0237-138">Trace and Debug Settings Schema</span></span>](index.md)
