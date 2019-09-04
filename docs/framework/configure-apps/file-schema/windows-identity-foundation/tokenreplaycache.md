---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 9f3a95fd0a39f199eaf13c7509aff22caa0e3b66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251785"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="5e283-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="5e283-101">\<tokenReplayCache></span></span>
<span data-ttu-id="5e283-102">トークン再生キャッシュをサービスまたはセキュリティトークンハンドラーコレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="5e283-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="5e283-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5e283-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5e283-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="5e283-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="5e283-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="5e283-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="5e283-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<キャッシュ >** ](caches.md)</span><span class="sxs-lookup"><span data-stu-id="5e283-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="5e283-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<tokenReplayCache >**</span><span class="sxs-lookup"><span data-stu-id="5e283-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e283-108">構文</span><span class="sxs-lookup"><span data-stu-id="5e283-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e283-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5e283-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5e283-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e283-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e283-111">属性</span><span class="sxs-lookup"><span data-stu-id="5e283-111">Attributes</span></span>  
  
|<span data-ttu-id="5e283-112">属性</span><span class="sxs-lookup"><span data-stu-id="5e283-112">Attribute</span></span>|<span data-ttu-id="5e283-113">説明</span><span class="sxs-lookup"><span data-stu-id="5e283-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e283-114">型</span><span class="sxs-lookup"><span data-stu-id="5e283-114">type</span></span>|<span data-ttu-id="5e283-115"><xref:System.IdentityModel.Tokens.TokenReplayCache>クラスから派生する型。</span><span class="sxs-lookup"><span data-stu-id="5e283-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="5e283-116">カスタム`type`を指定する方法の詳細については、「[カスタム型参照]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e283-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="5e283-117">子要素</span><span class="sxs-lookup"><span data-stu-id="5e283-117">Child Elements</span></span>  
 <span data-ttu-id="5e283-118">なし</span><span class="sxs-lookup"><span data-stu-id="5e283-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e283-119">親要素</span><span class="sxs-lookup"><span data-stu-id="5e283-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5e283-120">要素</span><span class="sxs-lookup"><span data-stu-id="5e283-120">Element</span></span>|<span data-ttu-id="5e283-121">説明</span><span class="sxs-lookup"><span data-stu-id="5e283-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e283-122">\<キャッシュ ></span><span class="sxs-lookup"><span data-stu-id="5e283-122">\<caches></span></span>](caches.md)|<span data-ttu-id="5e283-123">サービスまたはセキュリティトークンハンドラーコレクションによって使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="5e283-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e283-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="5e283-124">Remarks</span></span>  
 <span data-ttu-id="5e283-125">トークン再生キャッシュは、再生されたトークンを検出するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e283-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="5e283-126">トークンリプレイ検出は、トークンの最大有効期間を指定する[ \<tokenreplaydetection >](tokenreplaydetection.md)要素によって有効にされます。</span><span class="sxs-lookup"><span data-stu-id="5e283-126">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e283-127">例</span><span class="sxs-lookup"><span data-stu-id="5e283-127">Example</span></span>  
 <span data-ttu-id="5e283-128">次の XML は、再生されたトークンを検出するためのカスタムキャッシュの構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="5e283-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e283-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e283-129">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="5e283-130">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="5e283-130">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)
