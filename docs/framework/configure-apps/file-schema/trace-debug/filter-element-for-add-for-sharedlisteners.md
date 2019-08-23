---
title: <filter> の <add> の <sharedListeners> 要素
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
ms.openlocfilehash: 571a3add232f3e4f9747040dc104b85e8cc3085e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920509"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="a759d-102">\<sharedListeners > の\<add \<> の > 要素をフィルター処理します</span><span class="sxs-lookup"><span data-stu-id="a759d-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="a759d-103">`sharedListeners` コレクションのリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="a759d-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  
  
 <span data-ttu-id="a759d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a759d-104">\<configuration></span></span>  
<span data-ttu-id="a759d-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="a759d-105">\<system.diagnostics></span></span>  
<span data-ttu-id="a759d-106">\<sharedListeners > 要素</span><span class="sxs-lookup"><span data-stu-id="a759d-106">\<sharedListeners> Element</span></span>  
<span data-ttu-id="a759d-107">\<add></span><span class="sxs-lookup"><span data-stu-id="a759d-107">\<add></span></span>  
<span data-ttu-id="a759d-108">\<フィルター ></span><span class="sxs-lookup"><span data-stu-id="a759d-108">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a759d-109">構文</span><span class="sxs-lookup"><span data-stu-id="a759d-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a759d-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a759d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a759d-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a759d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a759d-112">属性</span><span class="sxs-lookup"><span data-stu-id="a759d-112">Attributes</span></span>  
  
|<span data-ttu-id="a759d-113">属性</span><span class="sxs-lookup"><span data-stu-id="a759d-113">Attribute</span></span>|<span data-ttu-id="a759d-114">説明</span><span class="sxs-lookup"><span data-stu-id="a759d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a759d-115">**type**</span><span class="sxs-lookup"><span data-stu-id="a759d-115">**type**</span></span>|<span data-ttu-id="a759d-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="a759d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="a759d-117">フィルターの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="a759d-117">Specifies the type of the filter.</span></span> <span data-ttu-id="a759d-118">型の完全な名前 ( <xref:System.Type.FullName%2A?displayProperty=nameWithType>プロパティの形式) のみを使用することも、アセンブリ情報を含む完全修飾型名 ( <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>プロパティの形式) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a759d-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="a759d-119">完全修飾型名の作成の詳細については、「[完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a759d-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="a759d-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="a759d-120">**initializeData**</span></span>|<span data-ttu-id="a759d-121">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="a759d-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a759d-122">指定したクラスのコンストラクターに渡される文字列。</span><span class="sxs-lookup"><span data-stu-id="a759d-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a759d-123">子要素</span><span class="sxs-lookup"><span data-stu-id="a759d-123">Child Elements</span></span>  
 <span data-ttu-id="a759d-124">なし。</span><span class="sxs-lookup"><span data-stu-id="a759d-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a759d-125">親要素</span><span class="sxs-lookup"><span data-stu-id="a759d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a759d-126">要素</span><span class="sxs-lookup"><span data-stu-id="a759d-126">Element</span></span>|<span data-ttu-id="a759d-127">説明</span><span class="sxs-lookup"><span data-stu-id="a759d-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a759d-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a759d-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a759d-129">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="a759d-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="a759d-130">任意のソースまたはトレース要素が参照できるリスナーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="a759d-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="a759d-131">リスナーを**sharedListeners**コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="a759d-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a759d-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="a759d-132">Remarks</span></span>  
 <span data-ttu-id="a759d-133">`<add>`リスナーが`<sharedListeners>`要素の要素で定義されている場合、そのリスナーのフィルターは、要素の`<add>`子`<filter>`である要素で定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a759d-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="a759d-134">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a759d-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a759d-135">例</span><span class="sxs-lookup"><span data-stu-id="a759d-135">Example</span></span>  
 <span data-ttu-id="a759d-136">次の例は、 `<filter>`要素を使用して、 `sharedListeners`コレクション内のトレースリスナー `console`にフィルターを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a759d-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a759d-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="a759d-137">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="a759d-138">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="a759d-138">Trace and Debug Settings Schema</span></span>](index.md)
