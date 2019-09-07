---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: aa2edafd9adc0317ed0023ad46688025dcecad67
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397523"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="e12e0-101">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="e12e0-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="e12e0-102">ワークフロー インスタンスの実行方法を制御する設定を指定するためのサービス動作。これには、永続する未処理の例外動作やアイドル状態の動作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e12e0-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="e12e0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e12e0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e12e0-104">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e12e0-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="e12e0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e12e0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="e12e0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e12e0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="e12e0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e12e0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="e12e0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowInstanceManagement >**</span><span class="sxs-lookup"><span data-stu-id="e12e0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e12e0-109">構文</span><span class="sxs-lookup"><span data-stu-id="e12e0-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e12e0-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e12e0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e12e0-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e12e0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e12e0-112">属性</span><span class="sxs-lookup"><span data-stu-id="e12e0-112">Attributes</span></span>  
  
|<span data-ttu-id="e12e0-113">属性</span><span class="sxs-lookup"><span data-stu-id="e12e0-113">Attribute</span></span>|<span data-ttu-id="e12e0-114">説明</span><span class="sxs-lookup"><span data-stu-id="e12e0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e12e0-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="e12e0-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="e12e0-116">子要素</span><span class="sxs-lookup"><span data-stu-id="e12e0-116">Child Elements</span></span>  
 <span data-ttu-id="e12e0-117">なし。</span><span class="sxs-lookup"><span data-stu-id="e12e0-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e12e0-118">親要素</span><span class="sxs-lookup"><span data-stu-id="e12e0-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e12e0-119">要素</span><span class="sxs-lookup"><span data-stu-id="e12e0-119">Element</span></span>|<span data-ttu-id="e12e0-120">説明</span><span class="sxs-lookup"><span data-stu-id="e12e0-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e12e0-121">\<servicebehaviors の\<動作 > ></span><span class="sxs-lookup"><span data-stu-id="e12e0-121">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="e12e0-122">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="e12e0-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e12e0-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="e12e0-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
