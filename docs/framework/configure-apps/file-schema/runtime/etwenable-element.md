---
title: <etwEnable> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb4d0ed5b33170c40aacb32bebbf1b59ca659be4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252614"
---
# <a name="etwenable-element"></a><span data-ttu-id="3ef90-102">\<etwEnable> 要素</span><span class="sxs-lookup"><span data-stu-id="3ef90-102">\<etwEnable> Element</span></span>
<span data-ttu-id="3ef90-103">共通言語ランタイム イベントで Windows イベント トレーシング (ETW) を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ef90-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
<span data-ttu-id="3ef90-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3ef90-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3ef90-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="3ef90-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="3ef90-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<etwEnabled>**</span><span class="sxs-lookup"><span data-stu-id="3ef90-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ef90-107">構文</span><span class="sxs-lookup"><span data-stu-id="3ef90-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ef90-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3ef90-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3ef90-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ef90-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ef90-110">属性</span><span class="sxs-lookup"><span data-stu-id="3ef90-110">Attributes</span></span>  
  
|<span data-ttu-id="3ef90-111">属性</span><span class="sxs-lookup"><span data-stu-id="3ef90-111">Attribute</span></span>|<span data-ttu-id="3ef90-112">説明</span><span class="sxs-lookup"><span data-stu-id="3ef90-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ef90-113">enabled</span><span class="sxs-lookup"><span data-stu-id="3ef90-113">enabled</span></span>|<span data-ttu-id="3ef90-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="3ef90-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="3ef90-115">ETW を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ef90-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3ef90-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="3ef90-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="3ef90-117">値</span><span class="sxs-lookup"><span data-stu-id="3ef90-117">Value</span></span>|<span data-ttu-id="3ef90-118">説明</span><span class="sxs-lookup"><span data-stu-id="3ef90-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ef90-119">true</span><span class="sxs-lookup"><span data-stu-id="3ef90-119">true</span></span>|<span data-ttu-id="3ef90-120">ETW を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ef90-120">Enable ETW.</span></span> <span data-ttu-id="3ef90-121">Windows Vista および Windows Server 2008 オペレーティングシステム以降のバージョンの Windows では、これが既定です。</span><span class="sxs-lookup"><span data-stu-id="3ef90-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="3ef90-122">False</span><span class="sxs-lookup"><span data-stu-id="3ef90-122">false</span></span>|<span data-ttu-id="3ef90-123">ETW を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3ef90-123">Disable ETW.</span></span> <span data-ttu-id="3ef90-124">これは、以前のバージョンの Windows では既定です。</span><span class="sxs-lookup"><span data-stu-id="3ef90-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ef90-125">子要素</span><span class="sxs-lookup"><span data-stu-id="3ef90-125">Child Elements</span></span>  
 <span data-ttu-id="3ef90-126">なし。</span><span class="sxs-lookup"><span data-stu-id="3ef90-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ef90-127">親要素</span><span class="sxs-lookup"><span data-stu-id="3ef90-127">Parent Elements</span></span>  
  
|<span data-ttu-id="3ef90-128">要素</span><span class="sxs-lookup"><span data-stu-id="3ef90-128">Element</span></span>|<span data-ttu-id="3ef90-129">説明</span><span class="sxs-lookup"><span data-stu-id="3ef90-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3ef90-130">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="3ef90-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3ef90-131">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ef90-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ef90-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="3ef90-132">Remarks</span></span>  
 <span data-ttu-id="3ef90-133">Windows Vista 以降では、ETW は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="3ef90-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="3ef90-134">アプリケーションの ETW を無効にするには、この要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="3ef90-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="3ef90-135">以前のバージョンの Windows では、この要素を使用して、アプリケーションの ETW を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ef90-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ef90-136">ETW は、レジストリ設定を使用して、サーバー上でグローバルに有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ef90-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="3ef90-137">「 [.NET Framework のログ記録の制御](../../../performance/controlling-logging.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ef90-137">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ef90-138">例</span><span class="sxs-lookup"><span data-stu-id="3ef90-138">Example</span></span>  
 <span data-ttu-id="3ef90-139">次の例は、アプリケーションの ETW トレースを有効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3ef90-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ef90-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ef90-140">See also</span></span>

- [<span data-ttu-id="3ef90-141">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="3ef90-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3ef90-142">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="3ef90-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3ef90-143">.NET Framework のログ記録の制御</span><span class="sxs-lookup"><span data-stu-id="3ef90-143">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
