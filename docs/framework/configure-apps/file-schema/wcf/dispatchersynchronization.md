---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: b95f25217c2a3558846cc7a0ef43e21aacd2ee2a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398002"
---
# \<dispatcherSynchronization>
  
<span data-ttu-id="a56d6-101">サービスが非同期に応答を返すことができるようにするエンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="a56d6-101">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**  
  
## <a name="syntax"></a><span data-ttu-id="a56d6-102">構文</span><span class="sxs-lookup"><span data-stu-id="a56d6-102">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="a56d6-103">Type</span><span class="sxs-lookup"><span data-stu-id="a56d6-103">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a56d6-104">属性と要素</span><span class="sxs-lookup"><span data-stu-id="a56d6-104">Attributes and elements</span></span>  
  
<span data-ttu-id="a56d6-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a56d6-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a56d6-106">属性</span><span class="sxs-lookup"><span data-stu-id="a56d6-106">Attributes</span></span>

| <span data-ttu-id="a56d6-107">属性</span><span class="sxs-lookup"><span data-stu-id="a56d6-107">Attribute</span></span>               | <span data-ttu-id="a56d6-108">説明</span><span class="sxs-lookup"><span data-stu-id="a56d6-108">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="a56d6-109">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="a56d6-109">asynchronousSendEnabled</span></span> | <span data-ttu-id="a56d6-110">非同期の送信動作が有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="a56d6-110">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="a56d6-111">チャネルで発行可能な同時受信の数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="a56d6-111">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="a56d6-112">この値は、サービス調整の動作を適切に構成した後に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a56d6-112">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="a56d6-113">子要素</span><span class="sxs-lookup"><span data-stu-id="a56d6-113">Child elements</span></span>

<span data-ttu-id="a56d6-114">なし。</span><span class="sxs-lookup"><span data-stu-id="a56d6-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a56d6-115">親要素</span><span class="sxs-lookup"><span data-stu-id="a56d6-115">Parent elements</span></span>

| <span data-ttu-id="a56d6-116">要素</span><span class="sxs-lookup"><span data-stu-id="a56d6-116">Element</span></span> | <span data-ttu-id="a56d6-117">Description</span><span class="sxs-lookup"><span data-stu-id="a56d6-117">Description</span></span> |  
| ------- | ----------- |  
| [\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a56d6-118">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="a56d6-118">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a56d6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a56d6-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
