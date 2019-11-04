---
title: ワークフローとワークフロー サービスの永続化を有効にする方法
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 5d0eeb8ad40f2f4f3349ab48487316014a561a1b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460896"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="2a3fa-102">ワークフローとワークフロー サービスの永続化を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="2a3fa-102">How to: Enable Persistence for Workflows and Workflow Services</span></span>

<span data-ttu-id="2a3fa-103">ここでは、ワークフローとワークフロー サービスの永続化を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-103">This topic describes how to enable persistence for workflows and workflow services.</span></span>

## <a name="enable-persistence-for-workflows"></a><span data-ttu-id="2a3fa-104">ワークフローの永続化を有効にする</span><span class="sxs-lookup"><span data-stu-id="2a3fa-104">Enable Persistence for Workflows</span></span>

<span data-ttu-id="2a3fa-105"><xref:System.Activities.WorkflowApplication> クラスの <xref:System.Activities.WorkflowApplication.InstanceStore%2A> プロパティを使用して、インスタンスストアを**WorkflowApplication**に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-105">You can associate an instance store with a **WorkflowApplication** by using the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property of the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="2a3fa-106"><xref:System.Activities.WorkflowApplication.Persist%2A> メソッドは、アプリケーションに関連付けられたインスタンス ストアにワークフローを保存または永続化します。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-106">The <xref:System.Activities.WorkflowApplication.Persist%2A> method saves or persists a workflow into the instance store associated with the application.</span></span> <span data-ttu-id="2a3fa-107"><xref:System.Activities.WorkflowApplication.Unload%2A> メソッドは、ワークフローをインスタンス ストアに永続化し、メモリからインスタンスをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-107">The <xref:System.Activities.WorkflowApplication.Unload%2A> method persists a workflow into the instance store and then unloads the instance from the memory.</span></span> <span data-ttu-id="2a3fa-108">**Load**メソッドは、インスタンスの永続化ストアに格納されているワークフローデータを使用して、ワークフローをメモリに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-108">The **Load** method loads a workflow into memory using the workflow data stored in the instance persistence store.</span></span>

<span data-ttu-id="2a3fa-109">**Persist**メソッドは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-109">The **Persist** method performs the following steps:</span></span>

1. <span data-ttu-id="2a3fa-110">ワークフローのスケジューラを一時停止し、アイドル状態に移行するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-110">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="2a3fa-111">ワークフローを永続化 (永続化ストアに保存) します。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-111">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="2a3fa-112">ワークフローのスケジューラを再開します。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-112">Resumes the workflow scheduler.</span></span>

 <span data-ttu-id="2a3fa-113">**Unload**メソッドは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-113">The **Unload** method performs the following steps:</span></span>

1. <span data-ttu-id="2a3fa-114">ワークフローのスケジューラを一時停止し、アイドル状態に移行するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-114">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="2a3fa-115">ワークフローを永続化 (永続化ストアに保存) します。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-115">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="2a3fa-116">メモリ内のワークフロー インスタンスを破棄します。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-116">Disposes the workflow instance in the memory.</span></span>

<span data-ttu-id="2a3fa-117">ワークフローが非永続化ゾーンを終了するまでは、**永続**化と**アンロード**の両方のメソッドがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-117">Both the **Persist** and **Unload** methods will block while a workflow is in a no-persist zone until the workflow exits the no-persist zone.</span></span> <span data-ttu-id="2a3fa-118">メソッドは、非永続化ゾーンの完了後に、永続化またはアンロードの操作を続行します。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-118">The method continues with the persist or unload operation after the no-persist zone completes.</span></span> <span data-ttu-id="2a3fa-119">期限切れになる前に非永続化ゾーンが完了しない場合、または永続化プロセスに時間がかかりすぎる場合は、TimeoutException がスローされます。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-119">If the no-persist zone does not complete before the time-out elapses, or if the persistence process takes too long, a TimeoutException will be thrown.</span></span>

## <a name="enable-persistence-for-workflow-services-in-code"></a><span data-ttu-id="2a3fa-120">コードでのワークフロー サービスの永続化を有効にする</span><span class="sxs-lookup"><span data-stu-id="2a3fa-120">Enable Persistence for Workflow Services in Code</span></span>

<span data-ttu-id="2a3fa-121"><xref:System.ServiceModel.WorkflowServiceHost> クラスの**DurableInstancingOptions**メンバーには、インスタンスストアと**WorkflowServiceHost**を関連付けるために使用できる、 **InstanceStore**という名前のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-121">The **DurableInstancingOptions** member of the <xref:System.ServiceModel.WorkflowServiceHost> class has a property named **InstanceStore** that you can use to associate an instance store with the **WorkflowServiceHost**.</span></span>

```csharp
// wsh is an instance of WorkflowServiceHost class
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();
```

<span data-ttu-id="2a3fa-122">**WorkflowServiceHost**が開かれると、 **DurableInstancingOptions**が null でない場合、永続化は自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-122">When the **WorkflowServiceHost** is opened, persistence is automatically enabled if the **DurableInstancingOptions.InstanceStore** is not null.</span></span>

<span data-ttu-id="2a3fa-123">通常、サービスの動作により、 **InstanceStore**プロパティを使用して、ワークフローサービスホストで使用される具象インスタンスストアが提供されます。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-123">Typically, a service behavior provides the concrete instance store to be used with a workflow service host by using the **InstanceStore** property.</span></span> <span data-ttu-id="2a3fa-124">たとえば、SqlWorkflowInstanceStoreBehavior は**SqlWorkflowInstanceStore**のインスタンスを作成して構成し、 **DurableInstancingOptions**に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-124">For example, the SqlWorkflowInstanceStoreBehavior creates an instance of the **SqlWorkflowInstanceStore**, configures it, and assigns it to the **DurableInstancingOptions.InstanceStore**.</span></span>

## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a><span data-ttu-id="2a3fa-125">アプリケーション構成ファイルを使用してワークフロー サービスの永続化を有効にする</span><span class="sxs-lookup"><span data-stu-id="2a3fa-125">Enable Persistence for Workflow Services Using an Application Configuration File</span></span>

<span data-ttu-id="2a3fa-126">次のコードを app.config または web.config file に追加すると、アプリケーション構成ファイルを使用して永続化を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="2a3fa-126">Persistence can be enabled using an application configuration file by adding the following code to your app.config or web.config file:</span></span>

```xml
<configuration>
  <system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior name="myBehavior">
          <sqlWorkflowInstanceStore connectionString="Data Source=myDatabaseServer;Initial Catalog=myPersistenceDatabase" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```
