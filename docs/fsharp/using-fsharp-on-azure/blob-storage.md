---
title: F# を使用した Azure Blob Storage の概要
description: Azure Blob storage を使用して、非構造化データをクラウドに格納します。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: c765f38cba7642e813a5966d3b7754c5ce45abbd
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107122"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="f5786-103">F を使用して Azure Blob storage を使ってみる\#</span><span class="sxs-lookup"><span data-stu-id="f5786-103">Get started with Azure Blob storage using F\#</span></span>

<span data-ttu-id="f5786-104">Azure BLOB Storage は、非構造化データをオブジェクト/BLOB としてクラウドに格納するサービスです。</span><span class="sxs-lookup"><span data-stu-id="f5786-104">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="f5786-105">Blob Storage は、ドキュメント、メディア ファイル、アプリケーション インストーラーなど、任意の種類のテキストまたはバイナリ データを格納できます。</span><span class="sxs-lookup"><span data-stu-id="f5786-105">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="f5786-106">Blob Storage は、オブジェクト ストレージとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f5786-106">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="f5786-107">この記事では、Blob storage を使用して一般的なタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f5786-107">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="f5786-108">サンプルは、.NET 用 Azure Storage クライアント ライブラリを使用した F# を使用して記述します。</span><span class="sxs-lookup"><span data-stu-id="f5786-108">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="f5786-109">説明するタスクには、blob のアップロード、一覧表示、ダウンロード、および削除の方法が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5786-109">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="f5786-110">Blob storage の概念の概要については、「 [.net ガイド](/azure/storage/storage-dotnet-how-to-use-blobs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5786-110">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f5786-111">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f5786-111">Prerequisites</span></span>

<span data-ttu-id="f5786-112">このガイドを使用するには、最初に[Azure ストレージアカウントを作成](/azure/storage/storage-create-storage-account)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5786-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="f5786-113">また、このアカウントのストレージアクセスキーも必要です。</span><span class="sxs-lookup"><span data-stu-id="f5786-113">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="f5786-114">作成して、F# スクリプトと開始 F# 対話型</span><span class="sxs-lookup"><span data-stu-id="f5786-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="f5786-115">この記事のサンプルは、F# アプリケーションまたは F# スクリプトのいずれかで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5786-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="f5786-116">F# スクリプトを作成するには、ファイルを作成、`.fsx`拡張機能の例では、 `blobs.fsx`、F# 開発環境にします。</span><span class="sxs-lookup"><span data-stu-id="f5786-116">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="f5786-117">次に、[パケット](https://fsprojects.github.io/Paket/)や`WindowsAzure.Storage` [NuGet](https://www.nuget.org/)などの[パッケージマネージャー](package-management.md)を使用して、 `Microsoft.WindowsAzure.ConfigurationManager` `#r`ディレクティブを使用し`Microsoft.WindowsAzure.Configuration.dll`て、パッケージとパッケージをインストールし、スクリプトにおよびを参照`WindowsAzure.Storage.dll`します。</span><span class="sxs-lookup"><span data-stu-id="f5786-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="f5786-118">名前空間宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="f5786-118">Add namespace declarations</span></span>

<span data-ttu-id="f5786-119">ファイルの先頭`open`に次のステートメントを追加します。 `blobs.fsx`</span><span class="sxs-lookup"><span data-stu-id="f5786-119">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="f5786-120">接続文字列を取得する</span><span class="sxs-lookup"><span data-stu-id="f5786-120">Get your connection string</span></span>

<span data-ttu-id="f5786-121">このチュートリアルでは、Azure Storage 接続文字列が必要です。</span><span class="sxs-lookup"><span data-stu-id="f5786-121">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="f5786-122">接続文字列の詳細については、「[ストレージ接続文字列の構成](/azure/storage/storage-configure-connection-string)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5786-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="f5786-123">このチュートリアルでは、次のように、スクリプトに接続文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="f5786-123">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="f5786-124">ただし、実際のプロジェクトではこの方法は**お勧めできません**。</span><span class="sxs-lookup"><span data-stu-id="f5786-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="f5786-125">ストレージアカウントキーは、ストレージアカウントのルートパスワードに似ています。</span><span class="sxs-lookup"><span data-stu-id="f5786-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="f5786-126">ストレージアカウントキーは常に慎重に保護してください。</span><span class="sxs-lookup"><span data-stu-id="f5786-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="f5786-127">他のユーザーに配布したり、ハードコーディングしたり、他のユーザーがアクセスできるプレーンテキストファイルに保存したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="f5786-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="f5786-128">侵害された可能性があると思われる場合は、Azure ポータルを使用してキーを再生成することができます。</span><span class="sxs-lookup"><span data-stu-id="f5786-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="f5786-129">実際のアプリケーションでは、ストレージ接続文字列を維持する最善の方法は構成ファイルにあります。</span><span class="sxs-lookup"><span data-stu-id="f5786-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="f5786-130">構成ファイルから接続文字列を取得するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f5786-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="f5786-131">Azure Configuration Manager の使用は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f5786-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="f5786-132">.NET Framework の`ConfigurationManager`型などの API を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5786-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="f5786-133">接続文字列を解析する</span><span class="sxs-lookup"><span data-stu-id="f5786-133">Parse the connection string</span></span>

<span data-ttu-id="f5786-134">接続文字列を解析するには、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="f5786-134">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="f5786-135">これにより`CloudStorageAccount`、が返されます。</span><span class="sxs-lookup"><span data-stu-id="f5786-135">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="f5786-136">いくつかのローカルダミーデータを作成する</span><span class="sxs-lookup"><span data-stu-id="f5786-136">Create some local dummy data</span></span>

<span data-ttu-id="f5786-137">開始する前に、スクリプトのディレクトリにダミーのローカルデータを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5786-137">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="f5786-138">後でこのデータをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="f5786-138">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="f5786-139">Blob service クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="f5786-139">Create the Blob service client</span></span>

<span data-ttu-id="f5786-140">型`CloudBlobClient`を使用すると、blob ストレージに格納されているコンテナーと blob を取得できます。</span><span class="sxs-lookup"><span data-stu-id="f5786-140">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="f5786-141">サービスクライアントを作成する方法の1つを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f5786-141">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="f5786-142">これで、Blob storage との間でデータを読み取り、データを書き込むコードを記述する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="f5786-142">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="f5786-143">コンテナーの作成</span><span class="sxs-lookup"><span data-stu-id="f5786-143">Create a container</span></span>

<span data-ttu-id="f5786-144">この例では、コンテナーがまだ存在しない場合に作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f5786-144">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="f5786-145">既定では、新しいコンテナーはプライベートです。つまり、このコンテナーから blob をダウンロードするには、ストレージアクセスキーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5786-145">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="f5786-146">コンテナー内のファイルをすべてのユーザーが使用できるようにする場合は、次のコードを使用して、コンテナーをパブリックに設定できます。</span><span class="sxs-lookup"><span data-stu-id="f5786-146">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="f5786-147">パブリックコンテナー内の blob は、インターネット上のすべてのユーザーが表示できますが、変更または削除するには、適切なアカウントアクセスキーまたは共有アクセス署名がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5786-147">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="f5786-148">コンテナーへの blob のアップロード</span><span class="sxs-lookup"><span data-stu-id="f5786-148">Upload a blob into a container</span></span>

<span data-ttu-id="f5786-149">Azure Blob Storage は、ブロック blob とページ blob をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f5786-149">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="f5786-150">ほとんどの場合、ブロック blob を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f5786-150">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="f5786-151">ファイルをブロック blob にアップロードするには、コンテナー参照を取得し、それを使用してブロック blob 参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="f5786-151">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="f5786-152">Blob の参照を取得したら、 `UploadFromFile`メソッドを呼び出すことによって、データの任意のストリームをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="f5786-152">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="f5786-153">この操作では、blob が既に存在していない場合は作成し、存在する場合は上書きします。</span><span class="sxs-lookup"><span data-stu-id="f5786-153">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="f5786-154">コンテナー内の blob を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="f5786-154">List the blobs in a container</span></span>

<span data-ttu-id="f5786-155">コンテナー内の blob を一覧表示するには、最初にコンテナー参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="f5786-155">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="f5786-156">その後、コンテナーの`ListBlobs`メソッドを使用して、その中の blob やディレクトリを取得できます。</span><span class="sxs-lookup"><span data-stu-id="f5786-156">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="f5786-157">返される`IListBlobItem`の豊富なプロパティおよびメソッドのセットにアクセスするには`CloudBlockBlob`、それを、 `CloudPageBlob`、または`CloudBlobDirectory`オブジェクトにキャストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5786-157">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="f5786-158">型が不明な場合は、型チェックを使用して、キャスト先を決定できます。</span><span class="sxs-lookup"><span data-stu-id="f5786-158">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="f5786-159">次のコードは、 `mydata`コンテナー内の各項目の URI を取得して出力する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f5786-159">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="f5786-160">Blob には、名前にパス情報を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5786-160">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="f5786-161">これにより、従来のファイルシステムと同じように整理および走査できる仮想ディレクトリ構造が作成されます。</span><span class="sxs-lookup"><span data-stu-id="f5786-161">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="f5786-162">ディレクトリ構造は仮想のみであり、Blob storage で使用できるリソースはコンテナーと blob のみであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f5786-162">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="f5786-163">ただし、ストレージクライアントライブラリは、仮想`CloudBlobDirectory`ディレクトリを参照するオブジェクトを提供し、この方法で構成されている blob を操作するプロセスを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="f5786-163">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="f5786-164">たとえば、という名前`photos`のコンテナー内の次の一連のブロック blob について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="f5786-164">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="f5786-165">*photo1.jpg*</span><span class="sxs-lookup"><span data-stu-id="f5786-165">*photo1.jpg*</span></span>\
<span data-ttu-id="f5786-166">*2015/architecture/description .txt*</span><span class="sxs-lookup"><span data-stu-id="f5786-166">*2015/architecture/description.txt*</span></span>\
<span data-ttu-id="f5786-167">*2015/architecture/photo3.jpg*</span><span class="sxs-lookup"><span data-stu-id="f5786-167">*2015/architecture/photo3.jpg*</span></span>\
<span data-ttu-id="f5786-168">*2015/architecture/photo4.jpg*</span><span class="sxs-lookup"><span data-stu-id="f5786-168">*2015/architecture/photo4.jpg*</span></span>\
<span data-ttu-id="f5786-169">*2016/architecture/photo5.jpg*</span><span class="sxs-lookup"><span data-stu-id="f5786-169">*2016/architecture/photo5.jpg*</span></span>\
<span data-ttu-id="f5786-170">*2016/architecture/photo6.jpg*</span><span class="sxs-lookup"><span data-stu-id="f5786-170">*2016/architecture/photo6.jpg*</span></span>\
<span data-ttu-id="f5786-171">*2016/architecture/description .txt*</span><span class="sxs-lookup"><span data-stu-id="f5786-171">*2016/architecture/description.txt*</span></span>\
<span data-ttu-id="f5786-172">*2016/photo7.jpg*</span><span class="sxs-lookup"><span data-stu-id="f5786-172">*2016/photo7.jpg*</span></span>\

<span data-ttu-id="f5786-173">コンテナーでを`ListBlobs`呼び出すと (上記のサンプルのように)、階層化された一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="f5786-173">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="f5786-174">コンテナー内のディレクトリ`CloudBlobDirectory`と`CloudBlockBlob` blob をそれぞれ表すオブジェクトとオブジェクトの両方が含まれている場合、結果の出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f5786-174">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="f5786-175">必要に応じて、 `UseFlatBlobListing` `ListBlobs`メソッドのパラメーターをに`true`設定できます。</span><span class="sxs-lookup"><span data-stu-id="f5786-175">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="f5786-176">この場合、コンテナー内のすべての blob が`CloudBlockBlob`オブジェクトとして返されます。</span><span class="sxs-lookup"><span data-stu-id="f5786-176">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="f5786-177">フラットリストを`ListBlobs`返すためのの呼び出しは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f5786-177">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="f5786-178">また、コンテナーの現在の内容によっては、結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f5786-178">and, depending on the current contents of your container, the results look like this:</span></span>

```console
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2015/architecture/description.txt
Block blob of length 314618: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo3.jpg
Block blob of length 522713: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo4.jpg
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2016/architecture/description.txt
Block blob of length 419048: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo5.jpg
Block blob of length 506388: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo6.jpg
Block blob of length 399751: https://<accountname>.blob.core.windows.net/photos/2016/photo7.jpg
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

## <a name="download-blobs"></a><span data-ttu-id="f5786-179">Blob のダウンロード</span><span class="sxs-lookup"><span data-stu-id="f5786-179">Download blobs</span></span>

<span data-ttu-id="f5786-180">Blob をダウンロードするには、まず blob の参照を取得`DownloadToStream`してから、メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f5786-180">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="f5786-181">次の例では`DownloadToStream` 、メソッドを使用して、ローカルファイルに永続化できるストリームオブジェクトに blob の内容を転送します。</span><span class="sxs-lookup"><span data-stu-id="f5786-181">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="f5786-182">`DownloadToStream`メソッドを使用して、blob の内容をテキスト文字列としてダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f5786-182">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="f5786-183">Blob の削除</span><span class="sxs-lookup"><span data-stu-id="f5786-183">Delete blobs</span></span>

<span data-ttu-id="f5786-184">Blob を削除するには、まず blob の参照を取得し`Delete` 、次にそのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f5786-184">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="f5786-185">ページ内の blob を非同期に一覧表示する</span><span class="sxs-lookup"><span data-stu-id="f5786-185">List blobs in pages asynchronously</span></span>

<span data-ttu-id="f5786-186">多数の blob を一覧表示する場合、または1つのリスティング操作で返す結果の数を制御する場合は、結果ページに blob を一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="f5786-186">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="f5786-187">この例では、大量の結果を返すために待機している間に実行がブロックされないように、結果をページ単位で非同期的に返す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f5786-187">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="f5786-188">この例はフラット blob リストを示していますが、 `useFlatBlobListing` `ListBlobsSegmentedAsync`メソッドのパラメーターをに設定する`false`ことによって、階層化された一覧を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5786-188">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="f5786-189">このサンプルでは、 `async`ブロックを使用して非同期メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="f5786-189">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="f5786-190">キーワード``let!``は、リスティングタスクが完了するまで、サンプルメソッドの実行を中断します。</span><span class="sxs-lookup"><span data-stu-id="f5786-190">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="f5786-191">次のように、この非同期ルーチンを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f5786-191">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="f5786-192">まずダミーデータをアップロードします (このチュートリアルで既に作成したローカルファイルを使用します)。</span><span class="sxs-lookup"><span data-stu-id="f5786-192">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="f5786-193">ここで、ルーチンを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f5786-193">Now, call the routine.</span></span> <span data-ttu-id="f5786-194">非同期操作`Async.RunSynchronously`の実行を強制するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="f5786-194">You use `Async.RunSynchronously` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="f5786-195">追加 blob への書き込み</span><span class="sxs-lookup"><span data-stu-id="f5786-195">Writing to an append blob</span></span>

<span data-ttu-id="f5786-196">追加 blob は、ログ記録などの追加操作用に最適化されています。</span><span class="sxs-lookup"><span data-stu-id="f5786-196">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="f5786-197">ブロック blob と同様に、追加 blob はブロックで構成されますが、追加 blob に新しいブロックを追加すると、常に blob の末尾に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f5786-197">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="f5786-198">追加 blob の既存のブロックを更新または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5786-198">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="f5786-199">追加 blob のブロック Id は、ブロック blob のブロック Id として公開されません。</span><span class="sxs-lookup"><span data-stu-id="f5786-199">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="f5786-200">追加 blob 内の各ブロックは、最大 4 MB までの異なるサイズにすることができ、追加 blob には最大5万のブロックを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f5786-200">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="f5786-201">このため、追加 blob の最大サイズは 195 GB (4 MB X 5万ブロック) よりも少し大きくなります。</span><span class="sxs-lookup"><span data-stu-id="f5786-201">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="f5786-202">次の例では、新しい追加 blob を作成し、データを追加して、単純なログ記録操作をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="f5786-202">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="f5786-203">3種類の blob の相違点の詳細については、「[ブロック blob、ページ blob、および追加 blob](https://msdn.microsoft.com/library/azure/ee691964.aspx)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5786-203">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="f5786-204">同時アクセス</span><span class="sxs-lookup"><span data-stu-id="f5786-204">Concurrent access</span></span>

<span data-ttu-id="f5786-205">複数のクライアントまたは複数のプロセスインスタンスからの blob への同時アクセスをサポートするには、 **etag**または**リース**を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5786-205">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

- <span data-ttu-id="f5786-206">**Etag** -blob またはコンテナーが別のプロセスによって変更されたことを検出する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="f5786-206">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

- <span data-ttu-id="f5786-207">**リース**-一定期間、blob への排他、更新、書き込み、または削除のアクセス権を取得する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="f5786-207">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="f5786-208">詳細については、「 [Microsoft Azure Storage での同時実行の管理](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5786-208">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="f5786-209">コンテナーの名前付け</span><span class="sxs-lookup"><span data-stu-id="f5786-209">Naming containers</span></span>

<span data-ttu-id="f5786-210">Azure storage 内のすべての blob は、コンテナー内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5786-210">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="f5786-211">コンテナーは、blob 名の一部を形成します。</span><span class="sxs-lookup"><span data-stu-id="f5786-211">The container forms part of the blob name.</span></span> <span data-ttu-id="f5786-212">たとえば、は`mydata` 、次のサンプル blob uri のコンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="f5786-212">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

- https://storagesample.blob.core.windows.net/mydata/blob1.txt
- https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="f5786-213">コンテナー名は、次の名前付け規則に準拠した有効な DNS 名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5786-213">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="f5786-214">コンテナー名の先頭には文字または数字を使用する必要があり、文字、数字、ダッシュ (-) 文字のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f5786-214">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="f5786-215">すべてのダッシュ (-) 文字は、その直後に文字または数字を付ける必要があります。連続するダッシュは、コンテナー名では使用できません。</span><span class="sxs-lookup"><span data-stu-id="f5786-215">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="f5786-216">コンテナー名のすべての文字は、小文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5786-216">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="f5786-217">コンテナー名は、3 ~ 63 文字の長さにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5786-217">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="f5786-218">コンテナーの名前は常に小文字にする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f5786-218">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="f5786-219">コンテナー名に大文字を含める場合や、コンテナーの名前付け規則に違反する場合は、400エラー (無効な要求) が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="f5786-219">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="f5786-220">Blob のセキュリティを管理する</span><span class="sxs-lookup"><span data-stu-id="f5786-220">Managing security for blobs</span></span>

<span data-ttu-id="f5786-221">既定では、アカウントの所有者にアクセスを制限することで、アカウントのアクセスキーを所有しているユーザーに対して、Azure Storage のデータのセキュリティを保護します。</span><span class="sxs-lookup"><span data-stu-id="f5786-221">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="f5786-222">ストレージアカウントで blob データを共有する必要がある場合は、アカウントアクセスキーのセキュリティを損なうことなくこの操作を行うことが重要です。</span><span class="sxs-lookup"><span data-stu-id="f5786-222">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="f5786-223">さらに、blob データを暗号化して、ネットワーク上および Azure Storage で安全に保護されるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f5786-223">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="f5786-224">Blob データへのアクセスの制御</span><span class="sxs-lookup"><span data-stu-id="f5786-224">Controlling access to blob data</span></span>

<span data-ttu-id="f5786-225">既定では、ストレージアカウントの blob データには、ストレージアカウントの所有者のみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f5786-225">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="f5786-226">Blob ストレージに対する要求の認証には、既定でアカウントアクセスキーが必要です。</span><span class="sxs-lookup"><span data-stu-id="f5786-226">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="f5786-227">ただし、特定の blob データを他のユーザーが使用できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f5786-227">However, you might want to make certain blob data available to other users.</span></span>

### <a name="encrypting-blob-data"></a><span data-ttu-id="f5786-228">Blob データの暗号化</span><span class="sxs-lookup"><span data-stu-id="f5786-228">Encrypting blob data</span></span>

<span data-ttu-id="f5786-229">Azure Storage は、クライアントとサーバーの両方で blob データの暗号化をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f5786-229">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f5786-230">次の手順</span><span class="sxs-lookup"><span data-stu-id="f5786-230">Next steps</span></span>

<span data-ttu-id="f5786-231">これで、Blob storage の基本を学習できました。詳細については、次のリンク先を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5786-231">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="f5786-232">ツール</span><span class="sxs-lookup"><span data-stu-id="f5786-232">Tools</span></span>

- <span data-ttu-id="f5786-233">[F#AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)</span><span class="sxs-lookup"><span data-stu-id="f5786-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)</span></span>\
<span data-ttu-id="f5786-234">Blob F# 、テーブル、およびキュー Azure Storage 資産を探索し、それらに対して CRUD 操作を簡単に適用するために使用できる型プロバイダー。</span><span class="sxs-lookup"><span data-stu-id="f5786-234">An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>

- <span data-ttu-id="f5786-235">[Fsharp.core](https://github.com/fsprojects/FSharp.Azure.Storage)</span><span class="sxs-lookup"><span data-stu-id="f5786-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)</span></span>\
<span data-ttu-id="f5786-236">Microsoft Azure F# Table Storage サービスを使用するための API</span><span class="sxs-lookup"><span data-stu-id="f5786-236">An F# API for using Microsoft Azure Table Storage service</span></span>

- <span data-ttu-id="f5786-237">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="f5786-237">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)</span></span>\
<span data-ttu-id="f5786-238">Windows、OS X、Linux で Azure Storage データを視覚的に操作できる Microsoft 製の無料のスタンドアロンアプリです。</span><span class="sxs-lookup"><span data-stu-id="f5786-238">A free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="f5786-239">Blob ストレージのリファレンス</span><span class="sxs-lookup"><span data-stu-id="f5786-239">Blob storage reference</span></span>

- [<span data-ttu-id="f5786-240">.NET 用 Api の Azure Storage</span><span class="sxs-lookup"><span data-stu-id="f5786-240">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="f5786-241">Azure Storage Services REST API リファレンス</span><span class="sxs-lookup"><span data-stu-id="f5786-241">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a><span data-ttu-id="f5786-242">関連ガイド</span><span class="sxs-lookup"><span data-stu-id="f5786-242">Related guides</span></span>

- [<span data-ttu-id="f5786-243">Azure Blob Storage でのはじめにC#</span><span class="sxs-lookup"><span data-stu-id="f5786-243">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="f5786-244">Windows で AzCopy コマンドラインユーティリティを使用してデータを転送する</span><span class="sxs-lookup"><span data-stu-id="f5786-244">Transfer data with the AzCopy command-line utility on Windows</span></span>](/azure/storage/common/storage-use-azcopy)
- [<span data-ttu-id="f5786-245">Linux で AzCopy コマンドラインユーティリティを使用してデータを転送する</span><span class="sxs-lookup"><span data-stu-id="f5786-245">Transfer data with the AzCopy command-line utility on Linux</span></span>](/azure/storage/common/storage-use-azcopy-linux)
- [<span data-ttu-id="f5786-246">Azure Storage 接続文字列を構成する</span><span class="sxs-lookup"><span data-stu-id="f5786-246">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="f5786-247">Azure Storage チームのブログ</span><span class="sxs-lookup"><span data-stu-id="f5786-247">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="f5786-248">クイック スタート:.NET を使用してオブジェクトストレージに blob を作成する</span><span class="sxs-lookup"><span data-stu-id="f5786-248">Quickstart: Use .NET to create a blob in object storage</span></span>](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
