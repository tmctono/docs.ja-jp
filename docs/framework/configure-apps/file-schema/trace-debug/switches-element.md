---
title: <switches> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
ms.openlocfilehash: 4aeb3cb0cd75f0fb27e3b359b86da61a77b491c7
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088800"
---
# <a name="switches-element"></a><span data-ttu-id="0315e-102">\<スイッチ > 要素</span><span class="sxs-lookup"><span data-stu-id="0315e-102">\<switches> Element</span></span>
<span data-ttu-id="0315e-103">トレース スイッチと、トレース スイッチを設定するレベルを保持します。</span><span class="sxs-lookup"><span data-stu-id="0315e-103">Contains trace switches and the level where the trace switches are set.</span></span>  

<span data-ttu-id="0315e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0315e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0315e-105">&nbsp;&nbsp;[ **\<** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="0315e-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="0315e-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<スイッチ >**</span><span class="sxs-lookup"><span data-stu-id="0315e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0315e-107">構文</span><span class="sxs-lookup"><span data-stu-id="0315e-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0315e-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0315e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0315e-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0315e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0315e-110">属性</span><span class="sxs-lookup"><span data-stu-id="0315e-110">Attributes</span></span>  
 <span data-ttu-id="0315e-111">なし。</span><span class="sxs-lookup"><span data-stu-id="0315e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0315e-112">子要素</span><span class="sxs-lookup"><span data-stu-id="0315e-112">Child Elements</span></span>  
  
|<span data-ttu-id="0315e-113">要素</span><span class="sxs-lookup"><span data-stu-id="0315e-113">Element</span></span>|<span data-ttu-id="0315e-114">説明</span><span class="sxs-lookup"><span data-stu-id="0315e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0315e-115">\<add></span><span class="sxs-lookup"><span data-stu-id="0315e-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="0315e-116">トレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="0315e-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0315e-117">親要素</span><span class="sxs-lookup"><span data-stu-id="0315e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0315e-118">要素</span><span class="sxs-lookup"><span data-stu-id="0315e-118">Element</span></span>|<span data-ttu-id="0315e-119">説明</span><span class="sxs-lookup"><span data-stu-id="0315e-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0315e-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="0315e-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="0315e-121">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="0315e-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0315e-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="0315e-122">Remarks</span></span>  
 <span data-ttu-id="0315e-123">トレーススイッチのレベルは、構成ファイルに配置することによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="0315e-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="0315e-124">スイッチが <xref:System.Diagnostics.BooleanSwitch>の場合は、オンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0315e-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="0315e-125">スイッチが <xref:System.Diagnostics.TraceSwitch>の場合は、別のレベルを割り当てて、アプリケーションが出力するトレースメッセージまたはデバッグメッセージの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0315e-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0315e-126">例</span><span class="sxs-lookup"><span data-stu-id="0315e-126">Example</span></span>  
 <span data-ttu-id="0315e-127">次の例では、 **\<switch >** 要素を使用して `General` トレーススイッチを <xref:System.Diagnostics.TraceLevel> レベルに設定し、`Data` ブール型のトレーススイッチを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0315e-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0315e-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="0315e-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="0315e-129">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="0315e-129">Trace and Debug Settings Schema</span></span>](index.md)
