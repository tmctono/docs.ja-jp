---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e1b40718638ded54e59743730159ea6e65a51a57
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398183"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="e0839-101">\<> のための/のタイムアウト</span><span class="sxs-lookup"><span data-stu-id="e0839-101">\<callbackTimeouts></span></span>
<span data-ttu-id="e0839-102">双方向コールバック コントラクト シナリオでトランザクションをサーバーからクライアントに転送する際のタイムアウト値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0839-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
<span data-ttu-id="e0839-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e0839-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e0839-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e0839-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e0839-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e0839-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e0839-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e0839-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="e0839-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e0839-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="e0839-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> のための/のタイムアウト**</span><span class="sxs-lookup"><span data-stu-id="e0839-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0839-109">構文</span><span class="sxs-lookup"><span data-stu-id="e0839-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="e0839-110">型</span><span class="sxs-lookup"><span data-stu-id="e0839-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0839-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e0839-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e0839-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0839-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0839-113">属性</span><span class="sxs-lookup"><span data-stu-id="e0839-113">Attributes</span></span>  
  
|<span data-ttu-id="e0839-114">属性</span><span class="sxs-lookup"><span data-stu-id="e0839-114">Attribute</span></span>|<span data-ttu-id="e0839-115">説明</span><span class="sxs-lookup"><span data-stu-id="e0839-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="e0839-116">トランザクションが完了する必要があるまたは自動的に終了される必要がある制限時間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="e0839-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="e0839-117">既定値は "00:00:00" です。</span><span class="sxs-lookup"><span data-stu-id="e0839-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0839-118">子要素</span><span class="sxs-lookup"><span data-stu-id="e0839-118">Child Elements</span></span>  
 <span data-ttu-id="e0839-119">なし。</span><span class="sxs-lookup"><span data-stu-id="e0839-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0839-120">親要素</span><span class="sxs-lookup"><span data-stu-id="e0839-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e0839-121">要素</span><span class="sxs-lookup"><span data-stu-id="e0839-121">Element</span></span>|<span data-ttu-id="e0839-122">説明</span><span class="sxs-lookup"><span data-stu-id="e0839-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0839-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e0839-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e0839-124">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0839-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0839-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0839-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
