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
ms.openlocfilehash: 44f5c918f19f84daf827ad4e8f3b6bfbc3e9f439
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196529"
---
# <a name="switches-element"></a><span data-ttu-id="5221f-102">\<スイッチ > 要素</span><span class="sxs-lookup"><span data-stu-id="5221f-102">\<switches> Element</span></span>
<span data-ttu-id="5221f-103">トレース スイッチと、トレース スイッチを設定するレベルを保持します。</span><span class="sxs-lookup"><span data-stu-id="5221f-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="5221f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5221f-104">\<configuration></span></span>  
<span data-ttu-id="5221f-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="5221f-105">\<system.diagnostics></span></span>  
<span data-ttu-id="5221f-106">\<switches></span><span class="sxs-lookup"><span data-stu-id="5221f-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5221f-107">構文</span><span class="sxs-lookup"><span data-stu-id="5221f-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5221f-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5221f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5221f-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5221f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5221f-110">属性</span><span class="sxs-lookup"><span data-stu-id="5221f-110">Attributes</span></span>  
 <span data-ttu-id="5221f-111">なし。</span><span class="sxs-lookup"><span data-stu-id="5221f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5221f-112">子要素</span><span class="sxs-lookup"><span data-stu-id="5221f-112">Child Elements</span></span>  
  
|<span data-ttu-id="5221f-113">要素</span><span class="sxs-lookup"><span data-stu-id="5221f-113">Element</span></span>|<span data-ttu-id="5221f-114">説明</span><span class="sxs-lookup"><span data-stu-id="5221f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5221f-115">\<add></span><span class="sxs-lookup"><span data-stu-id="5221f-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="5221f-116">トレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="5221f-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5221f-117">親要素</span><span class="sxs-lookup"><span data-stu-id="5221f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5221f-118">要素</span><span class="sxs-lookup"><span data-stu-id="5221f-118">Element</span></span>|<span data-ttu-id="5221f-119">説明</span><span class="sxs-lookup"><span data-stu-id="5221f-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5221f-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="5221f-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="5221f-121">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="5221f-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5221f-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="5221f-122">Remarks</span></span>  
 <span data-ttu-id="5221f-123">構成ファイル内に配置して、トレース スイッチのレベルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="5221f-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="5221f-124">スイッチの場合、 <xref:System.Diagnostics.BooleanSwitch>、オンとオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5221f-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="5221f-125">スイッチの場合、<xref:System.Diagnostics.TraceSwitch>デバッグ メッセージをアプリケーションの出力やトレースの種類を指定するためにさまざまなレベルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5221f-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5221f-126">例</span><span class="sxs-lookup"><span data-stu-id="5221f-126">Example</span></span>  
 <span data-ttu-id="5221f-127">次の例は、使用する方法を示します、 **\<切り替える >** を設定する要素、`General`トレース スイッチを<xref:System.Diagnostics.TraceLevel>レベル、および有効にする、`Data`ブール トレース スイッチ。</span><span class="sxs-lookup"><span data-stu-id="5221f-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5221f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="5221f-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="5221f-129">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="5221f-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
