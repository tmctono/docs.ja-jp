---
title: ワークフロー サービスへのトランザクションのフロー
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: ea14bc651258684fd31940aa6b88f9731348dcd1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978282"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a><span data-ttu-id="85e11-102">ワークフロー サービスへのトランザクションのフロー</span><span class="sxs-lookup"><span data-stu-id="85e11-102">Flowing Transactions into and out of Workflow Services</span></span>
<span data-ttu-id="85e11-103">ワークフロー サービスとワークフロー クライアントはトランザクションに参加できます。</span><span class="sxs-lookup"><span data-stu-id="85e11-103">Workflow services and clients can participate in transactions.</span></span>  <span data-ttu-id="85e11-104">サービス操作をアンビエント トランザクションの一部にするには、<xref:System.ServiceModel.Activities.Receive> アクティビティを <xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティの中に配置します。</span><span class="sxs-lookup"><span data-stu-id="85e11-104">For a service operation to become part of an ambient transaction, place a <xref:System.ServiceModel.Activities.Receive> activity within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="85e11-105"><xref:System.ServiceModel.Activities.Send> 内の <xref:System.ServiceModel.Activities.SendReply> または <xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティによる呼び出しが行われると、アンビエント トランザクション内でも呼び出しが行われます。</span><span class="sxs-lookup"><span data-stu-id="85e11-105">Any calls made by a <xref:System.ServiceModel.Activities.Send> or a <xref:System.ServiceModel.Activities.SendReply> activity within the <xref:System.ServiceModel.Activities.TransactedReceiveScope> will also be made within the ambient transaction.</span></span> <span data-ttu-id="85e11-106">ワークフロー クライアント アプリケーションでは、<xref:System.Activities.Statements.TransactionScope> アクティビティを使用してアンビエント トランザクションを作成し、そのアンビエント トランザクションを使用してサービス操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="85e11-106">A workflow client application can create an ambient transaction by using the <xref:System.Activities.Statements.TransactionScope> activity and call service operations using the ambient transaction.</span></span> <span data-ttu-id="85e11-107">ここでは、トランザクションに参加するワークフロー サービスとワークフロー クライアントを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="85e11-107">This topic walks you through creating a workflow service and workflow client that participate in transactions.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="85e11-108">ワークフローサービスインスタンスがトランザクション内に読み込まれ、ワークフローに <xref:System.Activities.Statements.Persist> アクティビティが含まれている場合、ワークフローインスタンスは、トランザクションがタイムアウトするまでブロックします。</span><span class="sxs-lookup"><span data-stu-id="85e11-108">If a workflow service instance is loaded within a transaction and the workflow contains a <xref:System.Activities.Statements.Persist> activity, the workflow instance will block until the transaction times out.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="85e11-109"><xref:System.ServiceModel.Activities.TransactedReceiveScope> を使用する場合は、ワークフロー内のすべての受信を <xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティに配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85e11-109">Whenever you use a <xref:System.ServiceModel.Activities.TransactedReceiveScope> it is recommended to place all Receives in the workflow within <xref:System.ServiceModel.Activities.TransactedReceiveScope> activities.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="85e11-110"><xref:System.ServiceModel.Activities.TransactedReceiveScope> を使用して、メッセージが不適切な順序で到着する場合、最初の順序を無視したメッセージを配信しようとするとワークフローは中止されます。</span><span class="sxs-lookup"><span data-stu-id="85e11-110">When using <xref:System.ServiceModel.Activities.TransactedReceiveScope> and messages arrive in the incorrect order, the workflow will be aborted when trying to deliver the first out of order message.</span></span> <span data-ttu-id="85e11-111">ワークフローがアイドル状態である場合、ワークフローは常に一致する停止ポイントにあるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85e11-111">You must make sure your workflow is always at a consistent stopping point when the workflow idles.</span></span> <span data-ttu-id="85e11-112">これによって、ワークフローが中止された場合、前の永続性ポイントからワークフローを再開することができます。</span><span class="sxs-lookup"><span data-stu-id="85e11-112">This will allow you to restart the workflow from a previous persistence point should the workflow be aborted.</span></span>  
  
### <a name="create-a-shared-library"></a><span data-ttu-id="85e11-113">共有ライブラリの作成</span><span class="sxs-lookup"><span data-stu-id="85e11-113">Create a shared library</span></span>  
  
1. <span data-ttu-id="85e11-114">新しい空の Visual Studio ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="85e11-114">Create a new empty Visual Studio Solution.</span></span>  
  
2. <span data-ttu-id="85e11-115">`Common` という新しいクラス ライブラリ プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="85e11-115">Add a new class library project called `Common`.</span></span> <span data-ttu-id="85e11-116">次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="85e11-116">Add references to the following assemblies:</span></span>  
  
    - <span data-ttu-id="85e11-117">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="85e11-117">System.Activities.dll</span></span>  
  
    - <span data-ttu-id="85e11-118">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="85e11-118">System.ServiceModel.dll</span></span>  
  
    - <span data-ttu-id="85e11-119">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="85e11-119">System.ServiceModel.Activities.dll</span></span>  
  
    - <span data-ttu-id="85e11-120">System.Transactions.dll</span><span class="sxs-lookup"><span data-stu-id="85e11-120">System.Transactions.dll</span></span>  
  
3. <span data-ttu-id="85e11-121">`PrintTransactionInfo` という新しいクラスを `Common` プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="85e11-121">Add a new class called `PrintTransactionInfo` to the `Common` project.</span></span> <span data-ttu-id="85e11-122">このクラスは <xref:System.Activities.NativeActivity> の派生クラスで、<xref:System.Activities.NativeActivity.Execute%2A> メソッドをオーバーロードします。</span><span class="sxs-lookup"><span data-stu-id="85e11-122">This class is derived from <xref:System.Activities.NativeActivity> and overloads the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>  
  
    ```csharp
    using System;  
    using System;  
    using System.Activities;  
    using System.Transactions;  
  
    namespace Common  
    {  
        public class PrintTransactionInfo : NativeActivity  
        {  
            protected override void Execute(NativeActivityContext context)  
            {  
                RuntimeTransactionHandle rth = context.Properties.Find(typeof(RuntimeTransactionHandle).FullName) as RuntimeTransactionHandle;  
  
                if (rth == null)  
                {  
                    Console.WriteLine("There is no ambient RuntimeTransactionHandle");  
                }  
  
                Transaction t = rth.GetCurrentTransaction(context);  
  
                if (t == null)  
                {  
                    Console.WriteLine("There is no ambient transaction");  
                }  
                else  
                {  
                    Console.WriteLine("Transaction: {0} is {1}", t.TransactionInformation.DistributedIdentifier, t.TransactionInformation.Status);  
                }  
            }  
        }  
  
    }  
    ```  
  
     <span data-ttu-id="85e11-123">これは、アンビエント トランザクションに関する情報を表示するネイティブ アクティビティで、ここで使用するサービス ワークフローとクライアント ワークフローの両方で使用されます。</span><span class="sxs-lookup"><span data-stu-id="85e11-123">This is a native activity that displays information about the ambient transaction and is used in both the service and client workflows used in this topic.</span></span> <span data-ttu-id="85e11-124">ソリューションをビルドして、このアクティビティを**ツールボックス**の **[共通]** セクションで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="85e11-124">Build the solution to make this activity available in the **Common** section of the **Toolbox**.</span></span>  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="85e11-125">ワークフロー サービスの実装</span><span class="sxs-lookup"><span data-stu-id="85e11-125">Implement the workflow service</span></span>  
  
1. <span data-ttu-id="85e11-126">`Common` プロジェクトに `WorkflowService` という新しい WCF ワークフローサービスを追加します。</span><span class="sxs-lookup"><span data-stu-id="85e11-126">Add a new WCF Workflow Service, called `WorkflowService` to the `Common` project.</span></span> <span data-ttu-id="85e11-127">これを行うには、`Common` プロジェクトを右クリックし、 **[追加]** 、 **[新しい項目]** の順に選択し、 **[インストールされたテンプレート]** で **[ワークフロー]** を選択して **[WCF ワークフローサービス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85e11-127">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **WCF Workflow Service**.</span></span>  
  
     ![ワークフロー サービスの追加](./media/flowing-transactions-into-and-out-of-workflow-services/add-workflow-service.jpg)  
  
2. <span data-ttu-id="85e11-129">既定の `ReceiveRequest` アクティビティと `SendResponse` アクティビティを削除します。</span><span class="sxs-lookup"><span data-stu-id="85e11-129">Delete the default `ReceiveRequest` and `SendResponse` activities.</span></span>  
  
3. <span data-ttu-id="85e11-130"><xref:System.Activities.Statements.WriteLine> アクティビティを `Sequential Service` アクティビティにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="85e11-130">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity into the `Sequential Service` activity.</span></span> <span data-ttu-id="85e11-131">次の例に示すように、Text プロパティを `"Workflow Service starting ..."` に設定します。</span><span class="sxs-lookup"><span data-stu-id="85e11-131">Set the text property to `"Workflow Service starting ..."` as shown in the following example.</span></span>  
  
     <span data-ttu-id="85e11-132">![シーケンシャルサービスアクティビティへの WriteLine アクティビティの追加 (./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-sequential-service.jpg)</span><span class="sxs-lookup"><span data-stu-id="85e11-132">![Adding a WriteLine activity to the Sequential Service activity(./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-sequential-service.jpg)</span></span>  
  
4. <span data-ttu-id="85e11-133"><xref:System.ServiceModel.Activities.TransactedReceiveScope> を <xref:System.Activities.Statements.WriteLine> アクティビティの後にドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="85e11-133">Drag and drop a <xref:System.ServiceModel.Activities.TransactedReceiveScope> after the <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="85e11-134"><xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティは、**ツールボックス**の **[メッセージング]** セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="85e11-134">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity can be found in the **Messaging** section of the **Toolbox**.</span></span> <span data-ttu-id="85e11-135"><xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティは、**要求**と**本文**の2つのセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="85e11-135">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity is composed of two sections **Request** and **Body**.</span></span> <span data-ttu-id="85e11-136">**要求**セクションには、<xref:System.ServiceModel.Activities.Receive> アクティビティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="85e11-136">The **Request** section contains the <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="85e11-137">**Body**セクションには、メッセージを受信した後にトランザクション内で実行されるアクティビティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="85e11-137">The **Body** section contains the activities to execute within a transaction after a message has been received.</span></span>  
  
     ![TransactedReceiveScope アクティビティの追加](./media/flowing-transactions-into-and-out-of-workflow-services/transactedreceivescope-activity.jpg)  
  
5. <span data-ttu-id="85e11-139"><xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティを選択し、 **[変数]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e11-139">Select the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity and click the **Variables** button.</span></span> <span data-ttu-id="85e11-140">次の変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="85e11-140">Add the following variables.</span></span>  
  
     ![TransactedReceiveScope への変数の追加](./media/flowing-transactions-into-and-out-of-workflow-services/add-transactedreceivescope-variables.jpg)  
  
    > [!NOTE]
    > <span data-ttu-id="85e11-142">既定で含まれているデータ変数は削除してかまいません。</span><span class="sxs-lookup"><span data-stu-id="85e11-142">You can delete the data variable that is there by default.</span></span> <span data-ttu-id="85e11-143">既存のハンドル変数を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="85e11-143">You can also use the existing handle variable.</span></span>  
  
6. <span data-ttu-id="85e11-144"><xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティの**Request**セクション内に <xref:System.ServiceModel.Activities.Receive> アクティビティをドラッグアンドドロップします。</span><span class="sxs-lookup"><span data-stu-id="85e11-144">Drag and drop a <xref:System.ServiceModel.Activities.Receive> activity within the **Request** section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="85e11-145">次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="85e11-145">Set the following properties:</span></span>  
  
    |<span data-ttu-id="85e11-146">property</span><span class="sxs-lookup"><span data-stu-id="85e11-146">Property</span></span>|<span data-ttu-id="85e11-147">[値]</span><span class="sxs-lookup"><span data-stu-id="85e11-147">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="85e11-148">CanCreateInstance</span><span class="sxs-lookup"><span data-stu-id="85e11-148">CanCreateInstance</span></span>|<span data-ttu-id="85e11-149">True (チェック ボックスをオンにする)</span><span class="sxs-lookup"><span data-stu-id="85e11-149">True (check the checkbox)</span></span>|  
    |<span data-ttu-id="85e11-150">OperationName</span><span class="sxs-lookup"><span data-stu-id="85e11-150">OperationName</span></span>|<span data-ttu-id="85e11-151">StartSample</span><span class="sxs-lookup"><span data-stu-id="85e11-151">StartSample</span></span>|  
    |<span data-ttu-id="85e11-152">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="85e11-152">ServiceContractName</span></span>|<span data-ttu-id="85e11-153">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="85e11-153">ITransactionSample</span></span>|  
  
     <span data-ttu-id="85e11-154">ワークフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="85e11-154">The workflow should look like this:</span></span>  
  
     ![Receive アクティビティの追加](./media/flowing-transactions-into-and-out-of-workflow-services/add-receive-activity.jpg)  
  
7. <span data-ttu-id="85e11-156"><xref:System.ServiceModel.Activities.Receive> アクティビティの **[定義...]** リンクをクリックし、次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="85e11-156">Click the **Define...** link in the <xref:System.ServiceModel.Activities.Receive> activity and make the following settings:</span></span>  
  
     ![Receive アクティビティのメッセージ設定を設定する](./media/flowing-transactions-into-and-out-of-workflow-services/receive-message-settings.jpg)  
  
8. <span data-ttu-id="85e11-158"><xref:System.Activities.Statements.Sequence> アクティビティを <xref:System.ServiceModel.Activities.TransactedReceiveScope> の Body セクションにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="85e11-158">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the Body section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="85e11-159"><xref:System.Activities.Statements.Sequence> アクティビティに 2 つの <xref:System.Activities.Statements.WriteLine> アクティビティをドラッグ アンド ドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを次の表のとおりに設定します。</span><span class="sxs-lookup"><span data-stu-id="85e11-159">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop two <xref:System.Activities.Statements.WriteLine> activities and set the <xref:System.Activities.Statements.WriteLine.Text%2A> properties as shown in the following table.</span></span>  
  
    |<span data-ttu-id="85e11-160">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="85e11-160">Activity</span></span>|<span data-ttu-id="85e11-161">[値]</span><span class="sxs-lookup"><span data-stu-id="85e11-161">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="85e11-162">1 つ目の WriteLine</span><span class="sxs-lookup"><span data-stu-id="85e11-162">1st WriteLine</span></span>|<span data-ttu-id="85e11-163">"サービス: 受信が完了しました"</span><span class="sxs-lookup"><span data-stu-id="85e11-163">"Service: Receive Completed"</span></span>|  
    |<span data-ttu-id="85e11-164">2 つ目の WriteLine</span><span class="sxs-lookup"><span data-stu-id="85e11-164">2nd WriteLine</span></span>|<span data-ttu-id="85e11-165">"Service: Received = " + requestMessage</span><span class="sxs-lookup"><span data-stu-id="85e11-165">"Service: Received = " + requestMessage</span></span>|  
  
     <span data-ttu-id="85e11-166">ワークフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="85e11-166">The workflow should now look like this:</span></span>  
  
     ![WriteLine アクティビティを追加した後のシーケンス](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-writelines.jpg)  
  
9. <span data-ttu-id="85e11-168">`PrintTransactionInfo` アクティビティを、<xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティの**本文**の2つ目の <xref:System.Activities.Statements.WriteLine> アクティビティの後にドラッグアンドドロップします。</span><span class="sxs-lookup"><span data-stu-id="85e11-168">Drag and drop the `PrintTransactionInfo` activity after the second <xref:System.Activities.Statements.WriteLine> activity in the **Body** in the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span>  
  
     ![PrintTransactionInfo を追加した後のシーケンス](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-printtransactioninfo.jpg )  
  
10. <span data-ttu-id="85e11-170"><xref:System.Activities.Statements.Assign> アクティビティを `PrintTransactionInfo` アクティビティの後にドラッグ アンド ドロップし、次の表のとおりにプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="85e11-170">Drag and drop an <xref:System.Activities.Statements.Assign> activity after the `PrintTransactionInfo` activity and set its properties according to the following table.</span></span>  
  
    |<span data-ttu-id="85e11-171">property</span><span class="sxs-lookup"><span data-stu-id="85e11-171">Property</span></span>|<span data-ttu-id="85e11-172">[値]</span><span class="sxs-lookup"><span data-stu-id="85e11-172">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="85e11-173">終了</span><span class="sxs-lookup"><span data-stu-id="85e11-173">To</span></span>|<span data-ttu-id="85e11-174">replyMessage</span><span class="sxs-lookup"><span data-stu-id="85e11-174">replyMessage</span></span>|  
    |<span data-ttu-id="85e11-175">[値]</span><span class="sxs-lookup"><span data-stu-id="85e11-175">Value</span></span>|<span data-ttu-id="85e11-176">"Service: Sending reply."</span><span class="sxs-lookup"><span data-stu-id="85e11-176">"Service: Sending reply."</span></span>|  
  
11. <span data-ttu-id="85e11-177"><xref:System.Activities.Statements.WriteLine> アクティビティを <xref:System.Activities.Statements.Assign> アクティビティの後にドラッグ アンド ドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを "Service: Begin reply" に設定します。</span><span class="sxs-lookup"><span data-stu-id="85e11-177">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.Activities.Statements.Assign> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Begin reply."</span></span>  
  
     <span data-ttu-id="85e11-178">ワークフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="85e11-178">The workflow should now look like this:</span></span>  
  
     ![Assign および WriteLine の追加後](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-sbr-writeline.jpg)  
  
12. <span data-ttu-id="85e11-180"><xref:System.ServiceModel.Activities.Receive> アクティビティを右クリックし、 **[SendReply の作成]** を選択して、最後の <xref:System.Activities.Statements.WriteLine> アクティビティの後に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="85e11-180">Right click the <xref:System.ServiceModel.Activities.Receive> activity and select **Create SendReply** and paste it after the last <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="85e11-181">`SendReplyToReceive` アクティビティの **[定義...]** リンクをクリックし、次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="85e11-181">Click the **Define...** link in the `SendReplyToReceive` activity and make the following settings.</span></span>  
  
     ![応答メッセージの設定](./media/flowing-transactions-into-and-out-of-workflow-services/reply-message-settings.jpg)  
  
13. <span data-ttu-id="85e11-183"><xref:System.Activities.Statements.WriteLine> アクティビティを `SendReplyToReceive` アクティビティの後にドラッグアンドドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを "Service: Reply sent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="85e11-183">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `SendReplyToReceive` activity and set it’s <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Reply sent."</span></span>  
  
14. <span data-ttu-id="85e11-184"><xref:System.Activities.Statements.WriteLine> アクティビティをワークフローの末尾にドラッグ アンド ドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを "Service: Workflow ends, press ENTER to exit" に設定します。</span><span class="sxs-lookup"><span data-stu-id="85e11-184">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the bottom of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Workflow ends, press ENTER to exit."</span></span>  
  
     <span data-ttu-id="85e11-185">完成したサービス ワークフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="85e11-185">The completed service workflow should look like this:</span></span>  
  
     ![完全なサービス ワークフロー](./media/flowing-transactions-into-and-out-of-workflow-services/service-complete-workflow.jpg)  
  
### <a name="implement-the-workflow-client"></a><span data-ttu-id="85e11-187">ワークフロー クライアントの実装</span><span class="sxs-lookup"><span data-stu-id="85e11-187">Implement the workflow client</span></span>  
  
1. <span data-ttu-id="85e11-188">`WorkflowClient` という新しい WCF ワークフロー アプリケーションを `Common` プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="85e11-188">Add a new WCF Workflow application, called `WorkflowClient` to the `Common` project.</span></span> <span data-ttu-id="85e11-189">これを行うには、`Common` プロジェクトを右クリックし、 **[追加]** 、 **[新しい項目]** の順に選択し、 **[インストールさ]** れたテンプレート で **[ワークフロー]** を選択して **[アクティビティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85e11-189">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **Activity**.</span></span>  
  
     ![アクティビティ プロジェクトの追加](./media/flowing-transactions-into-and-out-of-workflow-services/add-activity-project.jpg)  
  
2. <span data-ttu-id="85e11-191"><xref:System.Activities.Statements.Sequence> アクティビティをデザイン画面にドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="85e11-191">Drag and drop a <xref:System.Activities.Statements.Sequence> activity onto the design surface.</span></span>  
  
3. <span data-ttu-id="85e11-192"><xref:System.Activities.Statements.Sequence> アクティビティを <xref:System.Activities.Statements.WriteLine> アクティビティにドラッグ アンド ドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを `"Client: Workflow starting"` に設定します。</span><span class="sxs-lookup"><span data-stu-id="85e11-192">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop a <xref:System.Activities.Statements.WriteLine> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to `"Client: Workflow starting"`.</span></span> <span data-ttu-id="85e11-193">ワークフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="85e11-193">The workflow should now look like this:</span></span>  
  
     ![WriteLine アクティビティを追加する](./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-activity.jpg)  
  
4. <span data-ttu-id="85e11-195"><xref:System.Activities.Statements.TransactionScope> アクティビティを <xref:System.Activities.Statements.WriteLine> アクティビティの後にドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="85e11-195">Drag and drop a <xref:System.Activities.Statements.TransactionScope> activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  <span data-ttu-id="85e11-196"><xref:System.Activities.Statements.TransactionScope> アクティビティを選択し、[変数] をクリックして次の変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="85e11-196">Select the <xref:System.Activities.Statements.TransactionScope> activity, click the Variables button and add the following variables.</span></span>  
  
     ![TransactionScope への変数の追加](./media/flowing-transactions-into-and-out-of-workflow-services/transactionscope-variables.jpg)  
  
5. <span data-ttu-id="85e11-198"><xref:System.Activities.Statements.Sequence> アクティビティを <xref:System.Activities.Statements.TransactionScope> アクティビティの Body セクションにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="85e11-198">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the body of the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
6. <span data-ttu-id="85e11-199">`PrintTransactionInfo` アクティビティを <xref:System.Activities.Statements.Sequence> アクティビティにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="85e11-199">Drag and drop a `PrintTransactionInfo` activity within the <xref:System.Activities.Statements.Sequence></span></span>  
  
7. <span data-ttu-id="85e11-200"><xref:System.Activities.Statements.WriteLine> アクティビティを `PrintTransactionInfo` アクティビティの後にドラッグアンドドロップし、その <xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを "Client: from Send" に設定します。</span><span class="sxs-lookup"><span data-stu-id="85e11-200">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `PrintTransactionInfo` activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Beginning Send".</span></span> <span data-ttu-id="85e11-201">ワークフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="85e11-201">The workflow should now look like this:</span></span>  
  
     ![クライアントを追加しています: 送信アクティビティを開始しています](./media/flowing-transactions-into-and-out-of-workflow-services/client-add-cbs-writeline.jpg)  
  
8. <span data-ttu-id="85e11-203"><xref:System.ServiceModel.Activities.Send> アクティビティを <xref:System.Activities.Statements.Assign> アクティビティの後にドラッグ アンド ドロップし、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="85e11-203">Drag and drop a <xref:System.ServiceModel.Activities.Send> activity after the <xref:System.Activities.Statements.Assign> activity and set the following properties:</span></span>  
  
    |<span data-ttu-id="85e11-204">property</span><span class="sxs-lookup"><span data-stu-id="85e11-204">Property</span></span>|<span data-ttu-id="85e11-205">[値]</span><span class="sxs-lookup"><span data-stu-id="85e11-205">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="85e11-206">EndpointConfigurationName</span><span class="sxs-lookup"><span data-stu-id="85e11-206">EndpointConfigurationName</span></span>|<span data-ttu-id="85e11-207">workflowServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="85e11-207">workflowServiceEndpoint</span></span>|  
    |<span data-ttu-id="85e11-208">OperationName</span><span class="sxs-lookup"><span data-stu-id="85e11-208">OperationName</span></span>|<span data-ttu-id="85e11-209">StartSample</span><span class="sxs-lookup"><span data-stu-id="85e11-209">StartSample</span></span>|  
    |<span data-ttu-id="85e11-210">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="85e11-210">ServiceContractName</span></span>|<span data-ttu-id="85e11-211">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="85e11-211">ITransactionSample</span></span>|  
  
     <span data-ttu-id="85e11-212">ワークフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="85e11-212">The workflow should now look like this:</span></span>  
  
     ![Send アクティビティのプロパティの設定](./media/flowing-transactions-into-and-out-of-workflow-services/client-send-activity-settings.jpg)  
  
9. <span data-ttu-id="85e11-214">**[定義...]** リンクをクリックし、次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="85e11-214">Click the **Define...** link and make the following settings:</span></span>  
  
     ![Send アクティビティのメッセージの設定](./media/flowing-transactions-into-and-out-of-workflow-services/send-message-settings.jpg)  
  
10. <span data-ttu-id="85e11-216"><xref:System.ServiceModel.Activities.Send> アクティビティを右クリックし、 **[ReceiveReply の作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85e11-216">Right click the <xref:System.ServiceModel.Activities.Send> activity and select **Create ReceiveReply**.</span></span> <span data-ttu-id="85e11-217"><xref:System.ServiceModel.Activities.ReceiveReply> アクティビティが <xref:System.ServiceModel.Activities.Send> アクティビティの後に自動的に配置されます。</span><span class="sxs-lookup"><span data-stu-id="85e11-217">The <xref:System.ServiceModel.Activities.ReceiveReply> activity will be automatically placed after the <xref:System.ServiceModel.Activities.Send> activity.</span></span>  
  
11. <span data-ttu-id="85e11-218">ReceiveReplyForSend アクティビティの [定義] リンクをクリックし、次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="85e11-218">Click the Define... link on the ReceiveReplyForSend activity and make the following settings:</span></span>  
  
     ![ReceiveForSend メッセージの設定](./media/flowing-transactions-into-and-out-of-workflow-services/client-reply-message-settings.jpg)  
  
12. <span data-ttu-id="85e11-220"><xref:System.Activities.Statements.WriteLine> アクティビティを <xref:System.ServiceModel.Activities.Send> アクティビティと <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティの間にドラッグ アンド ドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを "Client: Send complete" に設定します。</span><span class="sxs-lookup"><span data-stu-id="85e11-220">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity between the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> activities and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Send complete."</span></span>  
  
13. <span data-ttu-id="85e11-221"><xref:System.Activities.Statements.WriteLine> アクティビティを <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティの後にドラッグ アンド ドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを "Client side: Reply received = " + replyMessage に設定します。</span><span class="sxs-lookup"><span data-stu-id="85e11-221">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.ServiceModel.Activities.ReceiveReply> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client side: Reply received = " + replyMessage</span></span>  
  
14. <span data-ttu-id="85e11-222">`PrintTransactionInfo` アクティビティを <xref:System.Activities.Statements.WriteLine> アクティビティの後にドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="85e11-222">Drag and drop a `PrintTransactionInfo` activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
15. <span data-ttu-id="85e11-223"><xref:System.Activities.Statements.WriteLine> アクティビティをワークフローの末尾にドラッグ アンド ドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを "Client workflow ends" に設定します。</span><span class="sxs-lookup"><span data-stu-id="85e11-223">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the end of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client workflow ends."</span></span> <span data-ttu-id="85e11-224">完成したクライアント ワークフローは次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="85e11-224">The completed client workflow should look like the following diagram.</span></span>  
  
     ![完成したクライアントワークフロー](./media/flowing-transactions-into-and-out-of-workflow-services/client-complete-workflow.jpg)  
  
16. <span data-ttu-id="85e11-226">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="85e11-226">Build the solution.</span></span>  
  
### <a name="create-the-service-application"></a><span data-ttu-id="85e11-227">サービス アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="85e11-227">Create the Service application</span></span>  
  
1. <span data-ttu-id="85e11-228">`Service` という新しいコンソール アプリケーション プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="85e11-228">Add a new Console Application project called `Service` to the solution.</span></span> <span data-ttu-id="85e11-229">次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="85e11-229">Add references to the following assemblies:</span></span>  
  
    1. <span data-ttu-id="85e11-230">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="85e11-230">System.Activities.dll</span></span>  
  
    2. <span data-ttu-id="85e11-231">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="85e11-231">System.ServiceModel.dll</span></span>  
  
    3. <span data-ttu-id="85e11-232">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="85e11-232">System.ServiceModel.Activities.dll</span></span>  
  
2. <span data-ttu-id="85e11-233">生成された Program.cs ファイルを開き、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="85e11-233">Open the generated Program.cs file and the following code:</span></span>  
  
    ```csharp
          static void Main()  
          {  
              Console.WriteLine("Building the server.");  
              using (WorkflowServiceHost host = new WorkflowServiceHost(new DeclarativeServiceWorkflow(), new Uri("net.tcp://localhost:8000/TransactedReceiveService/Declarative")))  
              {                
                  //Start the server  
                  host.Open();  
                  Console.WriteLine("Service started.");  
  
                  Console.WriteLine();  
                  Console.ReadLine();  
                  //Shutdown  
                  host.Close();  
              };         
          }  
    ```  
  
3. <span data-ttu-id="85e11-234">次の app.config ファイルをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="85e11-234">Add the following app.config file to the project.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <!-- Copyright © Microsoft Corporation.  All rights reserved. -->  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding transactionFlow="true" />  
                </netTcpBinding>  
            </bindings>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="create-the-client-application"></a><span data-ttu-id="85e11-235">クライアント アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="85e11-235">Create the client application</span></span>  
  
1. <span data-ttu-id="85e11-236">`Client` という新しいコンソール アプリケーション プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="85e11-236">Add a new Console Application project called `Client` to the solution.</span></span> <span data-ttu-id="85e11-237">System.Activities.dll への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="85e11-237">Add a reference to System.Activities.dll.</span></span>  
  
2. <span data-ttu-id="85e11-238">program.cs ファイルを開き、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="85e11-238">Open the program.cs file and add the following code.</span></span>  
  
    ```csharp
    class Program  
    {  

        private static AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
        static void Main(string[] args)  
        {  
            //Build client  
            Console.WriteLine("Building the client.");  
            WorkflowApplication client = new WorkflowApplication(new DeclarativeClientWorkflow());  
            client.Completed = Program.Completed;  
            client.Aborted = Program.Aborted;  
            client.OnUnhandledException = Program.OnUnhandledException;  
            //Wait for service to start  
            Console.WriteLine("Press ENTER once service is started.");  
            Console.ReadLine();  
  
            //Start the client              
            Console.WriteLine("Starting the client.");  
            client.Run();  
            syncEvent.WaitOne();  
  
            //Sample complete  
            Console.WriteLine();  
            Console.WriteLine("Client complete. Press ENTER to exit.");  
            Console.ReadLine();  
        }  
  
        private static void Completed(WorkflowApplicationCompletedEventArgs e)  
        {  
            Program.syncEvent.Set();  
        }  
  
        private static void Aborted(WorkflowApplicationAbortedEventArgs e)  
        {  
            Console.WriteLine("Client Aborted: {0}", e.Reason);  
            Program.syncEvent.Set();  
        }  
  
        private static UnhandledExceptionAction OnUnhandledException(WorkflowApplicationUnhandledExceptionEventArgs e)  
        {  
            Console.WriteLine("Client had an unhandled exception: {0}", e.UnhandledException);  
            return UnhandledExceptionAction.Cancel;  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="85e11-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="85e11-239">See also</span></span>

- [<span data-ttu-id="85e11-240">ワークフロー サービス</span><span class="sxs-lookup"><span data-stu-id="85e11-240">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="85e11-241">Windows Communication Foundation のトランザクションの概要</span><span class="sxs-lookup"><span data-stu-id="85e11-241">Windows Communication Foundation Transactions Overview</span></span>](../../../../docs/framework/wcf/feature-details/transactions-overview.md)
