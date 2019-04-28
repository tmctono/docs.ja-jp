---
title: F# を使用した Azure Queue Storage の概要
description: Azure キューでは、アプリケーション コンポーネント間で信頼性の高い非同期メッセージングを提供します。 クラウド メッセージングにより、アプリケーションのコンポーネントを個別にスケーリングします。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 58a46dfe905a32be77a13d11df8f0544546ea0ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756378"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="d5f00-104">F を使用した Azure Queue storage を概要します。\#</span><span class="sxs-lookup"><span data-stu-id="d5f00-104">Get started with Azure Queue storage using F\#</span></span>

<span data-ttu-id="d5f00-105">Azure Queue storage は、アプリケーション コンポーネント間のクラウド メッセージングを提供します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="d5f00-106">スケールのアプリケーションを設計するには、アプリケーション コンポーネントは多くの場合、分離、それらを個別に拡張できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d5f00-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="d5f00-107">キュー ストレージは、クラウド、デスクトップ、オンプレミス サーバーでは、またはモバイル デバイスで実行されているかどうか、アプリケーション コンポーネント間の通信用の非同期メッセージングを提供します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="d5f00-108">Queue storage では、非同期タスクの管理とプロセス ワークフローの構築もサポートします。</span><span class="sxs-lookup"><span data-stu-id="d5f00-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="d5f00-109">このチュートリアルについて</span><span class="sxs-lookup"><span data-stu-id="d5f00-109">About this tutorial</span></span>

<span data-ttu-id="d5f00-110">このチュートリアルは、記述する方法を示しています。 F# Azure Queue storage を使用して一般的なタスクのコード。</span><span class="sxs-lookup"><span data-stu-id="d5f00-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="d5f00-111">作成しキューの削除し追加、読み取り、およびキュー メッセージを削除する対象のタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d5f00-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="d5f00-112">Queue storage の概念的概要についてを参照してください[queue storage .NET ガイド](/azure/storage/storage-dotnet-how-to-use-queues)します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d5f00-113">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d5f00-113">Prerequisites</span></span>

<span data-ttu-id="d5f00-114">このガイドを使用するのにはまず[Azure ストレージ アカウントを作成](/azure/storage/storage-create-storage-account)です。</span><span class="sxs-lookup"><span data-stu-id="d5f00-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="d5f00-115">このアカウントのストレージ アクセス キーも必要になります。</span><span class="sxs-lookup"><span data-stu-id="d5f00-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="d5f00-116">作成して、F# スクリプトと開始 F# 対話型</span><span class="sxs-lookup"><span data-stu-id="d5f00-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="d5f00-117">この記事のサンプルは、F# アプリケーションまたは F# スクリプトのいずれかで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5f00-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="d5f00-118">F# スクリプトを作成するには、ファイルを作成、`.fsx`拡張機能の例では、 `queues.fsx`、F# 開発環境にします。</span><span class="sxs-lookup"><span data-stu-id="d5f00-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="d5f00-119">次に、使用、[パッケージ マネージャー](package-management.md)など[パケット](https://fsprojects.github.io/Paket/)または[NuGet](https://www.nuget.org/)をインストールする、`WindowsAzure.Storage`パッケージと参照`WindowsAzure.Storage.dll`を使用して、スクリプトで`#r`ディレクティブ。</span><span class="sxs-lookup"><span data-stu-id="d5f00-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="d5f00-120">名前空間宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-120">Add namespace declarations</span></span>

<span data-ttu-id="d5f00-121">次の追加`open`ステートメントの先頭に、`queues.fsx`ファイル。</span><span class="sxs-lookup"><span data-stu-id="d5f00-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="d5f00-122">接続文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-122">Get your connection string</span></span>

<span data-ttu-id="d5f00-123">このチュートリアルでは、Azure Storage 接続文字列を必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5f00-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="d5f00-124">接続文字列の詳細については、次を参照してください。[ストレージ接続文字列を構成](/azure/storage/storage-configure-connection-string)します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="d5f00-125">チュートリアルでは、次のように、スクリプトで、接続文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="d5f00-126">ただし、これは**しないで**の実際のプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5f00-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="d5f00-127">ストレージ アカウント キーは、ストレージ アカウントの root パスワードに似ています。</span><span class="sxs-lookup"><span data-stu-id="d5f00-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="d5f00-128">常に、ストレージ アカウント キーを保護するように注意します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="d5f00-129">ハード コーディング、または他のユーザーにアクセスできるプレーン テキスト ファイルに保存することは、他のユーザーに配布しないでください。</span><span class="sxs-lookup"><span data-stu-id="d5f00-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="d5f00-130">侵害されていると思われる場合は、Azure Portal を使用して、キーを再生成することができます。</span><span class="sxs-lookup"><span data-stu-id="d5f00-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="d5f00-131">実際のアプリケーションは、ストレージ接続文字列を維持するために最善の方法は、構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d5f00-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="d5f00-132">構成ファイルから接続文字列を取得するには、は、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d5f00-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="d5f00-133">Azure Configuration Manager の使用は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d5f00-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="d5f00-134">.NET Framework のなどの API を使用することもできます。`ConfigurationManager`型。</span><span class="sxs-lookup"><span data-stu-id="d5f00-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="d5f00-135">接続文字列を解析します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-135">Parse the connection string</span></span>

<span data-ttu-id="d5f00-136">接続文字列を解析するには、次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="d5f00-137">これにより返されます、`CloudStorageAccount`します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="d5f00-138">Queue サービス クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-138">Create the Queue service client</span></span>

<span data-ttu-id="d5f00-139">`CloudQueueClient`クラスでは、Queue storage に格納されているキューを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="d5f00-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="d5f00-140">サービス クライアントを作成する方法の 1 つを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="d5f00-141">キュー ストレージからデータを読み書きするコードを記述する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="d5f00-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="d5f00-142">キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-142">Create a queue</span></span>

<span data-ttu-id="d5f00-143">この例では、存在しない場合は、キューを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="d5f00-144">キューにメッセージを挿入します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-144">Insert a message into a queue</span></span>

<span data-ttu-id="d5f00-145">既存のキューにメッセージを挿入する最初の作成、新しい`CloudQueueMessage`します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="d5f00-146">次に、呼び出し、`AddMessage`メソッド。</span><span class="sxs-lookup"><span data-stu-id="d5f00-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="d5f00-147">A `CloudQueueMessage` (utf-8 形式) の文字列にいずれかから作成できる、または`byte`、このような配列。</span><span class="sxs-lookup"><span data-stu-id="d5f00-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="d5f00-148">次のメッセージをピークします。</span><span class="sxs-lookup"><span data-stu-id="d5f00-148">Peek at the next message</span></span>

<span data-ttu-id="d5f00-149">キューの先頭にあるメッセージをピークを呼び出して、キューから削除することがなく、`PeekMessage`メソッド。</span><span class="sxs-lookup"><span data-stu-id="d5f00-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="d5f00-150">処理のための次のメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-150">Get the next message for processing</span></span>

<span data-ttu-id="d5f00-151">処理のため、キューの先頭にあるメッセージを取得するには呼び出すことによって、`GetMessage`メソッド。</span><span class="sxs-lookup"><span data-stu-id="d5f00-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="d5f00-152">使用して、メッセージを正常に処理を後で示す`DeleteMessage`します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="d5f00-153">キューに置かれたメッセージの内容を変更します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-153">Change the contents of a queued message</span></span>

<span data-ttu-id="d5f00-154">取得したメッセージでインプレースでキューの内容を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d5f00-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="d5f00-155">メッセージが作業タスクである場合は、作業のタスクの状態を更新するこの機能を使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d5f00-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="d5f00-156">次のコードでは、新しい内容で、キュー メッセージを更新し、表示タイムアウトを 60 秒延長を設定します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="d5f00-157">これは、メッセージに関連付けられた作業の状態を保存され、クライアントは、メッセージの作業を続行する時間が 1 分。</span><span class="sxs-lookup"><span data-stu-id="d5f00-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="d5f00-158">この手法は、ハードウェアまたはソフトウェアの障害により、処理手順が失敗した場合、最初からやり直すことがなく、キュー メッセージに対して複数のステップのワークフローを追跡するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5f00-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="d5f00-159">同様に、再試行回数を保持して、削除する場合は、メッセージが再試行される回数のいくつかの数よりも多く、通常、します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="d5f00-160">これは、それが処理されるたびに、アプリケーション エラーをトリガーするメッセージから保護されます。</span><span class="sxs-lookup"><span data-stu-id="d5f00-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="d5f00-161">次のメッセージをデキューします。</span><span class="sxs-lookup"><span data-stu-id="d5f00-161">De-queue the next message</span></span>

<span data-ttu-id="d5f00-162">コードは、キューの 2 つの手順でキューからメッセージ。</span><span class="sxs-lookup"><span data-stu-id="d5f00-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="d5f00-163">呼び出すと`GetMessage`キュー内の次のメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="d5f00-164">返されたメッセージ`GetMessage`このキューからメッセージを読み取る他のコードを非表示になります。</span><span class="sxs-lookup"><span data-stu-id="d5f00-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="d5f00-165">既定では、このメッセージでは 30 秒間非表示に残ります。</span><span class="sxs-lookup"><span data-stu-id="d5f00-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="d5f00-166">キューからのメッセージの削除を完了する必要がありますも呼び出す`DeleteMessage`します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="d5f00-167">メッセージを削除するには、この 2 段階プロセスでは、コードは、ハードウェアまたはソフトウェアの障害のためのメッセージの処理に失敗すると、コードの別のインスタンスは同じメッセージを取得し、もう一度お試しことを保証します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="d5f00-168">コードの呼び出し`DeleteMessage`メッセージが処理された直後します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="d5f00-169">一般的な Queue storage Api を使用して非同期ワークフロー</span><span class="sxs-lookup"><span data-stu-id="d5f00-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="d5f00-170">この例では、一般的なキュー ストレージ Api で、非同期ワークフローを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="d5f00-171">メッセージのデキューの追加オプション</span><span class="sxs-lookup"><span data-stu-id="d5f00-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="d5f00-172">キューからメッセージの取得をカスタマイズする 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="d5f00-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="d5f00-173">最初に、(最大 32 個) のメッセージのバッチを取得できます。</span><span class="sxs-lookup"><span data-stu-id="d5f00-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="d5f00-174">次に、長いまたは短いの非表示タイムアウトを設定する、詳細や、各メッセージを完全に処理にかかる時間が、コードをできるようにします。</span><span class="sxs-lookup"><span data-stu-id="d5f00-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="d5f00-175">次のコード例では`GetMessages`20 を取得する 1 つのメッセージを呼び出すし、各メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="d5f00-176">また、メッセージごとに 5 分間に非表示タイムアウトを設定します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="d5f00-177">5 分以内に、すべてのメッセージに対して同時に、同時に開始するため 5 分が経過の呼び出し以降に`GetMessages`、削除されていないすべてのメッセージが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5f00-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="d5f00-178">キューの長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-178">Get the queue length</span></span>

<span data-ttu-id="d5f00-179">キューにメッセージの数の推定値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="d5f00-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="d5f00-180">`FetchAttributes`メソッドは、メッセージ数など、キューの属性を取得する Queue サービスを要求します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="d5f00-181">`ApproximateMessageCount`によって取得された最後の値を返します、`FetchAttributes`メソッドを呼び出さずに、キュー サービス。</span><span class="sxs-lookup"><span data-stu-id="d5f00-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="d5f00-182">キューを削除します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-182">Delete a queue</span></span>

<span data-ttu-id="d5f00-183">キューおよびそれに含まれるすべてのメッセージを削除する、`Delete`キュー オブジェクトのメソッド。</span><span class="sxs-lookup"><span data-stu-id="d5f00-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="d5f00-184">次の手順</span><span class="sxs-lookup"><span data-stu-id="d5f00-184">Next steps</span></span>

<span data-ttu-id="d5f00-185">これで、Queue storage の基本を学習するには、以下のリンクより複雑なストレージ タスクについて説明しますに従います。</span><span class="sxs-lookup"><span data-stu-id="d5f00-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="d5f00-186">.NET 用 azure Storage Api</span><span class="sxs-lookup"><span data-stu-id="d5f00-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="d5f00-187">Azure Storage 型プロバイダー</span><span class="sxs-lookup"><span data-stu-id="d5f00-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="d5f00-188">Azure Storage チーム ブログ</span><span class="sxs-lookup"><span data-stu-id="d5f00-188">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="d5f00-189">Azure Storage 接続文字列を構成します。</span><span class="sxs-lookup"><span data-stu-id="d5f00-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="d5f00-190">Azure ストレージ サービス REST API リファレンス</span><span class="sxs-lookup"><span data-stu-id="d5f00-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
