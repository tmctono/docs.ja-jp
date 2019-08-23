---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: 85f3954514fa8b532311b1fbfc34f32ebefa4099
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942827"
---
# <a name="claimtyperequired"></a><span data-ttu-id="645e8-101">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="645e8-101">\<claimTypeRequired></span></span>
<span data-ttu-id="645e8-102">受信セキュリティトークンに必要な要求のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="645e8-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="645e8-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="645e8-103">\<system.identityModel></span></span>  
<span data-ttu-id="645e8-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="645e8-104">\<identityConfiguration></span></span>  
<span data-ttu-id="645e8-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="645e8-105">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="645e8-106">構文</span><span class="sxs-lookup"><span data-stu-id="645e8-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="645e8-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="645e8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="645e8-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="645e8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="645e8-109">属性</span><span class="sxs-lookup"><span data-stu-id="645e8-109">Attributes</span></span>  
 <span data-ttu-id="645e8-110">なし</span><span class="sxs-lookup"><span data-stu-id="645e8-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="645e8-111">子要素</span><span class="sxs-lookup"><span data-stu-id="645e8-111">Child Elements</span></span>  
  
|<span data-ttu-id="645e8-112">要素</span><span class="sxs-lookup"><span data-stu-id="645e8-112">Element</span></span>|<span data-ttu-id="645e8-113">説明</span><span class="sxs-lookup"><span data-stu-id="645e8-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="645e8-114">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="645e8-114">\<claimType></span></span>](claimtype.md)|<span data-ttu-id="645e8-115">入力方向のセキュリティトークンに対して1つの省略可能なクレームまたは必須の要求を指定します。</span><span class="sxs-lookup"><span data-stu-id="645e8-115">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="645e8-116">親要素</span><span class="sxs-lookup"><span data-stu-id="645e8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="645e8-117">要素</span><span class="sxs-lookup"><span data-stu-id="645e8-117">Element</span></span>|<span data-ttu-id="645e8-118">説明</span><span class="sxs-lookup"><span data-stu-id="645e8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="645e8-119">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="645e8-119">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="645e8-120">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="645e8-120">Specifies service-level identity settings.</span></span>|
