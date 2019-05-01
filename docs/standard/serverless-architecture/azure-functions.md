---
title: Azure Functions でサーバーレス アプリ
description: Azure functions は、複数の言語 (c#、JavaScript、Java) サーバーレス機能を提供し、インスタント イベント ドリブンを提供するプラットフォームは、コードを拡張します。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4febcc01eebf3efce3fc1eb42e19c2ec6c0baa52
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "63807896"
---
# <a name="azure-functions"></a><span data-ttu-id="e240d-103">Azure Functions </span><span class="sxs-lookup"><span data-stu-id="e240d-103">Azure Functions</span></span>

<span data-ttu-id="e240d-104">Azure 関数は、サーバーレス コンピューティング エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e240d-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="e240d-105">によって、関数が呼び出される、*トリガー* (など、HTTP エンドポイントまたはタイマーへのアクセス) コードまたはビジネス ロジックのブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="e240d-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="e240d-106">関数のサポートが特殊化も*バインド*ストレージやキューなどのリソースに接続します。</span><span class="sxs-lookup"><span data-stu-id="e240d-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Azure functions のロゴ](./media/azure-functions-logo.png)

<span data-ttu-id="e240d-108">Azure Functions フレームワークの 2 つのバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="e240d-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="e240d-109">従来のバージョンは、完全な .NET Framework をサポートしています。 新しいランタイムは、クロス プラットフォーム対応 .NET Core アプリケーションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e240d-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="e240d-110">追加の言語だけでなくC#JavaScript などF#、Java がサポートされているとします。</span><span class="sxs-lookup"><span data-stu-id="e240d-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="e240d-111">ポータルで作成した関数では、豊富なスクリプト構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="e240d-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="e240d-112">完全なプラットフォームのサポートと機能を持つスタンドアロン プロジェクトとして作成した関数をデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="e240d-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="e240d-113">詳細については、次を参照してください。 [Azure Functions のドキュメント](https://docs.microsoft.com/azure/azure-functions)します。</span><span class="sxs-lookup"><span data-stu-id="e240d-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="e240d-114">関数の v1 と v2 の比較</span><span class="sxs-lookup"><span data-stu-id="e240d-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="e240d-115">Azure Functions ランタイムの 2 つのバージョンがあります。1.x と 2.x の場合は。</span><span class="sxs-lookup"><span data-stu-id="e240d-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="e240d-116">バージョン 1.x が一般公開 (GA) します。</span><span class="sxs-lookup"><span data-stu-id="e240d-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="e240d-117">ポータルまたは Windows マシンからの .NET 開発をサポートし、.NET Framework を使用します。</span><span class="sxs-lookup"><span data-stu-id="e240d-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="e240d-118">1.x がサポートしているC#、JavaScript、およびF#、Python、PHP、TypeScript、Batch、Bash、および PowerShell の実験的なサポートをします。</span><span class="sxs-lookup"><span data-stu-id="e240d-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="e240d-119">[バージョン 2.x は一般的に使用できるようになりましたことも、](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/)します。</span><span class="sxs-lookup"><span data-stu-id="e240d-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="e240d-120">.NET Core を利用し、Windows、macOS、および Linux マシンでのクロス プラットフォーム開発をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e240d-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="e240d-121">2.x の Java のファースト クラスのサポートを追加しますがまだ直接サポートしていません試験段階の言語のいずれか。</span><span class="sxs-lookup"><span data-stu-id="e240d-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="e240d-122">バージョン 2.x のバインディングの独立したバージョン管理、プラットフォームにサード パーティ製の拡張機能を有効にする新しいバインディング拡張モデルを使用してより実行環境を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="e240d-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="e240d-123">**1.x の既知の問題がある[バインディング リダイレクト サポート](https://github.com/Azure/azure-functions-host/issues/992)します。**</span><span class="sxs-lookup"><span data-stu-id="e240d-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="e240d-124">この問題は、.NET 開発に固有です。</span><span class="sxs-lookup"><span data-stu-id="e240d-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="e240d-125">ランタイムに含まれるライブラリから別のバージョンのライブラリへの依存関係を使用したプロジェクトが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="e240d-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="e240d-126">Functions チームが問題の具体的な進行状況をコミットします。</span><span class="sxs-lookup"><span data-stu-id="e240d-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="e240d-127">一般に入る前に、チームは 2.x でバインド リダイレクトを対処します。</span><span class="sxs-lookup"><span data-stu-id="e240d-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="e240d-128">チームの公式ステートメントの推奨される修正プログラムや回避策は、ここで入手できます。[Azure Functions でのアセンブリ解決](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions)します。</span><span class="sxs-lookup"><span data-stu-id="e240d-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="e240d-129">詳細については、次を参照してください。 [1.x と 2.x の比較](https://docs.microsoft.com/azure/azure-functions/functions-versions)します。</span><span class="sxs-lookup"><span data-stu-id="e240d-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="e240d-130">プログラミング言語のサポート</span><span class="sxs-lookup"><span data-stu-id="e240d-130">Programming language support</span></span>

<span data-ttu-id="e240d-131">次の言語がサポートされているか、一般公開 (GA) をプレビューまたは試験用。</span><span class="sxs-lookup"><span data-stu-id="e240d-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="e240d-132">言語</span><span class="sxs-lookup"><span data-stu-id="e240d-132">Language</span></span>      |<span data-ttu-id="e240d-133">1.x</span><span class="sxs-lookup"><span data-stu-id="e240d-133">1.x</span></span>         |<span data-ttu-id="e240d-134">2.x</span><span class="sxs-lookup"><span data-stu-id="e240d-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="e240d-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="e240d-135">**C#**</span></span>        |<span data-ttu-id="e240d-136">GA</span><span class="sxs-lookup"><span data-stu-id="e240d-136">GA</span></span>          |<span data-ttu-id="e240d-137">[プレビュー]</span><span class="sxs-lookup"><span data-stu-id="e240d-137">Preview</span></span>  |
|<span data-ttu-id="e240d-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="e240d-138">**JavaScript**</span></span>|<span data-ttu-id="e240d-139">GA</span><span class="sxs-lookup"><span data-stu-id="e240d-139">GA</span></span>          |<span data-ttu-id="e240d-140">[プレビュー]</span><span class="sxs-lookup"><span data-stu-id="e240d-140">Preview</span></span>  |
|<span data-ttu-id="e240d-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="e240d-141">**F#**</span></span>        |<span data-ttu-id="e240d-142">GA</span><span class="sxs-lookup"><span data-stu-id="e240d-142">GA</span></span>          |         |
|<span data-ttu-id="e240d-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="e240d-143">**Java**</span></span>      |            |<span data-ttu-id="e240d-144">[プレビュー]</span><span class="sxs-lookup"><span data-stu-id="e240d-144">Preview</span></span>  |
|<span data-ttu-id="e240d-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="e240d-145">**Python**</span></span>    |<span data-ttu-id="e240d-146">実験用</span><span class="sxs-lookup"><span data-stu-id="e240d-146">Experimental</span></span>|         |
|<span data-ttu-id="e240d-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="e240d-147">**PHP**</span></span>       |<span data-ttu-id="e240d-148">実験用</span><span class="sxs-lookup"><span data-stu-id="e240d-148">Experimental</span></span>|         |
|<span data-ttu-id="e240d-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="e240d-149">**TypeScript**</span></span>|<span data-ttu-id="e240d-150">実験用</span><span class="sxs-lookup"><span data-stu-id="e240d-150">Experimental</span></span>|         |
|<span data-ttu-id="e240d-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="e240d-151">**Batch**</span></span>     |<span data-ttu-id="e240d-152">実験用</span><span class="sxs-lookup"><span data-stu-id="e240d-152">Experimental</span></span>|         |
|<span data-ttu-id="e240d-153">**Bash**</span><span class="sxs-lookup"><span data-stu-id="e240d-153">**Bash**</span></span>      |<span data-ttu-id="e240d-154">実験用</span><span class="sxs-lookup"><span data-stu-id="e240d-154">Experimental</span></span>|         |
|<span data-ttu-id="e240d-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e240d-155">**PowerShell**</span></span>|<span data-ttu-id="e240d-156">実験用</span><span class="sxs-lookup"><span data-stu-id="e240d-156">Experimental</span></span>|         |

<span data-ttu-id="e240d-157">詳細については、次を参照してください。[サポートされる言語](https://docs.microsoft.com/azure/azure-functions/supported-languages)します。</span><span class="sxs-lookup"><span data-stu-id="e240d-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="e240d-158">App service プラン</span><span class="sxs-lookup"><span data-stu-id="e240d-158">App service plans</span></span>

<span data-ttu-id="e240d-159">関数が支え、 *app service プラン*します。</span><span class="sxs-lookup"><span data-stu-id="e240d-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="e240d-160">プランは、関数アプリで使用されるリソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="e240d-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="e240d-161">リージョンにプランを割り当てるを使用して、価格レベルを選択する仮想マシンの数とサイズを決定できます。</span><span class="sxs-lookup"><span data-stu-id="e240d-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="e240d-162">True のサーバーレス アプローチでは、関数アプリを使うことが、**消費**計画します。</span><span class="sxs-lookup"><span data-stu-id="e240d-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="e240d-163">従量課金プランでは、バックエンドの負荷に基づいて自動的に拡大縮小されます。</span><span class="sxs-lookup"><span data-stu-id="e240d-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="e240d-164">詳細については、次を参照してください。 [App service プラン](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)します。</span><span class="sxs-lookup"><span data-stu-id="e240d-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="e240d-165">最初の関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="e240d-165">Create your first function</span></span>

<span data-ttu-id="e240d-166">関数アプリを作成する 3 つの一般的な方法はあります。</span><span class="sxs-lookup"><span data-stu-id="e240d-166">There are three common ways you can create function apps.</span></span>

* <span data-ttu-id="e240d-167">ポータルでのスクリプト機能します。</span><span class="sxs-lookup"><span data-stu-id="e240d-167">Script functions in the portal.</span></span>
* <span data-ttu-id="e240d-168">Azure コマンド ライン インターフェイス (CLI) を使用しているために必要なリソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="e240d-168">Create the necessary resources using the Azure Command Line Interface (CLI).</span></span>
* <span data-ttu-id="e240d-169">お気に入りの IDE を使用してローカルで関数をビルドし、それらを Azure に発行します。</span><span class="sxs-lookup"><span data-stu-id="e240d-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="e240d-170">ポータルでスクリプト化された関数を作成する方法の詳細については、次を参照してください。 [、Azure portal で初めての関数を作成する](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)します。</span><span class="sxs-lookup"><span data-stu-id="e240d-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="e240d-171">Azure CLI から作成するを参照してください。 [Azure CLI を使用した初めての関数を作成する](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)します。</span><span class="sxs-lookup"><span data-stu-id="e240d-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="e240d-172">Visual Studio から関数を作成するを参照してください。 [Visual Studio を使用した初めての関数を作成する](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="e240d-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="e240d-173">トリガーとバインドを理解します。</span><span class="sxs-lookup"><span data-stu-id="e240d-173">Understand triggers and bindings</span></span>

<span data-ttu-id="e240d-174">関数を呼び出す、*トリガー* 1 つだけ持つことができます。</span><span class="sxs-lookup"><span data-stu-id="e240d-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="e240d-175">関数を呼び出すだけでなく特定のトリガーはバインドとしても機能します。</span><span class="sxs-lookup"><span data-stu-id="e240d-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="e240d-176">複数のバインドだけでなく、トリガーを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="e240d-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="e240d-177">*バインド*宣言型データ、コードを接続する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e240d-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="e240d-178">(入力) に渡すことができる、またはデータ (出力) を受信します。</span><span class="sxs-lookup"><span data-stu-id="e240d-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="e240d-179">トリガーとバインドする関数も使用する簡単にできます。</span><span class="sxs-lookup"><span data-stu-id="e240d-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="e240d-180">バインドは、手動で接続を作成するデータベースまたはファイル システムのオーバーヘッドを削除します。</span><span class="sxs-lookup"><span data-stu-id="e240d-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="e240d-181">特殊なに含まれているすべてのバインドのために必要な情報が*functions.json*スクリプトのファイルまたはコード内の属性で宣言されています。</span><span class="sxs-lookup"><span data-stu-id="e240d-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="e240d-182">いくつかの一般的なトリガーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e240d-182">Some common triggers include:</span></span>

* <span data-ttu-id="e240d-183">Blob Storage: は、ファイルまたはフォルダーをアップロードまたはストレージに変更されたときに、関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e240d-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
* <span data-ttu-id="e240d-184">HTTP: は、REST API のような関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e240d-184">HTTP: invoke your function like a REST API.</span></span>
* <span data-ttu-id="e240d-185">: キューは、キュー内の項目が存在する場合に、関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e240d-185">Queue: invoke your function when items exist in a queue.</span></span>
* <span data-ttu-id="e240d-186">タイマー: は、一定のリズムで関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e240d-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="e240d-187">バインドの例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e240d-187">Examples of bindings include:</span></span>

* <span data-ttu-id="e240d-188">Cosmos Db: は、読み込みまたはファイルを保存するデータベースに簡単に接続します。</span><span class="sxs-lookup"><span data-stu-id="e240d-188">CosmosDB: easily connect to the database to load or save files.</span></span>
* <span data-ttu-id="e240d-189">テーブル ストレージ: function app からキー/値ストレージを使用します。</span><span class="sxs-lookup"><span data-stu-id="e240d-189">Table Storage: work with key/value storage from your function app.</span></span>
* <span data-ttu-id="e240d-190">Queue Storage: は簡単に、キューから項目を取得または、新しいアイテムをキューに配置します。</span><span class="sxs-lookup"><span data-stu-id="e240d-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="e240d-191">次の例では、 *functions.json*ファイルは、トリガーとバインドを定義します。</span><span class="sxs-lookup"><span data-stu-id="e240d-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

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

<span data-ttu-id="e240d-192">内の blob ストレージへの変更により、この例では、関数がトリガーされる、`images`コンテナー。</span><span class="sxs-lookup"><span data-stu-id="e240d-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="e240d-193">ファイルの情報は、トリガーは、バインディングとしても機能するために渡されます。</span><span class="sxs-lookup"><span data-stu-id="e240d-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="e240d-194">という名前のキューに情報を配置する別のバインドが存在する`images`します。</span><span class="sxs-lookup"><span data-stu-id="e240d-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="e240d-195">関数の c# スクリプトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e240d-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="e240d-196">例は、ファイルの名前を受け取る単純な関数が変更されたまたは blob storage にアップロードし、後で処理するためのキューに配置されます。</span><span class="sxs-lookup"><span data-stu-id="e240d-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="e240d-197">トリガーとバインドの一覧については、次を参照してください。 [Azure Functions のトリガーとバインドの概念](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)します。</span><span class="sxs-lookup"><span data-stu-id="e240d-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="e240d-198">プロキシ</span><span class="sxs-lookup"><span data-stu-id="e240d-198">Proxies</span></span>

<span data-ttu-id="e240d-199">プロキシは、アプリケーションのリダイレクト機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="e240d-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="e240d-200">プロキシは、エンドポイントを公開し、そのエンドポイントを別のリソースにマップします。</span><span class="sxs-lookup"><span data-stu-id="e240d-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="e240d-201">プロキシは、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="e240d-201">With proxies, you can:</span></span>

* <span data-ttu-id="e240d-202">別のエンドポイントに受信要求を再ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="e240d-202">Reroute an incoming request to another endpoint.</span></span>
* <span data-ttu-id="e240d-203">に沿って渡す前に、着信要求を変更します。</span><span class="sxs-lookup"><span data-stu-id="e240d-203">Modify the incoming request before it's passed along.</span></span>
* <span data-ttu-id="e240d-204">変更するか、応答を提供します。</span><span class="sxs-lookup"><span data-stu-id="e240d-204">Modify or provide a response.</span></span>

<span data-ttu-id="e240d-205">プロキシがなどのシナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="e240d-205">Proxies are used for scenarios such as:</span></span>

* <span data-ttu-id="e240d-206">単純化するか、短縮するには、URL を変更します。</span><span class="sxs-lookup"><span data-stu-id="e240d-206">Simplifying, shortening, or changing the URL.</span></span>
* <span data-ttu-id="e240d-207">複数のバックエンド サービスへの一貫性のある API プレフィックスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e240d-207">Providing a consistent API prefix to multiple back-end services.</span></span>
* <span data-ttu-id="e240d-208">開発中のエンドポイントへの応答のモックを作成します。</span><span class="sxs-lookup"><span data-stu-id="e240d-208">Mocking a response to an endpoint being developed.</span></span>
* <span data-ttu-id="e240d-209">既知のエンドポイントへの静的な応答を提供します。</span><span class="sxs-lookup"><span data-stu-id="e240d-209">Providing a static response to a well-known endpoint.</span></span>
* <span data-ttu-id="e240d-210">API エンドポイントの一致の維持、バック エンドが移動または移行中にします。</span><span class="sxs-lookup"><span data-stu-id="e240d-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="e240d-211">プロキシは、JSON 定義として保存されます。</span><span class="sxs-lookup"><span data-stu-id="e240d-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="e240d-212">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e240d-212">Here is an example:</span></span>

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

<span data-ttu-id="e240d-213">`Domain Redirect`プロキシが簡略化されたルートに受け取り、長い関数のリソースにマップします。</span><span class="sxs-lookup"><span data-stu-id="e240d-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="e240d-214">変換は、ようになります。</span><span class="sxs-lookup"><span data-stu-id="e240d-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="e240d-215">`Root`プロキシはルート URL に送信されたもの (`https://--shorturl--/`) し、ドキュメント サイトにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="e240d-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="e240d-216">ビデオのプロキシを使用する例が示すように[Azure:サーバーレス Azure Functions を使用してクラウドにアプリをもたらす](https://channel9.msdn.com/events/Connect/2017/E102)します。</span><span class="sxs-lookup"><span data-stu-id="e240d-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="e240d-217">リアルタイムでローカルの SQL Server で実行されている ASP.NET Core アプリケーションは、Azure クラウドに移行されます。</span><span class="sxs-lookup"><span data-stu-id="e240d-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="e240d-218">プロキシは、関数を使用する従来の Web API プロジェクトのリファクタリングのために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e240d-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="e240d-219">プロキシの詳細については、次を参照してください。 [Azure Functions proxies 作業](https://docs.microsoft.com/azure/azure-functions/functions-proxies)します。</span><span class="sxs-lookup"><span data-stu-id="e240d-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e240d-220">[前へ](azure-serverless-platform.md)
>[次へ](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="e240d-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
