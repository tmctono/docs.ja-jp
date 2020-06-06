---
title: <etwEnable> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 14cea171a4a25e148ea32f75a8ef09b83a4ec8ad
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117390"
---
# <a name="etwenable-element"></a><span data-ttu-id="08844-102">\<etwEnable> 要素</span><span class="sxs-lookup"><span data-stu-id="08844-102">\<etwEnable> Element</span></span>
<span data-ttu-id="08844-103">共通言語ランタイム イベントで Windows イベント トレーシング (ETW) を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="08844-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**  
  
## <a name="syntax"></a><span data-ttu-id="08844-104">構文</span><span class="sxs-lookup"><span data-stu-id="08844-104">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08844-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="08844-105">Attributes and Elements</span></span>  
 <span data-ttu-id="08844-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="08844-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08844-107">属性</span><span class="sxs-lookup"><span data-stu-id="08844-107">Attributes</span></span>  
  
|<span data-ttu-id="08844-108">属性</span><span class="sxs-lookup"><span data-stu-id="08844-108">Attribute</span></span>|<span data-ttu-id="08844-109">説明</span><span class="sxs-lookup"><span data-stu-id="08844-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="08844-110">enabled</span><span class="sxs-lookup"><span data-stu-id="08844-110">enabled</span></span>|<span data-ttu-id="08844-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="08844-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="08844-112">ETW を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="08844-112">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="08844-113">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="08844-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="08844-114">値</span><span class="sxs-lookup"><span data-stu-id="08844-114">Value</span></span>|<span data-ttu-id="08844-115">Description</span><span class="sxs-lookup"><span data-stu-id="08844-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="08844-116">true</span><span class="sxs-lookup"><span data-stu-id="08844-116">true</span></span>|<span data-ttu-id="08844-117">ETW を有効にします。</span><span class="sxs-lookup"><span data-stu-id="08844-117">Enable ETW.</span></span> <span data-ttu-id="08844-118">Windows Vista および Windows Server 2008 オペレーティングシステム以降のバージョンの Windows では、これが既定です。</span><span class="sxs-lookup"><span data-stu-id="08844-118">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="08844-119">false</span><span class="sxs-lookup"><span data-stu-id="08844-119">false</span></span>|<span data-ttu-id="08844-120">ETW を無効にします。</span><span class="sxs-lookup"><span data-stu-id="08844-120">Disable ETW.</span></span> <span data-ttu-id="08844-121">これは、以前のバージョンの Windows では既定です。</span><span class="sxs-lookup"><span data-stu-id="08844-121">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08844-122">子要素</span><span class="sxs-lookup"><span data-stu-id="08844-122">Child Elements</span></span>  
 <span data-ttu-id="08844-123">なし。</span><span class="sxs-lookup"><span data-stu-id="08844-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08844-124">親要素</span><span class="sxs-lookup"><span data-stu-id="08844-124">Parent Elements</span></span>  
  
|<span data-ttu-id="08844-125">要素</span><span class="sxs-lookup"><span data-stu-id="08844-125">Element</span></span>|<span data-ttu-id="08844-126">Description</span><span class="sxs-lookup"><span data-stu-id="08844-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="08844-127">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="08844-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="08844-128">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="08844-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08844-129">解説</span><span class="sxs-lookup"><span data-stu-id="08844-129">Remarks</span></span>  
 <span data-ttu-id="08844-130">Windows Vista 以降では、ETW は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="08844-130">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="08844-131">アプリケーションの ETW を無効にするには、この要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="08844-131">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="08844-132">以前のバージョンの Windows では、この要素を使用して、アプリケーションの ETW を有効にします。</span><span class="sxs-lookup"><span data-stu-id="08844-132">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08844-133">ETW は、レジストリ設定を使用して、サーバー上でグローバルに有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="08844-133">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="08844-134">「 [.NET Framework のログ記録の制御](../../../performance/controlling-logging.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08844-134">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="08844-135">例</span><span class="sxs-lookup"><span data-stu-id="08844-135">Example</span></span>  
 <span data-ttu-id="08844-136">次の例は、アプリケーションの ETW トレースを有効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="08844-136">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="08844-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="08844-137">See also</span></span>

- [<span data-ttu-id="08844-138">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="08844-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="08844-139">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="08844-139">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="08844-140">.NET Framework のログ記録の制御</span><span class="sxs-lookup"><span data-stu-id="08844-140">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
