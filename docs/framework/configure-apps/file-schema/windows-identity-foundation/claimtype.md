---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 6bc185572528d4229ee53f1421eaa5bf27b053e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667224"
---
# <a name="claimtype"></a><span data-ttu-id="a2db8-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="a2db8-101">\<claimType></span></span>
<span data-ttu-id="a2db8-102">受け取ったセキュリティ トークンの 1 つの省略可能または必須のクレームを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2db8-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="a2db8-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="a2db8-103">\<system.identityModel></span></span>  
<span data-ttu-id="a2db8-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a2db8-104">\<identityConfiguration></span></span>  
<span data-ttu-id="a2db8-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="a2db8-105">\<claimTypeRequired></span></span>  
<span data-ttu-id="a2db8-106">\<claimType></span><span class="sxs-lookup"><span data-stu-id="a2db8-106">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2db8-107">構文</span><span class="sxs-lookup"><span data-stu-id="a2db8-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2db8-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a2db8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a2db8-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2db8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2db8-110">属性</span><span class="sxs-lookup"><span data-stu-id="a2db8-110">Attributes</span></span>  
  
|<span data-ttu-id="a2db8-111">属性</span><span class="sxs-lookup"><span data-stu-id="a2db8-111">Attribute</span></span>|<span data-ttu-id="a2db8-112">説明</span><span class="sxs-lookup"><span data-stu-id="a2db8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a2db8-113">種類</span><span class="sxs-lookup"><span data-stu-id="a2db8-113">type</span></span>|<span data-ttu-id="a2db8-114">要求の種類。</span><span class="sxs-lookup"><span data-stu-id="a2db8-114">The claim type.</span></span> <span data-ttu-id="a2db8-115">通常は URI です。</span><span class="sxs-lookup"><span data-stu-id="a2db8-115">Typically a URI.</span></span> <span data-ttu-id="a2db8-116">必須。</span><span class="sxs-lookup"><span data-stu-id="a2db8-116">Required.</span></span>|  
|<span data-ttu-id="a2db8-117">optional</span><span class="sxs-lookup"><span data-stu-id="a2db8-117">optional</span></span>|<span data-ttu-id="a2db8-118">要求の種類が省略可能かどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="a2db8-118">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="a2db8-119">任意。</span><span class="sxs-lookup"><span data-stu-id="a2db8-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2db8-120">子要素</span><span class="sxs-lookup"><span data-stu-id="a2db8-120">Child Elements</span></span>  
 <span data-ttu-id="a2db8-121">なし</span><span class="sxs-lookup"><span data-stu-id="a2db8-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2db8-122">親要素</span><span class="sxs-lookup"><span data-stu-id="a2db8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a2db8-123">要素</span><span class="sxs-lookup"><span data-stu-id="a2db8-123">Element</span></span>|<span data-ttu-id="a2db8-124">説明</span><span class="sxs-lookup"><span data-stu-id="a2db8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2db8-125">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="a2db8-125">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="a2db8-126">必要な受信セキュリティ トークンのクレームのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2db8-126">Specifies the set of required claims for incoming security tokens.</span></span>|
