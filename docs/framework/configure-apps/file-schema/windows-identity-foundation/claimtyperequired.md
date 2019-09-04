---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: 1c40c5e4b4a24a3c1bbd6e096f12b7b044331c88
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252060"
---
# <a name="claimtyperequired"></a><span data-ttu-id="4fafb-101">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="4fafb-101">\<claimTypeRequired></span></span>
<span data-ttu-id="4fafb-102">受信セキュリティトークンに必要な要求のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="4fafb-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
<span data-ttu-id="4fafb-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4fafb-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4fafb-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="4fafb-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="4fafb-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="4fafb-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="4fafb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<claimTypeRequired >**</span><span class="sxs-lookup"><span data-stu-id="4fafb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fafb-107">構文</span><span class="sxs-lookup"><span data-stu-id="4fafb-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fafb-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4fafb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4fafb-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fafb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fafb-110">属性</span><span class="sxs-lookup"><span data-stu-id="4fafb-110">Attributes</span></span>  
 <span data-ttu-id="4fafb-111">なし</span><span class="sxs-lookup"><span data-stu-id="4fafb-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4fafb-112">子要素</span><span class="sxs-lookup"><span data-stu-id="4fafb-112">Child Elements</span></span>  
  
|<span data-ttu-id="4fafb-113">要素</span><span class="sxs-lookup"><span data-stu-id="4fafb-113">Element</span></span>|<span data-ttu-id="4fafb-114">説明</span><span class="sxs-lookup"><span data-stu-id="4fafb-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fafb-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="4fafb-115">\<claimType></span></span>](claimtype.md)|<span data-ttu-id="4fafb-116">入力方向のセキュリティトークンに対して1つの省略可能なクレームまたは必須の要求を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fafb-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4fafb-117">親要素</span><span class="sxs-lookup"><span data-stu-id="4fafb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4fafb-118">要素</span><span class="sxs-lookup"><span data-stu-id="4fafb-118">Element</span></span>|<span data-ttu-id="4fafb-119">説明</span><span class="sxs-lookup"><span data-stu-id="4fafb-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fafb-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4fafb-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="4fafb-121">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fafb-121">Specifies service-level identity settings.</span></span>|
