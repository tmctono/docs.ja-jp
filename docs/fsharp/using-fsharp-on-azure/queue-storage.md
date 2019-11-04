---
title: F# を使用した Azure Queue Storage の概要
description: Azure キューは、アプリケーションコンポーネント間の信頼性の高い非同期メッセージングを提供します。 クラウドメッセージングを使用すると、アプリケーションコンポーネントを個別にスケーリングできます。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: a09cbdd4b995e34177c110ce91b02162bb19dfa8
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423847"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="a8fc6-104">F\# を使用した Azure Queue storage の概要</span><span class="sxs-lookup"><span data-stu-id="a8fc6-104">Get started with Azure Queue storage using F\#</span></span>

<span data-ttu-id="a8fc6-105">Azure Queue storage は、アプリケーションコンポーネント間のクラウドメッセージングを提供します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="a8fc6-106">大規模なアプリケーションの設計では、多くの場合、アプリケーションコンポーネントが分離され、個別に拡張できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="a8fc6-107">Queue storage は、アプリケーションコンポーネントがクラウド、デスクトップ、オンプレミスサーバー、モバイルデバイスのいずれで実行されているかにかかわらず、アプリケーションコンポーネント間の通信に使用する非同期メッセージングを提供します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="a8fc6-108">Queue storage では、非同期タスクの管理とプロセスワークフローの構築もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="a8fc6-109">このチュートリアルについて</span><span class="sxs-lookup"><span data-stu-id="a8fc6-109">About this tutorial</span></span>

<span data-ttu-id="a8fc6-110">このチュートリアルでは、Azure F# Queue storage を使用していくつかの一般的なタスクのコードを記述する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="a8fc6-111">キューの作成と削除、キューメッセージの追加、読み取り、削除などのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="a8fc6-112">Queue storage の概念の概要については、「 [.net のキューストレージに関するガイド](/azure/storage/storage-dotnet-how-to-use-queues)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a8fc6-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="a8fc6-113">Prerequisites</span></span>

<span data-ttu-id="a8fc6-114">このガイドを使用するには、最初に[Azure ストレージアカウントを作成](/azure/storage/storage-create-storage-account)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="a8fc6-115">また、このアカウントのストレージアクセスキーも必要になります。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="a8fc6-116">F#スクリプトを作成してF#対話形式で起動する</span><span class="sxs-lookup"><span data-stu-id="a8fc6-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="a8fc6-117">この記事のサンプルは、 F#アプリケーションまたはF#スクリプトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="a8fc6-118">F#スクリプトを作成するには、 F#開発環境で `queues.fsx`などの `.fsx` 拡張機能を使用してファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="a8fc6-119">次に、[パケット](https://fsprojects.github.io/Paket/)や[NuGet](https://www.nuget.org/)などの[パッケージマネージャー](package-management.md)を使用して、`#r` ディレクティブを使用してスクリプトに `WindowsAzure.Storage` パッケージと参照 `WindowsAzure.Storage.dll` をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="a8fc6-120">名前空間宣言の追加</span><span class="sxs-lookup"><span data-stu-id="a8fc6-120">Add namespace declarations</span></span>

<span data-ttu-id="a8fc6-121">`queues.fsx` ファイルの先頭に、次の `open` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="a8fc6-122">接続文字列を取得する</span><span class="sxs-lookup"><span data-stu-id="a8fc6-122">Get your connection string</span></span>

<span data-ttu-id="a8fc6-123">このチュートリアルでは、Azure Storage 接続文字列が必要です。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="a8fc6-124">接続文字列の詳細については、「[ストレージ接続文字列の構成](/azure/storage/storage-configure-connection-string)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="a8fc6-125">このチュートリアルでは、次のように、スクリプトに接続文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="a8fc6-126">ただし、実際のプロジェクトではこの方法は**お勧めできません**。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="a8fc6-127">ストレージアカウントキーは、ストレージアカウントのルートパスワードに似ています。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="a8fc6-128">ストレージアカウントキーは常に慎重に保護してください。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="a8fc6-129">他のユーザーに配布したり、ハードコーディングしたり、他のユーザーがアクセスできるプレーンテキストファイルに保存したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="a8fc6-130">侵害された可能性があると思われる場合は、Azure ポータルを使用してキーを再生成することができます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="a8fc6-131">実際のアプリケーションでは、ストレージ接続文字列を維持する最善の方法は構成ファイルにあります。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="a8fc6-132">構成ファイルから接続文字列を取得するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="a8fc6-133">Azure Configuration Manager の使用は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="a8fc6-134">.NET Framework の `ConfigurationManager` の種類などの API を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="a8fc6-135">接続文字列を解析する</span><span class="sxs-lookup"><span data-stu-id="a8fc6-135">Parse the connection string</span></span>

<span data-ttu-id="a8fc6-136">接続文字列を解析するには、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="a8fc6-137">これにより、`CloudStorageAccount`が返されます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="a8fc6-138">Queue サービスクライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="a8fc6-138">Create the Queue service client</span></span>

<span data-ttu-id="a8fc6-139">`CloudQueueClient` クラスを使用すると、Queue storage に格納されているキューを取得できます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="a8fc6-140">サービスクライアントを作成する方法の1つを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="a8fc6-141">これで、からデータを読み取り、キューストレージにデータを書き込むコードを記述する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="a8fc6-142">キューを作成する</span><span class="sxs-lookup"><span data-stu-id="a8fc6-142">Create a queue</span></span>

<span data-ttu-id="a8fc6-143">この例では、キューが存在しない場合に作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="a8fc6-144">メッセージをキューに挿入する</span><span class="sxs-lookup"><span data-stu-id="a8fc6-144">Insert a message into a queue</span></span>

<span data-ttu-id="a8fc6-145">既存のキューにメッセージを挿入するには、最初に新しい `CloudQueueMessage`を作成します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="a8fc6-146">次に、`AddMessage` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="a8fc6-147">`CloudQueueMessage` は、次のように、文字列 (UTF-8 形式) または `byte` 配列から作成できます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="a8fc6-148">次のメッセージを見る</span><span class="sxs-lookup"><span data-stu-id="a8fc6-148">Peek at the next message</span></span>

<span data-ttu-id="a8fc6-149">`PeekMessage` メソッドを呼び出すことにより、キューの先頭にあるメッセージをキューから削除せずにピークできます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="a8fc6-150">処理する次のメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-150">Get the next message for processing</span></span>

<span data-ttu-id="a8fc6-151">`GetMessage` メソッドを呼び出すことにより、キューの先頭にあるメッセージを処理のために取得できます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="a8fc6-152">後で `DeleteMessage`を使用して、メッセージの処理が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="a8fc6-153">キューに置かれたメッセージの内容を変更する</span><span class="sxs-lookup"><span data-stu-id="a8fc6-153">Change the contents of a queued message</span></span>

<span data-ttu-id="a8fc6-154">取得したメッセージの内容をキュー内のインプレースで変更できます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="a8fc6-155">メッセージが作業タスクを表している場合は、この機能を使用して作業タスクの状態を更新できます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="a8fc6-156">次のコードでは、キューメッセージを新しい内容で更新し、表示タイムアウトを別の60秒に拡張するように設定しています。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="a8fc6-157">これにより、メッセージに関連付けられている作業の状態が保存され、メッセージの処理を続行するためにクライアントにもう1分の時間が与えられます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="a8fc6-158">この手法を使用すると、キューメッセージの複数ステップのワークフローを追跡できます。ハードウェアまたはソフトウェアの障害が原因で処理手順が失敗した場合、最初からやり直す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="a8fc6-159">通常は、再試行回数も保持します。また、メッセージが何回も再試行される場合は、削除します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="a8fc6-160">これにより、処理されるたびにアプリケーションエラーをトリガーするメッセージから保護されます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="a8fc6-161">次のメッセージをキューから解除する</span><span class="sxs-lookup"><span data-stu-id="a8fc6-161">De-queue the next message</span></span>

<span data-ttu-id="a8fc6-162">コードでは、2つの手順でキューからメッセージをキューから除外します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="a8fc6-163">`GetMessage`を呼び出すと、キュー内の次のメッセージが取得されます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="a8fc6-164">`GetMessage` から返されたメッセージは、このキューからメッセージを読み取る他のコードからは見えなくなります。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="a8fc6-165">既定では、このメッセージは30秒間非表示のままになります。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="a8fc6-166">キューからのメッセージの削除を完了するには、`DeleteMessage`も呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="a8fc6-167">メッセージを削除するこの2段階のプロセスでは、ハードウェアまたはソフトウェアの障害によってコードがメッセージの処理に失敗した場合に、コードの別のインスタンスが同じメッセージを取得して、もう一度試すことができます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="a8fc6-168">このコードは、メッセージが処理された直後に `DeleteMessage` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="a8fc6-169">一般的な Queue storage Api での非同期ワークフローの使用</span><span class="sxs-lookup"><span data-stu-id="a8fc6-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="a8fc6-170">この例では、一般的な Queue storage Api で非同期ワークフローを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="a8fc6-171">キューからメッセージを解除するための追加オプション</span><span class="sxs-lookup"><span data-stu-id="a8fc6-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="a8fc6-172">キューからのメッセージの取得をカスタマイズするには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="a8fc6-173">まず、メッセージのバッチを取得できます (最大 32)。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="a8fc6-174">2つ目の方法として、非表示タイムアウトを長くまたは短くすることができます。これにより、コードで各メッセージを完全に処理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="a8fc6-175">次のコード例では、`GetMessages` を使用して1回の呼び出しで20個のメッセージを取得し、各メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="a8fc6-176">また、各メッセージの非表示タイムアウトを5分に設定します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="a8fc6-177">5分がすべてのメッセージに対して同時に開始されるため、`GetMessages`の呼び出しから5分が経過すると、削除されていないすべてのメッセージが再び表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="a8fc6-178">キューの長さを取得する</span><span class="sxs-lookup"><span data-stu-id="a8fc6-178">Get the queue length</span></span>

<span data-ttu-id="a8fc6-179">キュー内のメッセージ数の見積もりを取得できます。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="a8fc6-180">`FetchAttributes` メソッドは、メッセージ数を含むキューの属性を取得するように Queue サービスに要求します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="a8fc6-181">`ApproximateMessageCount` プロパティは、Queue サービスを呼び出さずに、`FetchAttributes` メソッドによって取得された最後の値を返します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="a8fc6-182">キューを削除する</span><span class="sxs-lookup"><span data-stu-id="a8fc6-182">Delete a queue</span></span>

<span data-ttu-id="a8fc6-183">キューおよびキューに格納されているすべてのメッセージを削除するには、キューオブジェクトの `Delete` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="a8fc6-184">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a8fc6-184">Next steps</span></span>

<span data-ttu-id="a8fc6-185">これで、Queue storage の基本を学習できました。さらに複雑なストレージタスクの詳細については、次のリンク先を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8fc6-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="a8fc6-186">.NET 用 Api の Azure Storage</span><span class="sxs-lookup"><span data-stu-id="a8fc6-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="a8fc6-187">Azure Storage 型プロバイダー</span><span class="sxs-lookup"><span data-stu-id="a8fc6-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="a8fc6-188">Azure Storage チームのブログ</span><span class="sxs-lookup"><span data-stu-id="a8fc6-188">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="a8fc6-189">Azure Storage 接続文字列を構成する</span><span class="sxs-lookup"><span data-stu-id="a8fc6-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="a8fc6-190">Azure Storage Services REST API リファレンス</span><span class="sxs-lookup"><span data-stu-id="a8fc6-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
