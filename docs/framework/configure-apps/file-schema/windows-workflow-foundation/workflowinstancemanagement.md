---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 98bc1b24da6e65a11a39d133057c1bb55b003a58
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191615"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="2ef11-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="2ef11-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="2ef11-102">ワークフロー インスタンスの実行方法を制御する設定を指定するためのサービス動作。これには、永続する未処理の例外動作やアイドル状態の動作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2ef11-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="2ef11-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2ef11-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2ef11-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="2ef11-104">\<behaviors></span></span>  
<span data-ttu-id="2ef11-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="2ef11-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="2ef11-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2ef11-106">\<behavior></span></span>  
<span data-ttu-id="2ef11-107">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="2ef11-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ef11-108">構文</span><span class="sxs-lookup"><span data-stu-id="2ef11-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ef11-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2ef11-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2ef11-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ef11-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ef11-111">属性</span><span class="sxs-lookup"><span data-stu-id="2ef11-111">Attributes</span></span>  
  
|<span data-ttu-id="2ef11-112">属性</span><span class="sxs-lookup"><span data-stu-id="2ef11-112">Attribute</span></span>|<span data-ttu-id="2ef11-113">説明</span><span class="sxs-lookup"><span data-stu-id="2ef11-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ef11-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="2ef11-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="2ef11-115">子要素</span><span class="sxs-lookup"><span data-stu-id="2ef11-115">Child Elements</span></span>  
 <span data-ttu-id="2ef11-116">なし。</span><span class="sxs-lookup"><span data-stu-id="2ef11-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ef11-117">親要素</span><span class="sxs-lookup"><span data-stu-id="2ef11-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2ef11-118">要素</span><span class="sxs-lookup"><span data-stu-id="2ef11-118">Element</span></span>|<span data-ttu-id="2ef11-119">説明</span><span class="sxs-lookup"><span data-stu-id="2ef11-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ef11-120">\<動作 > の\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2ef11-120">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="2ef11-121">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ef11-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ef11-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ef11-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
