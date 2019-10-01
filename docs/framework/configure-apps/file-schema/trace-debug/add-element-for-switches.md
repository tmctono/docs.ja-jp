---
title: <switches> の <add> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: 2edc890049d62913d693ad61d8d814d012c0f482
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697176"
---
# <a name="add-element-for-switches"></a><span data-ttu-id="34f63-102">\<add-1switches の > 要素を追加 ></span><span class="sxs-lookup"><span data-stu-id="34f63-102">\<add> Element for \<switches></span></span>
<span data-ttu-id="34f63-103">トレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="34f63-103">Specifies the level where a trace switch is set.</span></span>  
  
[<span data-ttu-id="34f63-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="34f63-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="34f63-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="34f63-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="34f63-106">&nbsp; @ no__t @ no__t @no__t @ no__t-3[ **-6switches >** ](switches-element.md)</span><span class="sxs-lookup"><span data-stu-id="34f63-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<switches>**](switches-element.md)</span></span>  
<span data-ttu-id="34f63-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="34f63-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34f63-108">構文</span><span class="sxs-lookup"><span data-stu-id="34f63-108">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34f63-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="34f63-109">Attributes and Elements</span></span>  
 <span data-ttu-id="34f63-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="34f63-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34f63-111">属性</span><span class="sxs-lookup"><span data-stu-id="34f63-111">Attributes</span></span>  
  
|<span data-ttu-id="34f63-112">属性</span><span class="sxs-lookup"><span data-stu-id="34f63-112">Attribute</span></span>|<span data-ttu-id="34f63-113">説明</span><span class="sxs-lookup"><span data-stu-id="34f63-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34f63-114">**name**</span><span class="sxs-lookup"><span data-stu-id="34f63-114">**name**</span></span>|<span data-ttu-id="34f63-115">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="34f63-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="34f63-116">スイッチの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="34f63-116">Specifies the name of the switch.</span></span> <span data-ttu-id="34f63-117">この属性の値は、スイッチコンストラクターに渡される*displayName*パラメーターに対応します。</span><span class="sxs-lookup"><span data-stu-id="34f63-117">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="34f63-118">**value**</span><span class="sxs-lookup"><span data-stu-id="34f63-118">**value**</span></span>|<span data-ttu-id="34f63-119">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="34f63-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="34f63-120">スイッチのレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="34f63-120">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34f63-121">子要素</span><span class="sxs-lookup"><span data-stu-id="34f63-121">Child Elements</span></span>  
 <span data-ttu-id="34f63-122">なし。</span><span class="sxs-lookup"><span data-stu-id="34f63-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34f63-123">親要素</span><span class="sxs-lookup"><span data-stu-id="34f63-123">Parent Elements</span></span>  
  
|<span data-ttu-id="34f63-124">要素</span><span class="sxs-lookup"><span data-stu-id="34f63-124">Element</span></span>|<span data-ttu-id="34f63-125">説明</span><span class="sxs-lookup"><span data-stu-id="34f63-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="34f63-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="34f63-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="34f63-127">トレース スイッチと、トレース スイッチを設定するレベルを保持します。</span><span class="sxs-lookup"><span data-stu-id="34f63-127">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="34f63-128">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="34f63-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34f63-129">コメント</span><span class="sxs-lookup"><span data-stu-id="34f63-129">Remarks</span></span>  
 <span data-ttu-id="34f63-130">トレーススイッチのレベルは、構成ファイルに配置することによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="34f63-130">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="34f63-131">スイッチが @no__t 0 の場合は、オンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="34f63-131">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="34f63-132">スイッチが @no__t 0 の場合は、別のレベルを割り当てて、アプリケーションが出力するトレースメッセージまたはデバッグメッセージの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="34f63-132">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34f63-133">例</span><span class="sxs-lookup"><span data-stu-id="34f63-133">Example</span></span>  
 <span data-ttu-id="34f63-134">次の例では、 **\<add >** 要素を使用して `General` トレーススイッチを <xref:System.Diagnostics.TraceLevel> レベルに設定し、@no__t ブールトレーススイッチを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="34f63-134">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="34f63-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="34f63-135">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="34f63-136">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="34f63-136">Trace and Debug Settings Schema</span></span>](index.md)
