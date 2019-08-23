---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: a22c72b7a683e3ecab4344c92e7d835a184a58d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947158"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="3c531-101">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="3c531-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="3c531-102">ワークフロー インスタンスの実行方法を制御する設定を指定するためのサービス動作。これには、永続する未処理の例外動作やアイドル状態の動作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3c531-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="3c531-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3c531-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3c531-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="3c531-104">\<behaviors></span></span>  
<span data-ttu-id="3c531-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="3c531-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="3c531-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3c531-106">\<behavior></span></span>  
<span data-ttu-id="3c531-107">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="3c531-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c531-108">構文</span><span class="sxs-lookup"><span data-stu-id="3c531-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c531-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3c531-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3c531-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c531-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c531-111">属性</span><span class="sxs-lookup"><span data-stu-id="3c531-111">Attributes</span></span>  
  
|<span data-ttu-id="3c531-112">属性</span><span class="sxs-lookup"><span data-stu-id="3c531-112">Attribute</span></span>|<span data-ttu-id="3c531-113">説明</span><span class="sxs-lookup"><span data-stu-id="3c531-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c531-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="3c531-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="3c531-115">子要素</span><span class="sxs-lookup"><span data-stu-id="3c531-115">Child Elements</span></span>  
 <span data-ttu-id="3c531-116">なし。</span><span class="sxs-lookup"><span data-stu-id="3c531-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c531-117">親要素</span><span class="sxs-lookup"><span data-stu-id="3c531-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3c531-118">要素</span><span class="sxs-lookup"><span data-stu-id="3c531-118">Element</span></span>|<span data-ttu-id="3c531-119">説明</span><span class="sxs-lookup"><span data-stu-id="3c531-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c531-120">\<servicebehaviors の\<動作 > ></span><span class="sxs-lookup"><span data-stu-id="3c531-120">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="3c531-121">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c531-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c531-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c531-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
