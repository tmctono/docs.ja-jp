---
title: F# を使用した Azure File Storage の概要
description: Azure File Storage を使用してクラウドにファイル データを格納し、Azure 仮想マシン (VM) から、または Windows を実行しているオンプレミスのアプリケーションからクラウド ファイル共有をマウントします。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: d58417e1e3161b958754e01423136a9cdd6a08a6
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935627"
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="f55e0-103">F\# を使用した Azure File storage の概要</span><span class="sxs-lookup"><span data-stu-id="f55e0-103">Get started with Azure File storage using F\#</span></span>

<span data-ttu-id="f55e0-104">Azure File Storage は、標準の [サーバー メッセージ ブロック (SMB) プロトコル](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)を使用してクラウドでファイル共有を提供するサービスです。</span><span class="sxs-lookup"><span data-stu-id="f55e0-104">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="f55e0-105">SMB 2.1 と SMB 3.0 の両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-105">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="f55e0-106">Azure File Storage を使用すると、コストがかかる書き換えを行わずに、ファイル共有に依存しているレガシ アプリケーションをすばやく Azure に移行することができます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-106">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="f55e0-107">Azure 仮想マシンまたはクラウド サービスで実行されているアプリケーション、またはオンプレミスのクライアントから実行されているアプリケーションは、デスクトップ アプリケーションが一般的な SMB 共有をマウントするのと同じように、クラウドにファイル共有をマウントできます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-107">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="f55e0-108">このため、任意の数のアプリケーション コンポーネントが、File Storage 共有をマウントして同時にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-108">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="f55e0-109">File storage の概念の概要については、「 [.net ガイド](/azure/storage/storage-dotnet-how-to-use-files)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f55e0-109">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f55e0-110">[前提条件]</span><span class="sxs-lookup"><span data-stu-id="f55e0-110">Prerequisites</span></span>

<span data-ttu-id="f55e0-111">このガイドを使用するには、最初に[Azure ストレージアカウントを作成](/azure/storage/storage-create-storage-account)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f55e0-111">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="f55e0-112">また、このアカウントのストレージアクセスキーも必要になります。</span><span class="sxs-lookup"><span data-stu-id="f55e0-112">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="f55e0-113">F#スクリプトを作成してF#対話形式で起動する</span><span class="sxs-lookup"><span data-stu-id="f55e0-113">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="f55e0-114">この記事のサンプルは、 F#アプリケーションまたはF#スクリプトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-114">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="f55e0-115">F#スクリプトを作成するには、 F#開発環境で `files.fsx`などの `.fsx` 拡張機能を使用してファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-115">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="f55e0-116">次に、[パケット](https://fsprojects.github.io/Paket/)や[NuGet](https://www.nuget.org/)などの[パッケージマネージャー](package-management.md)を使用して、`#r` ディレクティブを使用してスクリプトに `WindowsAzure.Storage` パッケージと参照 `WindowsAzure.Storage.dll` をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f55e0-116">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="f55e0-117">名前空間宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="f55e0-117">Add namespace declarations</span></span>

<span data-ttu-id="f55e0-118">次の `open` ステートメントを `files.fsx` ファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-118">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="f55e0-119">接続文字列を取得する</span><span class="sxs-lookup"><span data-stu-id="f55e0-119">Get your connection string</span></span>

<span data-ttu-id="f55e0-120">このチュートリアルでは、Azure Storage 接続文字列が必要です。</span><span class="sxs-lookup"><span data-stu-id="f55e0-120">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="f55e0-121">接続文字列の詳細については、「[ストレージ接続文字列の構成](/azure/storage/storage-configure-connection-string)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f55e0-121">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="f55e0-122">このチュートリアルでは、次のように、スクリプトに接続文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-122">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="f55e0-123">ただし、実際のプロジェクトではこの方法は**お勧めできません**。</span><span class="sxs-lookup"><span data-stu-id="f55e0-123">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="f55e0-124">ストレージ アカウント キーは、ストレージ アカウントの root パスワードに似ています。</span><span class="sxs-lookup"><span data-stu-id="f55e0-124">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="f55e0-125">ストレージ アカウント キーは常に慎重に保護してください。</span><span class="sxs-lookup"><span data-stu-id="f55e0-125">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="f55e0-126">このキーを他のユーザーに配布したり、ハードコーディングしたり、他のユーザーがアクセスできるプレーン テキスト ファイルに保存したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="f55e0-126">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="f55e0-127">侵害された可能性があると思われる場合は、Azure ポータルを使用してキーを再生成することができます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-127">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="f55e0-128">実際のアプリケーションでは、ストレージ接続文字列を維持する最善の方法は構成ファイルにあります。</span><span class="sxs-lookup"><span data-stu-id="f55e0-128">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="f55e0-129">構成ファイルから接続文字列を取得するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-129">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="f55e0-130">Azure Configuration Manager の使用はオプションです。</span><span class="sxs-lookup"><span data-stu-id="f55e0-130">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="f55e0-131">.NET Framework の `ConfigurationManager` の種類などの API を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-131">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="f55e0-132">接続文字列を解析する</span><span class="sxs-lookup"><span data-stu-id="f55e0-132">Parse the connection string</span></span>

<span data-ttu-id="f55e0-133">接続文字列を解析するには、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-133">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="f55e0-134">これにより、`CloudStorageAccount`が返されます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-134">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="f55e0-135">ファイルサービスクライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="f55e0-135">Create the File service client</span></span>

<span data-ttu-id="f55e0-136">`CloudFileClient` の種類を使用すると、ファイルストレージに格納されているファイルをプログラムで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-136">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="f55e0-137">サービス クライアントを作成する方法の 1 つを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-137">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="f55e0-138">これで、からデータを読み取り、ファイルストレージにデータを書き込むコードを記述する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="f55e0-138">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="f55e0-139">ファイル共有の作成</span><span class="sxs-lookup"><span data-stu-id="f55e0-139">Create a file share</span></span>

<span data-ttu-id="f55e0-140">この例では、ファイル共有がまだ存在しない場合に作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-140">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="f55e0-141">ルートディレクトリとサブディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="f55e0-141">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="f55e0-142">ここでは、ルートディレクトリを取得し、ルートのサブディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-142">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="f55e0-143">まだ存在しない場合は、両方を作成します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-143">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="f55e0-144">テキストをファイルとしてアップロードする</span><span class="sxs-lookup"><span data-stu-id="f55e0-144">Upload text as a file</span></span>

<span data-ttu-id="f55e0-145">この例では、テキストをファイルとしてアップロードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-145">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="f55e0-146">ファイルのローカルコピーにファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f55e0-146">Download a file to a local copy of the file</span></span>

<span data-ttu-id="f55e0-147">ここでは、作成したばかりのファイルをダウンロードし、ローカルファイルに内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-147">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="f55e0-148">ファイル共有の最大サイズの設定</span><span class="sxs-lookup"><span data-stu-id="f55e0-148">Set the maximum size for a file share</span></span>

<span data-ttu-id="f55e0-149">次の例では、共有の現在の使用状況を確認する方法と、共有のクォータを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-149">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="f55e0-150">共有の `Properties`を設定 `SetProperties` し、ローカルの変更を Azure File storage に反映するために `FetchAttributes` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f55e0-150">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="f55e0-151">ファイルまたはファイル共有の Shared Access Signature の生成</span><span class="sxs-lookup"><span data-stu-id="f55e0-151">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="f55e0-152">ファイル共有または個々のファイルの Shared Access Signature (SAS) を生成することができます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-152">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="f55e0-153">また、ファイル共有に共有アクセス ポリシーを作成して、Shared Access Signature を管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-153">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="f55e0-154">共有アクセス ポリシーを作成することをお勧めします。これにより、侵害されそうな場合に SAS を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-154">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="f55e0-155">ここでは、共有に対して共有アクセスポリシーを作成し、そのポリシーを使用して、共有内のファイルの SAS に対する制約を指定します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-155">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="f55e0-156">Shared Access Signature の作成と使用の詳細については、「[Shared Access Signature (SAS) の使用](/azure/storage/storage-dotnet-shared-access-signature-part-1)」と、[Blob Storage での SAS の作成と使用](/azure/storage/storage-dotnet-shared-access-signature-part-2)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f55e0-156">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="f55e0-157">ファイルをコピーする</span><span class="sxs-lookup"><span data-stu-id="f55e0-157">Copy files</span></span>

<span data-ttu-id="f55e0-158">ファイルを別のファイルまたは blob にコピーしたり、blob をファイルにコピーしたりできます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-158">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="f55e0-159">Blob をファイルにコピーする場合、またはファイルを blob にコピーする場合は、同じストレージアカウント内でコピーする場合でも、共有アクセス署名 (SAS) を使用してソースオブジェクトを認証する*必要があり*ます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-159">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="f55e0-160">別のファイルへのファイルのコピー</span><span class="sxs-lookup"><span data-stu-id="f55e0-160">Copy a file to another file</span></span>

<span data-ttu-id="f55e0-161">ここでは、同じ共有内の別のファイルにファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="f55e0-161">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="f55e0-162">このコピー操作では同じストレージ アカウント内のファイルがコピーされるため、共有キー認証を使用してコピーを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-162">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="f55e0-163">BLOB へのファイルのコピー</span><span class="sxs-lookup"><span data-stu-id="f55e0-163">Copy a file to a blob</span></span>

<span data-ttu-id="f55e0-164">ここでは、ファイルを作成し、同じストレージアカウント内の blob にコピーします。</span><span class="sxs-lookup"><span data-stu-id="f55e0-164">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="f55e0-165">コピー操作中にソースファイルへのアクセスを認証するためにサービスが使用するソースファイルの SAS を作成します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-165">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="f55e0-166">同じ方法で、ファイルに BLOB をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-166">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="f55e0-167">ソース オブジェクトが BLOB である場合、SAS を作成して、コピー操作中にその BLOB へのアクセスを認証します。</span><span class="sxs-lookup"><span data-stu-id="f55e0-167">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="f55e0-168">メトリックを使用した File Storage のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f55e0-168">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="f55e0-169">Azure Storage Analytics は、ファイルストレージのメトリックをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f55e0-169">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="f55e0-170">メトリック データを使用すると、要求のトレースや問題の診断ができます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-170">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="f55e0-171">[Azure Portal](https://portal.azure.com)から File storage のメトリックを有効にすることも、次のF#ようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f55e0-171">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="f55e0-172">次のステップ:</span><span class="sxs-lookup"><span data-stu-id="f55e0-172">Next steps</span></span>

<span data-ttu-id="f55e0-173">Azure File Storage の詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f55e0-173">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="f55e0-174">概念に関する記事とビデオ</span><span class="sxs-lookup"><span data-stu-id="f55e0-174">Conceptual articles and videos</span></span>

- [<span data-ttu-id="f55e0-175">Azure File Storage: Windows および Linux 用の円滑なクラウド SMB ファイル システム</span><span class="sxs-lookup"><span data-stu-id="f55e0-175">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="f55e0-176">Linux で Azure File Storage を使用する方法</span><span class="sxs-lookup"><span data-stu-id="f55e0-176">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="f55e0-177">File Storage 用のツールのサポート</span><span class="sxs-lookup"><span data-stu-id="f55e0-177">Tooling support for File storage</span></span>

- [<span data-ttu-id="f55e0-178">Azure Storage での Azure PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="f55e0-178">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="f55e0-179">Microsoft Azure Storage で AzCopy を使用する方法</span><span class="sxs-lookup"><span data-stu-id="f55e0-179">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="f55e0-180">Azure Storage での Azure CLI の使用</span><span class="sxs-lookup"><span data-stu-id="f55e0-180">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="f55e0-181">参照先</span><span class="sxs-lookup"><span data-stu-id="f55e0-181">Reference</span></span>

- [<span data-ttu-id="f55e0-182">.NET 用ストレージ クライアント ライブラリ リファレンス</span><span class="sxs-lookup"><span data-stu-id="f55e0-182">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="f55e0-183">File サービスの REST API リファレンス</span><span class="sxs-lookup"><span data-stu-id="f55e0-183">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="f55e0-184">ブログの投稿</span><span class="sxs-lookup"><span data-stu-id="f55e0-184">Blog posts</span></span>

- [<span data-ttu-id="f55e0-185">Azure File Storage の一般提供開始</span><span class="sxs-lookup"><span data-stu-id="f55e0-185">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="f55e0-186">Inside Azure File Storage (Azure File Storage の内部)</span><span class="sxs-lookup"><span data-stu-id="f55e0-186">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [<span data-ttu-id="f55e0-187">Microsoft Azure File サービスの概要</span><span class="sxs-lookup"><span data-stu-id="f55e0-187">Introducing Microsoft Azure File Service</span></span>](https://docs.microsoft.com/archive/blogs/windowsazurestorage/introducing-microsoft-azure-file-service)
- [<span data-ttu-id="f55e0-188">Microsoft Azure Files への接続の維持</span><span class="sxs-lookup"><span data-stu-id="f55e0-188">Persisting connections to Microsoft Azure Files</span></span>](https://docs.microsoft.com/archive/blogs/windowsazurestorage/persisting-connections-to-microsoft-azure-files)
