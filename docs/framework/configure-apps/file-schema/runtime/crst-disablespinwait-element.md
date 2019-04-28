---
title: < Crst_DisableSpinWait > 要素
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cde26250db0b3d11c51a18b7ebd378953ae0958
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704831"
---
# <a name="crstdisablespinwait-element"></a><span data-ttu-id="a24cb-102">\<Crst_DisableSpinWait > 要素</span><span class="sxs-lookup"><span data-stu-id="a24cb-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="a24cb-103">競合の多い場合、クリティカル セクションのスピン待機時間を無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a24cb-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span> \ 
  
 <span data-ttu-id="a24cb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a24cb-104">\<configuration></span></span>  
<span data-ttu-id="a24cb-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="a24cb-105">\<runtime></span></span>  
<span data-ttu-id="a24cb-106">\<Crst_DisableSpinWait></span><span class="sxs-lookup"><span data-stu-id="a24cb-106">\<Crst_DisableSpinWait></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a24cb-107">構文</span><span class="sxs-lookup"><span data-stu-id="a24cb-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a24cb-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a24cb-108">Attributes and Elements</span></span>

<span data-ttu-id="a24cb-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a24cb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a24cb-110">属性</span><span class="sxs-lookup"><span data-stu-id="a24cb-110">Attributes</span></span>  
  
|<span data-ttu-id="a24cb-111">属性</span><span class="sxs-lookup"><span data-stu-id="a24cb-111">Attribute</span></span>|<span data-ttu-id="a24cb-112">説明</span><span class="sxs-lookup"><span data-stu-id="a24cb-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a24cb-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="a24cb-113">**enabled**</span></span>|<span data-ttu-id="a24cb-114">競合の多いときにクリティカル セクションのスピン待機時間が有効かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a24cb-114">Specifies whether spin-waiting for critical sections is enabled when they are contended.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a24cb-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="a24cb-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a24cb-116">値</span><span class="sxs-lookup"><span data-stu-id="a24cb-116">Value</span></span>|<span data-ttu-id="a24cb-117">説明</span><span class="sxs-lookup"><span data-stu-id="a24cb-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a24cb-118">1</span><span class="sxs-lookup"><span data-stu-id="a24cb-118">1</span></span>|<span data-ttu-id="a24cb-119">スピン待ちになっています。</span><span class="sxs-lookup"><span data-stu-id="a24cb-119">Spin-waiting is enabled.</span></span>|  
|<span data-ttu-id="a24cb-120">0</span><span class="sxs-lookup"><span data-stu-id="a24cb-120">0</span></span>|<span data-ttu-id="a24cb-121">スピン待ちを無効になります。</span><span class="sxs-lookup"><span data-stu-id="a24cb-121">Spin-waiting is disabled.</span></span> <span data-ttu-id="a24cb-122">これは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="a24cb-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a24cb-123">子要素</span><span class="sxs-lookup"><span data-stu-id="a24cb-123">Child Elements</span></span>  
 <span data-ttu-id="a24cb-124">なし。</span><span class="sxs-lookup"><span data-stu-id="a24cb-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a24cb-125">親要素</span><span class="sxs-lookup"><span data-stu-id="a24cb-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a24cb-126">要素</span><span class="sxs-lookup"><span data-stu-id="a24cb-126">Element</span></span>|<span data-ttu-id="a24cb-127">説明</span><span class="sxs-lookup"><span data-stu-id="a24cb-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a24cb-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a24cb-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a24cb-129">さまざまなランタイムの構成設定についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="a24cb-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a24cb-130">例</span><span class="sxs-lookup"><span data-stu-id="a24cb-130">Example</span></span>  

<span data-ttu-id="a24cb-131">次の例を無効に競合の多いときに重要なセクションで待機中のスピンします。</span><span class="sxs-lookup"><span data-stu-id="a24cb-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a24cb-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="a24cb-132">See also</span></span>

- [<span data-ttu-id="a24cb-133">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a24cb-133">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="a24cb-134">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="a24cb-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
