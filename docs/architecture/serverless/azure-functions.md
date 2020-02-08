---
title: Azure Functions - サーバーレス アプリ
description: Azure Functions には、イベント ドリブンのインスタント スケール コードを提供する、複数の言語 (C#、JavaScript、Java) とプラットフォーム向けのサーバーレス機能が用意されています。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 8764e6a33f3fdd53e60fa767d0fb584a9c07de7e
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920974"
---
# <a name="azure-functions"></a><span data-ttu-id="1f035-103">Azure Functions</span><span class="sxs-lookup"><span data-stu-id="1f035-103">Azure Functions</span></span>

<span data-ttu-id="1f035-104">Azure Functions によってサーバーレスのコンピューティング エクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="1f035-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="1f035-105">*トリガー* (HTTP エンドポイントへのアクセスやタイマーなど) によって呼び出される関数によって、コードまたはビジネス ロジックのブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="1f035-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="1f035-106">ストレージやキューなどのリソースに接続する特別な "*バインド*" も Functions でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1f035-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Azure Functions のロゴ](./media/azure-functions-logo.png)

<span data-ttu-id="1f035-108">Azure Functions フレームワークには 2 つのバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="1f035-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="1f035-109">レガシ バージョンでは完全な .NET Framework がサポートされており、新しいランタイムではクロスプラットフォームの .NET Core アプリケーションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1f035-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="1f035-110">C# 以外に、JavaScript、F#、Java などのその他の言語がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1f035-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="1f035-111">ポータルで作成する関数には、豊富なスクリプト構文が用意されています。</span><span class="sxs-lookup"><span data-stu-id="1f035-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="1f035-112">スタンドアロン プロジェクトとして作成した関数を、完全なプラットフォームのサポートと機能を使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="1f035-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="1f035-113">詳細については、「[Azure Functions のドキュメント](https://docs.microsoft.com/azure/azure-functions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f035-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="1f035-114">Functions v1 と v2</span><span class="sxs-lookup"><span data-stu-id="1f035-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="1f035-115">Azure Functions ランタイムには 2 つのバージョンがあります: 1.x と 2.x。</span><span class="sxs-lookup"><span data-stu-id="1f035-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="1f035-116">バージョン 1.x は一般提供 (GA) されています。</span><span class="sxs-lookup"><span data-stu-id="1f035-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="1f035-117">ポータルまたは Windows コンピューターからの .NET 開発がサポートされており、.NET Framework が使用されています。</span><span class="sxs-lookup"><span data-stu-id="1f035-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="1f035-118">1.x では C#、JavaScript、F# がサポートされており、Python、PHP、TypeScript、Batch、Bash、PowerShell が実験的にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1f035-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="1f035-119">[現在はバージョン 2.x も一般提供されています](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/)。</span><span class="sxs-lookup"><span data-stu-id="1f035-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="1f035-120">.NET Core を使用し、Windows、macOS、Linux コンピューターでのクロスプラットフォーム開発がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1f035-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="1f035-121">2.x には Java の最高レベルのサポートが追加されていますが、実験的な言語はまだ直接サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1f035-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="1f035-122">バージョン 2.x では、新しいバインド拡張モデルを使用して、プラットフォームに対するサードパーティ製の拡張機能、バインドの独立したバージョン管理、より効率化された実行環境を実現しています。</span><span class="sxs-lookup"><span data-stu-id="1f035-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="1f035-123">**1. x には[バインド リダイレクトのサポート](https://github.com/Azure/azure-functions-host/issues/992)に関する既知の問題があります。**</span><span class="sxs-lookup"><span data-stu-id="1f035-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="1f035-124">その問題は .NET 開発に固有です。</span><span class="sxs-lookup"><span data-stu-id="1f035-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="1f035-125">ランタイムに含まれているライブラリとは異なるバージョンのライブラリに依存しているプロジェクトに影響します。</span><span class="sxs-lookup"><span data-stu-id="1f035-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="1f035-126">Functions チームは、問題の具体的な進展に努めています。</span><span class="sxs-lookup"><span data-stu-id="1f035-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="1f035-127">チームは、2. x が一般提供される前にバインド リダイレクトに対応する予定です。</span><span class="sxs-lookup"><span data-stu-id="1f035-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="1f035-128">修正案と回避策が記載された公式のチーム ステートメントについては、こちらを参照してください: [Azure Functions でのアセンブリ解決](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions)。</span><span class="sxs-lookup"><span data-stu-id="1f035-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="1f035-129">詳細については、[1.x と 2.x の比較](https://docs.microsoft.com/azure/azure-functions/functions-versions)のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f035-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="1f035-130">プログラミング言語のサポート</span><span class="sxs-lookup"><span data-stu-id="1f035-130">Programming language support</span></span>

<span data-ttu-id="1f035-131">次の言語は、一般提供 (GA)、プレビュー、試験段階のいずれかでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1f035-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="1f035-132">言語</span><span class="sxs-lookup"><span data-stu-id="1f035-132">Language</span></span>      |<span data-ttu-id="1f035-133">1.x</span><span class="sxs-lookup"><span data-stu-id="1f035-133">1.x</span></span>         |<span data-ttu-id="1f035-134">2.x</span><span class="sxs-lookup"><span data-stu-id="1f035-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="1f035-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="1f035-135">**C#**</span></span>        |<span data-ttu-id="1f035-136">GA</span><span class="sxs-lookup"><span data-stu-id="1f035-136">GA</span></span>          |<span data-ttu-id="1f035-137">[プレビュー]</span><span class="sxs-lookup"><span data-stu-id="1f035-137">Preview</span></span>  |
|<span data-ttu-id="1f035-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="1f035-138">**JavaScript**</span></span>|<span data-ttu-id="1f035-139">GA</span><span class="sxs-lookup"><span data-stu-id="1f035-139">GA</span></span>          |<span data-ttu-id="1f035-140">[プレビュー]</span><span class="sxs-lookup"><span data-stu-id="1f035-140">Preview</span></span>  |
|<span data-ttu-id="1f035-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="1f035-141">**F#**</span></span>        |<span data-ttu-id="1f035-142">GA</span><span class="sxs-lookup"><span data-stu-id="1f035-142">GA</span></span>          |         |
|<span data-ttu-id="1f035-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="1f035-143">**Java**</span></span>      |            |<span data-ttu-id="1f035-144">[プレビュー]</span><span class="sxs-lookup"><span data-stu-id="1f035-144">Preview</span></span>  |
|<span data-ttu-id="1f035-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="1f035-145">**Python**</span></span>    |<span data-ttu-id="1f035-146">実験用</span><span class="sxs-lookup"><span data-stu-id="1f035-146">Experimental</span></span>|         |
|<span data-ttu-id="1f035-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="1f035-147">**PHP**</span></span>       |<span data-ttu-id="1f035-148">実験用</span><span class="sxs-lookup"><span data-stu-id="1f035-148">Experimental</span></span>|         |
|<span data-ttu-id="1f035-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="1f035-149">**TypeScript**</span></span>|<span data-ttu-id="1f035-150">実験用</span><span class="sxs-lookup"><span data-stu-id="1f035-150">Experimental</span></span>|         |
|<span data-ttu-id="1f035-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="1f035-151">**Batch**</span></span>     |<span data-ttu-id="1f035-152">実験用</span><span class="sxs-lookup"><span data-stu-id="1f035-152">Experimental</span></span>|         |
|<span data-ttu-id="1f035-153">**Bash**</span><span class="sxs-lookup"><span data-stu-id="1f035-153">**Bash**</span></span>      |<span data-ttu-id="1f035-154">実験用</span><span class="sxs-lookup"><span data-stu-id="1f035-154">Experimental</span></span>|         |
|<span data-ttu-id="1f035-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1f035-155">**PowerShell**</span></span>|<span data-ttu-id="1f035-156">実験用</span><span class="sxs-lookup"><span data-stu-id="1f035-156">Experimental</span></span>|         |

<span data-ttu-id="1f035-157">詳細については、[サポートされている言語](https://docs.microsoft.com/azure/azure-functions/supported-languages)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f035-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="1f035-158">App Service プラン</span><span class="sxs-lookup"><span data-stu-id="1f035-158">App service plans</span></span>

<span data-ttu-id="1f035-159">Functions は "*App Service プラン*" によってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1f035-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="1f035-160">このプランでは、関数アプリによって使用されるリソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="1f035-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="1f035-161">プランをリージョンに割り当て、使用される仮想マシンのサイズと数を決定し、価格レベルを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="1f035-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="1f035-162">真のサーバーレス アプローチとして、関数アプリで**従量課金**プランを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1f035-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="1f035-163">従量課金プランでは、負荷に基づいてバックエンドが自動的にスケーリングされます。</span><span class="sxs-lookup"><span data-stu-id="1f035-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="1f035-164">詳細については、[App Service プラン](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f035-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="1f035-165">最初の関数を作成する</span><span class="sxs-lookup"><span data-stu-id="1f035-165">Create your first function</span></span>

<span data-ttu-id="1f035-166">関数アプリを作成するには、3 つの一般的な方法があります。</span><span class="sxs-lookup"><span data-stu-id="1f035-166">There are three common ways you can create function apps.</span></span>

- <span data-ttu-id="1f035-167">ポータルで関数をスクリプト化します。</span><span class="sxs-lookup"><span data-stu-id="1f035-167">Script functions in the portal.</span></span>
- <span data-ttu-id="1f035-168">Azure CLI を使用して必要なリソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f035-168">Create the necessary resources using the Azure CLI.</span></span>
- <span data-ttu-id="1f035-169">お気に入りの IDE を使用してローカルで関数をビルドし、Azure に発行します。</span><span class="sxs-lookup"><span data-stu-id="1f035-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="1f035-170">スクリプト化された関数をポータル上で作成する方法の詳細については、「[Azure portal で初めての関数を作成する](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f035-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="1f035-171">Azure CLI からビルドするには、[Azure CLI を使用して初めての関数を作成する](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)方法に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f035-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="1f035-172">Visual Studio で関数を作成するには、「[Visual Studio を使用して初めての関数を作成する](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f035-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="1f035-173">トリガーとバインドについて</span><span class="sxs-lookup"><span data-stu-id="1f035-173">Understand triggers and bindings</span></span>

<span data-ttu-id="1f035-174">関数は "*トリガー*" によって呼び出されます。関数に設定できるトリガーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="1f035-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="1f035-175">関数を呼び出すだけでなく、特定のトリガーにはバインドとしての機能もあります。</span><span class="sxs-lookup"><span data-stu-id="1f035-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="1f035-176">トリガーに加えて、複数のバインドを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="1f035-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="1f035-177">"*バインド*" は、宣言によってデータをコードに接続する方法です。</span><span class="sxs-lookup"><span data-stu-id="1f035-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="1f035-178">渡される場合 (入力) と、データを受け取る場合 (出力) があります。</span><span class="sxs-lookup"><span data-stu-id="1f035-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="1f035-179">トリガーとバインドを使用すると、関数を使用した作業が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="1f035-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="1f035-180">バインドによって、データベースまたはファイル システムの接続を手動で作成するオーバーヘッドが解消されます。</span><span class="sxs-lookup"><span data-stu-id="1f035-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="1f035-181">バインドに必要なすべての情報は、*functions.json* というスクリプト用の特別なファイル内に格納されます。または、コード内で属性を使用して宣言します。</span><span class="sxs-lookup"><span data-stu-id="1f035-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="1f035-182">次のような一般的なトリガーがあります。</span><span class="sxs-lookup"><span data-stu-id="1f035-182">Some common triggers include:</span></span>

- <span data-ttu-id="1f035-183">Blob Storage: ストレージ内でファイルまたはフォルダーがアップロードまたは変更されたときに、関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1f035-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
- <span data-ttu-id="1f035-184">HTTP: REST API のように関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1f035-184">HTTP: invoke your function like a REST API.</span></span>
- <span data-ttu-id="1f035-185">キュー: キューに項目が存在する場合に関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1f035-185">Queue: invoke your function when items exist in a queue.</span></span>
- <span data-ttu-id="1f035-186">タイマー: 関数を定期的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1f035-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="1f035-187">バインドの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1f035-187">Examples of bindings include:</span></span>

- <span data-ttu-id="1f035-188">CosmosDB: データベースに簡単に接続して、ファイルを読み込んだり保存したりできます。</span><span class="sxs-lookup"><span data-stu-id="1f035-188">CosmosDB: easily connect to the database to load or save files.</span></span>
- <span data-ttu-id="1f035-189">Table Storage: 関数アプリからキー/値のストレージを操作します。</span><span class="sxs-lookup"><span data-stu-id="1f035-189">Table Storage: work with key/value storage from your function app.</span></span>
- <span data-ttu-id="1f035-190">Queue Storage: キューからの項目の取得、または新しい項目のキューへの配置を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1f035-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="1f035-191">次の *functions.json* ファイルの例では、トリガーとバインドを定義しています。</span><span class="sxs-lookup"><span data-stu-id="1f035-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

<span data-ttu-id="1f035-192">この例では、`images` コンテナー内での BLOB ストレージに対する変更によって関数がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="1f035-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="1f035-193">ファイルの情報が渡され、トリガーはバインドとしても機能します。</span><span class="sxs-lookup"><span data-stu-id="1f035-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="1f035-194">`images` という名前のキューに情報を格納するための別のバインドが存在します。</span><span class="sxs-lookup"><span data-stu-id="1f035-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="1f035-195">関数の C# スクリプトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1f035-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="1f035-196">この例は、BLOB ストレージ内の変更またはアップロードされたファイルの名前を取得し、後で処理するためにキューに配置する単純な関数です。</span><span class="sxs-lookup"><span data-stu-id="1f035-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="1f035-197">トリガーとバインドの完全な一覧については、「[Azure Functions でのトリガーとバインドの概念](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f035-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="1f035-198">プロキシ</span><span class="sxs-lookup"><span data-stu-id="1f035-198">Proxies</span></span>

<span data-ttu-id="1f035-199">プロキシによってアプリケーションにリダイレクト機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1f035-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="1f035-200">プロキシはエンドポイントを公開し、そのエンドポイントを別のリソースにマップするものです。</span><span class="sxs-lookup"><span data-stu-id="1f035-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="1f035-201">プロキシを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="1f035-201">With proxies, you can:</span></span>

- <span data-ttu-id="1f035-202">受信要求を別のエンドポイントに再ルーティングする。</span><span class="sxs-lookup"><span data-stu-id="1f035-202">Reroute an incoming request to another endpoint.</span></span>
- <span data-ttu-id="1f035-203">受信要求を、渡す前に変更する。</span><span class="sxs-lookup"><span data-stu-id="1f035-203">Modify the incoming request before it's passed along.</span></span>
- <span data-ttu-id="1f035-204">応答を変更または提供する。</span><span class="sxs-lookup"><span data-stu-id="1f035-204">Modify or provide a response.</span></span>

<span data-ttu-id="1f035-205">プロキシは次のようなシナリオに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f035-205">Proxies are used for scenarios such as:</span></span>

- <span data-ttu-id="1f035-206">URL を簡略化、短縮、または変更する。</span><span class="sxs-lookup"><span data-stu-id="1f035-206">Simplifying, shortening, or changing the URL.</span></span>
- <span data-ttu-id="1f035-207">複数のバックエンド サービスに一貫した API プレフィックスを提供する。</span><span class="sxs-lookup"><span data-stu-id="1f035-207">Providing a consistent API prefix to multiple back-end services.</span></span>
- <span data-ttu-id="1f035-208">開発中のエンドポイントに対する応答のモックを作成する。</span><span class="sxs-lookup"><span data-stu-id="1f035-208">Mocking a response to an endpoint being developed.</span></span>
- <span data-ttu-id="1f035-209">既知のエンドポイントに対する静的な応答を提供する。</span><span class="sxs-lookup"><span data-stu-id="1f035-209">Providing a static response to a well-known endpoint.</span></span>
- <span data-ttu-id="1f035-210">バックエンドの移動または移行中に、API エンドポイントの整合性を維持する。</span><span class="sxs-lookup"><span data-stu-id="1f035-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="1f035-211">プロキシは JSON 定義として格納されます。</span><span class="sxs-lookup"><span data-stu-id="1f035-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="1f035-212">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1f035-212">Here is an example:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/proxies",
  "proxies": {
    "Domain Redirect": {
      "matchCondition": {
        "route": "/{shortUrl}"
      },
      "backendUri": "http://%WEBSITE_HOSTNAME%/api/UrlRedirect/{shortUrl}"
    },
    "Root": {
      "matchCondition": {
        "route": "/"
      },
      "responseOverrides": {
        "response.statusCode": "301",
        "response.statusReason": "Moved Permanently",
        "response.headers.location": "https://docs.microsoft.com/"
      }
    }
  }
}
```

<span data-ttu-id="1f035-213">`Domain Redirect` プロキシによって短いルートを取得し、それをルートの長い関数リソースにマップします。</span><span class="sxs-lookup"><span data-stu-id="1f035-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="1f035-214">この変換は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1f035-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="1f035-215">`Root` プロキシは、ルート URL (`https://--shorturl--/`) に送信されたものすべてを取得し、それをドキュメント サイトにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="1f035-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="1f035-216">プロキシの使用例については、ビデオ「[Azure: サーバーレスの Azure Functions を使用してアプリをクラウドに持ち込む](https://channel9.msdn.com/events/Connect/2017/E102)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1f035-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="1f035-217">ローカルの SQL Server 上で実行されている ASP.NET Core アプリケーションが、リアルタイムで Azure Cloud に移行されます。</span><span class="sxs-lookup"><span data-stu-id="1f035-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="1f035-218">プロキシは、従来の Web API プロジェクトを、関数を使用するようにリファクターするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f035-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="1f035-219">プロキシの詳細については、「[Azure Functions プロキシの操作](https://docs.microsoft.com/azure/azure-functions/functions-proxies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f035-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1f035-220">[前へ](azure-serverless-platform.md)
>[次へ](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="1f035-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
