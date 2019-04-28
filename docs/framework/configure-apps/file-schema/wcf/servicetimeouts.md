---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 5c2f0ef7ad509eb5d6c686802c3fe5a75ea1a258
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758094"
---
# <a name="servicetimeouts"></a><span data-ttu-id="93c7b-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="93c7b-101">\<serviceTimeouts></span></span>
<span data-ttu-id="93c7b-102">サービスのタイムアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="93c7b-102">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="93c7b-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="93c7b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="93c7b-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="93c7b-104">\<behaviors></span></span>  
<span data-ttu-id="93c7b-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="93c7b-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="93c7b-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="93c7b-106">\<behavior></span></span>  
<span data-ttu-id="93c7b-107">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="93c7b-107">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93c7b-108">構文</span><span class="sxs-lookup"><span data-stu-id="93c7b-108">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="93c7b-109">型</span><span class="sxs-lookup"><span data-stu-id="93c7b-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93c7b-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="93c7b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="93c7b-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="93c7b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93c7b-112">属性</span><span class="sxs-lookup"><span data-stu-id="93c7b-112">Attributes</span></span>  
  
|<span data-ttu-id="93c7b-113">属性</span><span class="sxs-lookup"><span data-stu-id="93c7b-113">Attribute</span></span>|<span data-ttu-id="93c7b-114">説明</span><span class="sxs-lookup"><span data-stu-id="93c7b-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="93c7b-115">クライアントからサーバーへのトランザクションが発生するまでに待機できる時間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="93c7b-115">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="93c7b-116">既定値は"00: 00:00"。</span><span class="sxs-lookup"><span data-stu-id="93c7b-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93c7b-117">子要素</span><span class="sxs-lookup"><span data-stu-id="93c7b-117">Child Elements</span></span>  
 <span data-ttu-id="93c7b-118">なし。</span><span class="sxs-lookup"><span data-stu-id="93c7b-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93c7b-119">親要素</span><span class="sxs-lookup"><span data-stu-id="93c7b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="93c7b-120">要素</span><span class="sxs-lookup"><span data-stu-id="93c7b-120">Element</span></span>|<span data-ttu-id="93c7b-121">説明</span><span class="sxs-lookup"><span data-stu-id="93c7b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93c7b-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="93c7b-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="93c7b-123">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="93c7b-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93c7b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="93c7b-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
