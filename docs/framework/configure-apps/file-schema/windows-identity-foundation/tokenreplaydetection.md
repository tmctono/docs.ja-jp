---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 2e2159a73ca79fc362a8138eea95dbd173dafb11
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944297"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="2dd5c-101">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="2dd5c-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="2dd5c-102">トークンリプレイ検出を有効にし、トークンの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="2dd5c-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="2dd5c-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="2dd5c-103">\<system.identityModel></span></span>  
<span data-ttu-id="2dd5c-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="2dd5c-104">\<identityConfiguration></span></span>  
<span data-ttu-id="2dd5c-105">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="2dd5c-105">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dd5c-106">構文</span><span class="sxs-lookup"><span data-stu-id="2dd5c-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="2dd5c-107">型</span><span class="sxs-lookup"><span data-stu-id="2dd5c-107">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2dd5c-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2dd5c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2dd5c-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dd5c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2dd5c-110">属性</span><span class="sxs-lookup"><span data-stu-id="2dd5c-110">Attributes</span></span>  
  
|<span data-ttu-id="2dd5c-111">属性</span><span class="sxs-lookup"><span data-stu-id="2dd5c-111">Attribute</span></span>|<span data-ttu-id="2dd5c-112">説明</span><span class="sxs-lookup"><span data-stu-id="2dd5c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2dd5c-113">enabled</span><span class="sxs-lookup"><span data-stu-id="2dd5c-113">enabled</span></span>|<span data-ttu-id="2dd5c-114">トークンリプレイ検出が有効かどうかを示す値です。"true" を使用してトークンリプレイ検出を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2dd5c-114">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="2dd5c-115">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="2dd5c-115">expirationPeriod</span></span>|<span data-ttu-id="2dd5c-116">項目が期限切れと見なされ、キャッシュから削除されるまでの最大時間を指定する。<xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="2dd5c-116">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="2dd5c-117">値を指定<xref:System.TimeSpan>する方法の詳細については、「 [Timespan values](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd5c-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2dd5c-118">子要素</span><span class="sxs-lookup"><span data-stu-id="2dd5c-118">Child Elements</span></span>  
 <span data-ttu-id="2dd5c-119">なし</span><span class="sxs-lookup"><span data-stu-id="2dd5c-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2dd5c-120">親要素</span><span class="sxs-lookup"><span data-stu-id="2dd5c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2dd5c-121">要素</span><span class="sxs-lookup"><span data-stu-id="2dd5c-121">Element</span></span>|<span data-ttu-id="2dd5c-122">説明</span><span class="sxs-lookup"><span data-stu-id="2dd5c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2dd5c-123">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="2dd5c-123">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="2dd5c-124">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="2dd5c-124">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="2dd5c-125">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2dd5c-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="2dd5c-126">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="2dd5c-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2dd5c-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="2dd5c-127">Remarks</span></span>  
 <span data-ttu-id="2dd5c-128">要素は、要素の`<identityConfiguration>`下のサービスレベルで指定することも、 `<securityTokenHandlerConfiguration>`要素の下のセキュリティトークンハンドラーコレクションレベルで指定することもできます。 `<tokenReplayDetection>`</span><span class="sxs-lookup"><span data-stu-id="2dd5c-128">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="2dd5c-129">トークンハンドラーコレクションの設定は、サービスで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="2dd5c-129">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="2dd5c-130">トークン再生キャッシュの種類は、 [ \<tokenreplaycache >](tokenreplaycache.md)要素によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="2dd5c-130">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
