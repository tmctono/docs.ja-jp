---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: ab21be7b5e2738ac6a7c9bea676d8180c69d1afd
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968568"
---
# <a name="commonparameters"></a><span data-ttu-id="33098-101">commonParameters > の \<</span><span class="sxs-lookup"><span data-stu-id="33098-101">\<commonParameters></span></span>
<span data-ttu-id="33098-102">複数のサービスでグローバルに使用されるパラメーターのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="33098-102">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="33098-103">このコレクションには通常、永続性サービスによって共有されるデータベース接続文字列が格納されます。</span><span class="sxs-lookup"><span data-stu-id="33098-103">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
<span data-ttu-id="33098-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33098-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33098-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="33098-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="33098-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<の動作**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="33098-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="33098-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="33098-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="33098-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="33098-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="33098-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**workflowRuntime >** ](workflowruntime.md)</span><span class="sxs-lookup"><span data-stu-id="33098-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span></span>\
<span data-ttu-id="33098-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**commonParameters\<**</span><span class="sxs-lookup"><span data-stu-id="33098-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<commonParameters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33098-111">構文</span><span class="sxs-lookup"><span data-stu-id="33098-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33098-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="33098-112">Attributes and Elements</span></span>  
 <span data-ttu-id="33098-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="33098-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33098-114">属性</span><span class="sxs-lookup"><span data-stu-id="33098-114">Attributes</span></span>  
 <span data-ttu-id="33098-115">なし。</span><span class="sxs-lookup"><span data-stu-id="33098-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="33098-116">子要素</span><span class="sxs-lookup"><span data-stu-id="33098-116">Child Elements</span></span>  
  
|<span data-ttu-id="33098-117">要素</span><span class="sxs-lookup"><span data-stu-id="33098-117">Element</span></span>|<span data-ttu-id="33098-118">説明</span><span class="sxs-lookup"><span data-stu-id="33098-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33098-119">\<add></span><span class="sxs-lookup"><span data-stu-id="33098-119">\<add></span></span>](add-of-commonparameters.md)|<span data-ttu-id="33098-120">サービスによって使用される共通パラメーターの名前と値のペアをコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="33098-120">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33098-121">親要素</span><span class="sxs-lookup"><span data-stu-id="33098-121">Parent Elements</span></span>  
  
|<span data-ttu-id="33098-122">要素</span><span class="sxs-lookup"><span data-stu-id="33098-122">Element</span></span>|<span data-ttu-id="33098-123">説明</span><span class="sxs-lookup"><span data-stu-id="33098-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33098-124">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="33098-124">\<workflowRuntime></span></span>](workflowruntime.md)|<span data-ttu-id="33098-125">ワークフローベース Windows Communication Foundation (WCF) サービスをホストするための <xref:System.Workflow.Runtime.WorkflowRuntime> のインスタンスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="33098-125">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33098-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="33098-126">Remarks</span></span>  
 <span data-ttu-id="33098-127">最初の要素 `<commonParameters>` は、複数のサービスでグローバルに使用されるパラメーターを定義します (たとえば `ConnectionString` を使用する場合の <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>)。</span><span class="sxs-lookup"><span data-stu-id="33098-127">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33098-128">SQL 追跡サービスでは、`ConnectionString` セクションに `<commonParameters>` 値を指定しても、その値が常に使用されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="33098-128">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="33098-129">`StateMachineWorkflowInstance.StateHistory` プロパティの取得のように、操作によっては失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="33098-129">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="33098-130">これを回避するには、次の例に示すように、追跡プロバイダーの構成セクションで `ConnectionString` 属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="33098-130">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  

```xml  
<add
type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" 
ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />
```  
  
 <span data-ttu-id="33098-131"><xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> や <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService> など、作業バッチを永続的ストアにコミットするサービスでは、`EnableRetries` パラメーターを次の例のように使用することで、トランザクションの再試行を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="33098-131">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="33098-132">`EnableRetries` パラメーターは、 *Commonparameters*セクションに示すようにグローバルレベルで設定することも、`EnableRetries` をサポートする個々のサービス (「*サービス*」セクションを参照) で設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="33098-132">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="33098-133">次のサンプルコードは、一般的なパラメーターをプログラムで変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="33098-133">The following sample code shows how to change the common parameters programmatically:</span></span>
  
```csharp  
Configuration config = WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");
var wfruntime = config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters = wfruntime.CommonParameters;
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="33098-134">構成ファイルを使用して、Windows Workflow Foundation ホストアプリケーションの <xref:System.Workflow.Runtime.WorkflowRuntime> オブジェクトの動作を制御する方法の詳細については、「[ワークフロー構成ファイル](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33098-134">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="33098-135">例</span><span class="sxs-lookup"><span data-stu-id="33098-135">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="33098-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="33098-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="33098-137">[ワークフロー構成ファイル](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="33098-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="33098-138">\<add></span><span class="sxs-lookup"><span data-stu-id="33098-138">\<add></span></span>](add-of-commonparameters.md)
