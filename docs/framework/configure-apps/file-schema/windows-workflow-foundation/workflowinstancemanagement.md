---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 98bc1b24da6e65a11a39d133057c1bb55b003a58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613460"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="321a1-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="321a1-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="321a1-102">ワークフロー インスタンスの実行方法を制御する設定を指定するためのサービス動作。これには、永続する未処理の例外動作やアイドル状態の動作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="321a1-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="321a1-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="321a1-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="321a1-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="321a1-104">\<behaviors></span></span>  
<span data-ttu-id="321a1-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="321a1-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="321a1-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="321a1-106">\<behavior></span></span>  
<span data-ttu-id="321a1-107">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="321a1-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="321a1-108">構文</span><span class="sxs-lookup"><span data-stu-id="321a1-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="321a1-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="321a1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="321a1-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="321a1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="321a1-111">属性</span><span class="sxs-lookup"><span data-stu-id="321a1-111">Attributes</span></span>  
  
|<span data-ttu-id="321a1-112">属性</span><span class="sxs-lookup"><span data-stu-id="321a1-112">Attribute</span></span>|<span data-ttu-id="321a1-113">説明</span><span class="sxs-lookup"><span data-stu-id="321a1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="321a1-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="321a1-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="321a1-115">子要素</span><span class="sxs-lookup"><span data-stu-id="321a1-115">Child Elements</span></span>  
 <span data-ttu-id="321a1-116">なし。</span><span class="sxs-lookup"><span data-stu-id="321a1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="321a1-117">親要素</span><span class="sxs-lookup"><span data-stu-id="321a1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="321a1-118">要素</span><span class="sxs-lookup"><span data-stu-id="321a1-118">Element</span></span>|<span data-ttu-id="321a1-119">説明</span><span class="sxs-lookup"><span data-stu-id="321a1-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="321a1-120">\<動作 > の\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="321a1-120">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="321a1-121">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="321a1-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="321a1-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="321a1-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
