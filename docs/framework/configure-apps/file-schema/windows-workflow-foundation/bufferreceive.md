---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 16d4546bce461b55695e0deed093396ce1c2b0b6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189566"
---
# \<bufferReceive>

<span data-ttu-id="0be92-101">サービスが、バッファーされた受信処理を使用するためのサービス動作。これにより、ワークフロー サービスは、順番を無視したメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="0be92-101">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="0be92-102">構文</span><span class="sxs-lookup"><span data-stu-id="0be92-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0be92-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0be92-103">Attributes and Elements</span></span>  

 <span data-ttu-id="0be92-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0be92-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0be92-105">属性</span><span class="sxs-lookup"><span data-stu-id="0be92-105">Attributes</span></span>  
  
|<span data-ttu-id="0be92-106">属性</span><span class="sxs-lookup"><span data-stu-id="0be92-106">Attribute</span></span>|<span data-ttu-id="0be92-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="0be92-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0be92-108">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="0be92-108">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="0be92-109">各チャネルで許容される保留状態のメッセージの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="0be92-109">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="0be92-110">既定値は 512 です。</span><span class="sxs-lookup"><span data-stu-id="0be92-110">The default value is 512.</span></span> <span data-ttu-id="0be92-111">このプロパティは、ワークフロー サービスで受信できる、順番を無視したメッセージの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="0be92-111">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0be92-112">子要素</span><span class="sxs-lookup"><span data-stu-id="0be92-112">Child Elements</span></span>  

 <span data-ttu-id="0be92-113">なし。</span><span class="sxs-lookup"><span data-stu-id="0be92-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0be92-114">親要素</span><span class="sxs-lookup"><span data-stu-id="0be92-114">Parent Elements</span></span>  
  
|<span data-ttu-id="0be92-115">要素</span><span class="sxs-lookup"><span data-stu-id="0be92-115">Element</span></span>|<span data-ttu-id="0be92-116">説明</span><span class="sxs-lookup"><span data-stu-id="0be92-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0be92-117">\<serviceBehaviors> の \<behavior></span><span class="sxs-lookup"><span data-stu-id="0be92-117">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="0be92-118">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="0be92-118">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0be92-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0be92-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
