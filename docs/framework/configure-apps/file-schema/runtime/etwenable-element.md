---
title: <etwEnable> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ba411114bfb853e06c83adb42713d43f1452d9c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704805"
---
# <a name="etwenable-element"></a><span data-ttu-id="77266-102">\<etwEnable > 要素</span><span class="sxs-lookup"><span data-stu-id="77266-102">\<etwEnable> Element</span></span>
<span data-ttu-id="77266-103">共通言語ランタイム イベントで Windows イベント トレーシング (ETW) を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="77266-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="77266-104">\<configuration > 要素</span><span class="sxs-lookup"><span data-stu-id="77266-104">\<configuration> Element</span></span>  
<span data-ttu-id="77266-105">\<ランタイム > 要素</span><span class="sxs-lookup"><span data-stu-id="77266-105">\<runtime> Element</span></span>  
<span data-ttu-id="77266-106">\<etwEnabled></span><span class="sxs-lookup"><span data-stu-id="77266-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77266-107">構文</span><span class="sxs-lookup"><span data-stu-id="77266-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77266-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="77266-108">Attributes and Elements</span></span>  
 <span data-ttu-id="77266-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="77266-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77266-110">属性</span><span class="sxs-lookup"><span data-stu-id="77266-110">Attributes</span></span>  
  
|<span data-ttu-id="77266-111">属性</span><span class="sxs-lookup"><span data-stu-id="77266-111">Attribute</span></span>|<span data-ttu-id="77266-112">説明</span><span class="sxs-lookup"><span data-stu-id="77266-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77266-113">enabled</span><span class="sxs-lookup"><span data-stu-id="77266-113">enabled</span></span>|<span data-ttu-id="77266-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="77266-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="77266-115">ETW を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="77266-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="77266-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="77266-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="77266-117">値</span><span class="sxs-lookup"><span data-stu-id="77266-117">Value</span></span>|<span data-ttu-id="77266-118">説明</span><span class="sxs-lookup"><span data-stu-id="77266-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="77266-119">true</span><span class="sxs-lookup"><span data-stu-id="77266-119">true</span></span>|<span data-ttu-id="77266-120">ETW を有効にします。</span><span class="sxs-lookup"><span data-stu-id="77266-120">Enable ETW.</span></span> <span data-ttu-id="77266-121">これは、Windows、Windows Vista および Windows Server 2008 オペレーティング システム以降のバージョンの既定値です。</span><span class="sxs-lookup"><span data-stu-id="77266-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="77266-122">False</span><span class="sxs-lookup"><span data-stu-id="77266-122">false</span></span>|<span data-ttu-id="77266-123">ETW を無効にします。</span><span class="sxs-lookup"><span data-stu-id="77266-123">Disable ETW.</span></span> <span data-ttu-id="77266-124">これは、Windows の以前のバージョンの既定値です。</span><span class="sxs-lookup"><span data-stu-id="77266-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77266-125">子要素</span><span class="sxs-lookup"><span data-stu-id="77266-125">Child Elements</span></span>  
 <span data-ttu-id="77266-126">なし。</span><span class="sxs-lookup"><span data-stu-id="77266-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77266-127">親要素</span><span class="sxs-lookup"><span data-stu-id="77266-127">Parent Elements</span></span>  
  
|<span data-ttu-id="77266-128">要素</span><span class="sxs-lookup"><span data-stu-id="77266-128">Element</span></span>|<span data-ttu-id="77266-129">説明</span><span class="sxs-lookup"><span data-stu-id="77266-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="77266-130">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="77266-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="77266-131">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="77266-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77266-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="77266-132">Remarks</span></span>  
 <span data-ttu-id="77266-133">ETW は Windows Vista 以降、既定で有効です。</span><span class="sxs-lookup"><span data-stu-id="77266-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="77266-134">アプリケーションの ETW を無効にするのにには、この要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="77266-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="77266-135">Windows の以前のバージョンでは、アプリケーションの ETW を有効にするのにこの要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="77266-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77266-136">ETW を有効になっているか、レジストリ設定を使用して、サーバーでグローバルに無効にします。</span><span class="sxs-lookup"><span data-stu-id="77266-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="77266-137">参照してください[.NET Framework のログ記録を制御する](../../../../../docs/framework/performance/controlling-logging.md)します。</span><span class="sxs-lookup"><span data-stu-id="77266-137">See [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="77266-138">例</span><span class="sxs-lookup"><span data-stu-id="77266-138">Example</span></span>  
 <span data-ttu-id="77266-139">次の例では、アプリケーションの ETW トレースを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="77266-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="77266-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="77266-140">See also</span></span>

- [<span data-ttu-id="77266-141">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="77266-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="77266-142">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="77266-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="77266-143">.NET Framework のログ記録の制御</span><span class="sxs-lookup"><span data-stu-id="77266-143">Controlling .NET Framework Logging</span></span>](../../../../../docs/framework/performance/controlling-logging.md)
