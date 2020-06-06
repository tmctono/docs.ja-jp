---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 29b6d8982e712a0fa595b3103803f1795adea892
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398560"
---
# \<workflowUnhandledException>
<span data-ttu-id="ecc6f-101">ワークフロー サービス内で未処理の例外が発生した場合のアクションを指定するためのサービス動作。</span><span class="sxs-lookup"><span data-stu-id="ecc6f-101">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**  
  
## <a name="syntax"></a><span data-ttu-id="ecc6f-102">構文</span><span class="sxs-lookup"><span data-stu-id="ecc6f-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ecc6f-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ecc6f-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ecc6f-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ecc6f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ecc6f-105">属性</span><span class="sxs-lookup"><span data-stu-id="ecc6f-105">Attributes</span></span>  
  
|<span data-ttu-id="ecc6f-106">属性</span><span class="sxs-lookup"><span data-stu-id="ecc6f-106">Attribute</span></span>|<span data-ttu-id="ecc6f-107">説明</span><span class="sxs-lookup"><span data-stu-id="ecc6f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ecc6f-108">action</span><span class="sxs-lookup"><span data-stu-id="ecc6f-108">action</span></span>|<span data-ttu-id="ecc6f-109">未処理の例外が発生した場合のアクションを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="ecc6f-109">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="ecc6f-110">この属性は <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction> 型です。</span><span class="sxs-lookup"><span data-stu-id="ecc6f-110">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ecc6f-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ecc6f-111">Child Elements</span></span>  
 <span data-ttu-id="ecc6f-112">なし。</span><span class="sxs-lookup"><span data-stu-id="ecc6f-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ecc6f-113">親要素</span><span class="sxs-lookup"><span data-stu-id="ecc6f-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ecc6f-114">要素</span><span class="sxs-lookup"><span data-stu-id="ecc6f-114">Element</span></span>|<span data-ttu-id="ecc6f-115">Description</span><span class="sxs-lookup"><span data-stu-id="ecc6f-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ecc6f-116">\<behavior>の\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ecc6f-116">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="ecc6f-117">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="ecc6f-117">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ecc6f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ecc6f-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
