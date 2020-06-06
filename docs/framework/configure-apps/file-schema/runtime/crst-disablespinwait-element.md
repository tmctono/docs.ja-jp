---
title: <Crst_DisableSpinWait> 要素
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 0683081183081e249b2a9c89e1a6a15f638fb339
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117635"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="eafeb-102">\<Crst_DisableSpinWait> 要素</span><span class="sxs-lookup"><span data-stu-id="eafeb-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="eafeb-103">競合がある場合に、クリティカルセクションのスピン待機を無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="eafeb-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a><span data-ttu-id="eafeb-104">構文</span><span class="sxs-lookup"><span data-stu-id="eafeb-104">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eafeb-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="eafeb-105">Attributes and Elements</span></span>

<span data-ttu-id="eafeb-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="eafeb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eafeb-107">属性</span><span class="sxs-lookup"><span data-stu-id="eafeb-107">Attributes</span></span>  
  
|<span data-ttu-id="eafeb-108">属性</span><span class="sxs-lookup"><span data-stu-id="eafeb-108">Attribute</span></span>|<span data-ttu-id="eafeb-109">説明</span><span class="sxs-lookup"><span data-stu-id="eafeb-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eafeb-110">**enabled**</span><span class="sxs-lookup"><span data-stu-id="eafeb-110">**enabled**</span></span>|<span data-ttu-id="eafeb-111">重要なセクションが競合している場合は、スピンを待機するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="eafeb-111">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="eafeb-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="eafeb-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="eafeb-113">値</span><span class="sxs-lookup"><span data-stu-id="eafeb-113">Value</span></span>|<span data-ttu-id="eafeb-114">説明</span><span class="sxs-lookup"><span data-stu-id="eafeb-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eafeb-115">1</span><span class="sxs-lookup"><span data-stu-id="eafeb-115">1</span></span>|<span data-ttu-id="eafeb-116">クリティカルセクションを取得できないときに、スピン待機を無効にします。</span><span class="sxs-lookup"><span data-stu-id="eafeb-116">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="eafeb-117">0</span><span class="sxs-lookup"><span data-stu-id="eafeb-117">0</span></span>|<span data-ttu-id="eafeb-118">クリティカルセクションを取得できない場合は、スピン待機を無効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="eafeb-118">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="eafeb-119">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="eafeb-119">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eafeb-120">子要素</span><span class="sxs-lookup"><span data-stu-id="eafeb-120">Child Elements</span></span>  
 <span data-ttu-id="eafeb-121">なし。</span><span class="sxs-lookup"><span data-stu-id="eafeb-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eafeb-122">親要素</span><span class="sxs-lookup"><span data-stu-id="eafeb-122">Parent Elements</span></span>  
  
|<span data-ttu-id="eafeb-123">要素</span><span class="sxs-lookup"><span data-stu-id="eafeb-123">Element</span></span>|<span data-ttu-id="eafeb-124">Description</span><span class="sxs-lookup"><span data-stu-id="eafeb-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eafeb-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="eafeb-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="eafeb-126">さまざまなランタイム構成設定に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eafeb-126">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eafeb-127">例</span><span class="sxs-lookup"><span data-stu-id="eafeb-127">Example</span></span>  

<span data-ttu-id="eafeb-128">次の例では、重要なセクションで、競合がある場合、スピン待機を無効にします。</span><span class="sxs-lookup"><span data-stu-id="eafeb-128">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eafeb-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="eafeb-129">See also</span></span>

- [<span data-ttu-id="eafeb-130">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="eafeb-130">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="eafeb-131">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="eafeb-131">Configuration File Schema</span></span>](../index.md)
