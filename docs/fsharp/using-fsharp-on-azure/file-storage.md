---
title: F# を使用した Azure File Storage の概要
description: Azure File storage を使用してクラウドにファイルデータを格納し、Azure 仮想マシン (VM) または Windows を実行するオンプレミスアプリケーションからクラウドファイル共有をマウントします。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: a0e3cab56ba0f3db27335822616b4976a5d9de62
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630498"
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="b33a1-103">F を使用して Azure File storage を使ってみる\#</span><span class="sxs-lookup"><span data-stu-id="b33a1-103">Get started with Azure File storage using F\#</span></span>

<span data-ttu-id="b33a1-104">Azure File storage は、標準の[サーバーメッセージブロック (SMB) プロトコル](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)を使用してクラウドでファイル共有を提供するサービスです。</span><span class="sxs-lookup"><span data-stu-id="b33a1-104">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="b33a1-105">SMB 2.1 と SMB 3.0 の両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b33a1-105">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="b33a1-106">Azure File storage を使用すると、ファイル共有に依存するレガシアプリケーションを、コストのかかる書き換えなしに迅速に Azure に移行できます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-106">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="b33a1-107">Azure virtual machines または cloud services またはオンプレミスのクライアントから実行されているアプリケーションは、デスクトップアプリケーションが一般的な SMB 共有をマウントするのと同じように、クラウドにファイル共有をマウントできます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-107">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="b33a1-108">その後、任意の数のアプリケーションコンポーネントがマウントし、ファイルストレージ共有に同時にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-108">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="b33a1-109">File storage の概念の概要については、「 [.net ガイド](/azure/storage/storage-dotnet-how-to-use-files)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b33a1-109">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b33a1-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b33a1-110">Prerequisites</span></span>

<span data-ttu-id="b33a1-111">このガイドを使用するには、最初に[Azure ストレージアカウントを作成](/azure/storage/storage-create-storage-account)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33a1-111">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="b33a1-112">また、このアカウントのストレージアクセスキーも必要になります。</span><span class="sxs-lookup"><span data-stu-id="b33a1-112">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="b33a1-113">作成して、F# スクリプトと開始 F# 対話型</span><span class="sxs-lookup"><span data-stu-id="b33a1-113">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="b33a1-114">この記事のサンプルは、F# アプリケーションまたは F# スクリプトのいずれかで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-114">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="b33a1-115">F# スクリプトを作成するには、ファイルを作成、`.fsx`拡張機能の例では、 `files.fsx`、F# 開発環境にします。</span><span class="sxs-lookup"><span data-stu-id="b33a1-115">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="b33a1-116">次に、[パケット](https://fsprojects.github.io/Paket/)や`WindowsAzure.Storage` [NuGet](https://www.nuget.org/)などの[パッケージマネージャー](package-management.md)を使用して、 `#r`ディレクティブを`WindowsAzure.Storage.dll`使用してスクリプトにパッケージと参照をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b33a1-116">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="b33a1-117">名前空間宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="b33a1-117">Add namespace declarations</span></span>

<span data-ttu-id="b33a1-118">ファイルの先頭`open`に次のステートメントを追加します。 `files.fsx`</span><span class="sxs-lookup"><span data-stu-id="b33a1-118">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="b33a1-119">接続文字列を取得する</span><span class="sxs-lookup"><span data-stu-id="b33a1-119">Get your connection string</span></span>

<span data-ttu-id="b33a1-120">このチュートリアルでは、Azure Storage 接続文字列が必要です。</span><span class="sxs-lookup"><span data-stu-id="b33a1-120">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="b33a1-121">接続文字列の詳細については、「[ストレージ接続文字列の構成](/azure/storage/storage-configure-connection-string)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b33a1-121">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="b33a1-122">このチュートリアルでは、次のように、スクリプトに接続文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="b33a1-122">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="b33a1-123">ただし、実際のプロジェクトではこの方法は**お勧めできません**。</span><span class="sxs-lookup"><span data-stu-id="b33a1-123">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="b33a1-124">ストレージアカウントキーは、ストレージアカウントのルートパスワードに似ています。</span><span class="sxs-lookup"><span data-stu-id="b33a1-124">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="b33a1-125">ストレージアカウントキーは常に慎重に保護してください。</span><span class="sxs-lookup"><span data-stu-id="b33a1-125">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="b33a1-126">他のユーザーに配布したり、ハードコーディングしたり、他のユーザーがアクセスできるプレーンテキストファイルに保存したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="b33a1-126">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="b33a1-127">侵害された可能性があると思われる場合は、Azure ポータルを使用してキーを再生成することができます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-127">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="b33a1-128">実際のアプリケーションでは、ストレージ接続文字列を維持する最善の方法は構成ファイルにあります。</span><span class="sxs-lookup"><span data-stu-id="b33a1-128">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="b33a1-129">構成ファイルから接続文字列を取得するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b33a1-129">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="b33a1-130">Azure Configuration Manager の使用は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b33a1-130">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="b33a1-131">.NET Framework の`ConfigurationManager`型などの API を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-131">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="b33a1-132">接続文字列を解析する</span><span class="sxs-lookup"><span data-stu-id="b33a1-132">Parse the connection string</span></span>

<span data-ttu-id="b33a1-133">接続文字列を解析するには、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="b33a1-133">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="b33a1-134">これにより、 `CloudStorageAccount`が返されます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-134">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="b33a1-135">ファイルサービスクライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="b33a1-135">Create the File service client</span></span>

<span data-ttu-id="b33a1-136">型`CloudFileClient`を使用すると、ファイルストレージに格納されているファイルをプログラムで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-136">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="b33a1-137">サービスクライアントを作成する方法の1つを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b33a1-137">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="b33a1-138">これで、からデータを読み取り、ファイルストレージにデータを書き込むコードを記述する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="b33a1-138">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="b33a1-139">ファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="b33a1-139">Create a file share</span></span>

<span data-ttu-id="b33a1-140">この例では、ファイル共有がまだ存在しない場合に作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b33a1-140">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="b33a1-141">ルートディレクトリとサブディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="b33a1-141">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="b33a1-142">ここでは、ルートディレクトリを取得し、ルートのサブディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="b33a1-142">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="b33a1-143">まだ存在しない場合は、両方を作成します。</span><span class="sxs-lookup"><span data-stu-id="b33a1-143">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="b33a1-144">テキストをファイルとしてアップロードする</span><span class="sxs-lookup"><span data-stu-id="b33a1-144">Upload text as a file</span></span>

<span data-ttu-id="b33a1-145">この例では、テキストをファイルとしてアップロードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b33a1-145">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="b33a1-146">ファイルのローカルコピーにファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="b33a1-146">Download a file to a local copy of the file</span></span>

<span data-ttu-id="b33a1-147">ここでは、作成したばかりのファイルをダウンロードし、ローカルファイルに内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="b33a1-147">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="b33a1-148">ファイル共有の最大サイズを設定する</span><span class="sxs-lookup"><span data-stu-id="b33a1-148">Set the maximum size for a file share</span></span>

<span data-ttu-id="b33a1-149">次の例では、共有の現在の使用状況を確認する方法と、共有のクォータを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b33a1-149">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="b33a1-150">`FetchAttributes`共有のを設定し`Properties` `SetProperties` 、ローカルの変更を Azure File storage に反映するには、を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33a1-150">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="b33a1-151">ファイルまたはファイル共有の共有アクセス署名を生成する</span><span class="sxs-lookup"><span data-stu-id="b33a1-151">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="b33a1-152">ファイル共有または個々のファイルの共有アクセス署名 (SAS) を生成できます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-152">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="b33a1-153">また、共有アクセスポリシーをファイル共有に作成して、共有アクセス署名を管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-153">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="b33a1-154">共有アクセスポリシーを作成することをお勧めします。これにより、セキュリティが侵害された場合に SAS を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-154">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="b33a1-155">ここでは、共有に対して共有アクセスポリシーを作成し、そのポリシーを使用して、共有内のファイルの SAS に対する制約を指定します。</span><span class="sxs-lookup"><span data-stu-id="b33a1-155">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="b33a1-156">Shared access signature の作成と使用の詳細については、「 [Shared Access signature (sas) の使用](/azure/storage/storage-dotnet-shared-access-signature-part-1)」および「 [Blob ストレージでの sas の作成と使用](/azure/storage/storage-dotnet-shared-access-signature-part-2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b33a1-156">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="b33a1-157">ファイルのコピー</span><span class="sxs-lookup"><span data-stu-id="b33a1-157">Copy files</span></span>

<span data-ttu-id="b33a1-158">ファイルを別のファイルまたは blob にコピーしたり、blob をファイルにコピーしたりできます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-158">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="b33a1-159">Blob をファイルにコピーする場合、またはファイルを blob にコピーする場合は、同じストレージアカウント内でコピーする場合でも、共有アクセス署名 (SAS) を使用してソースオブジェクトを認証する*必要があり*ます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-159">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="b33a1-160">ファイルを別のファイルにコピーする</span><span class="sxs-lookup"><span data-stu-id="b33a1-160">Copy a file to another file</span></span>

<span data-ttu-id="b33a1-161">ここでは、同じ共有内の別のファイルにファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="b33a1-161">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="b33a1-162">このコピー操作では同じストレージアカウント内のファイルがコピーされるため、共有キー認証を使用してコピーを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-162">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="b33a1-163">Blob へのファイルのコピー</span><span class="sxs-lookup"><span data-stu-id="b33a1-163">Copy a file to a blob</span></span>

<span data-ttu-id="b33a1-164">ここでは、ファイルを作成し、同じストレージアカウント内の blob にコピーします。</span><span class="sxs-lookup"><span data-stu-id="b33a1-164">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="b33a1-165">コピー操作中にソースファイルへのアクセスを認証するためにサービスが使用するソースファイルの SAS を作成します。</span><span class="sxs-lookup"><span data-stu-id="b33a1-165">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="b33a1-166">Blob は、同じ方法でファイルにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-166">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="b33a1-167">ソースオブジェクトが blob の場合は、コピー操作中にその blob へのアクセスを認証するための SAS を作成します。</span><span class="sxs-lookup"><span data-stu-id="b33a1-167">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="b33a1-168">メトリックを使用したファイルストレージのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b33a1-168">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="b33a1-169">Azure Storage Analytics は、ファイルストレージのメトリックをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b33a1-169">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="b33a1-170">メトリックデータを使用して、要求をトレースし、問題を診断することができます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-170">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="b33a1-171">[Azure Portal](https://portal.azure.com)から File storage のメトリックを有効にすることも、次のF#ようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b33a1-171">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="b33a1-172">次の手順</span><span class="sxs-lookup"><span data-stu-id="b33a1-172">Next steps</span></span>

<span data-ttu-id="b33a1-173">Azure File storage の詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b33a1-173">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="b33a1-174">概念に関する記事とビデオ</span><span class="sxs-lookup"><span data-stu-id="b33a1-174">Conceptual articles and videos</span></span>

- [<span data-ttu-id="b33a1-175">Azure Files Storage: Windows および Linux 用の、競合のないクラウド SMB ファイルシステム</span><span class="sxs-lookup"><span data-stu-id="b33a1-175">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="b33a1-176">Linux で Azure File Storage を使用する方法</span><span class="sxs-lookup"><span data-stu-id="b33a1-176">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="b33a1-177">ファイルストレージのツールのサポート</span><span class="sxs-lookup"><span data-stu-id="b33a1-177">Tooling support for File storage</span></span>

- [<span data-ttu-id="b33a1-178">Azure Storage での Azure PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="b33a1-178">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="b33a1-179">Microsoft Azure Storage で AzCopy を使用する方法</span><span class="sxs-lookup"><span data-stu-id="b33a1-179">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="b33a1-180">Azure Storage での Azure CLI の使用</span><span class="sxs-lookup"><span data-stu-id="b33a1-180">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="b33a1-181">参照</span><span class="sxs-lookup"><span data-stu-id="b33a1-181">Reference</span></span>

- [<span data-ttu-id="b33a1-182">.NET 用ストレージクライアントライブラリのリファレンス</span><span class="sxs-lookup"><span data-stu-id="b33a1-182">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="b33a1-183">ファイルサービス REST API リファレンス</span><span class="sxs-lookup"><span data-stu-id="b33a1-183">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="b33a1-184">ブログ投稿</span><span class="sxs-lookup"><span data-stu-id="b33a1-184">Blog posts</span></span>

- [<span data-ttu-id="b33a1-185">Azure File storage の一般提供が開始されました</span><span class="sxs-lookup"><span data-stu-id="b33a1-185">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="b33a1-186">Azure File Storage 内</span><span class="sxs-lookup"><span data-stu-id="b33a1-186">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [<span data-ttu-id="b33a1-187">Microsoft Azure ファイルサービスの概要</span><span class="sxs-lookup"><span data-stu-id="b33a1-187">Introducing Microsoft Azure File Service</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [<span data-ttu-id="b33a1-188">Microsoft Azure ファイルへの接続の保持</span><span class="sxs-lookup"><span data-stu-id="b33a1-188">Persisting connections to Microsoft Azure Files</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
