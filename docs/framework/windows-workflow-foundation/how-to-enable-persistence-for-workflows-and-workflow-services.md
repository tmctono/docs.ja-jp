---
title: '方法: ワークフローとワークフロー サービスの永続化を有効にする'
description: ワークフローとワークフローサービスの永続化をプログラムおよび構成ファイルを使用して有効にするように SQL Workflow Instance Store を構成する方法について説明します。
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 31fe6e3f06989e9a42254747565342cf97e4b9f1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421515"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="3908e-103">方法: ワークフローとワークフロー サービスの永続化を有効にする</span><span class="sxs-lookup"><span data-stu-id="3908e-103">How to: Enable Persistence for Workflows and Workflow Services</span></span>

<span data-ttu-id="3908e-104">ここでは、ワークフローとワークフロー サービスの永続化を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3908e-104">This topic describes how to enable persistence for workflows and workflow services.</span></span>

## <a name="enable-persistence-for-workflows"></a><span data-ttu-id="3908e-105">ワークフローの永続化を有効にする</span><span class="sxs-lookup"><span data-stu-id="3908e-105">Enable Persistence for Workflows</span></span>

<span data-ttu-id="3908e-106">クラスのプロパティを使用して、インスタンスストアを**WorkflowApplication**に関連付けることができ <xref:System.Activities.WorkflowApplication.InstanceStore%2A> <xref:System.Activities.WorkflowApplication> ます。</span><span class="sxs-lookup"><span data-stu-id="3908e-106">You can associate an instance store with a **WorkflowApplication** by using the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property of the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="3908e-107"><xref:System.Activities.WorkflowApplication.Persist%2A> メソッドは、アプリケーションに関連付けられたインスタンス ストアにワークフローを保存または永続化します。</span><span class="sxs-lookup"><span data-stu-id="3908e-107">The <xref:System.Activities.WorkflowApplication.Persist%2A> method saves or persists a workflow into the instance store associated with the application.</span></span> <span data-ttu-id="3908e-108"><xref:System.Activities.WorkflowApplication.Unload%2A> メソッドは、ワークフローをインスタンス ストアに永続化し、メモリからインスタンスをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="3908e-108">The <xref:System.Activities.WorkflowApplication.Unload%2A> method persists a workflow into the instance store and then unloads the instance from the memory.</span></span> <span data-ttu-id="3908e-109">**Load**メソッドは、インスタンスの永続化ストアに格納されているワークフローデータを使用して、ワークフローをメモリに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="3908e-109">The **Load** method loads a workflow into memory using the workflow data stored in the instance persistence store.</span></span>

<span data-ttu-id="3908e-110">**Persist**メソッドは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3908e-110">The **Persist** method performs the following steps:</span></span>

1. <span data-ttu-id="3908e-111">ワークフローのスケジューラを一時停止し、アイドル状態に移行するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="3908e-111">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="3908e-112">ワークフローを永続化 (永続化ストアに保存) します。</span><span class="sxs-lookup"><span data-stu-id="3908e-112">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="3908e-113">ワークフローのスケジューラを再開します。</span><span class="sxs-lookup"><span data-stu-id="3908e-113">Resumes the workflow scheduler.</span></span>

 <span data-ttu-id="3908e-114">**Unload**メソッドは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3908e-114">The **Unload** method performs the following steps:</span></span>

1. <span data-ttu-id="3908e-115">ワークフローのスケジューラを一時停止し、アイドル状態に移行するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="3908e-115">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="3908e-116">ワークフローを永続化 (永続化ストアに保存) します。</span><span class="sxs-lookup"><span data-stu-id="3908e-116">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="3908e-117">メモリ内のワークフロー インスタンスを破棄します。</span><span class="sxs-lookup"><span data-stu-id="3908e-117">Disposes the workflow instance in the memory.</span></span>

<span data-ttu-id="3908e-118">ワークフローが非永続化ゾーンを終了するまでは、**永続**化と**アンロード**の両方のメソッドがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="3908e-118">Both the **Persist** and **Unload** methods will block while a workflow is in a no-persist zone until the workflow exits the no-persist zone.</span></span> <span data-ttu-id="3908e-119">メソッドは、非永続化ゾーンの完了後に、永続化またはアンロードの操作を続行します。</span><span class="sxs-lookup"><span data-stu-id="3908e-119">The method continues with the persist or unload operation after the no-persist zone completes.</span></span> <span data-ttu-id="3908e-120">期限切れになる前に非永続化ゾーンが完了しない場合、または永続化プロセスに時間がかかりすぎる場合は、TimeoutException がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3908e-120">If the no-persist zone does not complete before the time-out elapses, or if the persistence process takes too long, a TimeoutException will be thrown.</span></span>

## <a name="enable-persistence-for-workflow-services-in-code"></a><span data-ttu-id="3908e-121">コードでのワークフロー サービスの永続化を有効にする</span><span class="sxs-lookup"><span data-stu-id="3908e-121">Enable Persistence for Workflow Services in Code</span></span>

<span data-ttu-id="3908e-122">クラスの**DurableInstancingOptions**メンバーに <xref:System.ServiceModel.WorkflowServiceHost> は、インスタンスストアと**WorkflowServiceHost**を関連付けるために使用できる、 **InstanceStore**という名前のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="3908e-122">The **DurableInstancingOptions** member of the <xref:System.ServiceModel.WorkflowServiceHost> class has a property named **InstanceStore** that you can use to associate an instance store with the **WorkflowServiceHost**.</span></span>

```csharp
// wsh is an instance of WorkflowServiceHost class
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();
```

<span data-ttu-id="3908e-123">**WorkflowServiceHost**が開かれると、 **DurableInstancingOptions**が null でない場合、永続化は自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="3908e-123">When the **WorkflowServiceHost** is opened, persistence is automatically enabled if the **DurableInstancingOptions.InstanceStore** is not null.</span></span>

<span data-ttu-id="3908e-124">通常、サービスの動作により、 **InstanceStore**プロパティを使用して、ワークフローサービスホストで使用される具象インスタンスストアが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3908e-124">Typically, a service behavior provides the concrete instance store to be used with a workflow service host by using the **InstanceStore** property.</span></span> <span data-ttu-id="3908e-125">たとえば、SqlWorkflowInstanceStoreBehavior は**SqlWorkflowInstanceStore**のインスタンスを作成して構成し、 **DurableInstancingOptions**に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3908e-125">For example, the SqlWorkflowInstanceStoreBehavior creates an instance of the **SqlWorkflowInstanceStore**, configures it, and assigns it to the **DurableInstancingOptions.InstanceStore**.</span></span>

## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a><span data-ttu-id="3908e-126">アプリケーション構成ファイルを使用してワークフロー サービスの永続化を有効にする</span><span class="sxs-lookup"><span data-stu-id="3908e-126">Enable Persistence for Workflow Services Using an Application Configuration File</span></span>

<span data-ttu-id="3908e-127">次のコードを app.config または web.config file に追加すると、アプリケーション構成ファイルを使用して永続化を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="3908e-127">Persistence can be enabled using an application configuration file by adding the following code to your app.config or web.config file:</span></span>

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
