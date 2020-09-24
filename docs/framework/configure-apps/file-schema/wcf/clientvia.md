---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 5e62201a38dc4dc251996531a4af5f294dd2395f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151104"
---
# \<clientVia>

<span data-ttu-id="2637c-101">トランスポート チャネルの作成対象となる URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="2637c-101">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="2637c-102">詳細については、「<xref:System.ServiceModel.Description.ClientViaBehavior>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2637c-102">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**  
  
## <a name="syntax"></a><span data-ttu-id="2637c-103">構文</span><span class="sxs-lookup"><span data-stu-id="2637c-103">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2637c-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2637c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="2637c-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2637c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2637c-106">属性</span><span class="sxs-lookup"><span data-stu-id="2637c-106">Attributes</span></span>  
  
|<span data-ttu-id="2637c-107">属性</span><span class="sxs-lookup"><span data-stu-id="2637c-107">Attribute</span></span>|<span data-ttu-id="2637c-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="2637c-108">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="2637c-109">メッセージの経路を示す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="2637c-109">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2637c-110">子要素</span><span class="sxs-lookup"><span data-stu-id="2637c-110">Child Elements</span></span>  

 <span data-ttu-id="2637c-111">None</span><span class="sxs-lookup"><span data-stu-id="2637c-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2637c-112">親要素</span><span class="sxs-lookup"><span data-stu-id="2637c-112">Parent Elements</span></span>  
  
|<span data-ttu-id="2637c-113">要素</span><span class="sxs-lookup"><span data-stu-id="2637c-113">Element</span></span>|<span data-ttu-id="2637c-114">説明</span><span class="sxs-lookup"><span data-stu-id="2637c-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="2637c-115">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="2637c-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2637c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2637c-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
