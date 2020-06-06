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
ms.openlocfilehash: 15cc9680d7a20341eb5d1d1df302c1e034e70e02
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153231"
---
# <a name="switches-element"></a><span data-ttu-id="0c4d4-102">\<switches> 要素</span><span class="sxs-lookup"><span data-stu-id="0c4d4-102">\<switches> Element</span></span>
<span data-ttu-id="0c4d4-103">トレース スイッチと、トレース スイッチを設定するレベルを保持します。</span><span class="sxs-lookup"><span data-stu-id="0c4d4-103">Contains trace switches and the level where the trace switches are set.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**

## <a name="syntax"></a><span data-ttu-id="0c4d4-104">構文</span><span class="sxs-lookup"><span data-stu-id="0c4d4-104">Syntax</span></span>  
  
```xml  
      <switches>
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c4d4-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0c4d4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0c4d4-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c4d4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c4d4-107">属性</span><span class="sxs-lookup"><span data-stu-id="0c4d4-107">Attributes</span></span>  
 <span data-ttu-id="0c4d4-108">なし。</span><span class="sxs-lookup"><span data-stu-id="0c4d4-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0c4d4-109">子要素</span><span class="sxs-lookup"><span data-stu-id="0c4d4-109">Child Elements</span></span>  
  
|<span data-ttu-id="0c4d4-110">要素</span><span class="sxs-lookup"><span data-stu-id="0c4d4-110">Element</span></span>|<span data-ttu-id="0c4d4-111">説明</span><span class="sxs-lookup"><span data-stu-id="0c4d4-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-switches.md)|<span data-ttu-id="0c4d4-112">トレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c4d4-112">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c4d4-113">親要素</span><span class="sxs-lookup"><span data-stu-id="0c4d4-113">Parent Elements</span></span>  
  
|<span data-ttu-id="0c4d4-114">要素</span><span class="sxs-lookup"><span data-stu-id="0c4d4-114">Element</span></span>|<span data-ttu-id="0c4d4-115">説明</span><span class="sxs-lookup"><span data-stu-id="0c4d4-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0c4d4-116">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="0c4d4-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="0c4d4-117">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c4d4-117">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c4d4-118">解説</span><span class="sxs-lookup"><span data-stu-id="0c4d4-118">Remarks</span></span>  
 <span data-ttu-id="0c4d4-119">トレーススイッチのレベルは、構成ファイルに配置することによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="0c4d4-119">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="0c4d4-120">スイッチがの場合は <xref:System.Diagnostics.BooleanSwitch> 、オンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0c4d4-120">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="0c4d4-121">スイッチがの場合は <xref:System.Diagnostics.TraceSwitch> 、別のレベルを割り当てて、アプリケーションが出力するトレースメッセージまたはデバッグメッセージの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c4d4-121">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c4d4-122">例</span><span class="sxs-lookup"><span data-stu-id="0c4d4-122">Example</span></span>  
 <span data-ttu-id="0c4d4-123">次の例では、要素を使用して **\<switch>** `General` トレーススイッチをレベルに設定 <xref:System.Diagnostics.TraceLevel> し、ブール型のトレーススイッチを有効にする方法を示し `Data` ます。</span><span class="sxs-lookup"><span data-stu-id="0c4d4-123">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0c4d4-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c4d4-124">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="0c4d4-125">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="0c4d4-125">Trace and Debug Settings Schema</span></span>](index.md)
