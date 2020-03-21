---
title: WorkflowServiceHost を使用して永続性を構成する方法
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 2974b6bcbb94c5b54d91025aeabe7c2d2e94c7e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185053"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a><span data-ttu-id="c2bf1-102">WorkflowServiceHost を使用して永続性を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c2bf1-102">How to: Configure Persistence with WorkflowServiceHost</span></span>
<span data-ttu-id="c2bf1-103">このトピックでは、構成ファイルを使用して、<xref:System.ServiceModel.Activities.WorkflowServiceHost> でホストされるワークフローに対して永続化を有効にするように、SQL Workflow Instance Store の機能を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-103">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for workflows hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> by using a configuration file.</span></span> <span data-ttu-id="c2bf1-104">SQL Workflow Instance Store 機能を使用する前に、ワークフロー インスタンスの永続化に使用する SQL データベースを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-104">Before using the SQL Workflow Instance Store feature you must create a SQL database that is used to persist workflow instances.</span></span> <span data-ttu-id="c2bf1-105">詳細については、「[方法 : ワークフローおよびワークフロー サービスの SQL 永続化を有効にする](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-105">For more information, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a><span data-ttu-id="c2bf1-106">構成において SQL Workflow Instance Store を構成するには</span><span class="sxs-lookup"><span data-stu-id="c2bf1-106">To Configure the SQL Workflow Instance Store in Configuration</span></span>  
  
1. <span data-ttu-id="c2bf1-107">SQL Workflow Instance Store のプロパティは、<xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> を使用して構成できます。これは、XML 構成で設定を変更するために使用できるサービス動作です。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-107">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through XML configuration.</span></span> <span data-ttu-id="c2bf1-108">次の構成例は、構成ファイル内の<>`sqlWorkflowInstanceStore`動作要素を使用して SQL ワークフロー インスタンス ストアを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-108">The following configuration example shows how to configure the SQL workflow instance store by using the <`sqlWorkflowInstanceStore`> behavior element in a configuration file.</span></span>  
  
    ```xml  
    <serviceBehaviors>  
        <behavior name="">  
            <sqlWorkflowInstanceStore
                 connectionString="provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"  
                 instanceEncodingOption="GZip | None"  
                 instanceCompletionAction="DeleteAll | DeleteNothing"  
                 instanceLockedExceptionAction="NoRetry | SimpleRetry | AggressiveRetry"  
                 hostLockRenewalPeriod="00:00:30"
                 runnableInstancesDetectionPeriod="00:00:05">  
            <sqlWorkflowInstanceStore/>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     <span data-ttu-id="c2bf1-109">SQL ワークフロー インスタンス ストアを構成する方法の詳細については、「[方法 : ワークフローおよびワークフロー サービスの SQL 永続化を有効にする](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-109">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="c2bf1-110"><>`sqlWorkflowInstanceStore`動作要素の個々の設定の詳細については[、「SQL ワークフロー インスタンス ストア](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-110">For more information about the individual settings for the <`sqlWorkflowInstanceStore`> behavior element, see [SQL Workflow Instance Store](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="c2bf1-111">Windows Server AppFabric は自己の永続ストアを提供します。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-111">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="c2bf1-112">詳細については、「 [Windows Server アプリ ファブリックの永続性](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-112">For more information, see [Windows Server App Fabric Persistence](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c2bf1-113">前の構成例では、簡略化された構成を使用しています。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-113">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="c2bf1-114">詳細については、[簡略化された構成を](../../../../docs/framework/wcf/simplified-configuration.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-114">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a><span data-ttu-id="c2bf1-115">コードで SQL Workflow Instance Store を構成するには</span><span class="sxs-lookup"><span data-stu-id="c2bf1-115">To Configure the SQL Workflow Instance Store in Code</span></span>  
  
1. <span data-ttu-id="c2bf1-116">SQL Workflow Instance Store のプロパティは、<xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> を使用して構成できます。これは、コードで設定を変更できるサービス動作です。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-116">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through code.</span></span> <span data-ttu-id="c2bf1-117">次の例では、コードで <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> という動作要素を使用して SQL Workflow Instance Store を構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-117">The following example shows how to configure the SQL workflow instance store by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element in a code</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new SqlWorkflowInstanceStoreBehavior  
    {  
       ConnectionString = "provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true",  
       InstanceEncodingOption = "GZip | None",  
       InstanceCompletionAction = "DeleteAll | DeleteNothing",  
       InstanceLockedExceptionAction = "NoRetry | SimpleRetry | AggressiveRetry",  
       HostLockRenewalPeriod = new TimeSpan(00, 00, 30),  
       RunnableInstancesDetectionPeriod = new TimeSpan(00, 00, 05)  
    });  
    ```  
  
     <span data-ttu-id="c2bf1-118">SQL ワークフロー インスタンス ストアを構成する方法の詳細については、「[方法 : ワークフローおよびワークフロー サービスの SQL 永続化を有効にする](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-118">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="c2bf1-119">動作要素の個々の設定の詳細については、「 SQL[ワークフロー インスタンス ストア](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)」を参照してください。 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior></span><span class="sxs-lookup"><span data-stu-id="c2bf1-119">For more information about the individual settings for the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element, see [SQL Workflow Instance Store](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="c2bf1-120">Windows Server AppFabric は自己の永続ストアを提供します。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-120">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="c2bf1-121">詳細については、「 [Windows Server アプリ ファブリックの永続性](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-121">For more information, see [Windows Server App Fabric Persistence](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c2bf1-122">前の構成例では、簡略化された構成を使用しています。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-122">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="c2bf1-123">詳細については、[簡略化された構成を](../../../../docs/framework/wcf/simplified-configuration.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-123">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)</span></span>  
  
     <span data-ttu-id="c2bf1-124">プログラムで永続化を構成する方法の例については、「[方法 : ワークフローとワークフロー サービスの永続化を有効にする](../../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2bf1-124">For an example of how to configure persistence programmatically see [How to: Enable Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2bf1-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2bf1-125">See also</span></span>

- [<span data-ttu-id="c2bf1-126">ワークフロー サービス</span><span class="sxs-lookup"><span data-stu-id="c2bf1-126">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="c2bf1-127">ワークフローの永続性</span><span class="sxs-lookup"><span data-stu-id="c2bf1-127">Workflow Persistence</span></span>](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)
- <span data-ttu-id="c2bf1-128">[Windows Server AppFabric の永続化](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c2bf1-128">[Windows Server App Fabric Persistence](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))</span></span>
