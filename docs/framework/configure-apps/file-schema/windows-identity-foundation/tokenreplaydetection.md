---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a4454042e1d97fb3cc2d6f2735104dadda6e7b5a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251771"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="ccbcd-101">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="ccbcd-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="ccbcd-102">トークンリプレイ検出を有効にし、トークンの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccbcd-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
<span data-ttu-id="ccbcd-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ccbcd-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ccbcd-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="ccbcd-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="ccbcd-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="ccbcd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="ccbcd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<tokenReplayDetection >**</span><span class="sxs-lookup"><span data-stu-id="ccbcd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccbcd-107">構文</span><span class="sxs-lookup"><span data-stu-id="ccbcd-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="ccbcd-108">型</span><span class="sxs-lookup"><span data-stu-id="ccbcd-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccbcd-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ccbcd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ccbcd-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ccbcd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccbcd-111">属性</span><span class="sxs-lookup"><span data-stu-id="ccbcd-111">Attributes</span></span>  
  
|<span data-ttu-id="ccbcd-112">属性</span><span class="sxs-lookup"><span data-stu-id="ccbcd-112">Attribute</span></span>|<span data-ttu-id="ccbcd-113">説明</span><span class="sxs-lookup"><span data-stu-id="ccbcd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ccbcd-114">enabled</span><span class="sxs-lookup"><span data-stu-id="ccbcd-114">enabled</span></span>|<span data-ttu-id="ccbcd-115">トークンリプレイ検出が有効かどうかを示す値です。"true" を使用してトークンリプレイ検出を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccbcd-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="ccbcd-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="ccbcd-116">expirationPeriod</span></span>|<span data-ttu-id="ccbcd-117">項目が期限切れと見なされ、キャッシュから削除されるまでの最大時間を指定する。<xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="ccbcd-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="ccbcd-118">値を指定<xref:System.TimeSpan>する方法の詳細については、「 [Timespan values](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccbcd-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ccbcd-119">子要素</span><span class="sxs-lookup"><span data-stu-id="ccbcd-119">Child Elements</span></span>  
 <span data-ttu-id="ccbcd-120">なし</span><span class="sxs-lookup"><span data-stu-id="ccbcd-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ccbcd-121">親要素</span><span class="sxs-lookup"><span data-stu-id="ccbcd-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ccbcd-122">要素</span><span class="sxs-lookup"><span data-stu-id="ccbcd-122">Element</span></span>|<span data-ttu-id="ccbcd-123">説明</span><span class="sxs-lookup"><span data-stu-id="ccbcd-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccbcd-124">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ccbcd-124">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="ccbcd-125">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccbcd-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="ccbcd-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ccbcd-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="ccbcd-127">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="ccbcd-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccbcd-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="ccbcd-128">Remarks</span></span>  
 <span data-ttu-id="ccbcd-129">要素は、要素の`<identityConfiguration>`下のサービスレベルで指定することも、 `<securityTokenHandlerConfiguration>`要素の下のセキュリティトークンハンドラーコレクションレベルで指定することもできます。 `<tokenReplayDetection>`</span><span class="sxs-lookup"><span data-stu-id="ccbcd-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="ccbcd-130">トークンハンドラーコレクションの設定は、サービスで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="ccbcd-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="ccbcd-131">トークン再生キャッシュの種類は、 [ \<tokenreplaycache >](tokenreplaycache.md)要素によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="ccbcd-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
