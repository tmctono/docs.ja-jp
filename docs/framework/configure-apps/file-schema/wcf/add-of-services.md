---
title: <add> の <services>
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 26d43460f225cb57946aca80e3d1e3fde2ea1100
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557711"
---
# <a name="add-of-services"></a><span data-ttu-id="84fc8-102">\<add> の \<services></span><span class="sxs-lookup"><span data-stu-id="84fc8-102">\<add> of \<services></span></span>
<span data-ttu-id="84fc8-103"><xref:System.Workflow.Runtime.WorkflowRuntime>ワークフローベースの Windows Communication Foundation (WCF) サービスをホストするためののインスタンスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="84fc8-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="84fc8-104">この要素は <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="84fc8-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services-of-workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="84fc8-105">構文</span><span class="sxs-lookup"><span data-stu-id="84fc8-105">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84fc8-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="84fc8-106">Attributes and Elements</span></span>  
 <span data-ttu-id="84fc8-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="84fc8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84fc8-108">属性</span><span class="sxs-lookup"><span data-stu-id="84fc8-108">Attributes</span></span>  
  
|<span data-ttu-id="84fc8-109">属性</span><span class="sxs-lookup"><span data-stu-id="84fc8-109">Attribute</span></span>|<span data-ttu-id="84fc8-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="84fc8-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="84fc8-111">type</span><span class="sxs-lookup"><span data-stu-id="84fc8-111">type</span></span>|<span data-ttu-id="84fc8-112">初期化するサービスのアセンブリ修飾型名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="84fc8-112">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="84fc8-113">指定されたサービスは、そのコンストラクターのシグネチャに関して一定の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="84fc8-113">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="84fc8-114">詳細については、「<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84fc8-114">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84fc8-115">子要素</span><span class="sxs-lookup"><span data-stu-id="84fc8-115">Child Elements</span></span>  
 <span data-ttu-id="84fc8-116">なし。</span><span class="sxs-lookup"><span data-stu-id="84fc8-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="84fc8-117">親要素</span><span class="sxs-lookup"><span data-stu-id="84fc8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="84fc8-118">要素</span><span class="sxs-lookup"><span data-stu-id="84fc8-118">Element</span></span>|<span data-ttu-id="84fc8-119">説明</span><span class="sxs-lookup"><span data-stu-id="84fc8-119">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services-of-workflowruntime.md)|<span data-ttu-id="84fc8-120"><xref:System.Workflow.Runtime.WorkflowRuntime> エンジンに追加されるサービスのコレクション。</span><span class="sxs-lookup"><span data-stu-id="84fc8-120">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="84fc8-121">要素は、<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="84fc8-121">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="84fc8-122">コレクションで指定されたサービスはワークフロー ランタイム エンジンによって初期化され、適切な <xref:System.Workflow.Runtime.WorkflowRuntime> コンストラクターが呼び出されるとワークフロー ランタイム エンジンのサービスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="84fc8-122">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="84fc8-123">したがって、コレクションで指定されたサービスは、そのコンストラクターのシグネチャに関して一定の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="84fc8-123">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="84fc8-124">詳細については、「<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84fc8-124">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84fc8-125">注釈</span><span class="sxs-lookup"><span data-stu-id="84fc8-125">Remarks</span></span>  
 <span data-ttu-id="84fc8-126">この要素で指定されたサービスはワークフロー ランタイム エンジンによって初期化され、適切な <xref:System.Workflow.Runtime.WorkflowRuntime> コンストラクターが呼び出されるとワークフロー ランタイム エンジンのサービスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="84fc8-126">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="84fc8-127">したがって、指定されたサービスは、そのコンストラクターのシグネチャに関して一定の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="84fc8-127">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="84fc8-128">詳細については、「<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84fc8-128">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84fc8-129">例</span><span class="sxs-lookup"><span data-stu-id="84fc8-129">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="84fc8-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="84fc8-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="84fc8-131">[ワークフロー構成ファイル](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="84fc8-131">[Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
