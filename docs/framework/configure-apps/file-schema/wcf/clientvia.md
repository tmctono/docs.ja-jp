---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: a1c2ee68fb039e24e1462148cb52daf1bb57f8ed
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398109"
---
# \<clientVia>
<span data-ttu-id="af4d3-101">トランスポート チャネルの作成対象となる URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="af4d3-101">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="af4d3-102">詳細については、「<xref:System.ServiceModel.Description.ClientViaBehavior>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af4d3-102">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**  
  
## <a name="syntax"></a><span data-ttu-id="af4d3-103">構文</span><span class="sxs-lookup"><span data-stu-id="af4d3-103">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af4d3-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="af4d3-104">Attributes and Elements</span></span>  
 <span data-ttu-id="af4d3-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="af4d3-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af4d3-106">属性</span><span class="sxs-lookup"><span data-stu-id="af4d3-106">Attributes</span></span>  
  
|<span data-ttu-id="af4d3-107">属性</span><span class="sxs-lookup"><span data-stu-id="af4d3-107">Attribute</span></span>|<span data-ttu-id="af4d3-108">説明</span><span class="sxs-lookup"><span data-stu-id="af4d3-108">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="af4d3-109">メッセージの経路を示す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="af4d3-109">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af4d3-110">子要素</span><span class="sxs-lookup"><span data-stu-id="af4d3-110">Child Elements</span></span>  
 <span data-ttu-id="af4d3-111">なし</span><span class="sxs-lookup"><span data-stu-id="af4d3-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af4d3-112">親要素</span><span class="sxs-lookup"><span data-stu-id="af4d3-112">Parent Elements</span></span>  
  
|<span data-ttu-id="af4d3-113">要素</span><span class="sxs-lookup"><span data-stu-id="af4d3-113">Element</span></span>|<span data-ttu-id="af4d3-114">Description</span><span class="sxs-lookup"><span data-stu-id="af4d3-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="af4d3-115">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="af4d3-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af4d3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="af4d3-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
