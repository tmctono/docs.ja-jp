---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5747a4cfa93118dd41292904b168bbef02fec415
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944075"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="1e32f-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="1e32f-101">\<tokenReplayCache></span></span>
<span data-ttu-id="1e32f-102">トークン再生キャッシュをサービスまたはセキュリティトークンハンドラーコレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="1e32f-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="1e32f-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="1e32f-103">\<system.identityModel></span></span>  
<span data-ttu-id="1e32f-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="1e32f-104">\<identityConfiguration></span></span>  
<span data-ttu-id="1e32f-105">\<キャッシュ ></span><span class="sxs-lookup"><span data-stu-id="1e32f-105">\<caches></span></span>  
<span data-ttu-id="1e32f-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="1e32f-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e32f-107">構文</span><span class="sxs-lookup"><span data-stu-id="1e32f-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e32f-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1e32f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1e32f-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e32f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e32f-110">属性</span><span class="sxs-lookup"><span data-stu-id="1e32f-110">Attributes</span></span>  
  
|<span data-ttu-id="1e32f-111">属性</span><span class="sxs-lookup"><span data-stu-id="1e32f-111">Attribute</span></span>|<span data-ttu-id="1e32f-112">説明</span><span class="sxs-lookup"><span data-stu-id="1e32f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e32f-113">型</span><span class="sxs-lookup"><span data-stu-id="1e32f-113">type</span></span>|<span data-ttu-id="1e32f-114"><xref:System.IdentityModel.Tokens.TokenReplayCache>クラスから派生する型。</span><span class="sxs-lookup"><span data-stu-id="1e32f-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="1e32f-115">カスタム`type`を指定する方法の詳細については、「[カスタム型参照]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e32f-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="1e32f-116">子要素</span><span class="sxs-lookup"><span data-stu-id="1e32f-116">Child Elements</span></span>  
 <span data-ttu-id="1e32f-117">なし</span><span class="sxs-lookup"><span data-stu-id="1e32f-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e32f-118">親要素</span><span class="sxs-lookup"><span data-stu-id="1e32f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1e32f-119">要素</span><span class="sxs-lookup"><span data-stu-id="1e32f-119">Element</span></span>|<span data-ttu-id="1e32f-120">説明</span><span class="sxs-lookup"><span data-stu-id="1e32f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e32f-121">\<キャッシュ ></span><span class="sxs-lookup"><span data-stu-id="1e32f-121">\<caches></span></span>](caches.md)|<span data-ttu-id="1e32f-122">サービスまたはセキュリティトークンハンドラーコレクションによって使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="1e32f-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e32f-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="1e32f-123">Remarks</span></span>  
 <span data-ttu-id="1e32f-124">トークン再生キャッシュは、再生されたトークンを検出するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1e32f-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="1e32f-125">トークンリプレイ検出は、トークンの最大有効期間を指定する[ \<tokenreplaydetection >](tokenreplaydetection.md)要素によって有効にされます。</span><span class="sxs-lookup"><span data-stu-id="1e32f-125">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e32f-126">例</span><span class="sxs-lookup"><span data-stu-id="1e32f-126">Example</span></span>  
 <span data-ttu-id="1e32f-127">次の XML は、再生されたトークンを検出するためのカスタムキャッシュの構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="1e32f-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e32f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e32f-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="1e32f-129">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="1e32f-129">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)
