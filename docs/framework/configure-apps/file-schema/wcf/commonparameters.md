---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: b9ab4e8ca5a71d54a80d17322b61c83d41af2b40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673590"
---
# <a name="commonparameters"></a><span data-ttu-id="9ab2a-101">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="9ab2a-101">\<commonParameters></span></span>
<span data-ttu-id="9ab2a-102">複数のサービスでグローバルに使用されるパラメーターのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="9ab2a-102">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="9ab2a-103">このコレクションには通常、永続性サービスによって共有されるデータベース接続文字列が格納されます。</span><span class="sxs-lookup"><span data-stu-id="9ab2a-103">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="9ab2a-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9ab2a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9ab2a-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="9ab2a-105">\<behaviors></span></span>  
<span data-ttu-id="9ab2a-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9ab2a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="9ab2a-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9ab2a-107">\<behavior></span></span>  
<span data-ttu-id="9ab2a-108">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="9ab2a-108">\<workflowRuntime></span></span>  
<span data-ttu-id="9ab2a-109">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="9ab2a-109">\<commonParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ab2a-110">構文</span><span class="sxs-lookup"><span data-stu-id="9ab2a-110">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ab2a-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9ab2a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9ab2a-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ab2a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ab2a-113">属性</span><span class="sxs-lookup"><span data-stu-id="9ab2a-113">Attributes</span></span>  
 <span data-ttu-id="9ab2a-114">なし。</span><span class="sxs-lookup"><span data-stu-id="9ab2a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9ab2a-115">子要素</span><span class="sxs-lookup"><span data-stu-id="9ab2a-115">Child Elements</span></span>  
  
|<span data-ttu-id="9ab2a-116">要素</span><span class="sxs-lookup"><span data-stu-id="9ab2a-116">Element</span></span>|<span data-ttu-id="9ab2a-117">説明</span><span class="sxs-lookup"><span data-stu-id="9ab2a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ab2a-118">\<add></span><span class="sxs-lookup"><span data-stu-id="9ab2a-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|<span data-ttu-id="9ab2a-119">サービスによって使用される共通パラメーターの名前と値のペアをコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="9ab2a-119">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ab2a-120">親要素</span><span class="sxs-lookup"><span data-stu-id="9ab2a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9ab2a-121">要素</span><span class="sxs-lookup"><span data-stu-id="9ab2a-121">Element</span></span>|<span data-ttu-id="9ab2a-122">説明</span><span class="sxs-lookup"><span data-stu-id="9ab2a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ab2a-123">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="9ab2a-123">\<workflowRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|<span data-ttu-id="9ab2a-124">インスタンスの設定を指定<xref:System.Workflow.Runtime.WorkflowRuntime>ワークフロー ベースの Windows Communication Foundation (WCF) サービスをホストするためです。</span><span class="sxs-lookup"><span data-stu-id="9ab2a-124">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ab2a-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="9ab2a-125">Remarks</span></span>  
 <span data-ttu-id="9ab2a-126">最初の要素 `<commonParameters>` は、複数のサービスでグローバルに使用されるパラメーターを定義します (たとえば `ConnectionString` を使用する場合の <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>)。</span><span class="sxs-lookup"><span data-stu-id="9ab2a-126">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ab2a-127">SQL 追跡サービスでは、`ConnectionString` セクションに `<commonParameters>` 値を指定しても、その値が常に使用されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="9ab2a-127">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="9ab2a-128">`StateMachineWorkflowInstance.StateHistory` プロパティの取得のように、操作によっては失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="9ab2a-128">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="9ab2a-129">これを回避するには、次の例に示すように、追跡プロバイダーの構成セクションで `ConnectionString` 属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ab2a-129">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="9ab2a-130"><xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> や <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService> など、作業バッチを永続的ストアにコミットするサービスでは、`EnableRetries` パラメーターを次の例のように使用することで、トランザクションの再試行を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="9ab2a-130">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<workflowRuntime name="SampleApplication"
                 unloadOnIdle="false">
  <commonParameters>
    <add name="ConnectionString"
         value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
    <add name="EnableRetries"
         value="True" />
  </commonParameters>
  <services>
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime,
               Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="9ab2a-131">注意して、`EnableRetries`グローバル レベルでパラメーターを設定することができます (ように、 *CommonParameters*セクション)、または個々 のサービスをサポートする`EnableRetries`(ように、*サービス*セクション)。</span><span class="sxs-lookup"><span data-stu-id="9ab2a-131">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="9ab2a-132">共通パラメーターをプログラムによって変更する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="9ab2a-132">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="9ab2a-133">動作を制御する構成ファイルの使用の詳細については、<xref:System.Workflow.Runtime.WorkflowRuntime>オブジェクトの Windows Workflow Foundation ホスト アプリケーションでは、次を参照してください。[ワークフロー構成ファイル](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))します。</span><span class="sxs-lookup"><span data-stu-id="9ab2a-133">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ab2a-134">例</span><span class="sxs-lookup"><span data-stu-id="9ab2a-134">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="9ab2a-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ab2a-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="9ab2a-136">[ワークフロー構成ファイル](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9ab2a-136">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="9ab2a-137">\<add></span><span class="sxs-lookup"><span data-stu-id="9ab2a-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)
