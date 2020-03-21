---
title: <sources> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
ms.openlocfilehash: 2a76816ee73f516b3c7544877a77531acaa8e09c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153270"
---
# <a name="sources-element"></a><span data-ttu-id="b8cb5-102">\<要素>ソース</span><span class="sxs-lookup"><span data-stu-id="b8cb5-102">\<sources> Element</span></span>
<span data-ttu-id="b8cb5-103">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8cb5-103">Specifies trace sources that initiate tracing messages.</span></span>  

<span data-ttu-id="b8cb5-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b8cb5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b8cb5-105">&nbsp;&nbsp;[**\<診断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="b8cb5-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="b8cb5-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<ソース>**</span><span class="sxs-lookup"><span data-stu-id="b8cb5-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b8cb5-107">構文</span><span class="sxs-lookup"><span data-stu-id="b8cb5-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8cb5-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b8cb5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b8cb5-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b8cb5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8cb5-110">属性</span><span class="sxs-lookup"><span data-stu-id="b8cb5-110">Attributes</span></span>  
 <span data-ttu-id="b8cb5-111">[なし] :</span><span class="sxs-lookup"><span data-stu-id="b8cb5-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b8cb5-112">子要素</span><span class="sxs-lookup"><span data-stu-id="b8cb5-112">Child Elements</span></span>  
  
|<span data-ttu-id="b8cb5-113">要素</span><span class="sxs-lookup"><span data-stu-id="b8cb5-113">Element</span></span>|<span data-ttu-id="b8cb5-114">説明</span><span class="sxs-lookup"><span data-stu-id="b8cb5-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8cb5-115">\<ソース></span><span class="sxs-lookup"><span data-stu-id="b8cb5-115">\<source></span></span>](source-element.md)|<span data-ttu-id="b8cb5-116">必須要素。</span><span class="sxs-lookup"><span data-stu-id="b8cb5-116">Required element.</span></span><br /><br /> <span data-ttu-id="b8cb5-117">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8cb5-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b8cb5-118">親要素</span><span class="sxs-lookup"><span data-stu-id="b8cb5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b8cb5-119">要素</span><span class="sxs-lookup"><span data-stu-id="b8cb5-119">Element</span></span>|<span data-ttu-id="b8cb5-120">説明</span><span class="sxs-lookup"><span data-stu-id="b8cb5-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b8cb5-121">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b8cb5-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b8cb5-122">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8cb5-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8cb5-123">解説</span><span class="sxs-lookup"><span data-stu-id="b8cb5-123">Remarks</span></span>  
 <span data-ttu-id="b8cb5-124">この要素は、コンピューター構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8cb5-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8cb5-125">例</span><span class="sxs-lookup"><span data-stu-id="b8cb5-125">Example</span></span>  
 <span data-ttu-id="b8cb5-126">次の例は、要素を`<sources>`使用してトレース ソース`mySource`を追加し、という名前`sourceSwitch`のソース スイッチのレベルを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b8cb5-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="b8cb5-127">トレース情報をコンソールに書き込むコンソール トレース リスナーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="b8cb5-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"
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
         <add name="sourceSwitch" value="Warning" />  
      </switches>
   </system.diagnostics>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8cb5-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8cb5-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="b8cb5-129">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="b8cb5-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b8cb5-130">\<ソース></span><span class="sxs-lookup"><span data-stu-id="b8cb5-130">\<source></span></span>](source-element.md)
