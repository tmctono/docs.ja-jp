---
title: <source> 要素
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 417722ce2f3865350158413307495e3ab435d386
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153296"
---
# <a name="source-element"></a><span data-ttu-id="3a064-102">\<ソース>要素</span><span class="sxs-lookup"><span data-stu-id="3a064-102">\<source> Element</span></span>
<span data-ttu-id="3a064-103">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="3a064-103">Specifies a trace source that initiates tracing messages.</span></span>  

<span data-ttu-id="3a064-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3a064-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3a064-105">&nbsp;&nbsp;[**\<診断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="3a064-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="3a064-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ソース>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="3a064-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="3a064-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ソース>**</span><span class="sxs-lookup"><span data-stu-id="3a064-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3a064-108">構文</span><span class="sxs-lookup"><span data-stu-id="3a064-108">Syntax</span></span>  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a064-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3a064-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3a064-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a064-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a064-111">属性</span><span class="sxs-lookup"><span data-stu-id="3a064-111">Attributes</span></span>  
  
|<span data-ttu-id="3a064-112">属性</span><span class="sxs-lookup"><span data-stu-id="3a064-112">Attribute</span></span>|<span data-ttu-id="3a064-113">説明</span><span class="sxs-lookup"><span data-stu-id="3a064-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="3a064-114">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3a064-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3a064-115">トレース ソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3a064-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="3a064-116">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3a064-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3a064-117">アプリケーション内のトレース スイッチ インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3a064-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="3a064-118">`<switches>`スイッチが要素内で識別されない場合、値はスイッチのレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="3a064-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="3a064-119">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3a064-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3a064-120">トレース スイッチの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="3a064-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="3a064-121">存在する場合、型は有効なクラス名である必要があり、空の文字列にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3a064-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="3a064-122">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="3a064-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3a064-123">そのトレース ソースのメソッドによって識別されるトレース ソース固有<xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A>の属性の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="3a064-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a064-124">子要素</span><span class="sxs-lookup"><span data-stu-id="3a064-124">Child Elements</span></span>  
  
|<span data-ttu-id="3a064-125">要素</span><span class="sxs-lookup"><span data-stu-id="3a064-125">Element</span></span>|<span data-ttu-id="3a064-126">説明</span><span class="sxs-lookup"><span data-stu-id="3a064-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a064-127">\<リスナー></span><span class="sxs-lookup"><span data-stu-id="3a064-127">\<listeners></span></span>](listeners-element-for-source.md)|<span data-ttu-id="3a064-128">メッセージを収集、格納、およびルーティングするリスナーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a064-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a064-129">親要素</span><span class="sxs-lookup"><span data-stu-id="3a064-129">Parent Elements</span></span>  
  
|<span data-ttu-id="3a064-130">要素</span><span class="sxs-lookup"><span data-stu-id="3a064-130">Element</span></span>|<span data-ttu-id="3a064-131">説明</span><span class="sxs-lookup"><span data-stu-id="3a064-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3a064-132">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="3a064-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="3a064-133">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="3a064-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="3a064-134">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="3a064-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a064-135">解説</span><span class="sxs-lookup"><span data-stu-id="3a064-135">Remarks</span></span>  
 <span data-ttu-id="3a064-136">この要素は、コンピューター構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a064-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a064-137">例</span><span class="sxs-lookup"><span data-stu-id="3a064-137">Example</span></span>  
 <span data-ttu-id="3a064-138">次の例は、要素を`<source>`使用してトレース ソース`mySource`を追加し、という名前`sourceSwitch`のソース スイッチのレベルを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3a064-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="3a064-139">トレース情報をコンソールに書き込むコンソール トレース リスナーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="3a064-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3a064-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a064-140">See also</span></span>

- [<span data-ttu-id="3a064-141">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="3a064-141">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3a064-142">トレース スイッチ</span><span class="sxs-lookup"><span data-stu-id="3a064-142">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
