---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: be5173ea43c6f7fca7180a311885a26c889b12db
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398834"
---
# <a name="bufferreceive"></a><span data-ttu-id="9ac30-101">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="9ac30-101">\<bufferReceive></span></span>
<span data-ttu-id="9ac30-102">サービスが、バッファーされた受信処理を使用するためのサービス動作。これにより、ワークフロー サービスは、順番を無視したメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="9ac30-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="9ac30-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9ac30-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9ac30-104">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9ac30-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="9ac30-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9ac30-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="9ac30-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9ac30-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="9ac30-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9ac30-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="9ac30-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bufferReceive >**</span><span class="sxs-lookup"><span data-stu-id="9ac30-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ac30-109">構文</span><span class="sxs-lookup"><span data-stu-id="9ac30-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ac30-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9ac30-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9ac30-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ac30-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ac30-112">属性</span><span class="sxs-lookup"><span data-stu-id="9ac30-112">Attributes</span></span>  
  
|<span data-ttu-id="9ac30-113">属性</span><span class="sxs-lookup"><span data-stu-id="9ac30-113">Attribute</span></span>|<span data-ttu-id="9ac30-114">説明</span><span class="sxs-lookup"><span data-stu-id="9ac30-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ac30-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="9ac30-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="9ac30-116">各チャネルで許容される保留状態のメッセージの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="9ac30-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="9ac30-117">既定値は 512 です。</span><span class="sxs-lookup"><span data-stu-id="9ac30-117">The default value is 512.</span></span> <span data-ttu-id="9ac30-118">このプロパティは、ワークフロー サービスで受信できる、順番を無視したメッセージの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="9ac30-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ac30-119">子要素</span><span class="sxs-lookup"><span data-stu-id="9ac30-119">Child Elements</span></span>  
 <span data-ttu-id="9ac30-120">なし。</span><span class="sxs-lookup"><span data-stu-id="9ac30-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ac30-121">親要素</span><span class="sxs-lookup"><span data-stu-id="9ac30-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9ac30-122">要素</span><span class="sxs-lookup"><span data-stu-id="9ac30-122">Element</span></span>|<span data-ttu-id="9ac30-123">説明</span><span class="sxs-lookup"><span data-stu-id="9ac30-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ac30-124">\<servicebehaviors の\<動作 > ></span><span class="sxs-lookup"><span data-stu-id="9ac30-124">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="9ac30-125">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ac30-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ac30-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ac30-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
