---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: 1c40c5e4b4a24a3c1bbd6e096f12b7b044331c88
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252060"
---
# \<claimTypeRequired>
<span data-ttu-id="70e84-101">受信セキュリティトークンに必要な要求のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="70e84-101">Specifies the set of required claims for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**  
  
## <a name="syntax"></a><span data-ttu-id="70e84-102">構文</span><span class="sxs-lookup"><span data-stu-id="70e84-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70e84-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="70e84-103">Attributes and Elements</span></span>  
 <span data-ttu-id="70e84-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="70e84-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70e84-105">属性</span><span class="sxs-lookup"><span data-stu-id="70e84-105">Attributes</span></span>  
 <span data-ttu-id="70e84-106">なし</span><span class="sxs-lookup"><span data-stu-id="70e84-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="70e84-107">子要素</span><span class="sxs-lookup"><span data-stu-id="70e84-107">Child Elements</span></span>  
  
|<span data-ttu-id="70e84-108">要素</span><span class="sxs-lookup"><span data-stu-id="70e84-108">Element</span></span>|<span data-ttu-id="70e84-109">説明</span><span class="sxs-lookup"><span data-stu-id="70e84-109">Description</span></span>|  
|-------------|-----------------|  
|[\<claimType>](claimtype.md)|<span data-ttu-id="70e84-110">入力方向のセキュリティトークンに対して1つの省略可能なクレームまたは必須の要求を指定します。</span><span class="sxs-lookup"><span data-stu-id="70e84-110">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="70e84-111">親要素</span><span class="sxs-lookup"><span data-stu-id="70e84-111">Parent Elements</span></span>  
  
|<span data-ttu-id="70e84-112">要素</span><span class="sxs-lookup"><span data-stu-id="70e84-112">Element</span></span>|<span data-ttu-id="70e84-113">説明</span><span class="sxs-lookup"><span data-stu-id="70e84-113">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="70e84-114">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="70e84-114">Specifies service-level identity settings.</span></span>|
