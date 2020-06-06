---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e1b40718638ded54e59743730159ea6e65a51a57
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398183"
---
# \<callbackTimeouts>
<span data-ttu-id="cd4ac-101">双方向コールバック コントラクト シナリオでトランザクションをサーバーからクライアントに転送する際のタイムアウト値を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd4ac-101">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="cd4ac-102">構文</span><span class="sxs-lookup"><span data-stu-id="cd4ac-102">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="cd4ac-103">Type</span><span class="sxs-lookup"><span data-stu-id="cd4ac-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd4ac-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cd4ac-104">Attributes and Elements</span></span>  
 <span data-ttu-id="cd4ac-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd4ac-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd4ac-106">属性</span><span class="sxs-lookup"><span data-stu-id="cd4ac-106">Attributes</span></span>  
  
|<span data-ttu-id="cd4ac-107">属性</span><span class="sxs-lookup"><span data-stu-id="cd4ac-107">Attribute</span></span>|<span data-ttu-id="cd4ac-108">説明</span><span class="sxs-lookup"><span data-stu-id="cd4ac-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="cd4ac-109">トランザクションが完了する必要があるまたは自動的に終了される必要がある制限時間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="cd4ac-109">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="cd4ac-110">既定値は "00:00:00" です。</span><span class="sxs-lookup"><span data-stu-id="cd4ac-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd4ac-111">子要素</span><span class="sxs-lookup"><span data-stu-id="cd4ac-111">Child Elements</span></span>  
 <span data-ttu-id="cd4ac-112">なし。</span><span class="sxs-lookup"><span data-stu-id="cd4ac-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd4ac-113">親要素</span><span class="sxs-lookup"><span data-stu-id="cd4ac-113">Parent Elements</span></span>  
  
|<span data-ttu-id="cd4ac-114">要素</span><span class="sxs-lookup"><span data-stu-id="cd4ac-114">Element</span></span>|<span data-ttu-id="cd4ac-115">Description</span><span class="sxs-lookup"><span data-stu-id="cd4ac-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="cd4ac-116">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd4ac-116">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd4ac-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd4ac-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
