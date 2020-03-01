---
title: Visual Studio での .NET Core Hello World アプリケーションの発行
description: 発行では、.NET Core アプリケーションを実行するために必要なファイルのセットを作成します。
author: BillWagner
ms.author: wiwagn
ms.date: 12/10/2019
ms.custom: vs-dotnet
ms.openlocfilehash: bdd6e28713bdece2bd144e6763bd84d719e91449
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156635"
---
# <a name="publish-your-net-core-hello-world-application-with-visual-studio"></a><span data-ttu-id="a4e2d-103">Visual Studio での .NET Core Hello World アプリケーションの発行</span><span class="sxs-lookup"><span data-stu-id="a4e2d-103">Publish your .NET Core Hello World application with Visual Studio</span></span>

<span data-ttu-id="a4e2d-104">「[Visual Studio での .NET Core を使用した Hello World アプリケーションの作成](with-visual-studio.md)」では、Hello World コンソール アプリケーションを作成しました。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-104">In [Create a Hello World application with .NET Core in Visual Studio](with-visual-studio.md), you built a Hello World console application.</span></span> <span data-ttu-id="a4e2d-105">「[Visual Studio での Hello World アプリケーションのデバッグ](debugging-with-visual-studio.md)」では、Visual Studio デバッガーを使ってそれをテストしました。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-105">In [Debug your Hello World application with Visual Studio](debugging-with-visual-studio.md), you tested it using the Visual Studio debugger.</span></span> <span data-ttu-id="a4e2d-106">正しく動作することが確認できたので、他のユーザーが使用できるように発行することができます。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-106">Now that you're sure that it works as expected, you can publish it so that other users can run it.</span></span> <span data-ttu-id="a4e2d-107">発行では、アプリケーションを実行するために必要なファイルのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-107">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="a4e2d-108">ファイルを配置するには、それをターゲット マシンにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-108">To deploy the files, copy them to the target machine.</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="a4e2d-109">アプリの発行</span><span class="sxs-lookup"><span data-stu-id="a4e2d-109">Publish the app</span></span>

1. <span data-ttu-id="a4e2d-110">Visual Studio がアプリケーションのリリース バージョンをビルドしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="a4e2d-111">必要に応じて、ツール バーのビルド構成の設定を **[デバッグ]** から **[リリース]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![リリース ビルドが選択された Visual Studio のツールバー](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="a4e2d-113">**HelloWorld** プロジェクト (HelloWorld ソリューションではなく) を右クリックし、メニューから **[発行]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span> <span data-ttu-id="a4e2d-114">(メイン メニューの **[ビルド]** から **[HelloWorld を発行]** を選択することもできます。)</span><span class="sxs-lookup"><span data-stu-id="a4e2d-114">(You can also select **Publish HelloWorld** from the main **Build** menu.)</span></span>

   ![Visual Studio の [発行] コンテキスト メニュー](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="a4e2d-116">**[発行先を選択]** ページで、 **[フォルダー]** を選択し、次に **[プロファイルの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-116">On the **Pick a publish target** page, select **Folder**, and then select **Create Profile**.</span></span>

   ![Visual Studio で発行先を選択します](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="a4e2d-118">**[発行]** ページで、 **[発行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-118">On the **Publish** page, select **Publish**.</span></span>

   ![Visual Studio の [発行] ウィンドウ](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="a4e2d-120">ファイルを検査する</span><span class="sxs-lookup"><span data-stu-id="a4e2d-120">Inspect the files</span></span>

<span data-ttu-id="a4e2d-121">発行プロセスでは、フレームワークに依存する配置が作成されます。これは、.NET Core がシステムにインストールされていれば、.NET Core によってサポートされる任意のプラットフォームで、発行されたアプリケーションが実行される配置の種類です。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-121">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on any platform supported by .NET Core with .NET Core installed on the system.</span></span> <span data-ttu-id="a4e2d-122">ユーザーは、実行可能ファイルをダブルクリックするか、コマンドプロンプトから `dotnet HelloWorld.dll` コマンドを実行することで、発行されたアプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-122">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="a4e2d-123">次の手順で、発行プロセスによって作成されるファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-123">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="a4e2d-124">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-124">Open a command prompt.</span></span>

   <span data-ttu-id="a4e2d-125">コマンド プロンプトを開く方法の 1 つとして、Windows タスク バーの検索ボックスに**コマンド プロンプト** (または短縮形の**cmd**) を入力する方法があります。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-125">One way to open a command prompt is to enter **Command Prompt** (or **cmd** for short) in the search box on the Windows taskbar.</span></span> <span data-ttu-id="a4e2d-126">**[コマンド プロンプト]** デスクトップ アプリを選択するか、検索結果で既に選択されている場合は、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-126">Select the **Command Prompt** desktop app, or press **Enter** if it's already selected in the search results.</span></span>

1. <span data-ttu-id="a4e2d-127">アプリケーションのプロジェクト ディレクトリの *bin\Release\netcoreapp3.1\publish* サブディレクトリで、発行されたアプリケーションに移動します。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-127">Navigate to the published application in the *bin\Release\netcoreapp3.1\publish* subdirectory of the application's project directory.</span></span>

   ![発行されたファイルが表示されているコンソール ウィンドウ](media/publishing-with-visual-studio/published-files-output.png)

   <span data-ttu-id="a4e2d-129">この図に示すように、発行された出力には次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-129">As the image shows, the published output includes the following files:</span></span>

      * <span data-ttu-id="a4e2d-130">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="a4e2d-130">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="a4e2d-131">このファイルは、アプリケーションのランタイム依存関係ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-131">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="a4e2d-132">これは、アプリの実行に必要な .NET Core コンポーネントとライブラリ (アプリケーションが含まれる動的リンク ライブラリを含む) を定義します。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-132">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="a4e2d-133">詳細については、「[ランタイム構成ファイル](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-133">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

      * <span data-ttu-id="a4e2d-134">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="a4e2d-134">*HelloWorld.dll*</span></span>

         <span data-ttu-id="a4e2d-135">これは、[フレームワークに依存する展開](../deploying/deploy-with-cli.md#framework-dependent-deployment)バージョンのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-135">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="a4e2d-136">このダイナミック リンク ライブラリを実行するには、コマンド プロンプトで`dotnet HelloWorld.dll` を入力します。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-136">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span>

      * <span data-ttu-id="a4e2d-137">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="a4e2d-137">*HelloWorld.exe*</span></span>

         <span data-ttu-id="a4e2d-138">これは、[フレームワークに依存する実行可能ファイル](../deploying/deploy-with-cli.md#framework-dependent-executable) バージョンのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-138">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="a4e2d-139">これを実行するには、コマンド プロンプトで `HelloWorld.exe` を入力します。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-139">To run it, enter `HelloWorld.exe` at a command prompt.</span></span>

      * <span data-ttu-id="a4e2d-140">*HelloWorld.pdb* (配置は省略可能)</span><span class="sxs-lookup"><span data-stu-id="a4e2d-140">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="a4e2d-141">これは、デバッグ シンボル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-141">This is the debug symbols file.</span></span> <span data-ttu-id="a4e2d-142">このファイルはアプリケーションと一緒に配置する必要はありませんが、発行されるバージョンのアプリケーションをデバッグする必要がある場合に保存しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-142">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="a4e2d-143">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="a4e2d-143">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="a4e2d-144">これは、アプリケーションのランタイム構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-144">This is the application's run-time configuration file.</span></span> <span data-ttu-id="a4e2d-145">ビルドされたアプリケーションが実行時に基盤とする .NET Core のバージョンを識別します。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-145">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="a4e2d-146">構成オプションを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-146">You can also add configuration options to it.</span></span> <span data-ttu-id="a4e2d-147">詳細については、「[.NET Core ランタイム構成設定](../run-time-config/index.md#runtimeconfigjson)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4e2d-147">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a4e2d-148">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="a4e2d-148">Additional resources</span></span>

- [<span data-ttu-id="a4e2d-149">.NET Core アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="a4e2d-149">.NET Core application deployment</span></span>](../deploying/index.md)
