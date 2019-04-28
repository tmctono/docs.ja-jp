---
title: <synchronousReceive> 要素
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: 20390f747c8beaccba1cfea7a9ea0ed366037ecb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757925"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="d2d9a-102">\<synchronousReceive > 要素</span><span class="sxs-lookup"><span data-stu-id="d2d9a-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="d2d9a-103">この構成要素は、サービスまたはクライアント アプリケーションでメッセージを受信する場合のランタイム動作を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="d2d9a-104">属性や子要素はありません。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="d2d9a-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d2d9a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d2d9a-106">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="d2d9a-106">\<behaviors></span></span>  
<span data-ttu-id="d2d9a-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="d2d9a-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="d2d9a-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d2d9a-108">\<behavior></span></span>  
<span data-ttu-id="d2d9a-109">\<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="d2d9a-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2d9a-110">構文</span><span class="sxs-lookup"><span data-stu-id="d2d9a-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2d9a-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d2d9a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d2d9a-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2d9a-113">属性</span><span class="sxs-lookup"><span data-stu-id="d2d9a-113">Attributes</span></span>  
 <span data-ttu-id="d2d9a-114">なし。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d2d9a-115">子要素</span><span class="sxs-lookup"><span data-stu-id="d2d9a-115">Child Elements</span></span>  
 <span data-ttu-id="d2d9a-116">なし。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2d9a-117">親要素</span><span class="sxs-lookup"><span data-stu-id="d2d9a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d2d9a-118">要素</span><span class="sxs-lookup"><span data-stu-id="d2d9a-118">Element</span></span>|<span data-ttu-id="d2d9a-119">説明</span><span class="sxs-lookup"><span data-stu-id="d2d9a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2d9a-120">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d2d9a-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d2d9a-121">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2d9a-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="d2d9a-122">Remarks</span></span>  
 <span data-ttu-id="d2d9a-123">この動作を使用して、既定の非同期受信ではなく同期受信を使用するようにチャネル リスナーに指示します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="d2d9a-124">Windows Communication Foundation (WCF) は、受け入れた各チャネルに対してに新しいスレッドを発行します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="d2d9a-125">チャネルが多数ある場合は、スレッドが不足する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2d9a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2d9a-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
