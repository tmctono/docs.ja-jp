---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 801a7aaf1f0d0fa267fa8cca3d2e7fd02919c475
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399550"
---
# \<serviceTimeouts>
<span data-ttu-id="ef386-101">サービスのタイムアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ef386-101">Specifies the timeout for a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**  
  
## <a name="syntax"></a><span data-ttu-id="ef386-102">構文</span><span class="sxs-lookup"><span data-stu-id="ef386-102">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="ef386-103">Type</span><span class="sxs-lookup"><span data-stu-id="ef386-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef386-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ef386-104">Attributes and Elements</span></span>  
 <span data-ttu-id="ef386-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ef386-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef386-106">属性</span><span class="sxs-lookup"><span data-stu-id="ef386-106">Attributes</span></span>  
  
|<span data-ttu-id="ef386-107">属性</span><span class="sxs-lookup"><span data-stu-id="ef386-107">Attribute</span></span>|<span data-ttu-id="ef386-108">説明</span><span class="sxs-lookup"><span data-stu-id="ef386-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="ef386-109">クライアントからサーバーへのトランザクションが発生するまでに待機できる時間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="ef386-109">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="ef386-110">既定値は "00:00:00" です。</span><span class="sxs-lookup"><span data-stu-id="ef386-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef386-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ef386-111">Child Elements</span></span>  
 <span data-ttu-id="ef386-112">なし。</span><span class="sxs-lookup"><span data-stu-id="ef386-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef386-113">親要素</span><span class="sxs-lookup"><span data-stu-id="ef386-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ef386-114">要素</span><span class="sxs-lookup"><span data-stu-id="ef386-114">Element</span></span>|<span data-ttu-id="ef386-115">Description</span><span class="sxs-lookup"><span data-stu-id="ef386-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ef386-116">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="ef386-116">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef386-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef386-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
