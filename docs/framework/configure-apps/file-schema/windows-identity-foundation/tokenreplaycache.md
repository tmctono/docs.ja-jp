---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5e695bb56b59da40ce9e83f9f4f77d0d22d0b40f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202423"
---
# \<tokenReplayCache>

<span data-ttu-id="3efd8-101">トークン再生キャッシュをサービスまたはセキュリティトークンハンドラーコレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="3efd8-101">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**  
  
## <a name="syntax"></a><span data-ttu-id="3efd8-102">構文</span><span class="sxs-lookup"><span data-stu-id="3efd8-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3efd8-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3efd8-103">Attributes and Elements</span></span>  

 <span data-ttu-id="3efd8-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3efd8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3efd8-105">属性</span><span class="sxs-lookup"><span data-stu-id="3efd8-105">Attributes</span></span>  
  
|<span data-ttu-id="3efd8-106">属性</span><span class="sxs-lookup"><span data-stu-id="3efd8-106">Attribute</span></span>|<span data-ttu-id="3efd8-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="3efd8-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3efd8-108">type</span><span class="sxs-lookup"><span data-stu-id="3efd8-108">type</span></span>|<span data-ttu-id="3efd8-109">クラスから派生する型 <xref:System.IdentityModel.Tokens.TokenReplayCache> 。</span><span class="sxs-lookup"><span data-stu-id="3efd8-109">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="3efd8-110">カスタムを指定する方法の詳細については `type` 、「[カスタム型参照]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3efd8-110">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="3efd8-111">子要素</span><span class="sxs-lookup"><span data-stu-id="3efd8-111">Child Elements</span></span>  

 <span data-ttu-id="3efd8-112">None</span><span class="sxs-lookup"><span data-stu-id="3efd8-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3efd8-113">親要素</span><span class="sxs-lookup"><span data-stu-id="3efd8-113">Parent Elements</span></span>  
  
|<span data-ttu-id="3efd8-114">要素</span><span class="sxs-lookup"><span data-stu-id="3efd8-114">Element</span></span>|<span data-ttu-id="3efd8-115">説明</span><span class="sxs-lookup"><span data-stu-id="3efd8-115">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="3efd8-116">サービスまたはセキュリティトークンハンドラーコレクションによって使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="3efd8-116">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3efd8-117">解説</span><span class="sxs-lookup"><span data-stu-id="3efd8-117">Remarks</span></span>  

 <span data-ttu-id="3efd8-118">トークン再生キャッシュは、再生されたトークンを検出するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3efd8-118">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="3efd8-119">トークンリプレイ検出は、要素によって有効にされ [\<tokenReplayDetection>](tokenreplaydetection.md) ます。これは、トークンの最大有効期間も指定します。</span><span class="sxs-lookup"><span data-stu-id="3efd8-119">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3efd8-120">例</span><span class="sxs-lookup"><span data-stu-id="3efd8-120">Example</span></span>  

 <span data-ttu-id="3efd8-121">次の XML は、再生されたトークンを検出するためのカスタムキャッシュの構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="3efd8-121">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3efd8-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="3efd8-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
