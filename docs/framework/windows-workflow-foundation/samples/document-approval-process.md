---
title: ドキュメント承認プロセス
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: dfc2e0a12d053733823427ac50066b1e4a0f97aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770400"
---
# <a name="document-approval-process"></a><span data-ttu-id="9adec-102">ドキュメント承認プロセス</span><span class="sxs-lookup"><span data-stu-id="9adec-102">Document Approval Process</span></span>
<span data-ttu-id="9adec-103">このサンプルでは、多くの Windows Workflow Foundation (WF) や Windows Communication Foundation (WCF) 機能の使用をまとめて示します。</span><span class="sxs-lookup"><span data-stu-id="9adec-103">This sample demonstrates the use of many Windows Workflow Foundation (WF) and Windows Communication Foundation (WCF) features together.</span></span> <span data-ttu-id="9adec-104">ドキュメント承認プロセスのシナリオを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9adec-104">Together they implement a document approval process scenario.</span></span> <span data-ttu-id="9adec-105">クライアント アプリケーションでは、承認の必要なドキュメントを送信したり、ドキュメントを承認したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9adec-105">A client application can submit documents for approval and approve documents.</span></span> <span data-ttu-id="9adec-106">クライアント間の通信を促進したり承認プロセスのルールを適用したりするための承認マネージャー アプリケーションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="9adec-106">An approval manager application exists to facilitate communications between clients and to enforce the rules of the approval process.</span></span> <span data-ttu-id="9adec-107">この承認プロセスは、複数の種類の承認を実行できるワークフローで、</span><span class="sxs-lookup"><span data-stu-id="9adec-107">The approval process is a workflow that can execute several types of approval.</span></span> <span data-ttu-id="9adec-108">単一承認、定足数承認 (承認者全体のパーセンテージ)、および複合承認 (定足数承認と単一承認のシーケンスから成る承認) を得るためのアクティビティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9adec-108">Activities exist to get a single approval, a quorum approval (a percentage of set of approvers), and a complex approval process that consists of a quorum and single approval in a sequence.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="9adec-109">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="9adec-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9adec-110">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9adec-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9adec-111">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="9adec-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9adec-112">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`  
  
## <a name="sample-details"></a><span data-ttu-id="9adec-113">サンプルの詳細</span><span class="sxs-lookup"><span data-stu-id="9adec-113">Sample Details</span></span>  
 <span data-ttu-id="9adec-114">次の図では、ドキュメント承認プロセスのワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="9adec-114">The following graphic demonstrates the document approval process workflow:</span></span>  
  
 ![ドキュメント承認プロセスのワークフロー](./media/document-approval-process/document-approval-process.jpg)  
  
 <span data-ttu-id="9adec-116">クライアントから見た場合、承認プロセスは次のように機能します。</span><span class="sxs-lookup"><span data-stu-id="9adec-116">From the client's perspective, the approval process functions as follows:</span></span>  
  
1. <span data-ttu-id="9adec-117">クライアントが承認プロセス システムに定期受信します。</span><span class="sxs-lookup"><span data-stu-id="9adec-117">A client subscribes to be a user in the approval process system.</span></span>  
  
2. <span data-ttu-id="9adec-118">WCF クライアントは、承認マネージャー アプリケーションによってホストされる WCF サービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="9adec-118">A WCF client sends to a WCF service hosted by the approval manager application.</span></span>  
  
3. <span data-ttu-id="9adec-119">一意のユーザー ID がクライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-119">A unique user ID is returned to the client.</span></span> <span data-ttu-id="9adec-120">これで、クライアントが承認プロセスに参加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9adec-120">The client can now participate in approval processes.</span></span>  
  
4. <span data-ttu-id="9adec-121">プロセスに参加したクライアントは、単一、定足数、または複合の承認プロセスを使用して、承認の必要なドキュメントを送信できます。</span><span class="sxs-lookup"><span data-stu-id="9adec-121">Once joined, a client can send a document for approval using single, quorum or complex approval processes.</span></span>  
  
5. <span data-ttu-id="9adec-122">クライアントのインターフェイスにあるボタンをクリックすると、クライアントのワークフロー サービス ホストでワークフロー インスタンスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-122">A button in the client’s interface is clicked, starting a workflow instance in a client Workflow Service Host.</span></span>  
  
6. <span data-ttu-id="9adec-123">ワークフローが承認マネージャー アプリケーションに承認要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="9adec-123">The workflow sends an approval request to the approval manager application.</span></span>  
  
7. <span data-ttu-id="9adec-124">ワークフロー マネージャーの側でも、承認プロセスを表すワークフローが開始されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-124">The workflow manager starts a workflow on its own side to represent an approval process.</span></span>  
  
8. <span data-ttu-id="9adec-125">マネージャーの承認ワークフローが実行されると、結果がクライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-125">Once the manager approval workflow executes, the results are sent back to the client.</span></span>  
  
9. <span data-ttu-id="9adec-126">結果がクライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-126">The client displays the results.</span></span>  
  
10. <span data-ttu-id="9adec-127">クライアントは、いつでも承認要求を受信してその要求に応答できます。</span><span class="sxs-lookup"><span data-stu-id="9adec-127">A client may receive an approval request and respond to the request at any point in time.</span></span>  
  
11. <span data-ttu-id="9adec-128">クライアントでホストされている WCF サービスは、承認マネージャー アプリケーションから、承認要求を受信できます。</span><span class="sxs-lookup"><span data-stu-id="9adec-128">A WCF service hosted on the client can receive an approval request from the approval manager application.</span></span>  
  
12. <span data-ttu-id="9adec-129">ドキュメントの情報がレビューのためにクライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-129">The document information is presented on the client for review.</span></span>  
  
13. <span data-ttu-id="9adec-130">ユーザーは、そのドキュメントを承認することも却下することもできます。</span><span class="sxs-lookup"><span data-stu-id="9adec-130">The user can approve or reject the document.</span></span>  
  
14. <span data-ttu-id="9adec-131">WCF クライアントは、承認マネージャー アプリケーションへの承認応答の送信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-131">A WCF client is used to send an approval response back to the approval manager application.</span></span>  
  
 <span data-ttu-id="9adec-132">承認マネージャー アプリケーションから見た場合、承認プロセスは次のように機能します。</span><span class="sxs-lookup"><span data-stu-id="9adec-132">From the approval manager application’s point of view, the approval process functions as follows:</span></span>  
  
1. <span data-ttu-id="9adec-133">クライアントが承認プロセス システムへの参加を要求します。</span><span class="sxs-lookup"><span data-stu-id="9adec-133">A client requests to participate to the approval process system.</span></span>  
  
2. <span data-ttu-id="9adec-134">承認マネージャーの WCF サービスでは、承認プロセス システムの一部として要求を受信します。</span><span class="sxs-lookup"><span data-stu-id="9adec-134">A WCF service on the approval manager receives a request to be part of the approval process system.</span></span>  
  
3. <span data-ttu-id="9adec-135">クライアントに対して一意の ID が生成され、</span><span class="sxs-lookup"><span data-stu-id="9adec-135">A unique ID is generated for the client.</span></span> <span data-ttu-id="9adec-136">ユーザー情報がデータベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-136">The user information is stored in a database.</span></span>  
  
4. <span data-ttu-id="9adec-137">一意の ID がユーザーに返されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-137">The unique ID is sent back to the user.</span></span>  
  
5. <span data-ttu-id="9adec-138">承認要求が受信されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-138">An approval request is receive.</span></span> <span data-ttu-id="9adec-139">承認マネージャーが承認プロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="9adec-139">The approval manager executes an approval process.</span></span>  
  
6. <span data-ttu-id="9adec-140">承認要求が承認マネージャーによって受信されると、新しいワークフローが開始されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-140">An approval request is received by the approval manager, starting a new workflow.</span></span>  
  
7. <span data-ttu-id="9adec-141">要求の種類 (単一、定足数、または複合) に応じて異なるアクティビティが実行されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-141">Depending on the type of request (simple, quorum, or complex) a different activity is executed.</span></span>  
  
8. <span data-ttu-id="9adec-142">相関関係を持つ Send アクティビティと Receive アクティビティを使用して、承認要求がレビューのためにクライアントに送信され、応答が受信されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-142">Send and Receive activities with correlation are used to send the approval request to the client for review and receive the response.</span></span>  
  
9. <span data-ttu-id="9adec-143">承認プロセス ワークフローの結果がクライアントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-143">The result of the approval process workflow is sent to the client.</span></span>  
  
## <a name="using-the-sample"></a><span data-ttu-id="9adec-144">サンプルの使用</span><span class="sxs-lookup"><span data-stu-id="9adec-144">Using the Sample</span></span>  
  
##### <a name="to-set-up-the-database"></a><span data-ttu-id="9adec-145">データベースを設定するには</span><span class="sxs-lookup"><span data-stu-id="9adec-145">To set up the database</span></span>  
  
1. <span data-ttu-id="9adec-146">管理者特権で開いた Visual Studio 2010 コマンド プロンプトでこの DocumentApprovalProcess フォルダーに移動し、Setup.cmd を実行します。</span><span class="sxs-lookup"><span data-stu-id="9adec-146">From a Visual Studio 2010 command prompt opened with Administrator privileges, navigate to this DocumentApprovalProcess folder and run Setup.cmd.</span></span>  
  
##### <a name="to-set-up-the-application"></a><span data-ttu-id="9adec-147">アプリケーションを設定するには</span><span class="sxs-lookup"><span data-stu-id="9adec-147">To set up the application</span></span>  
  
1. <span data-ttu-id="9adec-148">Visual Studio 2010 を使用して、DocumentApprovalProcess.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9adec-148">Using Visual Studio 2010, open the DocumentApprovalProcess.sln solution file.</span></span>  
  
2. <span data-ttu-id="9adec-149">ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9adec-149">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="9adec-150">ソリューションを実行するで ApprovalManager プロジェクトを右クリックして、承認マネージャー アプリケーションを起動、**ソリューション エクスプ ローラー**クリック**デバッグ**->**開始**右クリック メニューからの新しいインスタンス。</span><span class="sxs-lookup"><span data-stu-id="9adec-150">To run the solution, launch the Approval Manager Application by right-clicking the ApprovalManager project in the **Solution Explorer** and clicking **Debug**->**Start** new instance from the right-click menu.</span></span>  
  
     <span data-ttu-id="9adec-151">準備完了のメッセージが表示されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="9adec-151">Wait for the manager’s output to let you know that it is ready.</span></span>  
  
##### <a name="to-run-the-single-approval-scenario"></a><span data-ttu-id="9adec-152">単一承認のシナリオを実行するには</span><span class="sxs-lookup"><span data-stu-id="9adec-152">To run the single approval scenario</span></span>  
  
1. <span data-ttu-id="9adec-153">管理者のアクセス許可を使用してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="9adec-153">Open a command prompt with administrator permission.</span></span>  
  
2. <span data-ttu-id="9adec-154">ソリューションが含まれているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="9adec-154">Navigate to the directory that contains the solution.</span></span>  
  
3. <span data-ttu-id="9adec-155">ApprovalClient\Bin\Debug フォルダーに移動して、ApprovalClient.exe のインスタンスを 2 つ実行します。</span><span class="sxs-lookup"><span data-stu-id="9adec-155">Navigate to the ApprovalClient\Bin\Debug folder and execute two instances of ApprovalClient.exe.</span></span>  
  
4. <span data-ttu-id="9adec-156">をクリックして**検出**、まで待って、**サブスクライブ**ボタンが有効になります。</span><span class="sxs-lookup"><span data-stu-id="9adec-156">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5. <span data-ttu-id="9adec-157">任意のユーザー名を入力し、をクリックして**サブスクライブ**します。</span><span class="sxs-lookup"><span data-stu-id="9adec-157">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="9adec-158">一方のクライアントに対しては "`UserType1`" を使用し、もう一方のクライアントに対しては "`UserType2`" を使用します。</span><span class="sxs-lookup"><span data-stu-id="9adec-158">For one client, use `UserType1` and the other type `UserType2`.</span></span>  
  
6. <span data-ttu-id="9adec-159">`UserType1` クライアントで、ドロップダウン メニューから単一承認を選択し、ドキュメントの名前と内容を入力します。</span><span class="sxs-lookup"><span data-stu-id="9adec-159">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="9adec-160">クリックして**要求の承認**します。</span><span class="sxs-lookup"><span data-stu-id="9adec-160">Click **Request Approval**.</span></span>  
  
7. <span data-ttu-id="9adec-161">`UserType2` クライアントに承認待ちのドキュメントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-161">In the `UserType2` client, a document awaiting approval appears.</span></span> <span data-ttu-id="9adec-162">選択し、**承認**または**拒否**します。</span><span class="sxs-lookup"><span data-stu-id="9adec-162">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="9adec-163">`UserType1` クライアントに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-163">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-run-the-quorum-approval-scenario"></a><span data-ttu-id="9adec-164">定足数承認のシナリオを実行するには</span><span class="sxs-lookup"><span data-stu-id="9adec-164">To run the quorum approval scenario</span></span>  
  
1. <span data-ttu-id="9adec-165">管理者のアクセス許可を使用してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="9adec-165">Open a command prompt with administrator permission.</span></span>  
  
2. <span data-ttu-id="9adec-166">ソリューションが含まれているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="9adec-166">Navigate to the directory that contains the solution.</span></span>  
  
3. <span data-ttu-id="9adec-167">ApprovalClient\Bin\Debug フォルダーに移動して、ApprovalClient.exe のインスタンスを 3 つ実行します。</span><span class="sxs-lookup"><span data-stu-id="9adec-167">Navigate to the ApprovalClient\Bin\Debug folder and execute three instances of ApprovalClient.exe.</span></span>  
  
4. <span data-ttu-id="9adec-168">をクリックして**検出**、まで待って、**サブスクライブ**ボタンが有効になります。</span><span class="sxs-lookup"><span data-stu-id="9adec-168">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5. <span data-ttu-id="9adec-169">任意のユーザー名を入力し、をクリックして**サブスクライブ**します。</span><span class="sxs-lookup"><span data-stu-id="9adec-169">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="9adec-170">1 つのクライアントに対しては "`UserType1`" を使用し、残りの 2 つのクライアントに対しては "`UserType2`" を使用します。</span><span class="sxs-lookup"><span data-stu-id="9adec-170">For one client use `UserType1` and the other two type `UserType2`.</span></span>  
  
6. <span data-ttu-id="9adec-171">`UserType1` クライアントで、ドロップダウン メニューから定足数承認を選択し、ドキュメントの名前と内容を入力します。</span><span class="sxs-lookup"><span data-stu-id="9adec-171">In the `UserType1` client, select the quorum approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="9adec-172">クリックして**要求の承認**します。</span><span class="sxs-lookup"><span data-stu-id="9adec-172">Click **Request Approval**.</span></span> <span data-ttu-id="9adec-173">これにより、2 つの `UserType2` クライアントが、ドキュメントを承認または却下するように要求されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-173">This requests that the two `UserType2` clients approve or reject the document.</span></span> <span data-ttu-id="9adec-174">両方の `UserType2` クライアントが応答する必要がありますが、いずれか一方のクライアントが承認すればドキュメントは承認されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-174">While both `UserType2` clients must respond, only one client must approve the document for it to be approved.</span></span>  
  
7. <span data-ttu-id="9adec-175">2 つの `UserType2` クライアントに承認待ちのドキュメントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-175">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="9adec-176">選択し、**承認**または**拒否**します。</span><span class="sxs-lookup"><span data-stu-id="9adec-176">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="9adec-177">`UserType1` クライアントに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-177">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-run-the-complex-approval-scenario"></a><span data-ttu-id="9adec-178">複合承認のシナリオを実行するには</span><span class="sxs-lookup"><span data-stu-id="9adec-178">To run the complex approval scenario</span></span>  
  
1. <span data-ttu-id="9adec-179">管理者のアクセス許可を使用してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="9adec-179">Open a command prompt with administrator permission.</span></span>  
  
2. <span data-ttu-id="9adec-180">ソリューションが含まれているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="9adec-180">Navigate to the directory that contains the solution.</span></span>  
  
3. <span data-ttu-id="9adec-181">ApprovalClient\Bin\Debug フォルダーに移動して、ApprovalClient.exe のインスタンスを 4 つ実行します。</span><span class="sxs-lookup"><span data-stu-id="9adec-181">Navigate to the ApprovalClient\Bin\Debug folder and execute four instances of ApprovalClient.exe.</span></span>  
  
4. <span data-ttu-id="9adec-182">をクリックして**検出**、まで待って、**サブスクライブ**ボタンが有効になります。</span><span class="sxs-lookup"><span data-stu-id="9adec-182">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5. <span data-ttu-id="9adec-183">任意のユーザー名を入力し、をクリックして**サブスクライブ**します。</span><span class="sxs-lookup"><span data-stu-id="9adec-183">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="9adec-184">1 つのクライアントに対して "`UserType1`" を、2 つのクライアントに対して "`UserType2`" を、最後のクライアントに対して "`UserType3`" を使用します。</span><span class="sxs-lookup"><span data-stu-id="9adec-184">For one client use `UserType1`, in two uses type `UserType2`, and in the last use `UserType3`.</span></span>  
  
6. <span data-ttu-id="9adec-185">`UserType1` クライアントで、ドロップダウン メニューから単一承認を選択し、ドキュメントの名前と内容を入力します。</span><span class="sxs-lookup"><span data-stu-id="9adec-185">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="9adec-186">クリックして**要求の承認**します。</span><span class="sxs-lookup"><span data-stu-id="9adec-186">Click **Request Approval**.</span></span>  
  
7. <span data-ttu-id="9adec-187">2 つの `UserType2` クライアントに承認待ちのドキュメントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-187">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="9adec-188">選択し、**承認**に、ドキュメントが渡される、`UserType3`クライアント。</span><span class="sxs-lookup"><span data-stu-id="9adec-188">Select it and press **approve**, the document is passed to the `UserType3` client.</span></span>  
  
     <span data-ttu-id="9adec-189">ドキュメントは、最初の `UserType2` クライアントの定足数によって承認されると `UserType3` クライアントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-189">If the document is approved by the first `UserType2` quorum, the document is passed to the `UserType3` client.</span></span>  
  
8. <span data-ttu-id="9adec-190">`UserType3` クライアントでドキュメントを承認または却下します。</span><span class="sxs-lookup"><span data-stu-id="9adec-190">Approve or reject the document from the `UserType3` client.</span></span> <span data-ttu-id="9adec-191">`UserType1` クライアントに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9adec-191">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-clean-up"></a><span data-ttu-id="9adec-192">クリーンアップするには</span><span class="sxs-lookup"><span data-stu-id="9adec-192">To clean up</span></span>  
  
1. <span data-ttu-id="9adec-193">Visual Studio 2010 コマンド プロンプトから DocumentApprovalProcess フォルダーに移動し、Cleanup.cmd を実行します。</span><span class="sxs-lookup"><span data-stu-id="9adec-193">From a Visual Studio 2010 command prompt, navigate to the DocumentApprovalProcess folder and run Cleanup.cmd.</span></span>
