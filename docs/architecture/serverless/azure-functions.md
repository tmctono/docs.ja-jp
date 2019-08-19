---
title: Azure Functions サーバーレスアプリ
description: Azure functions では、複数の言語 (C#、JavaScript、Java) とプラットフォームに対してサーバーレスの機能を提供し、イベントドリブンのインスタントスケールコードを提供します。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4febcc01eebf3efce3fc1eb42e19c2ec6c0baa52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577605"
---
# <a name="azure-functions"></a><span data-ttu-id="6edda-103">Azure Functions</span><span class="sxs-lookup"><span data-stu-id="6edda-103">Azure Functions</span></span>

<span data-ttu-id="6edda-104">Azure functions は、サーバーレスのコンピューティングエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6edda-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="6edda-105">関数は、*トリガー* (HTTP エンドポイントまたはタイマーへのアクセスなど) によって呼び出され、コードまたはビジネスロジックのブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="6edda-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="6edda-106">関数は、ストレージやキューなどのリソースに接続する特殊な*バインド*もサポートします。</span><span class="sxs-lookup"><span data-stu-id="6edda-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Azure functions のロゴ](./media/azure-functions-logo.png)

<span data-ttu-id="6edda-108">Azure Functions framework には2つのバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="6edda-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="6edda-109">レガシバージョンでは完全な .NET Framework がサポートされており、新しいランタイムはクロスプラットフォームの .NET Core アプリケーションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6edda-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="6edda-110">JavaScript、 F#、 C# Java など、その他の言語もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6edda-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="6edda-111">ポータルで作成された関数は、豊富なスクリプト構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="6edda-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="6edda-112">スタンドアロンプロジェクトとして作成された関数は、完全なプラットフォームのサポートおよび機能を使用して配置できます。</span><span class="sxs-lookup"><span data-stu-id="6edda-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="6edda-113">詳細については、 [Azure Functions のドキュメント](https://docs.microsoft.com/azure/azure-functions)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6edda-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="6edda-114">Functions v1 と v2</span><span class="sxs-lookup"><span data-stu-id="6edda-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="6edda-115">Azure Functions ランタイムには、次の2つのバージョンがあります。1.x および2.x。</span><span class="sxs-lookup"><span data-stu-id="6edda-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="6edda-116">バージョン1.x は一般公開 (GA) されています。</span><span class="sxs-lookup"><span data-stu-id="6edda-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="6edda-117">ポータルまたは Windows マシンからの .NET 開発をサポートし、.NET Framework を使用します。</span><span class="sxs-lookup"><span data-stu-id="6edda-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="6edda-118">1.x は、Python C#、PHP、TypeScript F#、Batch、Bash、および PowerShell の実験的なサポートを使用して、、JavaScript、およびをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6edda-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="6edda-119">[バージョン2.x も一般公開さ](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/)れています。</span><span class="sxs-lookup"><span data-stu-id="6edda-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="6edda-120">.NET Core を活用し、Windows、macOS、Linux コンピューターでのクロスプラットフォーム開発をサポートします。</span><span class="sxs-lookup"><span data-stu-id="6edda-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="6edda-121">2.x では Java のファーストクラスのサポートが追加されますが、実験的な言語はまだ直接サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6edda-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="6edda-122">バージョン2.x では、新しいバインド拡張モデルを使用して、プラットフォームに対するサードパーティ製の拡張機能、バインドの独立したバージョン管理、より合理化された実行環境を実現しています。</span><span class="sxs-lookup"><span data-stu-id="6edda-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="6edda-123">**1. x に[バインドリダイレクトをサポート](https://github.com/Azure/azure-functions-host/issues/992)する既知の問題があります。**</span><span class="sxs-lookup"><span data-stu-id="6edda-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="6edda-124">この問題は、.NET 開発に固有のものです。</span><span class="sxs-lookup"><span data-stu-id="6edda-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="6edda-125">ランタイムに含まれているライブラリとは異なるバージョンのライブラリに依存しているプロジェクトが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="6edda-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="6edda-126">Functions チームは、問題の具体的な進行状況に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="6edda-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="6edda-127">チームは、一般公開される前に、2. x のバインドリダイレクトに対応します。</span><span class="sxs-lookup"><span data-stu-id="6edda-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="6edda-128">修正案と回避策が記載された公式のチームステートメントについては、こちらを参照してください。[Azure Functions でのアセンブリの解決](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions)。</span><span class="sxs-lookup"><span data-stu-id="6edda-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="6edda-129">詳細については、「 [1. x と](https://docs.microsoft.com/azure/azure-functions/functions-versions)2.X を比較する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6edda-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="6edda-130">プログラミング言語のサポート</span><span class="sxs-lookup"><span data-stu-id="6edda-130">Programming language support</span></span>

<span data-ttu-id="6edda-131">次の言語は、一般公開 (GA)、プレビュー、試験段階のいずれかでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6edda-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="6edda-132">言語</span><span class="sxs-lookup"><span data-stu-id="6edda-132">Language</span></span>      |<span data-ttu-id="6edda-133">記憶</span><span class="sxs-lookup"><span data-stu-id="6edda-133">1.x</span></span>         |<span data-ttu-id="6edda-134">2.x</span><span class="sxs-lookup"><span data-stu-id="6edda-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="6edda-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="6edda-135">**C#**</span></span>        |<span data-ttu-id="6edda-136">VGA</span><span class="sxs-lookup"><span data-stu-id="6edda-136">GA</span></span>          |<span data-ttu-id="6edda-137">[プレビュー]</span><span class="sxs-lookup"><span data-stu-id="6edda-137">Preview</span></span>  |
|<span data-ttu-id="6edda-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="6edda-138">**JavaScript**</span></span>|<span data-ttu-id="6edda-139">VGA</span><span class="sxs-lookup"><span data-stu-id="6edda-139">GA</span></span>          |<span data-ttu-id="6edda-140">[プレビュー]</span><span class="sxs-lookup"><span data-stu-id="6edda-140">Preview</span></span>  |
|<span data-ttu-id="6edda-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="6edda-141">**F#**</span></span>        |<span data-ttu-id="6edda-142">VGA</span><span class="sxs-lookup"><span data-stu-id="6edda-142">GA</span></span>          |         |
|<span data-ttu-id="6edda-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="6edda-143">**Java**</span></span>      |            |<span data-ttu-id="6edda-144">[プレビュー]</span><span class="sxs-lookup"><span data-stu-id="6edda-144">Preview</span></span>  |
|<span data-ttu-id="6edda-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="6edda-145">**Python**</span></span>    |<span data-ttu-id="6edda-146">実験用</span><span class="sxs-lookup"><span data-stu-id="6edda-146">Experimental</span></span>|         |
|<span data-ttu-id="6edda-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="6edda-147">**PHP**</span></span>       |<span data-ttu-id="6edda-148">実験用</span><span class="sxs-lookup"><span data-stu-id="6edda-148">Experimental</span></span>|         |
|<span data-ttu-id="6edda-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="6edda-149">**TypeScript**</span></span>|<span data-ttu-id="6edda-150">実験用</span><span class="sxs-lookup"><span data-stu-id="6edda-150">Experimental</span></span>|         |
|<span data-ttu-id="6edda-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="6edda-151">**Batch**</span></span>     |<span data-ttu-id="6edda-152">実験用</span><span class="sxs-lookup"><span data-stu-id="6edda-152">Experimental</span></span>|         |
|<span data-ttu-id="6edda-153">**Bash**</span><span class="sxs-lookup"><span data-stu-id="6edda-153">**Bash**</span></span>      |<span data-ttu-id="6edda-154">実験用</span><span class="sxs-lookup"><span data-stu-id="6edda-154">Experimental</span></span>|         |
|<span data-ttu-id="6edda-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6edda-155">**PowerShell**</span></span>|<span data-ttu-id="6edda-156">実験用</span><span class="sxs-lookup"><span data-stu-id="6edda-156">Experimental</span></span>|         |

<span data-ttu-id="6edda-157">詳細については、「[サポートされる言語](https://docs.microsoft.com/azure/azure-functions/supported-languages)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6edda-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="6edda-158">App service プラン</span><span class="sxs-lookup"><span data-stu-id="6edda-158">App service plans</span></span>

<span data-ttu-id="6edda-159">関数は、 *app service プラン*によって支えられています。</span><span class="sxs-lookup"><span data-stu-id="6edda-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="6edda-160">このプランでは、functions アプリによって使用されるリソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="6edda-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="6edda-161">リージョンにプランを割り当てたり、使用される仮想マシンのサイズと数を決定したり、価格レベルを選択したりできます。</span><span class="sxs-lookup"><span data-stu-id="6edda-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="6edda-162">真のサーバーレスアプローチの場合、関数アプリは**従量課金**プランを使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="6edda-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="6edda-163">従量課金プランでは、負荷に基づいてバックエンドが自動的にスケールされます。</span><span class="sxs-lookup"><span data-stu-id="6edda-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="6edda-164">詳細については、「 [App service プラン](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6edda-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="6edda-165">最初の関数を作成する</span><span class="sxs-lookup"><span data-stu-id="6edda-165">Create your first function</span></span>

<span data-ttu-id="6edda-166">関数アプリを作成するには、次の3つの一般的な方法があります。</span><span class="sxs-lookup"><span data-stu-id="6edda-166">There are three common ways you can create function apps.</span></span>

* <span data-ttu-id="6edda-167">ポータルで関数をスクリプト化します。</span><span class="sxs-lookup"><span data-stu-id="6edda-167">Script functions in the portal.</span></span>
* <span data-ttu-id="6edda-168">Azure コマンドラインインターフェイス (CLI) を使用して必要なリソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="6edda-168">Create the necessary resources using the Azure Command Line Interface (CLI).</span></span>
* <span data-ttu-id="6edda-169">お気に入りの IDE を使用してローカルで関数をビルドし、Azure に発行します。</span><span class="sxs-lookup"><span data-stu-id="6edda-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="6edda-170">ポータルでスクリプト化された関数を作成する方法の詳細については、「 [Azure portal で最初の関数を作成](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6edda-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="6edda-171">Azure CLI から構築するには、「 [Azure CLI を使用した初め](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)ての関数の作成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6edda-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="6edda-172">Visual Studio から関数を作成する方法については、「 [Visual studio を使用して初めての関数を作成](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6edda-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="6edda-173">トリガーとバインドについて</span><span class="sxs-lookup"><span data-stu-id="6edda-173">Understand triggers and bindings</span></span>

<span data-ttu-id="6edda-174">関数は*トリガー*によって呼び出され、1つだけを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="6edda-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="6edda-175">関数を呼び出すだけでなく、特定のトリガーもバインドとして機能します。</span><span class="sxs-lookup"><span data-stu-id="6edda-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="6edda-176">トリガーに加えて、複数のバインドを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="6edda-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="6edda-177">*バインディング*は、データをコードに接続するための宣言的な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="6edda-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="6edda-178">これらは、渡す (入力) か、データを受信する (出力) ことができます。</span><span class="sxs-lookup"><span data-stu-id="6edda-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="6edda-179">トリガーとバインドを使用すると、関数が簡単に操作できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6edda-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="6edda-180">バインドによって、データベースまたはファイルシステムの接続を手動で作成するオーバーヘッドが解消されます。</span><span class="sxs-lookup"><span data-stu-id="6edda-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="6edda-181">バインドに必要なすべての情報は、特別な関数の json ファイルに格納されてい*ます。* スクリプトの場合や、属性を使用してコードで宣言されている場合です。</span><span class="sxs-lookup"><span data-stu-id="6edda-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="6edda-182">次のような一般的なトリガーがあります。</span><span class="sxs-lookup"><span data-stu-id="6edda-182">Some common triggers include:</span></span>

* <span data-ttu-id="6edda-183">Blob Storage: ファイルまたはフォルダーがストレージでアップロードまたは変更されたときに、関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6edda-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
* <span data-ttu-id="6edda-184">HTTP: REST API のように関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6edda-184">HTTP: invoke your function like a REST API.</span></span>
* <span data-ttu-id="6edda-185">Queue: キューに項目が存在する場合に関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6edda-185">Queue: invoke your function when items exist in a queue.</span></span>
* <span data-ttu-id="6edda-186">Timer: 関数を定期的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6edda-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="6edda-187">バインディングの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6edda-187">Examples of bindings include:</span></span>

* <span data-ttu-id="6edda-188">CosmosDB: データベースに簡単に接続して、ファイルを読み込んだり保存したりできます。</span><span class="sxs-lookup"><span data-stu-id="6edda-188">CosmosDB: easily connect to the database to load or save files.</span></span>
* <span data-ttu-id="6edda-189">Table Storage: 関数アプリからキー/値のストレージを操作します。</span><span class="sxs-lookup"><span data-stu-id="6edda-189">Table Storage: work with key/value storage from your function app.</span></span>
* <span data-ttu-id="6edda-190">Queue Storage: キューから項目を簡単に取得したり、新しい項目をキューに配置したりできます。</span><span class="sxs-lookup"><span data-stu-id="6edda-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="6edda-191">次の関数の例では、トリガーとバインディングを定義して*います。*</span><span class="sxs-lookup"><span data-stu-id="6edda-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

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

<span data-ttu-id="6edda-192">この例では、 `images`コンテナー内の blob ストレージに対する変更によって関数がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="6edda-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="6edda-193">ファイルの情報が渡されるため、トリガーはバインドとしても機能します。</span><span class="sxs-lookup"><span data-stu-id="6edda-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="6edda-194">という名前`images`のキューに情報を格納するための別のバインディングが存在します。</span><span class="sxs-lookup"><span data-stu-id="6edda-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="6edda-195">関数のC#スクリプトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="6edda-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="6edda-196">この例は、blob ストレージに変更またはアップロードされたファイルの名前を取得し、後で処理するためにキューに配置する単純な関数です。</span><span class="sxs-lookup"><span data-stu-id="6edda-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="6edda-197">トリガーとバインディングの完全な一覧については、「 [Azure Functions のトリガーとバインドの概念](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6edda-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="6edda-198">プロキシ</span><span class="sxs-lookup"><span data-stu-id="6edda-198">Proxies</span></span>

<span data-ttu-id="6edda-199">プロキシは、アプリケーションのリダイレクト機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="6edda-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="6edda-200">プロキシはエンドポイントを公開し、そのエンドポイントを別のリソースにマップします。</span><span class="sxs-lookup"><span data-stu-id="6edda-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="6edda-201">プロキシを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="6edda-201">With proxies, you can:</span></span>

* <span data-ttu-id="6edda-202">受信要求を別のエンドポイントに再ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="6edda-202">Reroute an incoming request to another endpoint.</span></span>
* <span data-ttu-id="6edda-203">渡される前に受信要求を変更します。</span><span class="sxs-lookup"><span data-stu-id="6edda-203">Modify the incoming request before it's passed along.</span></span>
* <span data-ttu-id="6edda-204">応答を変更または提供します。</span><span class="sxs-lookup"><span data-stu-id="6edda-204">Modify or provide a response.</span></span>

<span data-ttu-id="6edda-205">プロキシは、次のようなシナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="6edda-205">Proxies are used for scenarios such as:</span></span>

* <span data-ttu-id="6edda-206">URL の簡略化、短縮、または変更。</span><span class="sxs-lookup"><span data-stu-id="6edda-206">Simplifying, shortening, or changing the URL.</span></span>
* <span data-ttu-id="6edda-207">一貫した API プレフィックスを複数のバックエンドサービスに提供します。</span><span class="sxs-lookup"><span data-stu-id="6edda-207">Providing a consistent API prefix to multiple back-end services.</span></span>
* <span data-ttu-id="6edda-208">開発中のエンドポイントへの応答をモックします。</span><span class="sxs-lookup"><span data-stu-id="6edda-208">Mocking a response to an endpoint being developed.</span></span>
* <span data-ttu-id="6edda-209">既知のエンドポイントへの静的な応答を提供します。</span><span class="sxs-lookup"><span data-stu-id="6edda-209">Providing a static response to a well-known endpoint.</span></span>
* <span data-ttu-id="6edda-210">バックエンドの移動または移行中に、API エンドポイントの整合性を維持します。</span><span class="sxs-lookup"><span data-stu-id="6edda-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="6edda-211">プロキシは JSON 定義として格納されます。</span><span class="sxs-lookup"><span data-stu-id="6edda-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="6edda-212">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6edda-212">Here is an example:</span></span>

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

<span data-ttu-id="6edda-213">プロキシ`Domain Redirect`は、短いルートを取得し、それより長い関数リソースにマップします。</span><span class="sxs-lookup"><span data-stu-id="6edda-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="6edda-214">変換は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6edda-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="6edda-215">プロキシ`Root`は、ルート URL (`https://--shorturl--/`) に送信されたすべてのものを取得し、ドキュメントサイトにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="6edda-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="6edda-216">プロキシの使用例については、Azure [のビデオを参照してください。サーバーレス Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102)を使用して、アプリをクラウドに持ち込むことができます。</span><span class="sxs-lookup"><span data-stu-id="6edda-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="6edda-217">ローカル SQL Server で実行されている ASP.NET Core アプリケーションは、リアルタイムで Azure クラウドに移行されます。</span><span class="sxs-lookup"><span data-stu-id="6edda-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="6edda-218">プロキシは、従来の Web API プロジェクトをリファクターして関数を使用するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6edda-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="6edda-219">プロキシの詳細については、「 [Azure Functions プロキシの操作](https://docs.microsoft.com/azure/azure-functions/functions-proxies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6edda-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6edda-220">[前へ](azure-serverless-platform.md)
>[次へ](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="6edda-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
