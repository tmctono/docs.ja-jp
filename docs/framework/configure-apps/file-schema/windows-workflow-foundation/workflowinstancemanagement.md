---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 532d4c31a582b2b0cd90f6f42b20e00790f9ab02
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148660"
---
# \<workflowInstanceManagement>

<span data-ttu-id="89c46-101">ワークフロー インスタンスの実行方法を制御する設定を指定するためのサービス動作。これには、永続する未処理の例外動作やアイドル状態の動作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="89c46-101">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**  
  
## <a name="syntax"></a><span data-ttu-id="89c46-102">構文</span><span class="sxs-lookup"><span data-stu-id="89c46-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89c46-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="89c46-103">Attributes and Elements</span></span>  

 <span data-ttu-id="89c46-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="89c46-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89c46-105">属性</span><span class="sxs-lookup"><span data-stu-id="89c46-105">Attributes</span></span>  
  
|<span data-ttu-id="89c46-106">属性</span><span class="sxs-lookup"><span data-stu-id="89c46-106">Attribute</span></span>|<span data-ttu-id="89c46-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="89c46-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89c46-108">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="89c46-108">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="89c46-109">子要素</span><span class="sxs-lookup"><span data-stu-id="89c46-109">Child Elements</span></span>  

 <span data-ttu-id="89c46-110">なし。</span><span class="sxs-lookup"><span data-stu-id="89c46-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89c46-111">親要素</span><span class="sxs-lookup"><span data-stu-id="89c46-111">Parent Elements</span></span>  
  
|<span data-ttu-id="89c46-112">要素</span><span class="sxs-lookup"><span data-stu-id="89c46-112">Element</span></span>|<span data-ttu-id="89c46-113">説明</span><span class="sxs-lookup"><span data-stu-id="89c46-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89c46-114">\<serviceBehaviors> の \<behavior></span><span class="sxs-lookup"><span data-stu-id="89c46-114">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="89c46-115">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="89c46-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89c46-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="89c46-116">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
