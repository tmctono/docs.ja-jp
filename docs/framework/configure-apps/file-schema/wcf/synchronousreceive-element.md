---
title: <synchronousReceive> 要素
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: b3f4860be6b7edac776a1c30611271b2eb36968e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399496"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="1741f-102">\<synchronousReceive > 要素</span><span class="sxs-lookup"><span data-stu-id="1741f-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="1741f-103">この構成要素は、サービスまたはクライアント アプリケーションでメッセージを受信する場合のランタイム動作を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1741f-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="1741f-104">属性や子要素はありません。</span><span class="sxs-lookup"><span data-stu-id="1741f-104">It does not have any attributes or child elements.</span></span>  
  
<span data-ttu-id="1741f-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1741f-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1741f-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1741f-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1741f-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1741f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="1741f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1741f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="1741f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1741f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="1741f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<synchronousReceive >**</span><span class="sxs-lookup"><span data-stu-id="1741f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1741f-111">構文</span><span class="sxs-lookup"><span data-stu-id="1741f-111">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1741f-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1741f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1741f-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1741f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1741f-114">属性</span><span class="sxs-lookup"><span data-stu-id="1741f-114">Attributes</span></span>  
 <span data-ttu-id="1741f-115">なし。</span><span class="sxs-lookup"><span data-stu-id="1741f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1741f-116">子要素</span><span class="sxs-lookup"><span data-stu-id="1741f-116">Child Elements</span></span>  
 <span data-ttu-id="1741f-117">なし。</span><span class="sxs-lookup"><span data-stu-id="1741f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1741f-118">親要素</span><span class="sxs-lookup"><span data-stu-id="1741f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1741f-119">要素</span><span class="sxs-lookup"><span data-stu-id="1741f-119">Element</span></span>|<span data-ttu-id="1741f-120">説明</span><span class="sxs-lookup"><span data-stu-id="1741f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1741f-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1741f-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1741f-122">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="1741f-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1741f-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="1741f-123">Remarks</span></span>  
 <span data-ttu-id="1741f-124">この動作を使用して、既定の非同期受信ではなく同期受信を使用するようにチャネル リスナーに指示します。</span><span class="sxs-lookup"><span data-stu-id="1741f-124">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="1741f-125">Windows Communication Foundation (WCF) は、受け入れられたチャネルごとに新しいスレッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="1741f-125">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="1741f-126">チャネルが多数ある場合は、スレッドが不足する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1741f-126">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1741f-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="1741f-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
