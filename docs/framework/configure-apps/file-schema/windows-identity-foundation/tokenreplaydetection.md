---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: df512960b522f17dc9247bb5959e246c8c1f15b8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169805"
---
# \<tokenReplayDetection>

<span data-ttu-id="39ea2-101">トークンリプレイ検出を有効にし、トークンの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="39ea2-101">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
## <a name="syntax"></a><span data-ttu-id="39ea2-102">構文</span><span class="sxs-lookup"><span data-stu-id="39ea2-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="39ea2-103">種類</span><span class="sxs-lookup"><span data-stu-id="39ea2-103">Type</span></span>  

 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39ea2-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="39ea2-104">Attributes and Elements</span></span>  

 <span data-ttu-id="39ea2-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="39ea2-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39ea2-106">属性</span><span class="sxs-lookup"><span data-stu-id="39ea2-106">Attributes</span></span>  
  
|<span data-ttu-id="39ea2-107">属性</span><span class="sxs-lookup"><span data-stu-id="39ea2-107">Attribute</span></span>|<span data-ttu-id="39ea2-108">説明</span><span class="sxs-lookup"><span data-stu-id="39ea2-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39ea2-109">enabled</span><span class="sxs-lookup"><span data-stu-id="39ea2-109">enabled</span></span>|<span data-ttu-id="39ea2-110">トークンリプレイ検出が有効かどうかを示す値です。"true" を使用してトークンリプレイ検出を有効にします。</span><span class="sxs-lookup"><span data-stu-id="39ea2-110">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="39ea2-111">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="39ea2-111">expirationPeriod</span></span>|<span data-ttu-id="39ea2-112"><xref:System.TimeSpan>項目が期限切れと見なされ、キャッシュから削除されるまでの最大時間を指定する。</span><span class="sxs-lookup"><span data-stu-id="39ea2-112">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="39ea2-113">値を指定する方法の詳細について <xref:System.TimeSpan> は、「 [Timespan values](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39ea2-113">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39ea2-114">子要素</span><span class="sxs-lookup"><span data-stu-id="39ea2-114">Child Elements</span></span>  

 <span data-ttu-id="39ea2-115">None</span><span class="sxs-lookup"><span data-stu-id="39ea2-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39ea2-116">親要素</span><span class="sxs-lookup"><span data-stu-id="39ea2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="39ea2-117">要素</span><span class="sxs-lookup"><span data-stu-id="39ea2-117">Element</span></span>|<span data-ttu-id="39ea2-118">説明</span><span class="sxs-lookup"><span data-stu-id="39ea2-118">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="39ea2-119">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="39ea2-119">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="39ea2-120">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="39ea2-120">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39ea2-121">解説</span><span class="sxs-lookup"><span data-stu-id="39ea2-121">Remarks</span></span>  

 <span data-ttu-id="39ea2-122">要素は `<tokenReplayDetection>` 、要素の下のサービスレベルで指定することも、 `<identityConfiguration>` 要素の下のセキュリティトークンハンドラーコレクションレベルで指定することもでき `<securityTokenHandlerConfiguration>` ます。</span><span class="sxs-lookup"><span data-stu-id="39ea2-122">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="39ea2-123">トークンハンドラーコレクションの設定は、サービスで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="39ea2-123">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="39ea2-124">トークン再生キャッシュの種類は、要素によって指定され [\<tokenReplayCache>](tokenreplaycache.md) ます。</span><span class="sxs-lookup"><span data-stu-id="39ea2-124">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
