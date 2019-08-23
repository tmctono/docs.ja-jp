---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 1d4611d6fee9dad057985f7d8f5ef961d384efcd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945972"
---
# <a name="bufferreceive"></a><span data-ttu-id="e89fd-101">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="e89fd-101">\<bufferReceive></span></span>
<span data-ttu-id="e89fd-102">サービスが、バッファーされた受信処理を使用するためのサービス動作。これにより、ワークフロー サービスは、順番を無視したメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="e89fd-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="e89fd-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e89fd-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e89fd-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="e89fd-104">\<behaviors></span></span>  
<span data-ttu-id="e89fd-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="e89fd-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="e89fd-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e89fd-106">\<behavior></span></span>  
<span data-ttu-id="e89fd-107">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="e89fd-107">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e89fd-108">構文</span><span class="sxs-lookup"><span data-stu-id="e89fd-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e89fd-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e89fd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e89fd-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e89fd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e89fd-111">属性</span><span class="sxs-lookup"><span data-stu-id="e89fd-111">Attributes</span></span>  
  
|<span data-ttu-id="e89fd-112">属性</span><span class="sxs-lookup"><span data-stu-id="e89fd-112">Attribute</span></span>|<span data-ttu-id="e89fd-113">説明</span><span class="sxs-lookup"><span data-stu-id="e89fd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e89fd-114">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="e89fd-114">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="e89fd-115">各チャネルで許容される保留状態のメッセージの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="e89fd-115">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="e89fd-116">既定値は 512 です。</span><span class="sxs-lookup"><span data-stu-id="e89fd-116">The default value is 512.</span></span> <span data-ttu-id="e89fd-117">このプロパティは、ワークフロー サービスで受信できる、順番を無視したメッセージの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="e89fd-117">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e89fd-118">子要素</span><span class="sxs-lookup"><span data-stu-id="e89fd-118">Child Elements</span></span>  
 <span data-ttu-id="e89fd-119">なし。</span><span class="sxs-lookup"><span data-stu-id="e89fd-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e89fd-120">親要素</span><span class="sxs-lookup"><span data-stu-id="e89fd-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e89fd-121">要素</span><span class="sxs-lookup"><span data-stu-id="e89fd-121">Element</span></span>|<span data-ttu-id="e89fd-122">説明</span><span class="sxs-lookup"><span data-stu-id="e89fd-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e89fd-123">\<servicebehaviors の\<動作 > ></span><span class="sxs-lookup"><span data-stu-id="e89fd-123">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="e89fd-124">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="e89fd-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e89fd-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e89fd-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
