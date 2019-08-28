---
title: ドキュメント承認プロセス
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: 20167cd1c06c2ae57dfe48fd07ab3a0e2adf9927
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038226"
---
# <a name="document-approval-process"></a><span data-ttu-id="099e6-102">ドキュメント承認プロセス</span><span class="sxs-lookup"><span data-stu-id="099e6-102">Document Approval Process</span></span>

<span data-ttu-id="099e6-103">このサンプルでは、多くの Windows Workflow Foundation (WF) および Windows Communication Foundation (WCF) 機能を一緒に使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="099e6-103">This sample demonstrates the use of many Windows Workflow Foundation (WF) and Windows Communication Foundation (WCF) features together.</span></span> <span data-ttu-id="099e6-104">ドキュメント承認プロセスのシナリオを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="099e6-104">Together they implement a document approval process scenario.</span></span> <span data-ttu-id="099e6-105">クライアント アプリケーションでは、承認の必要なドキュメントを送信したり、ドキュメントを承認したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="099e6-105">A client application can submit documents for approval and approve documents.</span></span> <span data-ttu-id="099e6-106">クライアント間の通信を促進したり承認プロセスのルールを適用したりするための承認マネージャー アプリケーションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="099e6-106">An approval manager application exists to facilitate communications between clients and to enforce the rules of the approval process.</span></span> <span data-ttu-id="099e6-107">この承認プロセスは、複数の種類の承認を実行できるワークフローで、</span><span class="sxs-lookup"><span data-stu-id="099e6-107">The approval process is a workflow that can execute several types of approval.</span></span> <span data-ttu-id="099e6-108">単一承認、定足数承認 (承認者全体のパーセンテージ)、および複合承認 (定足数承認と単一承認のシーケンスから成る承認) を得るためのアクティビティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="099e6-108">Activities exist to get a single approval, a quorum approval (a percentage of set of approvers), and a complex approval process that consists of a quorum and single approval in a sequence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="099e6-109">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="099e6-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="099e6-110">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="099e6-110">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="099e6-111">このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780)にアクセスして、すべての[!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (wcf) とサンプルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="099e6-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="099e6-112">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-112">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`

## <a name="sample-details"></a><span data-ttu-id="099e6-113">サンプルの詳細</span><span class="sxs-lookup"><span data-stu-id="099e6-113">Sample Details</span></span>

<span data-ttu-id="099e6-114">次の図は、ドキュメント承認プロセスのワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="099e6-114">The following graphic demonstrates the document approval process workflow:</span></span>

![ドキュメント承認プロセスのワークフロー](./media/document-approval-process/document-approval-process.jpg)

<span data-ttu-id="099e6-116">クライアントから見た場合、承認プロセスは次のように機能します。</span><span class="sxs-lookup"><span data-stu-id="099e6-116">From the client's perspective, the approval process functions as follows:</span></span>

1. <span data-ttu-id="099e6-117">クライアントが承認プロセス システムに定期受信します。</span><span class="sxs-lookup"><span data-stu-id="099e6-117">A client subscribes to be a user in the approval process system.</span></span>

2. <span data-ttu-id="099e6-118">WCF クライアントは、承認マネージャーアプリケーションによってホストされる WCF サービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="099e6-118">A WCF client sends to a WCF service hosted by the approval manager application.</span></span>

3. <span data-ttu-id="099e6-119">一意のユーザー ID がクライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-119">A unique user ID is returned to the client.</span></span> <span data-ttu-id="099e6-120">これで、クライアントが承認プロセスに参加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="099e6-120">The client can now participate in approval processes.</span></span>

4. <span data-ttu-id="099e6-121">プロセスに参加したクライアントは、単一、定足数、または複合の承認プロセスを使用して、承認の必要なドキュメントを送信できます。</span><span class="sxs-lookup"><span data-stu-id="099e6-121">Once joined, a client can send a document for approval using single, quorum or complex approval processes.</span></span>

5. <span data-ttu-id="099e6-122">クライアントのインターフェイスにあるボタンをクリックすると、クライアントのワークフロー サービス ホストでワークフロー インスタンスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-122">A button in the client’s interface is clicked, starting a workflow instance in a client Workflow Service Host.</span></span>

6. <span data-ttu-id="099e6-123">ワークフローが承認マネージャー アプリケーションに承認要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="099e6-123">The workflow sends an approval request to the approval manager application.</span></span>

7. <span data-ttu-id="099e6-124">ワークフロー マネージャーの側でも、承認プロセスを表すワークフローが開始されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-124">The workflow manager starts a workflow on its own side to represent an approval process.</span></span>

8. <span data-ttu-id="099e6-125">マネージャーの承認ワークフローが実行されると、結果がクライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-125">Once the manager approval workflow executes, the results are sent back to the client.</span></span>

9. <span data-ttu-id="099e6-126">結果がクライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-126">The client displays the results.</span></span>

10. <span data-ttu-id="099e6-127">クライアントは、いつでも承認要求を受信してその要求に応答できます。</span><span class="sxs-lookup"><span data-stu-id="099e6-127">A client may receive an approval request and respond to the request at any point in time.</span></span>

11. <span data-ttu-id="099e6-128">クライアントでホストされている WCF サービスは、承認マネージャーアプリケーションから承認要求を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="099e6-128">A WCF service hosted on the client can receive an approval request from the approval manager application.</span></span>

12. <span data-ttu-id="099e6-129">ドキュメントの情報がレビューのためにクライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-129">The document information is presented on the client for review.</span></span>

13. <span data-ttu-id="099e6-130">ユーザーは、そのドキュメントを承認することも却下することもできます。</span><span class="sxs-lookup"><span data-stu-id="099e6-130">The user can approve or reject the document.</span></span>

14. <span data-ttu-id="099e6-131">承認応答を承認マネージャーアプリケーションに返信するために、WCF クライアントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-131">A WCF client is used to send an approval response back to the approval manager application.</span></span>

<span data-ttu-id="099e6-132">承認マネージャー アプリケーションから見た場合、承認プロセスは次のように機能します。</span><span class="sxs-lookup"><span data-stu-id="099e6-132">From the approval manager application’s point of view, the approval process functions as follows:</span></span>

1. <span data-ttu-id="099e6-133">クライアントが承認プロセス システムへの参加を要求します。</span><span class="sxs-lookup"><span data-stu-id="099e6-133">A client requests to participate to the approval process system.</span></span>

2. <span data-ttu-id="099e6-134">承認マネージャーの WCF サービスは、承認プロセスシステムの一部として要求を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="099e6-134">A WCF service on the approval manager receives a request to be part of the approval process system.</span></span>

3. <span data-ttu-id="099e6-135">クライアントに対して一意の ID が生成され、</span><span class="sxs-lookup"><span data-stu-id="099e6-135">A unique ID is generated for the client.</span></span> <span data-ttu-id="099e6-136">ユーザー情報がデータベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-136">The user information is stored in a database.</span></span>

4. <span data-ttu-id="099e6-137">一意の ID がユーザーに返されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-137">The unique ID is sent back to the user.</span></span>

5. <span data-ttu-id="099e6-138">承認要求が受信されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-138">An approval request is receive.</span></span> <span data-ttu-id="099e6-139">承認マネージャーが承認プロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="099e6-139">The approval manager executes an approval process.</span></span>

6. <span data-ttu-id="099e6-140">承認要求が承認マネージャーによって受信されると、新しいワークフローが開始されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-140">An approval request is received by the approval manager, starting a new workflow.</span></span>

7. <span data-ttu-id="099e6-141">要求の種類 (単一、定足数、または複合) に応じて異なるアクティビティが実行されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-141">Depending on the type of request (simple, quorum, or complex) a different activity is executed.</span></span>

8. <span data-ttu-id="099e6-142">相関関係を持つ Send アクティビティと Receive アクティビティを使用して、承認要求がレビューのためにクライアントに送信され、応答が受信されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-142">Send and Receive activities with correlation are used to send the approval request to the client for review and receive the response.</span></span>

9. <span data-ttu-id="099e6-143">承認プロセス ワークフローの結果がクライアントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-143">The result of the approval process workflow is sent to the client.</span></span>

## <a name="using-the-sample"></a><span data-ttu-id="099e6-144">サンプルの使用</span><span class="sxs-lookup"><span data-stu-id="099e6-144">Using the Sample</span></span>

##### <a name="to-set-up-the-database"></a><span data-ttu-id="099e6-145">データベースを設定するには</span><span class="sxs-lookup"><span data-stu-id="099e6-145">To set up the database</span></span>

1. <span data-ttu-id="099e6-146">管理者特権で Visual Studio 2010 コマンドプロンプトを開き、この DocumentApprovalProcess フォルダーに移動して、Setup.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="099e6-146">From a Visual Studio 2010 command prompt opened with Administrator privileges, navigate to this DocumentApprovalProcess folder and run Setup.cmd.</span></span>

##### <a name="to-set-up-the-application"></a><span data-ttu-id="099e6-147">アプリケーションを設定するには</span><span class="sxs-lookup"><span data-stu-id="099e6-147">To set up the application</span></span>

1. <span data-ttu-id="099e6-148">Visual Studio 2010 を使用して、DocumentApprovalProcess. .sln ソリューションファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="099e6-148">Using Visual Studio 2010, open the DocumentApprovalProcess.sln solution file.</span></span>

2. <span data-ttu-id="099e6-149">ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="099e6-149">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="099e6-150">ソリューションを実行するには、**ソリューションエクスプローラー**で approvalmanager プロジェクトを右クリックし、右クリックメニューから [**デバッグ**->] [新しいインスタンス] の順にクリックして、承認マネージャーアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="099e6-150">To run the solution, launch the Approval Manager Application by right-clicking the ApprovalManager project in the **Solution Explorer** and clicking **Debug**->**Start** new instance from the right-click menu.</span></span>

    <span data-ttu-id="099e6-151">準備完了のメッセージが表示されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="099e6-151">Wait for the manager’s output to let you know that it is ready.</span></span>

##### <a name="to-run-the-single-approval-scenario"></a><span data-ttu-id="099e6-152">単一承認のシナリオを実行するには</span><span class="sxs-lookup"><span data-stu-id="099e6-152">To run the single approval scenario</span></span>

1. <span data-ttu-id="099e6-153">管理者のアクセス許可を使用してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="099e6-153">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="099e6-154">ソリューションが含まれているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="099e6-154">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="099e6-155">ApprovalClient\Bin\Debug フォルダーに移動して、ApprovalClient.exe のインスタンスを 2 つ実行します。</span><span class="sxs-lookup"><span data-stu-id="099e6-155">Navigate to the ApprovalClient\Bin\Debug folder and execute two instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="099e6-156">**[検出]** をクリックし、 **[サブスクライブ]** ボタンが有効になるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="099e6-156">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="099e6-157">任意のユーザー名を入力し、 **[サブスクライブ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="099e6-157">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="099e6-158">一方のクライアントに対しては "`UserType1`" を使用し、もう一方のクライアントに対しては "`UserType2`" を使用します。</span><span class="sxs-lookup"><span data-stu-id="099e6-158">For one client, use `UserType1` and the other type `UserType2`.</span></span>

6. <span data-ttu-id="099e6-159">`UserType1` クライアントで、ドロップダウン メニューから単一承認を選択し、ドキュメントの名前と内容を入力します。</span><span class="sxs-lookup"><span data-stu-id="099e6-159">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="099e6-160">**[Request Approval]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="099e6-160">Click **Request Approval**.</span></span>

7. <span data-ttu-id="099e6-161">`UserType2` クライアントに承認待ちのドキュメントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-161">In the `UserType2` client, a document awaiting approval appears.</span></span> <span data-ttu-id="099e6-162">それを選択し、 **[承認]** または **[拒否]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="099e6-162">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="099e6-163">`UserType1` クライアントに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-163">The results should show in the `UserType1` client.</span></span>

##### <a name="to-run-the-quorum-approval-scenario"></a><span data-ttu-id="099e6-164">定足数承認のシナリオを実行するには</span><span class="sxs-lookup"><span data-stu-id="099e6-164">To run the quorum approval scenario</span></span>

1. <span data-ttu-id="099e6-165">管理者のアクセス許可を使用してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="099e6-165">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="099e6-166">ソリューションが含まれているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="099e6-166">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="099e6-167">ApprovalClient\Bin\Debug フォルダーに移動して、ApprovalClient.exe のインスタンスを 3 つ実行します。</span><span class="sxs-lookup"><span data-stu-id="099e6-167">Navigate to the ApprovalClient\Bin\Debug folder and execute three instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="099e6-168">**[検出]** をクリックし、 **[サブスクライブ]** ボタンが有効になるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="099e6-168">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="099e6-169">任意のユーザー名を入力し、 **[サブスクライブ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="099e6-169">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="099e6-170">1 つのクライアントに対しては "`UserType1`" を使用し、残りの 2 つのクライアントに対しては "`UserType2`" を使用します。</span><span class="sxs-lookup"><span data-stu-id="099e6-170">For one client use `UserType1` and the other two type `UserType2`.</span></span>

6. <span data-ttu-id="099e6-171">`UserType1` クライアントで、ドロップダウン メニューから定足数承認を選択し、ドキュメントの名前と内容を入力します。</span><span class="sxs-lookup"><span data-stu-id="099e6-171">In the `UserType1` client, select the quorum approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="099e6-172">**[Request Approval]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="099e6-172">Click **Request Approval**.</span></span> <span data-ttu-id="099e6-173">これにより、2 つの `UserType2` クライアントが、ドキュメントを承認または却下するように要求されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-173">This requests that the two `UserType2` clients approve or reject the document.</span></span> <span data-ttu-id="099e6-174">両方の `UserType2` クライアントが応答する必要がありますが、いずれか一方のクライアントが承認すればドキュメントは承認されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-174">While both `UserType2` clients must respond, only one client must approve the document for it to be approved.</span></span>

7. <span data-ttu-id="099e6-175">2 つの `UserType2` クライアントに承認待ちのドキュメントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-175">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="099e6-176">それを選択し、 **[承認]** または **[拒否]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="099e6-176">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="099e6-177">`UserType1` クライアントに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-177">The results should show in the `UserType1` client.</span></span>

##### <a name="to-run-the-complex-approval-scenario"></a><span data-ttu-id="099e6-178">複合承認のシナリオを実行するには</span><span class="sxs-lookup"><span data-stu-id="099e6-178">To run the complex approval scenario</span></span>

1. <span data-ttu-id="099e6-179">管理者のアクセス許可を使用してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="099e6-179">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="099e6-180">ソリューションが含まれているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="099e6-180">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="099e6-181">ApprovalClient\Bin\Debug フォルダーに移動して、ApprovalClient.exe のインスタンスを 4 つ実行します。</span><span class="sxs-lookup"><span data-stu-id="099e6-181">Navigate to the ApprovalClient\Bin\Debug folder and execute four instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="099e6-182">**[検出]** をクリックし、 **[サブスクライブ]** ボタンが有効になるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="099e6-182">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="099e6-183">任意のユーザー名を入力し、 **[サブスクライブ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="099e6-183">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="099e6-184">1 つのクライアントに対して "`UserType1`" を、2 つのクライアントに対して "`UserType2`" を、最後のクライアントに対して "`UserType3`" を使用します。</span><span class="sxs-lookup"><span data-stu-id="099e6-184">For one client use `UserType1`, in two uses type `UserType2`, and in the last use `UserType3`.</span></span>

6. <span data-ttu-id="099e6-185">`UserType1` クライアントで、ドロップダウン メニューから単一承認を選択し、ドキュメントの名前と内容を入力します。</span><span class="sxs-lookup"><span data-stu-id="099e6-185">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="099e6-186">**[Request Approval]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="099e6-186">Click **Request Approval**.</span></span>

7. <span data-ttu-id="099e6-187">2 つの `UserType2` クライアントに承認待ちのドキュメントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-187">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="099e6-188">これを選択して **[承認]** を押すと、 `UserType3`ドキュメントがクライアントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-188">Select it and press **approve**, the document is passed to the `UserType3` client.</span></span>

    <span data-ttu-id="099e6-189">ドキュメントは、最初の `UserType2` クライアントの定足数によって承認されると `UserType3` クライアントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-189">If the document is approved by the first `UserType2` quorum, the document is passed to the `UserType3` client.</span></span>

8. <span data-ttu-id="099e6-190">`UserType3` クライアントでドキュメントを承認または却下します。</span><span class="sxs-lookup"><span data-stu-id="099e6-190">Approve or reject the document from the `UserType3` client.</span></span> <span data-ttu-id="099e6-191">`UserType1` クライアントに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="099e6-191">The results should show in the `UserType1` client.</span></span>

##### <a name="to-clean-up"></a><span data-ttu-id="099e6-192">クリーンアップするには</span><span class="sxs-lookup"><span data-stu-id="099e6-192">To clean up</span></span>

1. <span data-ttu-id="099e6-193">Visual Studio 2010 のコマンドプロンプトで、DocumentApprovalProcess フォルダーに移動し、Cleanup を実行します。</span><span class="sxs-lookup"><span data-stu-id="099e6-193">From a Visual Studio 2010 command prompt, navigate to the DocumentApprovalProcess folder and run Cleanup.cmd.</span></span>
