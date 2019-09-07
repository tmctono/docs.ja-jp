---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: a1c2ee68fb039e24e1462148cb52daf1bb57f8ed
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398109"
---
# <a name="clientvia"></a><span data-ttu-id="14a54-101">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="14a54-101">\<clientVia></span></span>
<span data-ttu-id="14a54-102">トランスポート チャネルの作成対象となる URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="14a54-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="14a54-103">詳細については、「 <xref:System.ServiceModel.Description.ClientViaBehavior> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14a54-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
<span data-ttu-id="14a54-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="14a54-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="14a54-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="14a54-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="14a54-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="14a54-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="14a54-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="14a54-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="14a54-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="14a54-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="14a54-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clientVia >**</span><span class="sxs-lookup"><span data-stu-id="14a54-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14a54-110">構文</span><span class="sxs-lookup"><span data-stu-id="14a54-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14a54-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="14a54-111">Attributes and Elements</span></span>  
 <span data-ttu-id="14a54-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14a54-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14a54-113">属性</span><span class="sxs-lookup"><span data-stu-id="14a54-113">Attributes</span></span>  
  
|<span data-ttu-id="14a54-114">属性</span><span class="sxs-lookup"><span data-stu-id="14a54-114">Attribute</span></span>|<span data-ttu-id="14a54-115">説明</span><span class="sxs-lookup"><span data-stu-id="14a54-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="14a54-116">メッセージの経路を示す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="14a54-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14a54-117">子要素</span><span class="sxs-lookup"><span data-stu-id="14a54-117">Child Elements</span></span>  
 <span data-ttu-id="14a54-118">なし</span><span class="sxs-lookup"><span data-stu-id="14a54-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14a54-119">親要素</span><span class="sxs-lookup"><span data-stu-id="14a54-119">Parent Elements</span></span>  
  
|<span data-ttu-id="14a54-120">要素</span><span class="sxs-lookup"><span data-stu-id="14a54-120">Element</span></span>|<span data-ttu-id="14a54-121">説明</span><span class="sxs-lookup"><span data-stu-id="14a54-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14a54-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="14a54-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="14a54-123">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="14a54-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14a54-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="14a54-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
