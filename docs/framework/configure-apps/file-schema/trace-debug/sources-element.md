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
ms.openlocfilehash: 670fb359f892d83feac56c849361c4b980d9a922
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173810"
---
# <a name="sources-element"></a><span data-ttu-id="12144-102">\<sources> 要素</span><span class="sxs-lookup"><span data-stu-id="12144-102">\<sources> Element</span></span>

<span data-ttu-id="12144-103">トレースメッセージを開始するトレースソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="12144-103">Specifies trace sources that initiate tracing messages.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**

## <a name="syntax"></a><span data-ttu-id="12144-104">構文</span><span class="sxs-lookup"><span data-stu-id="12144-104">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12144-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="12144-105">Attributes and Elements</span></span>  

 <span data-ttu-id="12144-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="12144-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12144-107">属性</span><span class="sxs-lookup"><span data-stu-id="12144-107">Attributes</span></span>  

 <span data-ttu-id="12144-108">なし。</span><span class="sxs-lookup"><span data-stu-id="12144-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="12144-109">子要素</span><span class="sxs-lookup"><span data-stu-id="12144-109">Child Elements</span></span>  
  
|<span data-ttu-id="12144-110">要素</span><span class="sxs-lookup"><span data-stu-id="12144-110">Element</span></span>|<span data-ttu-id="12144-111">説明</span><span class="sxs-lookup"><span data-stu-id="12144-111">Description</span></span>|  
|-------------|-----------------|  
|[\<source>](source-element.md)|<span data-ttu-id="12144-112">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="12144-112">Required element.</span></span><br /><br /> <span data-ttu-id="12144-113">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="12144-113">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="12144-114">親要素</span><span class="sxs-lookup"><span data-stu-id="12144-114">Parent Elements</span></span>  
  
|<span data-ttu-id="12144-115">要素</span><span class="sxs-lookup"><span data-stu-id="12144-115">Element</span></span>|<span data-ttu-id="12144-116">説明</span><span class="sxs-lookup"><span data-stu-id="12144-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="12144-117">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="12144-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="12144-118">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="12144-118">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12144-119">解説</span><span class="sxs-lookup"><span data-stu-id="12144-119">Remarks</span></span>  

 <span data-ttu-id="12144-120">この要素は、マシン構成ファイル (Machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="12144-120">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12144-121">例</span><span class="sxs-lookup"><span data-stu-id="12144-121">Example</span></span>  

 <span data-ttu-id="12144-122">次の例では、要素を使用してトレースソースを追加し、と `<sources>` `mySource` いう名前のソーススイッチのレベルを設定する方法を示し `sourceSwitch` ます。</span><span class="sxs-lookup"><span data-stu-id="12144-122">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="12144-123">トレース情報をコンソールに書き込むコンソールトレースリスナーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="12144-123">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12144-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="12144-124">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="12144-125">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="12144-125">Trace and Debug Settings Schema</span></span>](index.md)
- [\<source>](source-element.md)
