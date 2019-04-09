---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 1567c669b5e682a7a771d7bedc95a8effa474e36
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113387"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="a2720-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="a2720-101">\<tokenReplayCache></span></span>
<span data-ttu-id="a2720-102">トークン再生キャッシュ サービスまたはセキュリティ トークン ハンドラー コレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="a2720-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="a2720-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="a2720-103">\<system.identityModel></span></span>  
<span data-ttu-id="a2720-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a2720-104">\<identityConfiguration></span></span>  
<span data-ttu-id="a2720-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="a2720-105">\<caches></span></span>  
<span data-ttu-id="a2720-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="a2720-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2720-107">構文</span><span class="sxs-lookup"><span data-stu-id="a2720-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2720-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a2720-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a2720-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2720-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2720-110">属性</span><span class="sxs-lookup"><span data-stu-id="a2720-110">Attributes</span></span>  
  
|<span data-ttu-id="a2720-111">属性</span><span class="sxs-lookup"><span data-stu-id="a2720-111">Attribute</span></span>|<span data-ttu-id="a2720-112">説明</span><span class="sxs-lookup"><span data-stu-id="a2720-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a2720-113">型</span><span class="sxs-lookup"><span data-stu-id="a2720-113">type</span></span>|<span data-ttu-id="a2720-114">派生した型、<xref:System.IdentityModel.Tokens.TokenReplayCache>クラス。</span><span class="sxs-lookup"><span data-stu-id="a2720-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="a2720-115">詳細については、ユーザー設定を指定する方法についての`type`、[カスタム型の参照] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2720-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="a2720-116">子要素</span><span class="sxs-lookup"><span data-stu-id="a2720-116">Child Elements</span></span>  
 <span data-ttu-id="a2720-117">なし</span><span class="sxs-lookup"><span data-stu-id="a2720-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2720-118">親要素</span><span class="sxs-lookup"><span data-stu-id="a2720-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a2720-119">要素</span><span class="sxs-lookup"><span data-stu-id="a2720-119">Element</span></span>|<span data-ttu-id="a2720-120">説明</span><span class="sxs-lookup"><span data-stu-id="a2720-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2720-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="a2720-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="a2720-122">サービスまたはセキュリティ トークン ハンドラー コレクションで使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="a2720-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2720-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="a2720-123">Remarks</span></span>  
 <span data-ttu-id="a2720-124">トークン再生キャッシュを使用して、再生されたトークンを検出できます。</span><span class="sxs-lookup"><span data-stu-id="a2720-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="a2720-125">トークン リプレイ検出が有効になっている、 [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)要素もトークンの最大有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2720-125">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2720-126">例</span><span class="sxs-lookup"><span data-stu-id="a2720-126">Example</span></span>  
 <span data-ttu-id="a2720-127">次の XML は、再生されたトークンを検出するためのカスタム キャッシュの構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="a2720-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2720-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2720-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="a2720-129">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="a2720-129">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
