---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 801a7aaf1f0d0fa267fa8cca3d2e7fd02919c475
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399550"
---
# <a name="servicetimeouts"></a><span data-ttu-id="e809b-101">\<serviceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="e809b-101">\<serviceTimeouts></span></span>
<span data-ttu-id="e809b-102">サービスのタイムアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e809b-102">Specifies the timeout for a service.</span></span>  
  
<span data-ttu-id="e809b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e809b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e809b-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e809b-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e809b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e809b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e809b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e809b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="e809b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e809b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="e809b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceTimeouts >**</span><span class="sxs-lookup"><span data-stu-id="e809b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e809b-109">構文</span><span class="sxs-lookup"><span data-stu-id="e809b-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="e809b-110">型</span><span class="sxs-lookup"><span data-stu-id="e809b-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e809b-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e809b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e809b-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e809b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e809b-113">属性</span><span class="sxs-lookup"><span data-stu-id="e809b-113">Attributes</span></span>  
  
|<span data-ttu-id="e809b-114">属性</span><span class="sxs-lookup"><span data-stu-id="e809b-114">Attribute</span></span>|<span data-ttu-id="e809b-115">説明</span><span class="sxs-lookup"><span data-stu-id="e809b-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="e809b-116">クライアントからサーバーへのトランザクションが発生するまでに待機できる時間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="e809b-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="e809b-117">既定値は "00:00:00" です。</span><span class="sxs-lookup"><span data-stu-id="e809b-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e809b-118">子要素</span><span class="sxs-lookup"><span data-stu-id="e809b-118">Child Elements</span></span>  
 <span data-ttu-id="e809b-119">なし。</span><span class="sxs-lookup"><span data-stu-id="e809b-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e809b-120">親要素</span><span class="sxs-lookup"><span data-stu-id="e809b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e809b-121">要素</span><span class="sxs-lookup"><span data-stu-id="e809b-121">Element</span></span>|<span data-ttu-id="e809b-122">説明</span><span class="sxs-lookup"><span data-stu-id="e809b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e809b-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e809b-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e809b-124">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="e809b-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e809b-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e809b-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
