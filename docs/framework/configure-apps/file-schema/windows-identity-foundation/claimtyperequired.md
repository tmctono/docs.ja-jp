---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: eafaf253e27db632f17acfce4445a07d18b109aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778457"
---
# <a name="claimtyperequired"></a><span data-ttu-id="ac500-101">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="ac500-101">\<claimTypeRequired></span></span>
<span data-ttu-id="ac500-102">必要な受信セキュリティ トークンのクレームのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac500-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="ac500-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ac500-103">\<system.identityModel></span></span>  
<span data-ttu-id="ac500-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ac500-104">\<identityConfiguration></span></span>  
<span data-ttu-id="ac500-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="ac500-105">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac500-106">構文</span><span class="sxs-lookup"><span data-stu-id="ac500-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac500-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ac500-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ac500-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac500-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac500-109">属性</span><span class="sxs-lookup"><span data-stu-id="ac500-109">Attributes</span></span>  
 <span data-ttu-id="ac500-110">なし</span><span class="sxs-lookup"><span data-stu-id="ac500-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ac500-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ac500-111">Child Elements</span></span>  
  
|<span data-ttu-id="ac500-112">要素</span><span class="sxs-lookup"><span data-stu-id="ac500-112">Element</span></span>|<span data-ttu-id="ac500-113">説明</span><span class="sxs-lookup"><span data-stu-id="ac500-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac500-114">\<claimType></span><span class="sxs-lookup"><span data-stu-id="ac500-114">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="ac500-115">受け取ったセキュリティ トークンの 1 つの省略可能または必須のクレームを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac500-115">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ac500-116">親要素</span><span class="sxs-lookup"><span data-stu-id="ac500-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ac500-117">要素</span><span class="sxs-lookup"><span data-stu-id="ac500-117">Element</span></span>|<span data-ttu-id="ac500-118">説明</span><span class="sxs-lookup"><span data-stu-id="ac500-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac500-119">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ac500-119">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="ac500-120">サービス レベルの id の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac500-120">Specifies service-level identity settings.</span></span>|
