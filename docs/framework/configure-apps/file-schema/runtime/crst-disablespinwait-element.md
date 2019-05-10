---
title: < Crst_DisableSpinWait > 要素
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f89f0558c11e229fef2ca3cd619e3c033f12c858
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754674"
---
# <a name="crstdisablespinwait-element"></a><span data-ttu-id="9200c-102">\<Crst_DisableSpinWait > 要素</span><span class="sxs-lookup"><span data-stu-id="9200c-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="9200c-103">競合の多い場合、クリティカル セクションのスピン待機時間を無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9200c-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
 <span data-ttu-id="9200c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9200c-104">\<configuration></span></span>  
<span data-ttu-id="9200c-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="9200c-105">\<runtime></span></span>  
<span data-ttu-id="9200c-106">\<Crst_DisableSpinWait></span><span class="sxs-lookup"><span data-stu-id="9200c-106">\<Crst_DisableSpinWait></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9200c-107">構文</span><span class="sxs-lookup"><span data-stu-id="9200c-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9200c-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9200c-108">Attributes and Elements</span></span>

<span data-ttu-id="9200c-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9200c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9200c-110">属性</span><span class="sxs-lookup"><span data-stu-id="9200c-110">Attributes</span></span>  
  
|<span data-ttu-id="9200c-111">属性</span><span class="sxs-lookup"><span data-stu-id="9200c-111">Attribute</span></span>|<span data-ttu-id="9200c-112">説明</span><span class="sxs-lookup"><span data-stu-id="9200c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9200c-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="9200c-113">**enabled**</span></span>|<span data-ttu-id="9200c-114">重要なセクションでは、競合の多いときの待機中のスピンが無効になっているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9200c-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9200c-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="9200c-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9200c-116">値</span><span class="sxs-lookup"><span data-stu-id="9200c-116">Value</span></span>|<span data-ttu-id="9200c-117">説明</span><span class="sxs-lookup"><span data-stu-id="9200c-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9200c-118">1</span><span class="sxs-lookup"><span data-stu-id="9200c-118">1</span></span>|<span data-ttu-id="9200c-119">クリティカル セクションを取得できない場合は、スピン待ちを無効にします。</span><span class="sxs-lookup"><span data-stu-id="9200c-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="9200c-120">0</span><span class="sxs-lookup"><span data-stu-id="9200c-120">0</span></span>|<span data-ttu-id="9200c-121">クリティカル セクションを取得できない場合にスピン待ちを無効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="9200c-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="9200c-122">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="9200c-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9200c-123">子要素</span><span class="sxs-lookup"><span data-stu-id="9200c-123">Child Elements</span></span>  
 <span data-ttu-id="9200c-124">なし。</span><span class="sxs-lookup"><span data-stu-id="9200c-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9200c-125">親要素</span><span class="sxs-lookup"><span data-stu-id="9200c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9200c-126">要素</span><span class="sxs-lookup"><span data-stu-id="9200c-126">Element</span></span>|<span data-ttu-id="9200c-127">説明</span><span class="sxs-lookup"><span data-stu-id="9200c-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9200c-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="9200c-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9200c-129">さまざまなランタイムの構成設定についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="9200c-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9200c-130">例</span><span class="sxs-lookup"><span data-stu-id="9200c-130">Example</span></span>  

<span data-ttu-id="9200c-131">次の例を無効に競合の多いときに重要なセクションで待機中のスピンします。</span><span class="sxs-lookup"><span data-stu-id="9200c-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9200c-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="9200c-132">See also</span></span>

- [<span data-ttu-id="9200c-133">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9200c-133">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="9200c-134">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="9200c-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
