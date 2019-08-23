---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: d57a888a19e684ac13632c1ab2476e304667c3e3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919658"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="5ade0-101">\<> のための/のタイムアウト</span><span class="sxs-lookup"><span data-stu-id="5ade0-101">\<callbackTimeouts></span></span>
<span data-ttu-id="5ade0-102">双方向コールバック コントラクト シナリオでトランザクションをサーバーからクライアントに転送する際のタイムアウト値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ade0-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="5ade0-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5ade0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5ade0-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="5ade0-104">\<behaviors></span></span>  
<span data-ttu-id="5ade0-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5ade0-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="5ade0-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5ade0-106">\<behavior></span></span>  
<span data-ttu-id="5ade0-107">\<> のための/のタイムアウト</span><span class="sxs-lookup"><span data-stu-id="5ade0-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ade0-108">構文</span><span class="sxs-lookup"><span data-stu-id="5ade0-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="5ade0-109">型</span><span class="sxs-lookup"><span data-stu-id="5ade0-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ade0-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5ade0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5ade0-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ade0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ade0-112">属性</span><span class="sxs-lookup"><span data-stu-id="5ade0-112">Attributes</span></span>  
  
|<span data-ttu-id="5ade0-113">属性</span><span class="sxs-lookup"><span data-stu-id="5ade0-113">Attribute</span></span>|<span data-ttu-id="5ade0-114">説明</span><span class="sxs-lookup"><span data-stu-id="5ade0-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="5ade0-115">トランザクションが完了する必要があるまたは自動的に終了される必要がある制限時間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="5ade0-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="5ade0-116">既定値は "00:00:00" です。</span><span class="sxs-lookup"><span data-stu-id="5ade0-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ade0-117">子要素</span><span class="sxs-lookup"><span data-stu-id="5ade0-117">Child Elements</span></span>  
 <span data-ttu-id="5ade0-118">なし。</span><span class="sxs-lookup"><span data-stu-id="5ade0-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ade0-119">親要素</span><span class="sxs-lookup"><span data-stu-id="5ade0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5ade0-120">要素</span><span class="sxs-lookup"><span data-stu-id="5ade0-120">Element</span></span>|<span data-ttu-id="5ade0-121">説明</span><span class="sxs-lookup"><span data-stu-id="5ade0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ade0-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5ade0-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5ade0-123">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ade0-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ade0-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ade0-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
