---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 6e3993e43aac746f380a30341fe4ebffcd257c5f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148517"
---
# \<workflowUnhandledException>

<span data-ttu-id="4eebe-101">ワークフロー サービス内で未処理の例外が発生した場合のアクションを指定するためのサービス動作。</span><span class="sxs-lookup"><span data-stu-id="4eebe-101">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**  
  
## <a name="syntax"></a><span data-ttu-id="4eebe-102">構文</span><span class="sxs-lookup"><span data-stu-id="4eebe-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4eebe-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4eebe-103">Attributes and Elements</span></span>  

 <span data-ttu-id="4eebe-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4eebe-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4eebe-105">属性</span><span class="sxs-lookup"><span data-stu-id="4eebe-105">Attributes</span></span>  
  
|<span data-ttu-id="4eebe-106">属性</span><span class="sxs-lookup"><span data-stu-id="4eebe-106">Attribute</span></span>|<span data-ttu-id="4eebe-107">説明</span><span class="sxs-lookup"><span data-stu-id="4eebe-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4eebe-108">action</span><span class="sxs-lookup"><span data-stu-id="4eebe-108">action</span></span>|<span data-ttu-id="4eebe-109">未処理の例外が発生した場合のアクションを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="4eebe-109">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="4eebe-110">この属性は <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction> 型です。</span><span class="sxs-lookup"><span data-stu-id="4eebe-110">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4eebe-111">子要素</span><span class="sxs-lookup"><span data-stu-id="4eebe-111">Child Elements</span></span>  

 <span data-ttu-id="4eebe-112">なし。</span><span class="sxs-lookup"><span data-stu-id="4eebe-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4eebe-113">親要素</span><span class="sxs-lookup"><span data-stu-id="4eebe-113">Parent Elements</span></span>  
  
|<span data-ttu-id="4eebe-114">要素</span><span class="sxs-lookup"><span data-stu-id="4eebe-114">Element</span></span>|<span data-ttu-id="4eebe-115">説明</span><span class="sxs-lookup"><span data-stu-id="4eebe-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4eebe-116">\<serviceBehaviors> の \<behavior></span><span class="sxs-lookup"><span data-stu-id="4eebe-116">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="4eebe-117">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="4eebe-117">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4eebe-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4eebe-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
