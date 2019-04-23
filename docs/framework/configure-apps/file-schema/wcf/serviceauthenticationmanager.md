---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 0940248364488bb38a329c5e461d72463c574e74
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192045"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="4ea51-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="4ea51-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="4ea51-102">サービス レベルで転送、メッセージ、または送信元の有効性を確立するワークフロー構成要素を提供します。</span><span class="sxs-lookup"><span data-stu-id="4ea51-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="4ea51-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4ea51-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="4ea51-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="4ea51-104">\<behaviors></span></span>  
<span data-ttu-id="4ea51-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4ea51-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="4ea51-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4ea51-106">\<behavior></span></span>  
<span data-ttu-id="4ea51-107">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="4ea51-107">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ea51-108">構文</span><span class="sxs-lookup"><span data-stu-id="4ea51-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ea51-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4ea51-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4ea51-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ea51-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ea51-111">属性</span><span class="sxs-lookup"><span data-stu-id="4ea51-111">Attributes</span></span>  
  
|<span data-ttu-id="4ea51-112">属性</span><span class="sxs-lookup"><span data-stu-id="4ea51-112">Attribute</span></span>|<span data-ttu-id="4ea51-113">説明</span><span class="sxs-lookup"><span data-stu-id="4ea51-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ea51-114">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="4ea51-114">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="4ea51-115">現在の動作の認証ポリシーの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="4ea51-115">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ea51-116">子要素</span><span class="sxs-lookup"><span data-stu-id="4ea51-116">Child Elements</span></span>  
 <span data-ttu-id="4ea51-117">なし。</span><span class="sxs-lookup"><span data-stu-id="4ea51-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ea51-118">親要素</span><span class="sxs-lookup"><span data-stu-id="4ea51-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4ea51-119">要素</span><span class="sxs-lookup"><span data-stu-id="4ea51-119">Element</span></span>|<span data-ttu-id="4ea51-120">説明</span><span class="sxs-lookup"><span data-stu-id="4ea51-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ea51-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4ea51-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="4ea51-122">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ea51-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ea51-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ea51-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
