---
title: <switches> の <add> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: db2de681227dfdb7420808963219b9f52381f8fe
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088956"
---
# <a name="add-element-for-switches"></a><span data-ttu-id="49b7b-102">\<switches> の \<add> 要素</span><span class="sxs-lookup"><span data-stu-id="49b7b-102">\<add> Element for \<switches></span></span>
<span data-ttu-id="49b7b-103">トレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="49b7b-103">Specifies the level where a trace switch is set.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<switches>**](switches-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="49b7b-104">構文</span><span class="sxs-lookup"><span data-stu-id="49b7b-104">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49b7b-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="49b7b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="49b7b-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="49b7b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49b7b-107">属性</span><span class="sxs-lookup"><span data-stu-id="49b7b-107">Attributes</span></span>  
  
|<span data-ttu-id="49b7b-108">属性</span><span class="sxs-lookup"><span data-stu-id="49b7b-108">Attribute</span></span>|<span data-ttu-id="49b7b-109">説明</span><span class="sxs-lookup"><span data-stu-id="49b7b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="49b7b-110">**name**</span><span class="sxs-lookup"><span data-stu-id="49b7b-110">**name**</span></span>|<span data-ttu-id="49b7b-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="49b7b-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="49b7b-112">スイッチの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="49b7b-112">Specifies the name of the switch.</span></span> <span data-ttu-id="49b7b-113">この属性の値は、スイッチコンストラクターに渡される*displayName*パラメーターに対応します。</span><span class="sxs-lookup"><span data-stu-id="49b7b-113">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="49b7b-114">**value**</span><span class="sxs-lookup"><span data-stu-id="49b7b-114">**value**</span></span>|<span data-ttu-id="49b7b-115">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="49b7b-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="49b7b-116">スイッチのレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="49b7b-116">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49b7b-117">子要素</span><span class="sxs-lookup"><span data-stu-id="49b7b-117">Child Elements</span></span>  
 <span data-ttu-id="49b7b-118">なし。</span><span class="sxs-lookup"><span data-stu-id="49b7b-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="49b7b-119">親要素</span><span class="sxs-lookup"><span data-stu-id="49b7b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="49b7b-120">要素</span><span class="sxs-lookup"><span data-stu-id="49b7b-120">Element</span></span>|<span data-ttu-id="49b7b-121">Description</span><span class="sxs-lookup"><span data-stu-id="49b7b-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="49b7b-122">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="49b7b-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="49b7b-123">トレース スイッチと、トレース スイッチを設定するレベルを保持します。</span><span class="sxs-lookup"><span data-stu-id="49b7b-123">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="49b7b-124">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="49b7b-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49b7b-125">解説</span><span class="sxs-lookup"><span data-stu-id="49b7b-125">Remarks</span></span>  
 <span data-ttu-id="49b7b-126">トレーススイッチのレベルは、構成ファイルに配置することによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="49b7b-126">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="49b7b-127">スイッチがの場合は <xref:System.Diagnostics.BooleanSwitch> 、オンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="49b7b-127">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="49b7b-128">スイッチがの場合は <xref:System.Diagnostics.TraceSwitch> 、別のレベルを割り当てて、アプリケーションが出力するトレースメッセージまたはデバッグメッセージの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="49b7b-128">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49b7b-129">例</span><span class="sxs-lookup"><span data-stu-id="49b7b-129">Example</span></span>  
 <span data-ttu-id="49b7b-130">次の例では、要素を使用して **\<add>** `General` トレーススイッチをレベルに設定 <xref:System.Diagnostics.TraceLevel> し、ブール型のトレーススイッチを有効にする方法を示し `Data` ます。</span><span class="sxs-lookup"><span data-stu-id="49b7b-130">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="49b7b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="49b7b-131">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="49b7b-132">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="49b7b-132">Trace and Debug Settings Schema</span></span>](index.md)
