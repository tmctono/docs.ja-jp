---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 6be9752e8102a5d4db4fed31aae8ff6d56fdd24e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673408"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="a3623-101">\<dispatcherSynchronization ></span><span class="sxs-lookup"><span data-stu-id="a3623-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="a3623-102">サービスが非同期に応答を返すことができるようにするエンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="a3623-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="a3623-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a3623-103">\<system.serviceModel></span></span>  
<span data-ttu-id="a3623-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="a3623-104">\<behaviors></span></span>  
<span data-ttu-id="a3623-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a3623-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="a3623-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a3623-106">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3623-107">構文</span><span class="sxs-lookup"><span data-stu-id="a3623-107">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="a3623-108">型</span><span class="sxs-lookup"><span data-stu-id="a3623-108">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3623-109">属性と要素</span><span class="sxs-lookup"><span data-stu-id="a3623-109">Attributes and elements</span></span>  
  
<span data-ttu-id="a3623-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3623-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3623-111">属性</span><span class="sxs-lookup"><span data-stu-id="a3623-111">Attributes</span></span>

| <span data-ttu-id="a3623-112">属性</span><span class="sxs-lookup"><span data-stu-id="a3623-112">Attribute</span></span>               | <span data-ttu-id="a3623-113">説明</span><span class="sxs-lookup"><span data-stu-id="a3623-113">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="a3623-114">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="a3623-114">asynchronousSendEnabled</span></span> | <span data-ttu-id="a3623-115">非同期の送信動作が有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="a3623-115">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="a3623-116">チャネルで発行可能な同時受信の数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="a3623-116">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="a3623-117">この値は、サービス調整の動作を適切に構成した後に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3623-117">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="a3623-118">子要素</span><span class="sxs-lookup"><span data-stu-id="a3623-118">Child elements</span></span>

<span data-ttu-id="a3623-119">なし。</span><span class="sxs-lookup"><span data-stu-id="a3623-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a3623-120">親要素</span><span class="sxs-lookup"><span data-stu-id="a3623-120">Parent elements</span></span>

| <span data-ttu-id="a3623-121">要素</span><span class="sxs-lookup"><span data-stu-id="a3623-121">Element</span></span> | <span data-ttu-id="a3623-122">説明</span><span class="sxs-lookup"><span data-stu-id="a3623-122">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="a3623-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a3623-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a3623-124">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="a3623-124">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a3623-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3623-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
