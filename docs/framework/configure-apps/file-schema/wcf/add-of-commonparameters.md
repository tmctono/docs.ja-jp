---
title: <add> の <commonParameters>
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: d682acd7fff6bab2c66660a028f8a75b780e21d2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400675"
---
# <a name="add-of-commonparameters"></a><span data-ttu-id="08dd6-102">\<add> of \<commonParameters></span><span class="sxs-lookup"><span data-stu-id="08dd6-102">\<add> of \<commonParameters></span></span>
<span data-ttu-id="08dd6-103">複数のサービスでグローバルに使用されるパラメーターの名前と値のペアを指定します。</span><span class="sxs-lookup"><span data-stu-id="08dd6-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="08dd6-104">このパラメーターには通常、永続性サービスによって共有されるデータベース接続文字列が格納されます。</span><span class="sxs-lookup"><span data-stu-id="08dd6-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
<span data-ttu-id="08dd6-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="08dd6-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="08dd6-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="08dd6-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="08dd6-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="08dd6-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="08dd6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="08dd6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="08dd6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="08dd6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="08dd6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowRuntime >** ](workflowruntime.md)</span><span class="sxs-lookup"><span data-stu-id="08dd6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span></span>\
<span data-ttu-id="08dd6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<commonParameters >** ](commonparameters.md)</span><span class="sxs-lookup"><span data-stu-id="08dd6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<commonParameters>**](commonparameters.md)</span></span>\
<span data-ttu-id="08dd6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="08dd6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08dd6-113">構文</span><span class="sxs-lookup"><span data-stu-id="08dd6-113">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08dd6-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="08dd6-114">Attributes and Elements</span></span>  
 <span data-ttu-id="08dd6-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="08dd6-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08dd6-116">属性</span><span class="sxs-lookup"><span data-stu-id="08dd6-116">Attributes</span></span>  
  
|<span data-ttu-id="08dd6-117">属性</span><span class="sxs-lookup"><span data-stu-id="08dd6-117">Attribute</span></span>|<span data-ttu-id="08dd6-118">説明</span><span class="sxs-lookup"><span data-stu-id="08dd6-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="08dd6-119">name</span><span class="sxs-lookup"><span data-stu-id="08dd6-119">name</span></span>|<span data-ttu-id="08dd6-120">サービスに対して指定されたパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="08dd6-120">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="08dd6-121">value</span><span class="sxs-lookup"><span data-stu-id="08dd6-121">value</span></span>|<span data-ttu-id="08dd6-122">サービスに対して指定されたパラメーターの値。</span><span class="sxs-lookup"><span data-stu-id="08dd6-122">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08dd6-123">子要素</span><span class="sxs-lookup"><span data-stu-id="08dd6-123">Child Elements</span></span>  
 <span data-ttu-id="08dd6-124">なし。</span><span class="sxs-lookup"><span data-stu-id="08dd6-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08dd6-125">親要素</span><span class="sxs-lookup"><span data-stu-id="08dd6-125">Parent Elements</span></span>  
  
|<span data-ttu-id="08dd6-126">要素</span><span class="sxs-lookup"><span data-stu-id="08dd6-126">Element</span></span>|<span data-ttu-id="08dd6-127">説明</span><span class="sxs-lookup"><span data-stu-id="08dd6-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08dd6-128">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="08dd6-128">\<commonParameters></span></span>](commonparameters.md)|<span data-ttu-id="08dd6-129">サービスによって使用される共通パラメーターのコレクション。</span><span class="sxs-lookup"><span data-stu-id="08dd6-129">A collection of common parameters used by services.</span></span> <span data-ttu-id="08dd6-130">このコレクションには通常、永続性サービスによって共有されるデータベース接続文字列が格納されます。</span><span class="sxs-lookup"><span data-stu-id="08dd6-130">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08dd6-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="08dd6-131">Remarks</span></span>  
 <span data-ttu-id="08dd6-132">最初の要素 `<commonParameters>` は、複数のサービスでグローバルに使用されるパラメーターを定義します (たとえば `ConnectionString` を使用する場合の <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>)。</span><span class="sxs-lookup"><span data-stu-id="08dd6-132">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="08dd6-133"><xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> や <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService> など、作業バッチを永続的ストアにコミットするサービスでは、`EnableRetries` パラメーターを次の例のように使用することで、トランザクションの再試行を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="08dd6-133">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="08dd6-134">パラメーターは`EnableRetries` 、 *commonparameters*セクションに示されているようにグローバルレベルで設定するか、(*サービス*セクションに示すように`EnableRetries` ) をサポートする個々のサービスに対して設定できます。</span><span class="sxs-lookup"><span data-stu-id="08dd6-134">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="08dd6-135">構成ファイルを使用して Windows Workflow Foundation ホストアプリケーションの<xref:System.Workflow.Runtime.WorkflowRuntime>オブジェクトの動作を制御する方法の詳細については、「[ワークフロー構成ファイル](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08dd6-135">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="08dd6-136">例</span><span class="sxs-lookup"><span data-stu-id="08dd6-136">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="08dd6-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="08dd6-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="08dd6-138">[ワークフロー構成ファイル](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="08dd6-138">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="08dd6-139">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="08dd6-139">\<commonParameters></span></span>](commonparameters.md)
