---
title: <add> の <services>
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 31a4d2a5a3baf3d53cf18ab6e37edfaf7acb8540
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204984"
---
# <a name="add-of-services"></a><span data-ttu-id="3e3e1-102">\<add> の \<services></span><span class="sxs-lookup"><span data-stu-id="3e3e1-102">\<add> of \<services></span></span>

<span data-ttu-id="3e3e1-103"><xref:System.Workflow.Runtime.WorkflowRuntime>ワークフローベースの Windows Communication Foundation (WCF) サービスをホストするためののインスタンスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="3e3e1-104">この要素は <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services-of-workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="3e3e1-105">構文</span><span class="sxs-lookup"><span data-stu-id="3e3e1-105">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e3e1-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3e3e1-106">Attributes and Elements</span></span>  

 <span data-ttu-id="3e3e1-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e3e1-108">属性</span><span class="sxs-lookup"><span data-stu-id="3e3e1-108">Attributes</span></span>  
  
|<span data-ttu-id="3e3e1-109">属性</span><span class="sxs-lookup"><span data-stu-id="3e3e1-109">Attribute</span></span>|<span data-ttu-id="3e3e1-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="3e3e1-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e3e1-111">type</span><span class="sxs-lookup"><span data-stu-id="3e3e1-111">type</span></span>|<span data-ttu-id="3e3e1-112">初期化するサービスのアセンブリ修飾型名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-112">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="3e3e1-113">指定されたサービスは、そのコンストラクターのシグネチャに関して一定の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-113">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="3e3e1-114">詳細については、「 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-114">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e3e1-115">子要素</span><span class="sxs-lookup"><span data-stu-id="3e3e1-115">Child Elements</span></span>  

 <span data-ttu-id="3e3e1-116">なし。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e3e1-117">親要素</span><span class="sxs-lookup"><span data-stu-id="3e3e1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3e3e1-118">要素</span><span class="sxs-lookup"><span data-stu-id="3e3e1-118">Element</span></span>|<span data-ttu-id="3e3e1-119">説明</span><span class="sxs-lookup"><span data-stu-id="3e3e1-119">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services-of-workflowruntime.md)|<span data-ttu-id="3e3e1-120"><xref:System.Workflow.Runtime.WorkflowRuntime> エンジンに追加されるサービスのコレクション。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-120">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="3e3e1-121">要素は、<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-121">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="3e3e1-122">コレクションで指定されたサービスはワークフロー ランタイム エンジンによって初期化され、適切な <xref:System.Workflow.Runtime.WorkflowRuntime> コンストラクターが呼び出されるとワークフロー ランタイム エンジンのサービスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-122">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="3e3e1-123">したがって、コレクションで指定されたサービスは、そのコンストラクターのシグネチャに関して一定の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-123">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="3e3e1-124">詳細については、「 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-124">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e3e1-125">解説</span><span class="sxs-lookup"><span data-stu-id="3e3e1-125">Remarks</span></span>  

 <span data-ttu-id="3e3e1-126">この要素で指定されたサービスはワークフロー ランタイム エンジンによって初期化され、適切な <xref:System.Workflow.Runtime.WorkflowRuntime> コンストラクターが呼び出されるとワークフロー ランタイム エンジンのサービスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-126">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="3e3e1-127">したがって、指定されたサービスは、そのコンストラクターのシグネチャに関して一定の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-127">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="3e3e1-128">詳細については、「 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e3e1-128">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e3e1-129">例</span><span class="sxs-lookup"><span data-stu-id="3e3e1-129">Example</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="ServiceBehavior">
    <workflowRuntime name="WorkflowServiceHostRuntime"
                     validateOnCreate="true"
                     enablePerformanceCounters="true">
      <services>
        <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common" />
      </services>
    </workflowRuntime>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="3e3e1-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e3e1-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="3e3e1-131">[ワークフロー構成ファイル](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3e3e1-131">[Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
