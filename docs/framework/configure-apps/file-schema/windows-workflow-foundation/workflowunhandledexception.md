---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 29b6d8982e712a0fa595b3103803f1795adea892
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398560"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="96386-101">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="96386-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="96386-102">ワークフロー サービス内で未処理の例外が発生した場合のアクションを指定するためのサービス動作。</span><span class="sxs-lookup"><span data-stu-id="96386-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="96386-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="96386-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="96386-104">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="96386-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="96386-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="96386-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="96386-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="96386-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="96386-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="96386-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="96386-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowUnhandledException >**</span><span class="sxs-lookup"><span data-stu-id="96386-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96386-109">構文</span><span class="sxs-lookup"><span data-stu-id="96386-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96386-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="96386-110">Attributes and Elements</span></span>  
 <span data-ttu-id="96386-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="96386-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96386-112">属性</span><span class="sxs-lookup"><span data-stu-id="96386-112">Attributes</span></span>  
  
|<span data-ttu-id="96386-113">属性</span><span class="sxs-lookup"><span data-stu-id="96386-113">Attribute</span></span>|<span data-ttu-id="96386-114">説明</span><span class="sxs-lookup"><span data-stu-id="96386-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="96386-115">アクション (action)</span><span class="sxs-lookup"><span data-stu-id="96386-115">action</span></span>|<span data-ttu-id="96386-116">未処理の例外が発生した場合のアクションを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="96386-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="96386-117">この属性は <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction> 型です。</span><span class="sxs-lookup"><span data-stu-id="96386-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96386-118">子要素</span><span class="sxs-lookup"><span data-stu-id="96386-118">Child Elements</span></span>  
 <span data-ttu-id="96386-119">なし。</span><span class="sxs-lookup"><span data-stu-id="96386-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96386-120">親要素</span><span class="sxs-lookup"><span data-stu-id="96386-120">Parent Elements</span></span>  
  
|<span data-ttu-id="96386-121">要素</span><span class="sxs-lookup"><span data-stu-id="96386-121">Element</span></span>|<span data-ttu-id="96386-122">説明</span><span class="sxs-lookup"><span data-stu-id="96386-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96386-123">\<servicebehaviors の\<動作 > ></span><span class="sxs-lookup"><span data-stu-id="96386-123">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="96386-124">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="96386-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96386-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="96386-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
