---
title: <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: 4a450fb6f02bbf0f1681f7b2fabea9da7b65cbea
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183599"
---
# \<workflowRuntime>

<span data-ttu-id="59894-101"><xref:System.Workflow.Runtime.WorkflowRuntime>ワークフローベースの Windows Communication Foundation (WCF) サービスをホストするためののインスタンスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="59894-101">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowRuntime>**  
  
## <a name="syntax"></a><span data-ttu-id="59894-102">構文</span><span class="sxs-lookup"><span data-stu-id="59894-102">Syntax</span></span>  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"
                 enablePerformanceCounters="Boolean"
                 name="String"
                 validateOnCreate="Boolean">
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59894-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="59894-103">Attributes and Elements</span></span>  

 <span data-ttu-id="59894-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="59894-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59894-105">属性</span><span class="sxs-lookup"><span data-stu-id="59894-105">Attributes</span></span>  
  
|<span data-ttu-id="59894-106">属性</span><span class="sxs-lookup"><span data-stu-id="59894-106">Attribute</span></span>|<span data-ttu-id="59894-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="59894-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59894-108">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="59894-108">cachedInstanceExpiration</span></span>|<span data-ttu-id="59894-109">ワークフロー インスタンスが強制的にアンロードまたは中止される前に、アイドル状態でメモリに残ることができる最大期間を指定する、省略可能な <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="59894-109">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="59894-110">unloadOnIdle を実行する `PersistenceService` が workflowruntime に設定されている場合、この属性は無視されます。</span><span class="sxs-lookup"><span data-stu-id="59894-110">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="59894-111">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="59894-111">enablePerformanceCounters</span></span>|<span data-ttu-id="59894-112">パフォーマンス カウンターが有効であるかどうかを指定する省略可能なブール値。</span><span class="sxs-lookup"><span data-stu-id="59894-112">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="59894-113">パフォーマンス カウンターは、ワークフローに関連したさまざまな統計情報を提供します。ただしそのために、ワークフロー ランタイム エンジンが起動してワークフロー インスタンスが実行されている間は、パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="59894-113">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="59894-114">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="59894-114">The default value is `true`.</span></span>|  
|<span data-ttu-id="59894-115">name</span><span class="sxs-lookup"><span data-stu-id="59894-115">name</span></span>|<span data-ttu-id="59894-116">ワークフロー ランタイム エンジンの名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="59894-116">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="59894-117">名前は出力で使用され、このランタイムを、システムで実行されている他のランタイム (パフォーマンス カウンターなど) と区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="59894-117">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="59894-118">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="59894-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="59894-119">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="59894-119">validateOnCreate</span></span>|<span data-ttu-id="59894-120">WorkflowServiceHost を開いたときにワークフロー定義の検証を行うかどうかを指定する省略可能なブール値。</span><span class="sxs-lookup"><span data-stu-id="59894-120">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="59894-121">この属性が `true` に設定されているときは、`WorkflowServiceHost.Open` が呼び出されるたびにワークフローの検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="59894-121">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="59894-122">検証エラーが見つかった場合は、<xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="59894-122">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="59894-123">このプロパティが `false` に設定されている場合、ワークフロー定義の検証は行われません。</span><span class="sxs-lookup"><span data-stu-id="59894-123">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="59894-124">このプロパティの既定値は、`true` です。</span><span class="sxs-lookup"><span data-stu-id="59894-124">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59894-125">子要素</span><span class="sxs-lookup"><span data-stu-id="59894-125">Child Elements</span></span>  
  
|<span data-ttu-id="59894-126">要素</span><span class="sxs-lookup"><span data-stu-id="59894-126">Element</span></span>|<span data-ttu-id="59894-127">説明</span><span class="sxs-lookup"><span data-stu-id="59894-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59894-128">commonParameters</span><span class="sxs-lookup"><span data-stu-id="59894-128">commonParameters</span></span>|<span data-ttu-id="59894-129">サービスによって使用される共通パラメーターのコレクション。</span><span class="sxs-lookup"><span data-stu-id="59894-129">A collection of common parameters used by services.</span></span> <span data-ttu-id="59894-130">このコレクションには通常、永続性サービスによって共有されるデータベース接続文字列が格納されます。</span><span class="sxs-lookup"><span data-stu-id="59894-130">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="59894-131">services</span><span class="sxs-lookup"><span data-stu-id="59894-131">services</span></span>|<span data-ttu-id="59894-132"><xref:System.Workflow.Runtime.WorkflowRuntime> エンジンに追加されるサービスのコレクション。</span><span class="sxs-lookup"><span data-stu-id="59894-132">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="59894-133">要素は、<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="59894-133">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="59894-134">コレクションで指定されたサービスはワークフロー ランタイム エンジンによって初期化され、適切な <xref:System.Workflow.Runtime.WorkflowRuntime> コンストラクターが呼び出されるとワークフロー ランタイム エンジンのサービスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="59894-134">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="59894-135">したがって、コレクションで指定されたサービスは、そのコンストラクターのシグネチャに関して一定の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="59894-135">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="59894-136">詳細については、「 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59894-136">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59894-137">親要素</span><span class="sxs-lookup"><span data-stu-id="59894-137">Parent Elements</span></span>  
  
|<span data-ttu-id="59894-138">要素</span><span class="sxs-lookup"><span data-stu-id="59894-138">Element</span></span>|<span data-ttu-id="59894-139">説明</span><span class="sxs-lookup"><span data-stu-id="59894-139">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="59894-140">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="59894-140">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59894-141">解説</span><span class="sxs-lookup"><span data-stu-id="59894-141">Remarks</span></span>  

 <span data-ttu-id="59894-142">構成ファイルを使用して Windows Workflow Foundation ホストアプリケーションのオブジェクトの動作を制御する方法の詳細につい <xref:System.Workflow.Runtime.WorkflowRuntime> ては、「 [ワークフロー構成ファイル](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59894-142">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59894-143">例</span><span class="sxs-lookup"><span data-stu-id="59894-143">Example</span></span>  
  
```xml  
<serviceBehaviors>
   <behavior name="ServiceBehavior">
      <workflowRuntime name="WorkflowServiceHostRuntime"
                       validateOnCreate="true"
                       enablePerformanceCounters="true">
         <commonParameters>
            <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
            <add name="EnableRetries" value="True" />
         </commonParameters>
         <services>
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>
         </services>
      </workflowRuntime>
   </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="59894-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="59894-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="59894-145">[ワークフロー構成ファイル](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="59894-145">[Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
