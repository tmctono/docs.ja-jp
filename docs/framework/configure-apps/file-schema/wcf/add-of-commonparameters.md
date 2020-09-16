---
title: <add> の <commonParameters>
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: 8328b6d08c1b57ad7a899c8cb489e07037e5af09
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558162"
---
# <a name="add-of-commonparameters"></a><span data-ttu-id="16e32-102">\<add> の \<commonParameters></span><span class="sxs-lookup"><span data-stu-id="16e32-102">\<add> of \<commonParameters></span></span>
<span data-ttu-id="16e32-103">複数のサービスでグローバルに使用されるパラメーターの名前と値のペアを指定します。</span><span class="sxs-lookup"><span data-stu-id="16e32-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="16e32-104">このパラメーターには通常、永続性サービスによって共有されるデータベース接続文字列が格納されます。</span><span class="sxs-lookup"><span data-stu-id="16e32-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<commonParameters>**](commonparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="16e32-105">構文</span><span class="sxs-lookup"><span data-stu-id="16e32-105">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16e32-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="16e32-106">Attributes and Elements</span></span>  
 <span data-ttu-id="16e32-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="16e32-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16e32-108">属性</span><span class="sxs-lookup"><span data-stu-id="16e32-108">Attributes</span></span>  
  
|<span data-ttu-id="16e32-109">属性</span><span class="sxs-lookup"><span data-stu-id="16e32-109">Attribute</span></span>|<span data-ttu-id="16e32-110">説明</span><span class="sxs-lookup"><span data-stu-id="16e32-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="16e32-111">name</span><span class="sxs-lookup"><span data-stu-id="16e32-111">name</span></span>|<span data-ttu-id="16e32-112">サービスに対して指定されたパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="16e32-112">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="16e32-113">値</span><span class="sxs-lookup"><span data-stu-id="16e32-113">value</span></span>|<span data-ttu-id="16e32-114">サービスに対して指定されたパラメーターの値。</span><span class="sxs-lookup"><span data-stu-id="16e32-114">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16e32-115">子要素</span><span class="sxs-lookup"><span data-stu-id="16e32-115">Child Elements</span></span>  
 <span data-ttu-id="16e32-116">なし。</span><span class="sxs-lookup"><span data-stu-id="16e32-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16e32-117">親要素</span><span class="sxs-lookup"><span data-stu-id="16e32-117">Parent Elements</span></span>  
  
|<span data-ttu-id="16e32-118">要素</span><span class="sxs-lookup"><span data-stu-id="16e32-118">Element</span></span>|<span data-ttu-id="16e32-119">説明</span><span class="sxs-lookup"><span data-stu-id="16e32-119">Description</span></span>|  
|-------------|-----------------|  
|[\<commonParameters>](commonparameters.md)|<span data-ttu-id="16e32-120">サービスによって使用される共通パラメーターのコレクション。</span><span class="sxs-lookup"><span data-stu-id="16e32-120">A collection of common parameters used by services.</span></span> <span data-ttu-id="16e32-121">このコレクションには通常、永続性サービスによって共有されるデータベース接続文字列が格納されます。</span><span class="sxs-lookup"><span data-stu-id="16e32-121">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16e32-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="16e32-122">Remarks</span></span>  
 <span data-ttu-id="16e32-123">最初の要素 `<commonParameters>` は、複数のサービスでグローバルに使用されるパラメーターを定義します (たとえば `ConnectionString` を使用する場合の <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>)。</span><span class="sxs-lookup"><span data-stu-id="16e32-123">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="16e32-124"><xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> や <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService> など、作業バッチを永続的ストアにコミットするサービスでは、`EnableRetries` パラメーターを次の例のように使用することで、トランザクションの再試行を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="16e32-124">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="16e32-125">パラメーターは、 `EnableRetries` *commonparameters* セクションに示されているようにグローバルレベルで設定するか `EnableRetries` 、( *サービス* セクションに示すように) をサポートする個々のサービスに対して設定できます。</span><span class="sxs-lookup"><span data-stu-id="16e32-125">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="16e32-126">構成ファイルを使用して Windows Workflow Foundation ホストアプリケーションのオブジェクトの動作を制御する方法の詳細につい <xref:System.Workflow.Runtime.WorkflowRuntime> ては、「 [ワークフロー構成ファイル](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16e32-126">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="16e32-127">例</span><span class="sxs-lookup"><span data-stu-id="16e32-127">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="16e32-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="16e32-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="16e32-129">[ワークフロー構成ファイル](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="16e32-129">[Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [\<commonParameters>](commonparameters.md)
