---
title: < Crst_DisableSpinWait> 要素
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a91e21120ecebbe7af2fb93798bc68d274fa92c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252720"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="2d5e9-102">\<Crst_DisableSpinWait> 要素</span><span class="sxs-lookup"><span data-stu-id="2d5e9-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="2d5e9-103">競合の多い場合、クリティカル セクションのスピン待機時間を無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d5e9-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
<span data-ttu-id="2d5e9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2d5e9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2d5e9-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="2d5e9-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="2d5e9-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Crst_DisableSpinWait >**</span><span class="sxs-lookup"><span data-stu-id="2d5e9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d5e9-107">構文</span><span class="sxs-lookup"><span data-stu-id="2d5e9-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d5e9-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2d5e9-108">Attributes and Elements</span></span>

<span data-ttu-id="2d5e9-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d5e9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d5e9-110">属性</span><span class="sxs-lookup"><span data-stu-id="2d5e9-110">Attributes</span></span>  
  
|<span data-ttu-id="2d5e9-111">属性</span><span class="sxs-lookup"><span data-stu-id="2d5e9-111">Attribute</span></span>|<span data-ttu-id="2d5e9-112">説明</span><span class="sxs-lookup"><span data-stu-id="2d5e9-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2d5e9-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="2d5e9-113">**enabled**</span></span>|<span data-ttu-id="2d5e9-114">重要なセクションが競合している場合は、スピンを待機するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d5e9-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2d5e9-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="2d5e9-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="2d5e9-116">値</span><span class="sxs-lookup"><span data-stu-id="2d5e9-116">Value</span></span>|<span data-ttu-id="2d5e9-117">説明</span><span class="sxs-lookup"><span data-stu-id="2d5e9-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2d5e9-118">1</span><span class="sxs-lookup"><span data-stu-id="2d5e9-118">1</span></span>|<span data-ttu-id="2d5e9-119">クリティカルセクションを取得できないときに、スピン待機を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d5e9-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="2d5e9-120">0</span><span class="sxs-lookup"><span data-stu-id="2d5e9-120">0</span></span>|<span data-ttu-id="2d5e9-121">クリティカルセクションを取得できない場合は、スピン待機を無効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="2d5e9-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="2d5e9-122">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="2d5e9-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d5e9-123">子要素</span><span class="sxs-lookup"><span data-stu-id="2d5e9-123">Child Elements</span></span>  
 <span data-ttu-id="2d5e9-124">なし。</span><span class="sxs-lookup"><span data-stu-id="2d5e9-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d5e9-125">親要素</span><span class="sxs-lookup"><span data-stu-id="2d5e9-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2d5e9-126">要素</span><span class="sxs-lookup"><span data-stu-id="2d5e9-126">Element</span></span>|<span data-ttu-id="2d5e9-127">説明</span><span class="sxs-lookup"><span data-stu-id="2d5e9-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2d5e9-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="2d5e9-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2d5e9-129">さまざまなランタイム構成設定に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d5e9-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2d5e9-130">例</span><span class="sxs-lookup"><span data-stu-id="2d5e9-130">Example</span></span>  

<span data-ttu-id="2d5e9-131">次の例では、重要なセクションで、競合がある場合、スピン待機を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d5e9-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d5e9-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d5e9-132">See also</span></span>

- [<span data-ttu-id="2d5e9-133">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="2d5e9-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2d5e9-134">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="2d5e9-134">Configuration File Schema</span></span>](../index.md)
