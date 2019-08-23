---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 4253aec961b812b6893ee201861d2ab38048032a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942877"
---
# <a name="claimtype"></a><span data-ttu-id="7e0e6-101">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="7e0e6-101">\<claimType></span></span>
<span data-ttu-id="7e0e6-102">入力方向のセキュリティトークンに対して1つの省略可能なクレームまたは必須の要求を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e0e6-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="7e0e6-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="7e0e6-103">\<system.identityModel></span></span>  
<span data-ttu-id="7e0e6-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="7e0e6-104">\<identityConfiguration></span></span>  
<span data-ttu-id="7e0e6-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="7e0e6-105">\<claimTypeRequired></span></span>  
<span data-ttu-id="7e0e6-106">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="7e0e6-106">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e0e6-107">構文</span><span class="sxs-lookup"><span data-stu-id="7e0e6-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e0e6-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7e0e6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7e0e6-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e0e6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e0e6-110">属性</span><span class="sxs-lookup"><span data-stu-id="7e0e6-110">Attributes</span></span>  
  
|<span data-ttu-id="7e0e6-111">属性</span><span class="sxs-lookup"><span data-stu-id="7e0e6-111">Attribute</span></span>|<span data-ttu-id="7e0e6-112">説明</span><span class="sxs-lookup"><span data-stu-id="7e0e6-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e0e6-113">種類</span><span class="sxs-lookup"><span data-stu-id="7e0e6-113">type</span></span>|<span data-ttu-id="7e0e6-114">要求の種類。</span><span class="sxs-lookup"><span data-stu-id="7e0e6-114">The claim type.</span></span> <span data-ttu-id="7e0e6-115">通常は URI です。</span><span class="sxs-lookup"><span data-stu-id="7e0e6-115">Typically a URI.</span></span> <span data-ttu-id="7e0e6-116">必須。</span><span class="sxs-lookup"><span data-stu-id="7e0e6-116">Required.</span></span>|  
|<span data-ttu-id="7e0e6-117">optional</span><span class="sxs-lookup"><span data-stu-id="7e0e6-117">optional</span></span>|<span data-ttu-id="7e0e6-118">要求の種類が省略可能かどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="7e0e6-118">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="7e0e6-119">任意。</span><span class="sxs-lookup"><span data-stu-id="7e0e6-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e0e6-120">子要素</span><span class="sxs-lookup"><span data-stu-id="7e0e6-120">Child Elements</span></span>  
 <span data-ttu-id="7e0e6-121">なし</span><span class="sxs-lookup"><span data-stu-id="7e0e6-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e0e6-122">親要素</span><span class="sxs-lookup"><span data-stu-id="7e0e6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7e0e6-123">要素</span><span class="sxs-lookup"><span data-stu-id="7e0e6-123">Element</span></span>|<span data-ttu-id="7e0e6-124">説明</span><span class="sxs-lookup"><span data-stu-id="7e0e6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e0e6-125">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="7e0e6-125">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="7e0e6-126">受信セキュリティトークンに必要な要求のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="7e0e6-126">Specifies the set of required claims for incoming security tokens.</span></span>|
