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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153296"
---
# <a name="source-element"></a><span data-ttu-id="d8ea4-102">\<source> 要素</span><span class="sxs-lookup"><span data-stu-id="d8ea4-102">\<source> Element</span></span>
<span data-ttu-id="d8ea4-103">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-103">Specifies a trace source that initiates tracing messages.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**

## <a name="syntax"></a><span data-ttu-id="d8ea4-104">構文</span><span class="sxs-lookup"><span data-stu-id="d8ea4-104">Syntax</span></span>  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8ea4-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d8ea4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d8ea4-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8ea4-107">属性</span><span class="sxs-lookup"><span data-stu-id="d8ea4-107">Attributes</span></span>  
  
|<span data-ttu-id="d8ea4-108">属性</span><span class="sxs-lookup"><span data-stu-id="d8ea4-108">Attribute</span></span>|<span data-ttu-id="d8ea4-109">説明</span><span class="sxs-lookup"><span data-stu-id="d8ea4-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="d8ea4-110">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d8ea4-111">トレースソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-111">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="d8ea4-112">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d8ea4-113">アプリケーションのトレーススイッチインスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-113">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="d8ea4-114">スイッチが要素で識別されない場合は、 `<switches>` スイッチのレベルを値で指定します。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-114">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="d8ea4-115">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d8ea4-116">トレーススイッチの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-116">Specifies the type of the trace switch.</span></span> <span data-ttu-id="d8ea4-117">存在する場合、型は有効なクラス名である必要があり、空の文字列にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-117">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="d8ea4-118">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d8ea4-119">トレースソースに対してメソッドによって識別される、トレースソース固有の属性の値を指定し <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-119">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8ea4-120">子要素</span><span class="sxs-lookup"><span data-stu-id="d8ea4-120">Child Elements</span></span>  
  
|<span data-ttu-id="d8ea4-121">要素</span><span class="sxs-lookup"><span data-stu-id="d8ea4-121">Element</span></span>|<span data-ttu-id="d8ea4-122">Description</span><span class="sxs-lookup"><span data-stu-id="d8ea4-122">Description</span></span>|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-source.md)|<span data-ttu-id="d8ea4-123">メッセージを収集、格納、およびルーティングするリスナーを格納します。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-123">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8ea4-124">親要素</span><span class="sxs-lookup"><span data-stu-id="d8ea4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d8ea4-125">要素</span><span class="sxs-lookup"><span data-stu-id="d8ea4-125">Element</span></span>|<span data-ttu-id="d8ea4-126">Description</span><span class="sxs-lookup"><span data-stu-id="d8ea4-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d8ea4-127">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d8ea4-128">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="d8ea4-129">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-129">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8ea4-130">解説</span><span class="sxs-lookup"><span data-stu-id="d8ea4-130">Remarks</span></span>  
 <span data-ttu-id="d8ea4-131">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8ea4-132">例</span><span class="sxs-lookup"><span data-stu-id="d8ea4-132">Example</span></span>  
 <span data-ttu-id="d8ea4-133">次の例では、要素を使用してトレースソースを追加し、と `<source>` `mySource` いう名前のソーススイッチのレベルを設定する方法を示し `sourceSwitch` ます。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-133">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="d8ea4-134">トレース情報をコンソールに書き込むコンソールトレースリスナーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="d8ea4-134">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d8ea4-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8ea4-135">See also</span></span>

- [<span data-ttu-id="d8ea4-136">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="d8ea4-136">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d8ea4-137">トレース スイッチ</span><span class="sxs-lookup"><span data-stu-id="d8ea4-137">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
