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
ms.openlocfilehash: 0ca35d9be5e1eaf36a2c9cae99efc2736ef3403d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699206"
---
# <a name="sources-element"></a><span data-ttu-id="e220e-102">@no__t 0sources > 要素</span><span class="sxs-lookup"><span data-stu-id="e220e-102">\<sources> Element</span></span>
<span data-ttu-id="e220e-103">トレースメッセージを開始するトレースソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="e220e-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
[<span data-ttu-id="e220e-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="e220e-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="e220e-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="e220e-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="e220e-106">&nbsp; @ no__t-1 @ no__t @ no__t **\<sources >**</span><span class="sxs-lookup"><span data-stu-id="e220e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e220e-107">構文</span><span class="sxs-lookup"><span data-stu-id="e220e-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e220e-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e220e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e220e-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e220e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e220e-110">属性</span><span class="sxs-lookup"><span data-stu-id="e220e-110">Attributes</span></span>  
 <span data-ttu-id="e220e-111">[なし] :</span><span class="sxs-lookup"><span data-stu-id="e220e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e220e-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e220e-112">Child Elements</span></span>  
  
|<span data-ttu-id="e220e-113">要素</span><span class="sxs-lookup"><span data-stu-id="e220e-113">Element</span></span>|<span data-ttu-id="e220e-114">説明</span><span class="sxs-lookup"><span data-stu-id="e220e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e220e-115">\<source></span><span class="sxs-lookup"><span data-stu-id="e220e-115">\<source></span></span>](source-element.md)|<span data-ttu-id="e220e-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="e220e-116">Required element.</span></span><br /><br /> <span data-ttu-id="e220e-117">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="e220e-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e220e-118">親要素</span><span class="sxs-lookup"><span data-stu-id="e220e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e220e-119">要素</span><span class="sxs-lookup"><span data-stu-id="e220e-119">Element</span></span>|<span data-ttu-id="e220e-120">説明</span><span class="sxs-lookup"><span data-stu-id="e220e-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e220e-121">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="e220e-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e220e-122">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="e220e-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e220e-123">コメント</span><span class="sxs-lookup"><span data-stu-id="e220e-123">Remarks</span></span>  
 <span data-ttu-id="e220e-124">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e220e-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e220e-125">例</span><span class="sxs-lookup"><span data-stu-id="e220e-125">Example</span></span>  
 <span data-ttu-id="e220e-126">次の例では、`<sources>` の要素を使用してトレース @no__t ソースを追加し、`sourceSwitch` という名前のソーススイッチのレベルを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e220e-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="e220e-127">トレース情報をコンソールに書き込むコンソールトレースリスナーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="e220e-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e220e-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="e220e-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="e220e-129">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="e220e-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e220e-130">\<source></span><span class="sxs-lookup"><span data-stu-id="e220e-130">\<source></span></span>](source-element.md)
