---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a4454042e1d97fb3cc2d6f2735104dadda6e7b5a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251771"
---
# \<tokenReplayDetection>
<span data-ttu-id="b48ca-101">トークンリプレイ検出を有効にし、トークンの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="b48ca-101">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
## <a name="syntax"></a><span data-ttu-id="b48ca-102">構文</span><span class="sxs-lookup"><span data-stu-id="b48ca-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="b48ca-103">Type</span><span class="sxs-lookup"><span data-stu-id="b48ca-103">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b48ca-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b48ca-104">Attributes and Elements</span></span>  
 <span data-ttu-id="b48ca-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b48ca-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b48ca-106">属性</span><span class="sxs-lookup"><span data-stu-id="b48ca-106">Attributes</span></span>  
  
|<span data-ttu-id="b48ca-107">属性</span><span class="sxs-lookup"><span data-stu-id="b48ca-107">Attribute</span></span>|<span data-ttu-id="b48ca-108">説明</span><span class="sxs-lookup"><span data-stu-id="b48ca-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b48ca-109">enabled</span><span class="sxs-lookup"><span data-stu-id="b48ca-109">enabled</span></span>|<span data-ttu-id="b48ca-110">トークンリプレイ検出が有効かどうかを示す値です。"true" を使用してトークンリプレイ検出を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b48ca-110">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="b48ca-111">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="b48ca-111">expirationPeriod</span></span>|<span data-ttu-id="b48ca-112"><xref:System.TimeSpan>項目が期限切れと見なされ、キャッシュから削除されるまでの最大時間を指定する。</span><span class="sxs-lookup"><span data-stu-id="b48ca-112">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="b48ca-113">値を指定する方法の詳細について <xref:System.TimeSpan> は、「 [Timespan values](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b48ca-113">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b48ca-114">子要素</span><span class="sxs-lookup"><span data-stu-id="b48ca-114">Child Elements</span></span>  
 <span data-ttu-id="b48ca-115">なし</span><span class="sxs-lookup"><span data-stu-id="b48ca-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b48ca-116">親要素</span><span class="sxs-lookup"><span data-stu-id="b48ca-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b48ca-117">要素</span><span class="sxs-lookup"><span data-stu-id="b48ca-117">Element</span></span>|<span data-ttu-id="b48ca-118">Description</span><span class="sxs-lookup"><span data-stu-id="b48ca-118">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="b48ca-119">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b48ca-119">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="b48ca-120">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="b48ca-120">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b48ca-121">解説</span><span class="sxs-lookup"><span data-stu-id="b48ca-121">Remarks</span></span>  
 <span data-ttu-id="b48ca-122">要素は `<tokenReplayDetection>` 、要素の下のサービスレベルで指定することも、 `<identityConfiguration>` 要素の下のセキュリティトークンハンドラーコレクションレベルで指定することもでき `<securityTokenHandlerConfiguration>` ます。</span><span class="sxs-lookup"><span data-stu-id="b48ca-122">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="b48ca-123">トークンハンドラーコレクションの設定は、サービスで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="b48ca-123">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="b48ca-124">トークン再生キャッシュの種類は、要素によって指定され [\<tokenReplayCache>](tokenreplaycache.md) ます。</span><span class="sxs-lookup"><span data-stu-id="b48ca-124">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
