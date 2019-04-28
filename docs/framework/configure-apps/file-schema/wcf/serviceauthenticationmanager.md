---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 0940248364488bb38a329c5e461d72463c574e74
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670379"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="94d6f-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="94d6f-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="94d6f-102">サービス レベルで転送、メッセージ、または送信元の有効性を確立するワークフロー構成要素を提供します。</span><span class="sxs-lookup"><span data-stu-id="94d6f-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="94d6f-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="94d6f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="94d6f-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="94d6f-104">\<behaviors></span></span>  
<span data-ttu-id="94d6f-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="94d6f-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="94d6f-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="94d6f-106">\<behavior></span></span>  
<span data-ttu-id="94d6f-107">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="94d6f-107">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94d6f-108">構文</span><span class="sxs-lookup"><span data-stu-id="94d6f-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94d6f-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="94d6f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="94d6f-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="94d6f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94d6f-111">属性</span><span class="sxs-lookup"><span data-stu-id="94d6f-111">Attributes</span></span>  
  
|<span data-ttu-id="94d6f-112">属性</span><span class="sxs-lookup"><span data-stu-id="94d6f-112">Attribute</span></span>|<span data-ttu-id="94d6f-113">説明</span><span class="sxs-lookup"><span data-stu-id="94d6f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="94d6f-114">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="94d6f-114">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="94d6f-115">現在の動作の認証ポリシーの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="94d6f-115">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94d6f-116">子要素</span><span class="sxs-lookup"><span data-stu-id="94d6f-116">Child Elements</span></span>  
 <span data-ttu-id="94d6f-117">なし。</span><span class="sxs-lookup"><span data-stu-id="94d6f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="94d6f-118">親要素</span><span class="sxs-lookup"><span data-stu-id="94d6f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="94d6f-119">要素</span><span class="sxs-lookup"><span data-stu-id="94d6f-119">Element</span></span>|<span data-ttu-id="94d6f-120">説明</span><span class="sxs-lookup"><span data-stu-id="94d6f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94d6f-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="94d6f-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="94d6f-122">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="94d6f-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94d6f-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="94d6f-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
