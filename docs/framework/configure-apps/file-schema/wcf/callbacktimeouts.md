---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 98523489aacebf910bcf5d81c479819183887dff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198887"
---
# \<callbackTimeouts>

<span data-ttu-id="741ea-101">双方向コールバック コントラクト シナリオでトランザクションをサーバーからクライアントに転送する際のタイムアウト値を指定します。</span><span class="sxs-lookup"><span data-stu-id="741ea-101">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="741ea-102">構文</span><span class="sxs-lookup"><span data-stu-id="741ea-102">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="741ea-103">種類</span><span class="sxs-lookup"><span data-stu-id="741ea-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="741ea-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="741ea-104">Attributes and Elements</span></span>  

 <span data-ttu-id="741ea-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="741ea-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="741ea-106">属性</span><span class="sxs-lookup"><span data-stu-id="741ea-106">Attributes</span></span>  
  
|<span data-ttu-id="741ea-107">属性</span><span class="sxs-lookup"><span data-stu-id="741ea-107">Attribute</span></span>|<span data-ttu-id="741ea-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="741ea-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="741ea-109">トランザクションが完了する必要があるまたは自動的に終了される必要がある制限時間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="741ea-109">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="741ea-110">既定値は "00:00:00" です。</span><span class="sxs-lookup"><span data-stu-id="741ea-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="741ea-111">子要素</span><span class="sxs-lookup"><span data-stu-id="741ea-111">Child Elements</span></span>  

 <span data-ttu-id="741ea-112">なし。</span><span class="sxs-lookup"><span data-stu-id="741ea-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="741ea-113">親要素</span><span class="sxs-lookup"><span data-stu-id="741ea-113">Parent Elements</span></span>  
  
|<span data-ttu-id="741ea-114">要素</span><span class="sxs-lookup"><span data-stu-id="741ea-114">Element</span></span>|<span data-ttu-id="741ea-115">説明</span><span class="sxs-lookup"><span data-stu-id="741ea-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="741ea-116">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="741ea-116">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="741ea-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="741ea-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
