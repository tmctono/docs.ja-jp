---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: be5173ea43c6f7fca7180a311885a26c889b12db
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398834"
---
# \<bufferReceive>
<span data-ttu-id="5c3c8-101">サービスが、バッファーされた受信処理を使用するためのサービス動作。これにより、ワークフロー サービスは、順番を無視したメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="5c3c8-101">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="5c3c8-102">構文</span><span class="sxs-lookup"><span data-stu-id="5c3c8-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c3c8-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5c3c8-103">Attributes and Elements</span></span>  
 <span data-ttu-id="5c3c8-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c3c8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c3c8-105">属性</span><span class="sxs-lookup"><span data-stu-id="5c3c8-105">Attributes</span></span>  
  
|<span data-ttu-id="5c3c8-106">属性</span><span class="sxs-lookup"><span data-stu-id="5c3c8-106">Attribute</span></span>|<span data-ttu-id="5c3c8-107">説明</span><span class="sxs-lookup"><span data-stu-id="5c3c8-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c3c8-108">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="5c3c8-108">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="5c3c8-109">各チャネルで許容される保留状態のメッセージの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="5c3c8-109">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="5c3c8-110">既定値は 512 です。</span><span class="sxs-lookup"><span data-stu-id="5c3c8-110">The default value is 512.</span></span> <span data-ttu-id="5c3c8-111">このプロパティは、ワークフロー サービスで受信できる、順番を無視したメッセージの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="5c3c8-111">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c3c8-112">子要素</span><span class="sxs-lookup"><span data-stu-id="5c3c8-112">Child Elements</span></span>  
 <span data-ttu-id="5c3c8-113">なし。</span><span class="sxs-lookup"><span data-stu-id="5c3c8-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c3c8-114">親要素</span><span class="sxs-lookup"><span data-stu-id="5c3c8-114">Parent Elements</span></span>  
  
|<span data-ttu-id="5c3c8-115">要素</span><span class="sxs-lookup"><span data-stu-id="5c3c8-115">Element</span></span>|<span data-ttu-id="5c3c8-116">Description</span><span class="sxs-lookup"><span data-stu-id="5c3c8-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c3c8-117">\<behavior>の\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5c3c8-117">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="5c3c8-118">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c3c8-118">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c3c8-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c3c8-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
