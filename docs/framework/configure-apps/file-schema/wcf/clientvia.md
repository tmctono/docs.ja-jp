---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b8864760c1700cd785922b922346204d194f56cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176814"
---
# <a name="clientvia"></a><span data-ttu-id="54915-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="54915-101">\<clientVia></span></span>
<span data-ttu-id="54915-102">トランスポート チャネルの作成対象となる URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="54915-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="54915-103">詳細については、「 <xref:System.ServiceModel.Description.ClientViaBehavior> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54915-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="54915-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="54915-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="54915-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="54915-105">\<behaviors></span></span>  
<span data-ttu-id="54915-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="54915-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="54915-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="54915-107">\<behavior></span></span>  
<span data-ttu-id="54915-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="54915-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54915-109">構文</span><span class="sxs-lookup"><span data-stu-id="54915-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54915-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="54915-110">Attributes and Elements</span></span>  
 <span data-ttu-id="54915-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="54915-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54915-112">属性</span><span class="sxs-lookup"><span data-stu-id="54915-112">Attributes</span></span>  
  
|<span data-ttu-id="54915-113">属性</span><span class="sxs-lookup"><span data-stu-id="54915-113">Attribute</span></span>|<span data-ttu-id="54915-114">説明</span><span class="sxs-lookup"><span data-stu-id="54915-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="54915-115">メッセージの経路を示す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="54915-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54915-116">子要素</span><span class="sxs-lookup"><span data-stu-id="54915-116">Child Elements</span></span>  
 <span data-ttu-id="54915-117">なし</span><span class="sxs-lookup"><span data-stu-id="54915-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="54915-118">親要素</span><span class="sxs-lookup"><span data-stu-id="54915-118">Parent Elements</span></span>  
  
|<span data-ttu-id="54915-119">要素</span><span class="sxs-lookup"><span data-stu-id="54915-119">Element</span></span>|<span data-ttu-id="54915-120">説明</span><span class="sxs-lookup"><span data-stu-id="54915-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54915-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="54915-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="54915-122">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="54915-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54915-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="54915-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
