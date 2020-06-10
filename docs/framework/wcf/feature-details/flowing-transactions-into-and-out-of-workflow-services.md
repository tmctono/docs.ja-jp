---
title: ワークフロー サービスへのトランザクションのフロー
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: 17c05139b5977c47e20e888e436a311ba145018a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597463"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a><span data-ttu-id="ea513-102">ワークフロー サービスへのトランザクションのフロー</span><span class="sxs-lookup"><span data-stu-id="ea513-102">Flowing Transactions into and out of Workflow Services</span></span>
<span data-ttu-id="ea513-103">ワークフロー サービスとワークフロー クライアントはトランザクションに参加できます。</span><span class="sxs-lookup"><span data-stu-id="ea513-103">Workflow services and clients can participate in transactions.</span></span>  <span data-ttu-id="ea513-104">サービス操作をアンビエント トランザクションの一部にするには、<xref:System.ServiceModel.Activities.Receive> アクティビティを <xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティの中に配置します。</span><span class="sxs-lookup"><span data-stu-id="ea513-104">For a service operation to become part of an ambient transaction, place a <xref:System.ServiceModel.Activities.Receive> activity within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="ea513-105"><xref:System.ServiceModel.Activities.Send> 内の <xref:System.ServiceModel.Activities.SendReply> または <xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティによる呼び出しが行われると、アンビエント トランザクション内でも呼び出しが行われます。</span><span class="sxs-lookup"><span data-stu-id="ea513-105">Any calls made by a <xref:System.ServiceModel.Activities.Send> or a <xref:System.ServiceModel.Activities.SendReply> activity within the <xref:System.ServiceModel.Activities.TransactedReceiveScope> will also be made within the ambient transaction.</span></span> <span data-ttu-id="ea513-106">ワークフロー クライアント アプリケーションでは、<xref:System.Activities.Statements.TransactionScope> アクティビティを使用してアンビエント トランザクションを作成し、そのアンビエント トランザクションを使用してサービス操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ea513-106">A workflow client application can create an ambient transaction by using the <xref:System.Activities.Statements.TransactionScope> activity and call service operations using the ambient transaction.</span></span> <span data-ttu-id="ea513-107">ここでは、トランザクションに参加するワークフロー サービスとワークフロー クライアントを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea513-107">This topic walks you through creating a workflow service and workflow client that participate in transactions.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="ea513-108">ワークフローサービスインスタンスがトランザクション内に読み込まれ、ワークフローにアクティビティが含まれている場合、ワークフローインスタンスは、 <xref:System.Activities.Statements.Persist> トランザクションがタイムアウトするまでブロックします。</span><span class="sxs-lookup"><span data-stu-id="ea513-108">If a workflow service instance is loaded within a transaction and the workflow contains a <xref:System.Activities.Statements.Persist> activity, the workflow instance will block until the transaction times out.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ea513-109"><xref:System.ServiceModel.Activities.TransactedReceiveScope> を使用する場合は、ワークフロー内のすべての受信を <xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティに配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ea513-109">Whenever you use a <xref:System.ServiceModel.Activities.TransactedReceiveScope> it is recommended to place all Receives in the workflow within <xref:System.ServiceModel.Activities.TransactedReceiveScope> activities.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ea513-110"><xref:System.ServiceModel.Activities.TransactedReceiveScope> を使用して、メッセージが不適切な順序で到着する場合、最初の順序を無視したメッセージを配信しようとするとワークフローは中止されます。</span><span class="sxs-lookup"><span data-stu-id="ea513-110">When using <xref:System.ServiceModel.Activities.TransactedReceiveScope> and messages arrive in the incorrect order, the workflow will be aborted when trying to deliver the first out of order message.</span></span> <span data-ttu-id="ea513-111">ワークフローがアイドル状態である場合、ワークフローは常に一致する停止ポイントにあるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea513-111">You must make sure your workflow is always at a consistent stopping point when the workflow idles.</span></span> <span data-ttu-id="ea513-112">これによって、ワークフローが中止された場合、前の永続性ポイントからワークフローを再開することができます。</span><span class="sxs-lookup"><span data-stu-id="ea513-112">This will allow you to restart the workflow from a previous persistence point should the workflow be aborted.</span></span>  
  
### <a name="create-a-shared-library"></a><span data-ttu-id="ea513-113">共有ライブラリの作成</span><span class="sxs-lookup"><span data-stu-id="ea513-113">Create a shared library</span></span>  
  
1. <span data-ttu-id="ea513-114">新しい空の Visual Studio ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea513-114">Create a new empty Visual Studio Solution.</span></span>  
  
2. <span data-ttu-id="ea513-115">`Common` という新しいクラス ライブラリ プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="ea513-115">Add a new class library project called `Common`.</span></span> <span data-ttu-id="ea513-116">次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="ea513-116">Add references to the following assemblies:</span></span>  
  
    - <span data-ttu-id="ea513-117">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="ea513-117">System.Activities.dll</span></span>  
  
    - <span data-ttu-id="ea513-118">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="ea513-118">System.ServiceModel.dll</span></span>  
  
    - <span data-ttu-id="ea513-119">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="ea513-119">System.ServiceModel.Activities.dll</span></span>  
  
    - <span data-ttu-id="ea513-120">System.Transactions.dll</span><span class="sxs-lookup"><span data-stu-id="ea513-120">System.Transactions.dll</span></span>  
  
3. <span data-ttu-id="ea513-121">`PrintTransactionInfo` という新しいクラスを `Common` プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="ea513-121">Add a new class called `PrintTransactionInfo` to the `Common` project.</span></span> <span data-ttu-id="ea513-122">このクラスは <xref:System.Activities.NativeActivity> の派生クラスで、<xref:System.Activities.NativeActivity.Execute%2A> メソッドをオーバーロードします。</span><span class="sxs-lookup"><span data-stu-id="ea513-122">This class is derived from <xref:System.Activities.NativeActivity> and overloads the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>  
  
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
  
     <span data-ttu-id="ea513-123">これは、アンビエント トランザクションに関する情報を表示するネイティブ アクティビティで、ここで使用するサービス ワークフローとクライアント ワークフローの両方で使用されます。</span><span class="sxs-lookup"><span data-stu-id="ea513-123">This is a native activity that displays information about the ambient transaction and is used in both the service and client workflows used in this topic.</span></span> <span data-ttu-id="ea513-124">ソリューションをビルドして、このアクティビティを**ツールボックス**の [**共通**] セクションで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ea513-124">Build the solution to make this activity available in the **Common** section of the **Toolbox**.</span></span>  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="ea513-125">ワークフロー サービスの実装</span><span class="sxs-lookup"><span data-stu-id="ea513-125">Implement the workflow service</span></span>  
  
1. <span data-ttu-id="ea513-126">という新しい WCF ワークフローサービスを `WorkflowService` プロジェクトに追加し `Common` ます。</span><span class="sxs-lookup"><span data-stu-id="ea513-126">Add a new WCF Workflow Service, called `WorkflowService` to the `Common` project.</span></span> <span data-ttu-id="ea513-127">これを行うには、プロジェクトを右クリックし、[ `Common` **追加**]、[**新しい項目**] の順に選択し、[**インストールされたテンプレート**] で [**ワークフロー** ] を選択して、[ **WCF workflow Service**] を選択します</span><span class="sxs-lookup"><span data-stu-id="ea513-127">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **WCF Workflow Service**.</span></span>  
  
     ![ワークフロー サービスの追加](./media/flowing-transactions-into-and-out-of-workflow-services/add-workflow-service.jpg)  
  
2. <span data-ttu-id="ea513-129">既定の `ReceiveRequest` アクティビティと `SendResponse` アクティビティを削除します。</span><span class="sxs-lookup"><span data-stu-id="ea513-129">Delete the default `ReceiveRequest` and `SendResponse` activities.</span></span>  
  
3. <span data-ttu-id="ea513-130"><xref:System.Activities.Statements.WriteLine> アクティビティを `Sequential Service` アクティビティにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="ea513-130">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity into the `Sequential Service` activity.</span></span> <span data-ttu-id="ea513-131">次の例に示すように、Text プロパティを `"Workflow Service starting ..."` に設定します。</span><span class="sxs-lookup"><span data-stu-id="ea513-131">Set the text property to `"Workflow Service starting ..."` as shown in the following example.</span></span>  
  
     <span data-ttu-id="ea513-132">![シーケンシャルサービスアクティビティへの WriteLine アクティビティの追加 (./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-sequential-service.jpg)</span><span class="sxs-lookup"><span data-stu-id="ea513-132">![Adding a WriteLine activity to the Sequential Service activity(./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-sequential-service.jpg)</span></span>  
  
4. <span data-ttu-id="ea513-133"><xref:System.ServiceModel.Activities.TransactedReceiveScope> を <xref:System.Activities.Statements.WriteLine> アクティビティの後にドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="ea513-133">Drag and drop a <xref:System.ServiceModel.Activities.TransactedReceiveScope> after the <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="ea513-134">アクティビティは、 <xref:System.ServiceModel.Activities.TransactedReceiveScope> **ツールボックス**の [**メッセージング**] セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="ea513-134">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity can be found in the **Messaging** section of the **Toolbox**.</span></span> <span data-ttu-id="ea513-135"><xref:System.ServiceModel.Activities.TransactedReceiveScope>アクティビティは、**要求**と**本文**の2つのセクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="ea513-135">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity is composed of two sections **Request** and **Body**.</span></span> <span data-ttu-id="ea513-136">**要求**セクションには、アクティビティが含まれてい <xref:System.ServiceModel.Activities.Receive> ます。</span><span class="sxs-lookup"><span data-stu-id="ea513-136">The **Request** section contains the <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="ea513-137">**Body**セクションには、メッセージを受信した後にトランザクション内で実行されるアクティビティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ea513-137">The **Body** section contains the activities to execute within a transaction after a message has been received.</span></span>  
  
     ![TransactedReceiveScope アクティビティの追加](./media/flowing-transactions-into-and-out-of-workflow-services/transactedreceivescope-activity.jpg)  
  
5. <span data-ttu-id="ea513-139">アクティビティを選択し <xref:System.ServiceModel.Activities.TransactedReceiveScope> 、[**変数**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea513-139">Select the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity and click the **Variables** button.</span></span> <span data-ttu-id="ea513-140">次の変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="ea513-140">Add the following variables.</span></span>  
  
     ![TransactedReceiveScope への変数の追加](./media/flowing-transactions-into-and-out-of-workflow-services/add-transactedreceivescope-variables.jpg)  
  
    > [!NOTE]
    > <span data-ttu-id="ea513-142">既定で含まれているデータ変数は削除してかまいません。</span><span class="sxs-lookup"><span data-stu-id="ea513-142">You can delete the data variable that is there by default.</span></span> <span data-ttu-id="ea513-143">既存のハンドル変数を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea513-143">You can also use the existing handle variable.</span></span>  
  
6. <span data-ttu-id="ea513-144">アクティビティを <xref:System.ServiceModel.Activities.Receive> アクティビティの**Request**セクション内にドラッグアンドドロップし <xref:System.ServiceModel.Activities.TransactedReceiveScope> ます。</span><span class="sxs-lookup"><span data-stu-id="ea513-144">Drag and drop a <xref:System.ServiceModel.Activities.Receive> activity within the **Request** section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="ea513-145">次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ea513-145">Set the following properties:</span></span>  
  
    |<span data-ttu-id="ea513-146">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ea513-146">Property</span></span>|<span data-ttu-id="ea513-147">値</span><span class="sxs-lookup"><span data-stu-id="ea513-147">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="ea513-148">CanCreateInstance</span><span class="sxs-lookup"><span data-stu-id="ea513-148">CanCreateInstance</span></span>|<span data-ttu-id="ea513-149">True (チェック ボックスをオンにする)</span><span class="sxs-lookup"><span data-stu-id="ea513-149">True (check the checkbox)</span></span>|  
    |<span data-ttu-id="ea513-150">OperationName</span><span class="sxs-lookup"><span data-stu-id="ea513-150">OperationName</span></span>|<span data-ttu-id="ea513-151">StartSample</span><span class="sxs-lookup"><span data-stu-id="ea513-151">StartSample</span></span>|  
    |<span data-ttu-id="ea513-152">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="ea513-152">ServiceContractName</span></span>|<span data-ttu-id="ea513-153">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="ea513-153">ITransactionSample</span></span>|  
  
     <span data-ttu-id="ea513-154">ワークフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ea513-154">The workflow should look like this:</span></span>  
  
     ![Receive アクティビティの追加](./media/flowing-transactions-into-and-out-of-workflow-services/add-receive-activity.jpg)  
  
7. <span data-ttu-id="ea513-156">アクティビティの [**定義...** ] リンクをクリックし、 <xref:System.ServiceModel.Activities.Receive> 次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="ea513-156">Click the **Define...** link in the <xref:System.ServiceModel.Activities.Receive> activity and make the following settings:</span></span>  
  
     ![Receive アクティビティのメッセージ設定を設定する](./media/flowing-transactions-into-and-out-of-workflow-services/receive-message-settings.jpg)  
  
8. <span data-ttu-id="ea513-158"><xref:System.Activities.Statements.Sequence> アクティビティを <xref:System.ServiceModel.Activities.TransactedReceiveScope> の Body セクションにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="ea513-158">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the Body section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="ea513-159"><xref:System.Activities.Statements.Sequence> アクティビティに 2 つの <xref:System.Activities.Statements.WriteLine> アクティビティをドラッグ アンド ドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを次の表のとおりに設定します。</span><span class="sxs-lookup"><span data-stu-id="ea513-159">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop two <xref:System.Activities.Statements.WriteLine> activities and set the <xref:System.Activities.Statements.WriteLine.Text%2A> properties as shown in the following table.</span></span>  
  
    |<span data-ttu-id="ea513-160">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="ea513-160">Activity</span></span>|<span data-ttu-id="ea513-161">値</span><span class="sxs-lookup"><span data-stu-id="ea513-161">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="ea513-162">1 つ目の WriteLine</span><span class="sxs-lookup"><span data-stu-id="ea513-162">1st WriteLine</span></span>|<span data-ttu-id="ea513-163">"サービス: 受信が完了しました"</span><span class="sxs-lookup"><span data-stu-id="ea513-163">"Service: Receive Completed"</span></span>|  
    |<span data-ttu-id="ea513-164">2 つ目の WriteLine</span><span class="sxs-lookup"><span data-stu-id="ea513-164">2nd WriteLine</span></span>|<span data-ttu-id="ea513-165">"Service: Received = " + requestMessage</span><span class="sxs-lookup"><span data-stu-id="ea513-165">"Service: Received = " + requestMessage</span></span>|  
  
     <span data-ttu-id="ea513-166">ワークフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ea513-166">The workflow should now look like this:</span></span>  
  
     ![WriteLine アクティビティを追加した後のシーケンス](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-writelines.jpg)  
  
9. <span data-ttu-id="ea513-168">アクティビティを、 `PrintTransactionInfo` アクティビティの本体の2番目のアクティビティの後にドラッグアンドドロップし <xref:System.Activities.Statements.WriteLine> **Body** <xref:System.ServiceModel.Activities.TransactedReceiveScope> ます。</span><span class="sxs-lookup"><span data-stu-id="ea513-168">Drag and drop the `PrintTransactionInfo` activity after the second <xref:System.Activities.Statements.WriteLine> activity in the **Body** in the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span>  
  
     ![PrintTransactionInfo を追加した後のシーケンス](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-printtransactioninfo.jpg )  
  
10. <span data-ttu-id="ea513-170"><xref:System.Activities.Statements.Assign> アクティビティを `PrintTransactionInfo` アクティビティの後にドラッグ アンド ドロップし、次の表のとおりにプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ea513-170">Drag and drop an <xref:System.Activities.Statements.Assign> activity after the `PrintTransactionInfo` activity and set its properties according to the following table.</span></span>  
  
    |<span data-ttu-id="ea513-171">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ea513-171">Property</span></span>|<span data-ttu-id="ea513-172">値</span><span class="sxs-lookup"><span data-stu-id="ea513-172">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="ea513-173">終了</span><span class="sxs-lookup"><span data-stu-id="ea513-173">To</span></span>|<span data-ttu-id="ea513-174">replyMessage</span><span class="sxs-lookup"><span data-stu-id="ea513-174">replyMessage</span></span>|  
    |<span data-ttu-id="ea513-175">値</span><span class="sxs-lookup"><span data-stu-id="ea513-175">Value</span></span>|<span data-ttu-id="ea513-176">"Service: Sending reply."</span><span class="sxs-lookup"><span data-stu-id="ea513-176">"Service: Sending reply."</span></span>|  
  
11. <span data-ttu-id="ea513-177"><xref:System.Activities.Statements.WriteLine> アクティビティを <xref:System.Activities.Statements.Assign> アクティビティの後にドラッグ アンド ドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを "Service: Begin reply" に設定します。</span><span class="sxs-lookup"><span data-stu-id="ea513-177">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.Activities.Statements.Assign> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Begin reply."</span></span>  
  
     <span data-ttu-id="ea513-178">ワークフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ea513-178">The workflow should now look like this:</span></span>  
  
     ![Assign および WriteLine の追加後](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-sbr-writeline.jpg)  
  
12. <span data-ttu-id="ea513-180">アクティビティを右クリック <xref:System.ServiceModel.Activities.Receive> し、[ **SendReply の作成**] を選択して、最後のアクティビティの後に貼り付け <xref:System.Activities.Statements.WriteLine> ます。</span><span class="sxs-lookup"><span data-stu-id="ea513-180">Right click the <xref:System.ServiceModel.Activities.Receive> activity and select **Create SendReply** and paste it after the last <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="ea513-181">アクティビティの [**定義...** ] リンクをクリックし、 `SendReplyToReceive` 次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="ea513-181">Click the **Define...** link in the `SendReplyToReceive` activity and make the following settings.</span></span>  
  
     ![応答メッセージの設定](./media/flowing-transactions-into-and-out-of-workflow-services/reply-message-settings.jpg)  
  
13. <span data-ttu-id="ea513-183">アクティビティを <xref:System.Activities.Statements.WriteLine> アクティビティの後にドラッグアンドドロップ `SendReplyToReceive` し、 <xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを "Service: Reply sent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="ea513-183">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `SendReplyToReceive` activity and set it’s <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Reply sent."</span></span>  
  
14. <span data-ttu-id="ea513-184"><xref:System.Activities.Statements.WriteLine> アクティビティをワークフローの末尾にドラッグ アンド ドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを "Service: Workflow ends, press ENTER to exit" に設定します。</span><span class="sxs-lookup"><span data-stu-id="ea513-184">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the bottom of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Workflow ends, press ENTER to exit."</span></span>  
  
     <span data-ttu-id="ea513-185">完成したサービス ワークフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ea513-185">The completed service workflow should look like this:</span></span>  
  
     ![完全なサービス ワークフロー](./media/flowing-transactions-into-and-out-of-workflow-services/service-complete-workflow.jpg)  
  
### <a name="implement-the-workflow-client"></a><span data-ttu-id="ea513-187">ワークフロー クライアントの実装</span><span class="sxs-lookup"><span data-stu-id="ea513-187">Implement the workflow client</span></span>  
  
1. <span data-ttu-id="ea513-188">`WorkflowClient` という新しい WCF ワークフロー アプリケーションを `Common` プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="ea513-188">Add a new WCF Workflow application, called `WorkflowClient` to the `Common` project.</span></span> <span data-ttu-id="ea513-189">これを行うには、プロジェクトを右クリックし、[ `Common` **追加**]、[**新しい項目**] の順に選択し、[**インストールされたテンプレート**] で [**ワークフロー** ] を選択して [**アクティビティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea513-189">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **Activity**.</span></span>  
  
     ![アクティビティ プロジェクトの追加](./media/flowing-transactions-into-and-out-of-workflow-services/add-activity-project.jpg)  
  
2. <span data-ttu-id="ea513-191"><xref:System.Activities.Statements.Sequence> アクティビティをデザイン画面にドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="ea513-191">Drag and drop a <xref:System.Activities.Statements.Sequence> activity onto the design surface.</span></span>  
  
3. <span data-ttu-id="ea513-192"><xref:System.Activities.Statements.Sequence> アクティビティを <xref:System.Activities.Statements.WriteLine> アクティビティにドラッグ アンド ドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを `"Client: Workflow starting"` に設定します。</span><span class="sxs-lookup"><span data-stu-id="ea513-192">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop a <xref:System.Activities.Statements.WriteLine> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to `"Client: Workflow starting"`.</span></span> <span data-ttu-id="ea513-193">ワークフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ea513-193">The workflow should now look like this:</span></span>  
  
     ![WriteLine アクティビティを追加する](./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-activity.jpg)  
  
4. <span data-ttu-id="ea513-195"><xref:System.Activities.Statements.TransactionScope> アクティビティを <xref:System.Activities.Statements.WriteLine> アクティビティの後にドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="ea513-195">Drag and drop a <xref:System.Activities.Statements.TransactionScope> activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  <span data-ttu-id="ea513-196"><xref:System.Activities.Statements.TransactionScope> アクティビティを選択し、[変数] をクリックして次の変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="ea513-196">Select the <xref:System.Activities.Statements.TransactionScope> activity, click the Variables button and add the following variables.</span></span>  
  
     ![TransactionScope への変数の追加](./media/flowing-transactions-into-and-out-of-workflow-services/transactionscope-variables.jpg)  
  
5. <span data-ttu-id="ea513-198"><xref:System.Activities.Statements.Sequence> アクティビティを <xref:System.Activities.Statements.TransactionScope> アクティビティの Body セクションにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="ea513-198">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the body of the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
6. <span data-ttu-id="ea513-199">`PrintTransactionInfo` アクティビティを <xref:System.Activities.Statements.Sequence> アクティビティにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="ea513-199">Drag and drop a `PrintTransactionInfo` activity within the <xref:System.Activities.Statements.Sequence></span></span>  
  
7. <span data-ttu-id="ea513-200">アクティビティを <xref:System.Activities.Statements.WriteLine> アクティビティの後にドラッグアンドドロップ `PrintTransactionInfo` し、 <xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを "Client: from Send" に設定します。</span><span class="sxs-lookup"><span data-stu-id="ea513-200">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `PrintTransactionInfo` activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Beginning Send".</span></span> <span data-ttu-id="ea513-201">ワークフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ea513-201">The workflow should now look like this:</span></span>  
  
     ![クライアントを追加しています: 送信アクティビティを開始しています](./media/flowing-transactions-into-and-out-of-workflow-services/client-add-cbs-writeline.jpg)  
  
8. <span data-ttu-id="ea513-203"><xref:System.ServiceModel.Activities.Send> アクティビティを <xref:System.Activities.Statements.Assign> アクティビティの後にドラッグ アンド ドロップし、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ea513-203">Drag and drop a <xref:System.ServiceModel.Activities.Send> activity after the <xref:System.Activities.Statements.Assign> activity and set the following properties:</span></span>  
  
    |<span data-ttu-id="ea513-204">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ea513-204">Property</span></span>|<span data-ttu-id="ea513-205">値</span><span class="sxs-lookup"><span data-stu-id="ea513-205">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="ea513-206">EndpointConfigurationName</span><span class="sxs-lookup"><span data-stu-id="ea513-206">EndpointConfigurationName</span></span>|<span data-ttu-id="ea513-207">workflowServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="ea513-207">workflowServiceEndpoint</span></span>|  
    |<span data-ttu-id="ea513-208">OperationName</span><span class="sxs-lookup"><span data-stu-id="ea513-208">OperationName</span></span>|<span data-ttu-id="ea513-209">StartSample</span><span class="sxs-lookup"><span data-stu-id="ea513-209">StartSample</span></span>|  
    |<span data-ttu-id="ea513-210">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="ea513-210">ServiceContractName</span></span>|<span data-ttu-id="ea513-211">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="ea513-211">ITransactionSample</span></span>|  
  
     <span data-ttu-id="ea513-212">ワークフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ea513-212">The workflow should now look like this:</span></span>  
  
     ![Send アクティビティのプロパティの設定](./media/flowing-transactions-into-and-out-of-workflow-services/client-send-activity-settings.jpg)  
  
9. <span data-ttu-id="ea513-214">[**定義...** ] リンクをクリックし、次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="ea513-214">Click the **Define...** link and make the following settings:</span></span>  
  
     ![Send アクティビティのメッセージの設定](./media/flowing-transactions-into-and-out-of-workflow-services/send-message-settings.jpg)  
  
10. <span data-ttu-id="ea513-216">アクティビティを右クリック <xref:System.ServiceModel.Activities.Send> し、[ **ReceiveReply の作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea513-216">Right click the <xref:System.ServiceModel.Activities.Send> activity and select **Create ReceiveReply**.</span></span> <span data-ttu-id="ea513-217"><xref:System.ServiceModel.Activities.ReceiveReply> アクティビティが <xref:System.ServiceModel.Activities.Send> アクティビティの後に自動的に配置されます。</span><span class="sxs-lookup"><span data-stu-id="ea513-217">The <xref:System.ServiceModel.Activities.ReceiveReply> activity will be automatically placed after the <xref:System.ServiceModel.Activities.Send> activity.</span></span>  
  
11. <span data-ttu-id="ea513-218">ReceiveReplyForSend アクティビティの [定義] リンクをクリックし、次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="ea513-218">Click the Define... link on the ReceiveReplyForSend activity and make the following settings:</span></span>  
  
     ![ReceiveForSend メッセージの設定](./media/flowing-transactions-into-and-out-of-workflow-services/client-reply-message-settings.jpg)  
  
12. <span data-ttu-id="ea513-220"><xref:System.Activities.Statements.WriteLine> アクティビティを <xref:System.ServiceModel.Activities.Send> アクティビティと <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティの間にドラッグ アンド ドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを "Client: Send complete" に設定します。</span><span class="sxs-lookup"><span data-stu-id="ea513-220">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity between the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> activities and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Send complete."</span></span>  
  
13. <span data-ttu-id="ea513-221"><xref:System.Activities.Statements.WriteLine> アクティビティを <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティの後にドラッグ アンド ドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを "Client side: Reply received = " + replyMessage に設定します。</span><span class="sxs-lookup"><span data-stu-id="ea513-221">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.ServiceModel.Activities.ReceiveReply> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client side: Reply received = " + replyMessage</span></span>  
  
14. <span data-ttu-id="ea513-222">`PrintTransactionInfo` アクティビティを <xref:System.Activities.Statements.WriteLine> アクティビティの後にドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="ea513-222">Drag and drop a `PrintTransactionInfo` activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
15. <span data-ttu-id="ea513-223"><xref:System.Activities.Statements.WriteLine> アクティビティをワークフローの末尾にドラッグ アンド ドロップし、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティを "Client workflow ends" に設定します。</span><span class="sxs-lookup"><span data-stu-id="ea513-223">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the end of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client workflow ends."</span></span> <span data-ttu-id="ea513-224">完成したクライアント ワークフローは次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="ea513-224">The completed client workflow should look like the following diagram.</span></span>  
  
     ![完成したクライアントワークフロー](./media/flowing-transactions-into-and-out-of-workflow-services/client-complete-workflow.jpg)  
  
16. <span data-ttu-id="ea513-226">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="ea513-226">Build the solution.</span></span>  
  
### <a name="create-the-service-application"></a><span data-ttu-id="ea513-227">サービス アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="ea513-227">Create the Service application</span></span>  
  
1. <span data-ttu-id="ea513-228">`Service` という新しいコンソール アプリケーション プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="ea513-228">Add a new Console Application project called `Service` to the solution.</span></span> <span data-ttu-id="ea513-229">次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="ea513-229">Add references to the following assemblies:</span></span>  
  
    1. <span data-ttu-id="ea513-230">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="ea513-230">System.Activities.dll</span></span>  
  
    2. <span data-ttu-id="ea513-231">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="ea513-231">System.ServiceModel.dll</span></span>  
  
    3. <span data-ttu-id="ea513-232">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="ea513-232">System.ServiceModel.Activities.dll</span></span>  
  
2. <span data-ttu-id="ea513-233">生成された Program.cs ファイルを開き、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ea513-233">Open the generated Program.cs file and the following code:</span></span>  
  
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
  
3. <span data-ttu-id="ea513-234">次の app.config ファイルをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="ea513-234">Add the following app.config file to the project.</span></span>  
  
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
  
### <a name="create-the-client-application"></a><span data-ttu-id="ea513-235">クライアント アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="ea513-235">Create the client application</span></span>  
  
1. <span data-ttu-id="ea513-236">`Client` という新しいコンソール アプリケーション プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="ea513-236">Add a new Console Application project called `Client` to the solution.</span></span> <span data-ttu-id="ea513-237">System.Activities.dll への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="ea513-237">Add a reference to System.Activities.dll.</span></span>  
  
2. <span data-ttu-id="ea513-238">program.cs ファイルを開き、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ea513-238">Open the program.cs file and add the following code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ea513-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea513-239">See also</span></span>

- [<span data-ttu-id="ea513-240">ワークフロー サービス</span><span class="sxs-lookup"><span data-stu-id="ea513-240">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="ea513-241">Windows Communication Foundation のトランザクションの概要</span><span class="sxs-lookup"><span data-stu-id="ea513-241">Windows Communication Foundation Transactions Overview</span></span>](transactions-overview.md)
