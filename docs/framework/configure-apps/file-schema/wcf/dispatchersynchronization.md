---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 7336c9f7d8a117f9a9bfd338e47941eeb648fa51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925853"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="1afde-101">\<dispatcherSynchronization ></span><span class="sxs-lookup"><span data-stu-id="1afde-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="1afde-102">サービスが非同期に応答を返すことができるようにするエンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="1afde-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="1afde-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1afde-103">\<system.serviceModel></span></span>  
<span data-ttu-id="1afde-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="1afde-104">\<behaviors></span></span>  
<span data-ttu-id="1afde-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="1afde-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="1afde-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1afde-106">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1afde-107">構文</span><span class="sxs-lookup"><span data-stu-id="1afde-107">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="1afde-108">種類</span><span class="sxs-lookup"><span data-stu-id="1afde-108">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1afde-109">属性と要素</span><span class="sxs-lookup"><span data-stu-id="1afde-109">Attributes and elements</span></span>  
  
<span data-ttu-id="1afde-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1afde-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1afde-111">属性</span><span class="sxs-lookup"><span data-stu-id="1afde-111">Attributes</span></span>

| <span data-ttu-id="1afde-112">属性</span><span class="sxs-lookup"><span data-stu-id="1afde-112">Attribute</span></span>               | <span data-ttu-id="1afde-113">説明</span><span class="sxs-lookup"><span data-stu-id="1afde-113">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="1afde-114">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="1afde-114">asynchronousSendEnabled</span></span> | <span data-ttu-id="1afde-115">非同期の送信動作が有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="1afde-115">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="1afde-116">チャネルで発行可能な同時受信の数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="1afde-116">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="1afde-117">この値は、サービス調整の動作を適切に構成した後に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1afde-117">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="1afde-118">子要素</span><span class="sxs-lookup"><span data-stu-id="1afde-118">Child elements</span></span>

<span data-ttu-id="1afde-119">なし。</span><span class="sxs-lookup"><span data-stu-id="1afde-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1afde-120">親要素</span><span class="sxs-lookup"><span data-stu-id="1afde-120">Parent elements</span></span>

| <span data-ttu-id="1afde-121">要素</span><span class="sxs-lookup"><span data-stu-id="1afde-121">Element</span></span> | <span data-ttu-id="1afde-122">説明</span><span class="sxs-lookup"><span data-stu-id="1afde-122">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="1afde-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1afde-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1afde-124">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="1afde-124">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1afde-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="1afde-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
