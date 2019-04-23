---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 1567c669b5e682a7a771d7bedc95a8effa474e36
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113387"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="41022-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="41022-101">\<tokenReplayCache></span></span>
<span data-ttu-id="41022-102">トークン再生キャッシュ サービスまたはセキュリティ トークン ハンドラー コレクションに登録します。</span><span class="sxs-lookup"><span data-stu-id="41022-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="41022-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="41022-103">\<system.identityModel></span></span>  
<span data-ttu-id="41022-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="41022-104">\<identityConfiguration></span></span>  
<span data-ttu-id="41022-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="41022-105">\<caches></span></span>  
<span data-ttu-id="41022-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="41022-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41022-107">構文</span><span class="sxs-lookup"><span data-stu-id="41022-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41022-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="41022-108">Attributes and Elements</span></span>  
 <span data-ttu-id="41022-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="41022-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41022-110">属性</span><span class="sxs-lookup"><span data-stu-id="41022-110">Attributes</span></span>  
  
|<span data-ttu-id="41022-111">属性</span><span class="sxs-lookup"><span data-stu-id="41022-111">Attribute</span></span>|<span data-ttu-id="41022-112">説明</span><span class="sxs-lookup"><span data-stu-id="41022-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="41022-113">型</span><span class="sxs-lookup"><span data-stu-id="41022-113">type</span></span>|<span data-ttu-id="41022-114">派生した型、<xref:System.IdentityModel.Tokens.TokenReplayCache>クラス。</span><span class="sxs-lookup"><span data-stu-id="41022-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="41022-115">詳細については、ユーザー設定を指定する方法についての`type`、[カスタム型の参照] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41022-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="41022-116">子要素</span><span class="sxs-lookup"><span data-stu-id="41022-116">Child Elements</span></span>  
 <span data-ttu-id="41022-117">なし</span><span class="sxs-lookup"><span data-stu-id="41022-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41022-118">親要素</span><span class="sxs-lookup"><span data-stu-id="41022-118">Parent Elements</span></span>  
  
|<span data-ttu-id="41022-119">要素</span><span class="sxs-lookup"><span data-stu-id="41022-119">Element</span></span>|<span data-ttu-id="41022-120">説明</span><span class="sxs-lookup"><span data-stu-id="41022-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41022-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="41022-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="41022-122">サービスまたはセキュリティ トークン ハンドラー コレクションで使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="41022-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41022-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="41022-123">Remarks</span></span>  
 <span data-ttu-id="41022-124">トークン再生キャッシュを使用して、再生されたトークンを検出できます。</span><span class="sxs-lookup"><span data-stu-id="41022-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="41022-125">トークン リプレイ検出が有効になっている、 [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)要素もトークンの最大有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="41022-125">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41022-126">例</span><span class="sxs-lookup"><span data-stu-id="41022-126">Example</span></span>  
 <span data-ttu-id="41022-127">次の XML は、再生されたトークンを検出するためのカスタム キャッシュの構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="41022-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="41022-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="41022-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="41022-129">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="41022-129">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
