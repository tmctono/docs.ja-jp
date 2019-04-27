---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b8864760c1700cd785922b922346204d194f56cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673629"
---
# <a name="clientvia"></a><span data-ttu-id="f1fc6-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="f1fc6-101">\<clientVia></span></span>
<span data-ttu-id="f1fc6-102">トランスポート チャネルの作成対象となる URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1fc6-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="f1fc6-103">詳細については、「 <xref:System.ServiceModel.Description.ClientViaBehavior> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1fc6-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="f1fc6-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f1fc6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f1fc6-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="f1fc6-105">\<behaviors></span></span>  
<span data-ttu-id="f1fc6-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="f1fc6-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="f1fc6-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f1fc6-107">\<behavior></span></span>  
<span data-ttu-id="f1fc6-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="f1fc6-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1fc6-109">構文</span><span class="sxs-lookup"><span data-stu-id="f1fc6-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1fc6-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f1fc6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f1fc6-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1fc6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1fc6-112">属性</span><span class="sxs-lookup"><span data-stu-id="f1fc6-112">Attributes</span></span>  
  
|<span data-ttu-id="f1fc6-113">属性</span><span class="sxs-lookup"><span data-stu-id="f1fc6-113">Attribute</span></span>|<span data-ttu-id="f1fc6-114">説明</span><span class="sxs-lookup"><span data-stu-id="f1fc6-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="f1fc6-115">メッセージの経路を示す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="f1fc6-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1fc6-116">子要素</span><span class="sxs-lookup"><span data-stu-id="f1fc6-116">Child Elements</span></span>  
 <span data-ttu-id="f1fc6-117">なし</span><span class="sxs-lookup"><span data-stu-id="f1fc6-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f1fc6-118">親要素</span><span class="sxs-lookup"><span data-stu-id="f1fc6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f1fc6-119">要素</span><span class="sxs-lookup"><span data-stu-id="f1fc6-119">Element</span></span>|<span data-ttu-id="f1fc6-120">説明</span><span class="sxs-lookup"><span data-stu-id="f1fc6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1fc6-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f1fc6-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f1fc6-122">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1fc6-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1fc6-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1fc6-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
