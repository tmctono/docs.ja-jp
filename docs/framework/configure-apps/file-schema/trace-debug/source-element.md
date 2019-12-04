---
title: <source> 要素
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: b59144f4772c940f8c7e6ca19aa21666069b4b55
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088832"
---
# <a name="source-element"></a><span data-ttu-id="a90eb-102">\<source> 要素</span><span class="sxs-lookup"><span data-stu-id="a90eb-102">\<source> Element</span></span>
<span data-ttu-id="a90eb-103">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="a90eb-103">Specifies a trace source that initiates tracing messages.</span></span>  

<span data-ttu-id="a90eb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a90eb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a90eb-105">&nbsp;&nbsp;[**\<system.diagnostics**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="a90eb-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="a90eb-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**sources**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="a90eb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="a90eb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**source>**</span><span class="sxs-lookup"><span data-stu-id="a90eb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a90eb-108">構文</span><span class="sxs-lookup"><span data-stu-id="a90eb-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a90eb-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a90eb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a90eb-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a90eb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a90eb-111">属性</span><span class="sxs-lookup"><span data-stu-id="a90eb-111">Attributes</span></span>  
  
|<span data-ttu-id="a90eb-112">属性</span><span class="sxs-lookup"><span data-stu-id="a90eb-112">Attribute</span></span>|<span data-ttu-id="a90eb-113">説明</span><span class="sxs-lookup"><span data-stu-id="a90eb-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="a90eb-114">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="a90eb-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a90eb-115">トレースソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a90eb-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="a90eb-116">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="a90eb-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a90eb-117">アプリケーションのトレーススイッチインスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a90eb-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="a90eb-118">スイッチが `<switches>` 要素で識別されない場合は、スイッチのレベルを値で指定します。</span><span class="sxs-lookup"><span data-stu-id="a90eb-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="a90eb-119">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="a90eb-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a90eb-120">トレーススイッチの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="a90eb-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="a90eb-121">存在する場合、型は有効なクラス名である必要があり、空の文字列にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a90eb-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="a90eb-122">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="a90eb-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a90eb-123">トレースソースの <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> メソッドによって識別される、トレースソース固有の属性の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="a90eb-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a90eb-124">子要素</span><span class="sxs-lookup"><span data-stu-id="a90eb-124">Child Elements</span></span>  
  
|<span data-ttu-id="a90eb-125">要素</span><span class="sxs-lookup"><span data-stu-id="a90eb-125">Element</span></span>|<span data-ttu-id="a90eb-126">説明</span><span class="sxs-lookup"><span data-stu-id="a90eb-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a90eb-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="a90eb-127">\<listeners></span></span>](listeners-element-for-source.md)|<span data-ttu-id="a90eb-128">メッセージを収集、格納、およびルーティングするリスナーを格納します。</span><span class="sxs-lookup"><span data-stu-id="a90eb-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a90eb-129">親要素</span><span class="sxs-lookup"><span data-stu-id="a90eb-129">Parent Elements</span></span>  
  
|<span data-ttu-id="a90eb-130">要素</span><span class="sxs-lookup"><span data-stu-id="a90eb-130">Element</span></span>|<span data-ttu-id="a90eb-131">説明</span><span class="sxs-lookup"><span data-stu-id="a90eb-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a90eb-132">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a90eb-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a90eb-133">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="a90eb-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="a90eb-134">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="a90eb-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a90eb-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="a90eb-135">Remarks</span></span>  
 <span data-ttu-id="a90eb-136">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a90eb-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a90eb-137">例</span><span class="sxs-lookup"><span data-stu-id="a90eb-137">Example</span></span>  
 <span data-ttu-id="a90eb-138">次の例では、`<source>` 要素を使用してトレースソース `mySource` を追加し、`sourceSwitch`という名前のソーススイッチのレベルを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a90eb-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="a90eb-139">トレース情報をコンソールに書き込むコンソールトレースリスナーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="a90eb-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a90eb-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="a90eb-140">See also</span></span>

- [<span data-ttu-id="a90eb-141">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="a90eb-141">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a90eb-142">トレース スイッチ</span><span class="sxs-lookup"><span data-stu-id="a90eb-142">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
