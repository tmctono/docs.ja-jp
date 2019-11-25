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
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088956"
---
# <a name="add-element-for-switches"></a><span data-ttu-id="91c94-102">\<スイッチの > 要素を追加 \<</span><span class="sxs-lookup"><span data-stu-id="91c94-102">\<add> Element for \<switches></span></span>
<span data-ttu-id="91c94-103">トレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="91c94-103">Specifies the level where a trace switch is set.</span></span>  

<span data-ttu-id="91c94-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="91c94-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="91c94-105">&nbsp;&nbsp;[ **\<** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="91c94-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="91c94-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**スイッチ**](switches-element.md)</span><span class="sxs-lookup"><span data-stu-id="91c94-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<switches>**](switches-element.md)</span></span>\
<span data-ttu-id="91c94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**追加 >**</span><span class="sxs-lookup"><span data-stu-id="91c94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="91c94-108">構文</span><span class="sxs-lookup"><span data-stu-id="91c94-108">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91c94-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="91c94-109">Attributes and Elements</span></span>  
 <span data-ttu-id="91c94-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="91c94-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91c94-111">属性</span><span class="sxs-lookup"><span data-stu-id="91c94-111">Attributes</span></span>  
  
|<span data-ttu-id="91c94-112">属性</span><span class="sxs-lookup"><span data-stu-id="91c94-112">Attribute</span></span>|<span data-ttu-id="91c94-113">説明</span><span class="sxs-lookup"><span data-stu-id="91c94-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="91c94-114">**name**</span><span class="sxs-lookup"><span data-stu-id="91c94-114">**name**</span></span>|<span data-ttu-id="91c94-115">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="91c94-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="91c94-116">スイッチの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="91c94-116">Specifies the name of the switch.</span></span> <span data-ttu-id="91c94-117">この属性の値は、スイッチコンストラクターに渡される*displayName*パラメーターに対応します。</span><span class="sxs-lookup"><span data-stu-id="91c94-117">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="91c94-118">**value**</span><span class="sxs-lookup"><span data-stu-id="91c94-118">**value**</span></span>|<span data-ttu-id="91c94-119">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="91c94-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="91c94-120">スイッチのレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="91c94-120">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91c94-121">子要素</span><span class="sxs-lookup"><span data-stu-id="91c94-121">Child Elements</span></span>  
 <span data-ttu-id="91c94-122">なし。</span><span class="sxs-lookup"><span data-stu-id="91c94-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91c94-123">親要素</span><span class="sxs-lookup"><span data-stu-id="91c94-123">Parent Elements</span></span>  
  
|<span data-ttu-id="91c94-124">要素</span><span class="sxs-lookup"><span data-stu-id="91c94-124">Element</span></span>|<span data-ttu-id="91c94-125">説明</span><span class="sxs-lookup"><span data-stu-id="91c94-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="91c94-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="91c94-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="91c94-127">トレース スイッチと、トレース スイッチを設定するレベルを保持します。</span><span class="sxs-lookup"><span data-stu-id="91c94-127">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="91c94-128">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="91c94-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91c94-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="91c94-129">Remarks</span></span>  
 <span data-ttu-id="91c94-130">トレーススイッチのレベルは、構成ファイルに配置することによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="91c94-130">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="91c94-131">スイッチが <xref:System.Diagnostics.BooleanSwitch>の場合は、オンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="91c94-131">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="91c94-132">スイッチが <xref:System.Diagnostics.TraceSwitch>の場合は、別のレベルを割り当てて、アプリケーションが出力するトレースメッセージまたはデバッグメッセージの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="91c94-132">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91c94-133">例</span><span class="sxs-lookup"><span data-stu-id="91c94-133">Example</span></span>  
 <span data-ttu-id="91c94-134">次の例では、 **\<add >** 要素を使用して `General` トレーススイッチを <xref:System.Diagnostics.TraceLevel> レベルに設定し、`Data` ブール型のトレーススイッチを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="91c94-134">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="91c94-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="91c94-135">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="91c94-136">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="91c94-136">Trace and Debug Settings Schema</span></span>](index.md)
