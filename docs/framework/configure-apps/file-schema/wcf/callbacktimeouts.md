---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e666bac0be772e417f140e1482649f82ea70e2f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173642"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="5d09b-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="5d09b-101">\<callbackTimeouts></span></span>
<span data-ttu-id="5d09b-102">双方向コールバック コントラクト シナリオでトランザクションをサーバーからクライアントに転送する際のタイムアウト値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d09b-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="5d09b-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5d09b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5d09b-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="5d09b-104">\<behaviors></span></span>  
<span data-ttu-id="5d09b-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5d09b-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="5d09b-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5d09b-106">\<behavior></span></span>  
<span data-ttu-id="5d09b-107">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="5d09b-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d09b-108">構文</span><span class="sxs-lookup"><span data-stu-id="5d09b-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="5d09b-109">型</span><span class="sxs-lookup"><span data-stu-id="5d09b-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d09b-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5d09b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5d09b-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d09b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d09b-112">属性</span><span class="sxs-lookup"><span data-stu-id="5d09b-112">Attributes</span></span>  
  
|<span data-ttu-id="5d09b-113">属性</span><span class="sxs-lookup"><span data-stu-id="5d09b-113">Attribute</span></span>|<span data-ttu-id="5d09b-114">説明</span><span class="sxs-lookup"><span data-stu-id="5d09b-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="5d09b-115">トランザクションが完了する必要があるまたは自動的に終了される必要がある制限時間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="5d09b-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="5d09b-116">既定値は"00: 00:00"。</span><span class="sxs-lookup"><span data-stu-id="5d09b-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d09b-117">子要素</span><span class="sxs-lookup"><span data-stu-id="5d09b-117">Child Elements</span></span>  
 <span data-ttu-id="5d09b-118">なし。</span><span class="sxs-lookup"><span data-stu-id="5d09b-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d09b-119">親要素</span><span class="sxs-lookup"><span data-stu-id="5d09b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5d09b-120">要素</span><span class="sxs-lookup"><span data-stu-id="5d09b-120">Element</span></span>|<span data-ttu-id="5d09b-121">説明</span><span class="sxs-lookup"><span data-stu-id="5d09b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d09b-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5d09b-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5d09b-123">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d09b-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d09b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d09b-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
