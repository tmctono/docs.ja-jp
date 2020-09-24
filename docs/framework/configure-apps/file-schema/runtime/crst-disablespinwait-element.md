---
title: <Crst_DisableSpinWait> 要素
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 45052d99bb297ac39d058fa405fe57a7c991f738
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151351"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="85fd1-102">\<Crst_DisableSpinWait> 要素</span><span class="sxs-lookup"><span data-stu-id="85fd1-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="85fd1-103">競合がある場合に、クリティカルセクションのスピン待機を無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="85fd1-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a><span data-ttu-id="85fd1-104">構文</span><span class="sxs-lookup"><span data-stu-id="85fd1-104">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85fd1-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="85fd1-105">Attributes and Elements</span></span>

<span data-ttu-id="85fd1-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="85fd1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85fd1-107">属性</span><span class="sxs-lookup"><span data-stu-id="85fd1-107">Attributes</span></span>  
  
|<span data-ttu-id="85fd1-108">属性</span><span class="sxs-lookup"><span data-stu-id="85fd1-108">Attribute</span></span>|<span data-ttu-id="85fd1-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="85fd1-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85fd1-110">**有効**</span><span class="sxs-lookup"><span data-stu-id="85fd1-110">**enabled**</span></span>|<span data-ttu-id="85fd1-111">重要なセクションが競合している場合は、スピンを待機するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="85fd1-111">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="85fd1-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="85fd1-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="85fd1-113">値</span><span class="sxs-lookup"><span data-stu-id="85fd1-113">Value</span></span>|<span data-ttu-id="85fd1-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="85fd1-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="85fd1-115">1</span><span class="sxs-lookup"><span data-stu-id="85fd1-115">1</span></span>|<span data-ttu-id="85fd1-116">クリティカルセクションを取得できないときに、スピン待機を無効にします。</span><span class="sxs-lookup"><span data-stu-id="85fd1-116">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="85fd1-117">0</span><span class="sxs-lookup"><span data-stu-id="85fd1-117">0</span></span>|<span data-ttu-id="85fd1-118">クリティカルセクションを取得できない場合は、スピン待機を無効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="85fd1-118">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="85fd1-119">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="85fd1-119">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85fd1-120">子要素</span><span class="sxs-lookup"><span data-stu-id="85fd1-120">Child Elements</span></span>  

 <span data-ttu-id="85fd1-121">なし。</span><span class="sxs-lookup"><span data-stu-id="85fd1-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85fd1-122">親要素</span><span class="sxs-lookup"><span data-stu-id="85fd1-122">Parent Elements</span></span>  
  
|<span data-ttu-id="85fd1-123">要素</span><span class="sxs-lookup"><span data-stu-id="85fd1-123">Element</span></span>|<span data-ttu-id="85fd1-124">説明</span><span class="sxs-lookup"><span data-stu-id="85fd1-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="85fd1-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="85fd1-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="85fd1-126">さまざまなランタイム構成設定に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="85fd1-126">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="85fd1-127">例</span><span class="sxs-lookup"><span data-stu-id="85fd1-127">Example</span></span>  

<span data-ttu-id="85fd1-128">次の例では、重要なセクションで、競合がある場合、スピン待機を無効にします。</span><span class="sxs-lookup"><span data-stu-id="85fd1-128">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="85fd1-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="85fd1-129">See also</span></span>

- [<span data-ttu-id="85fd1-130">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="85fd1-130">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="85fd1-131">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="85fd1-131">Configuration File Schema</span></span>](../index.md)
