---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: aa2edafd9adc0317ed0023ad46688025dcecad67
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397523"
---
# \<workflowInstanceManagement>
<span data-ttu-id="1cd8b-101">ワークフロー インスタンスの実行方法を制御する設定を指定するためのサービス動作。これには、永続する未処理の例外動作やアイドル状態の動作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1cd8b-101">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**  
  
## <a name="syntax"></a><span data-ttu-id="1cd8b-102">構文</span><span class="sxs-lookup"><span data-stu-id="1cd8b-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1cd8b-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1cd8b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1cd8b-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1cd8b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1cd8b-105">属性</span><span class="sxs-lookup"><span data-stu-id="1cd8b-105">Attributes</span></span>  
  
|<span data-ttu-id="1cd8b-106">属性</span><span class="sxs-lookup"><span data-stu-id="1cd8b-106">Attribute</span></span>|<span data-ttu-id="1cd8b-107">説明</span><span class="sxs-lookup"><span data-stu-id="1cd8b-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1cd8b-108">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="1cd8b-108">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="1cd8b-109">子要素</span><span class="sxs-lookup"><span data-stu-id="1cd8b-109">Child Elements</span></span>  
 <span data-ttu-id="1cd8b-110">なし。</span><span class="sxs-lookup"><span data-stu-id="1cd8b-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1cd8b-111">親要素</span><span class="sxs-lookup"><span data-stu-id="1cd8b-111">Parent Elements</span></span>  
  
|<span data-ttu-id="1cd8b-112">要素</span><span class="sxs-lookup"><span data-stu-id="1cd8b-112">Element</span></span>|<span data-ttu-id="1cd8b-113">Description</span><span class="sxs-lookup"><span data-stu-id="1cd8b-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cd8b-114">\<behavior>の\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1cd8b-114">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="1cd8b-115">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="1cd8b-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1cd8b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1cd8b-116">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
