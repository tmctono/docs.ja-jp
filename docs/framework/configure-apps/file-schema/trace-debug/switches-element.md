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
ms.openlocfilehash: c161f842192396101dcc6850f3b3da328958eac3
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697084"
---
# <a name="switches-element"></a><span data-ttu-id="be875-102">\<switches > 要素</span><span class="sxs-lookup"><span data-stu-id="be875-102">\<switches> Element</span></span>
<span data-ttu-id="be875-103">トレース スイッチと、トレース スイッチを設定するレベルを保持します。</span><span class="sxs-lookup"><span data-stu-id="be875-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
[<span data-ttu-id="be875-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="be875-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="be875-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="be875-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="be875-106">&nbsp; @ no__t-1 @ no__t @ no__t-3 **\<switches >**</span><span class="sxs-lookup"><span data-stu-id="be875-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be875-107">構文</span><span class="sxs-lookup"><span data-stu-id="be875-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be875-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="be875-108">Attributes and Elements</span></span>  
 <span data-ttu-id="be875-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="be875-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be875-110">属性</span><span class="sxs-lookup"><span data-stu-id="be875-110">Attributes</span></span>  
 <span data-ttu-id="be875-111">[なし] :</span><span class="sxs-lookup"><span data-stu-id="be875-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="be875-112">子要素</span><span class="sxs-lookup"><span data-stu-id="be875-112">Child Elements</span></span>  
  
|<span data-ttu-id="be875-113">要素</span><span class="sxs-lookup"><span data-stu-id="be875-113">Element</span></span>|<span data-ttu-id="be875-114">説明</span><span class="sxs-lookup"><span data-stu-id="be875-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be875-115">\<add></span><span class="sxs-lookup"><span data-stu-id="be875-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="be875-116">トレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="be875-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="be875-117">親要素</span><span class="sxs-lookup"><span data-stu-id="be875-117">Parent Elements</span></span>  
  
|<span data-ttu-id="be875-118">要素</span><span class="sxs-lookup"><span data-stu-id="be875-118">Element</span></span>|<span data-ttu-id="be875-119">説明</span><span class="sxs-lookup"><span data-stu-id="be875-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="be875-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="be875-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="be875-121">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="be875-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be875-122">コメント</span><span class="sxs-lookup"><span data-stu-id="be875-122">Remarks</span></span>  
 <span data-ttu-id="be875-123">トレーススイッチのレベルは、構成ファイルに配置することによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="be875-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="be875-124">スイッチが @no__t 0 の場合は、オンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="be875-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="be875-125">スイッチが @no__t 0 の場合は、別のレベルを割り当てて、アプリケーションが出力するトレースメッセージまたはデバッグメッセージの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="be875-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be875-126">例</span><span class="sxs-lookup"><span data-stu-id="be875-126">Example</span></span>  
 <span data-ttu-id="be875-127">次の例では、 **\<switch >** 要素を使用して `General` トレーススイッチを <xref:System.Diagnostics.TraceLevel> レベルに設定し、@no__t ブールトレーススイッチを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="be875-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="be875-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="be875-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="be875-129">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="be875-129">Trace and Debug Settings Schema</span></span>](index.md)
 