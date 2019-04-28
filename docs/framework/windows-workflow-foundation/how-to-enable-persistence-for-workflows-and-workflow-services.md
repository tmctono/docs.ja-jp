---
title: '方法: ワークフローとワークフロー サービスの永続化を有効にする'
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 6a2a8d73298e14f92f376b97b9637db91532e937
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761430"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="942dd-102">方法: ワークフローとワークフロー サービスの永続化を有効にする</span><span class="sxs-lookup"><span data-stu-id="942dd-102">How to: Enable Persistence for Workflows and Workflow Services</span></span>
<span data-ttu-id="942dd-103">ここでは、ワークフローとワークフロー サービスの永続化を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="942dd-103">This topic describes how to enable persistence for workflows and workflow services.</span></span>  
  
## <a name="enable-persistence-for-workflows"></a><span data-ttu-id="942dd-104">ワークフローの永続化を有効にする</span><span class="sxs-lookup"><span data-stu-id="942dd-104">Enable Persistence for Workflows</span></span>  
 <span data-ttu-id="942dd-105">使用して、インスタンス ストアを関連付けることができます、 **WorkflowApplication**を使用して、<xref:System.Activities.WorkflowApplication.InstanceStore%2A>のプロパティ、<xref:System.Activities.WorkflowApplication>クラス。</span><span class="sxs-lookup"><span data-stu-id="942dd-105">You can associate an instance store with a **WorkflowApplication** by using the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property of the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="942dd-106"><xref:System.Activities.WorkflowApplication.Persist%2A> メソッドは、アプリケーションに関連付けられたインスタンス ストアにワークフローを保存または永続化します。</span><span class="sxs-lookup"><span data-stu-id="942dd-106">The <xref:System.Activities.WorkflowApplication.Persist%2A> method saves or persists a workflow into the instance store associated with the application.</span></span> <span data-ttu-id="942dd-107"><xref:System.Activities.WorkflowApplication.Unload%2A> メソッドは、ワークフローをインスタンス ストアに永続化し、メモリからインスタンスをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="942dd-107">The <xref:System.Activities.WorkflowApplication.Unload%2A> method persists a workflow into the instance store and then unloads the instance from the memory.</span></span> <span data-ttu-id="942dd-108">**ロード**メソッドは、インスタンスの永続化ストアに格納されているワークフロー データを使用してメモリにワークフローを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="942dd-108">The **Load** method loads a workflow into memory using the workflow data stored in the instance persistence store.</span></span>  
  
 <span data-ttu-id="942dd-109">**Persist**メソッドは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="942dd-109">The **Persist** method performs the following steps:</span></span>  
  
1. <span data-ttu-id="942dd-110">ワークフローのスケジューラを一時停止し、アイドル状態に移行するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="942dd-110">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>  
  
2. <span data-ttu-id="942dd-111">ワークフローを永続化 (永続化ストアに保存) します。</span><span class="sxs-lookup"><span data-stu-id="942dd-111">Persists or saves the workflow into the persistence store.</span></span>  
  
3. <span data-ttu-id="942dd-112">ワークフローのスケジューラを再開します。</span><span class="sxs-lookup"><span data-stu-id="942dd-112">Resumes the workflow scheduler.</span></span>  
  
 <span data-ttu-id="942dd-113">**アンロード**メソッドは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="942dd-113">The **Unload** method performs the following steps:</span></span>  
  
1. <span data-ttu-id="942dd-114">ワークフローのスケジューラを一時停止し、アイドル状態に移行するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="942dd-114">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>  
  
2. <span data-ttu-id="942dd-115">ワークフローを永続化 (永続化ストアに保存) します。</span><span class="sxs-lookup"><span data-stu-id="942dd-115">Persists or saves the workflow into the persistence store.</span></span>  
  
3. <span data-ttu-id="942dd-116">メモリ内のワークフロー インスタンスを破棄します。</span><span class="sxs-lookup"><span data-stu-id="942dd-116">Disposes the workflow instance in the memory.</span></span>  
  
 <span data-ttu-id="942dd-117">両方の**Persist**と**アンロード**メソッドは、ワークフローが非永続化ゾーンを終了するまでに、ワークフローが非永続化ゾーンではブロックされます。</span><span class="sxs-lookup"><span data-stu-id="942dd-117">Both the **Persist** and **Unload** methods will block while a workflow is in a no-persist zone until the workflow exits the no-persist zone.</span></span> <span data-ttu-id="942dd-118">メソッドは、非永続化ゾーンの完了後に、永続化またはアンロードの操作を続行します。</span><span class="sxs-lookup"><span data-stu-id="942dd-118">The method continues with the persist or unload operation after the no-persist zone completes.</span></span> <span data-ttu-id="942dd-119">期限切れになる前に非永続化ゾーンが完了しない場合、または永続化プロセスに時間がかかりすぎる場合は、TimeoutException がスローされます。</span><span class="sxs-lookup"><span data-stu-id="942dd-119">If the no-persist zone does not complete before the time-out elapses, or if the persistence process takes too long, a TimeoutException will be thrown.</span></span>  
  
## <a name="enable-persistence-for-workflow-services-in-code"></a><span data-ttu-id="942dd-120">コードでのワークフロー サービスの永続化を有効にする</span><span class="sxs-lookup"><span data-stu-id="942dd-120">Enable Persistence for Workflow Services in Code</span></span>  
 <span data-ttu-id="942dd-121">**DurableInstancingOptions**のメンバー、<xref:System.ServiceModel.WorkflowServiceHost>クラスという名前のプロパティには**InstanceStore**に関連付ける、インスタンス ストアを使用できる、 **WorkflowServiceHost**.</span><span class="sxs-lookup"><span data-stu-id="942dd-121">The **DurableInstancingOptions** member of the <xref:System.ServiceModel.WorkflowServiceHost> class has a property named **InstanceStore** that you can use to associate an instance store with the **WorkflowServiceHost**.</span></span>  
  
```  
// wsh is an instance of WorkflowServiceHost class  
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();  
```  
  
 <span data-ttu-id="942dd-122">ときに、 **WorkflowServiceHost**が開かれると、永続化は自動的に有効になっている場合、 **DurableInstancingOptions.InstanceStore**が null でないです。</span><span class="sxs-lookup"><span data-stu-id="942dd-122">When the **WorkflowServiceHost** is opened, persistence is automatically enabled if the **DurableInstancingOptions.InstanceStore** is not null.</span></span>  
  
 <span data-ttu-id="942dd-123">通常、サービスの動作を使用して、ワークフロー サービス ホストで使用する具象インスタンス ストアを提供します。、 **InstanceStore**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="942dd-123">Typically, a service behavior provides the concrete instance store to be used with a workflow service host by using the **InstanceStore** property.</span></span> <span data-ttu-id="942dd-124">たとえば、SqlWorkflowInstanceStoreBehavior のインスタンスを作成、 **SqlWorkflowInstanceStore**、構成、およびに割り当てます、 **DurableInstancingOptions.InstanceStore**します。</span><span class="sxs-lookup"><span data-stu-id="942dd-124">For example, the SqlWorkflowInstanceStoreBehavior creates an instance of the **SqlWorkflowInstanceStore**, configures it, and assigns it to the **DurableInstancingOptions.InstanceStore**.</span></span>  
  
## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a><span data-ttu-id="942dd-125">アプリケーション構成ファイルを使用してワークフロー サービスの永続化を有効にする</span><span class="sxs-lookup"><span data-stu-id="942dd-125">Enable Persistence for Workflow Services Using an Application Configuration File</span></span>  
 <span data-ttu-id="942dd-126">次のコードを app.config または web.config file に追加すると、アプリケーション構成ファイルを使用して永続化を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="942dd-126">Persistence can be enabled using an application configuration file by adding the following code to your app.config or web.config file:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="myBehavior">  
          <SqlWorkflowInstanceStore connectionString="Data Source=myDatatbaseServer;Initial Catalog=myPersistenceDatabase">  
        </behavior>  
      </serviceBehaviors>  
    <behaviors>  
  </system.serviceModel>  
</configuration>  
```
