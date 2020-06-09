---
title: Visual Studio での .NET Core Hello World アプリケーションの発行
description: 発行では、.NET Core アプリケーションを実行するために必要なファイルのセットを作成します。
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 745fb2af332afa278c78ec9baeea7230fe725c02
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241496"
---
# <a name="tutorial-publish-a-net-core-console-application-with-visual-studio"></a><span data-ttu-id="5e1e1-103">チュートリアル: Visual Studio での .NET Core コンソール アプリケーションの発行</span><span class="sxs-lookup"><span data-stu-id="5e1e1-103">Tutorial: Publish a .NET Core console application with Visual Studio</span></span>

<span data-ttu-id="5e1e1-104">このチュートリアルでは、他のユーザーが実行できるコンソール アプリを発行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="5e1e1-105">発行では、アプリケーションを実行するために必要なファイルのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="5e1e1-106">ファイルを配置するには、それをターゲット マシンにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5e1e1-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5e1e1-107">Prerequisites</span></span>

- <span data-ttu-id="5e1e1-108">このチュートリアルでは、[Visual Studio 2019 での .NET Core コンソール アプリケーションの作成](with-visual-studio.md)に関するページで作成した、コンソール アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-108">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="5e1e1-109">アプリの発行</span><span class="sxs-lookup"><span data-stu-id="5e1e1-109">Publish the app</span></span>

1. <span data-ttu-id="5e1e1-110">Visual Studio がアプリケーションのリリース バージョンをビルドしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="5e1e1-111">必要に応じて、ツール バーのビルド構成の設定を **[デバッグ]** から **[リリース]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![リリース ビルドが選択された Visual Studio のツールバー](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="5e1e1-113">**HelloWorld** プロジェクト (HelloWorld ソリューションではなく) を右クリックし、メニューから **[発行]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   ![Visual Studio の [発行] コンテキスト メニュー](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="5e1e1-115">**[発行]** ページの **[ターゲット]** タブで、 **[フォルダー]** 、 **[次へ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-115">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   ![Visual Studio で発行先を選択します](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="5e1e1-117">**[発行]** ページの **[場所]** タブで、 **[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-117">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   ![Visual Studio の [発行] ページの [場所] タブ](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. <span data-ttu-id="5e1e1-119">**[発行]** ウィンドウの **[発行]** タブで、 **[発行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-119">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   ![Visual Studio の [発行] ウィンドウ](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="5e1e1-121">ファイルを検査する</span><span class="sxs-lookup"><span data-stu-id="5e1e1-121">Inspect the files</span></span>

<span data-ttu-id="5e1e1-122">この発行プロセスでは、フレームワークに依存する配置が作成されます。つまり、.NET Core のランタイムがインストールされているコンピューターで、発行されたアプリケーションが実行される配置の種類です。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-122">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="5e1e1-123">ユーザーは、実行可能ファイルをダブルクリックするか、コマンドプロンプトから `dotnet HelloWorld.dll` コマンドを実行することで、発行されたアプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-123">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="5e1e1-124">次の手順で、発行プロセスによって作成されるファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-124">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="5e1e1-125">**ソリューション エクスプローラー**で、 **[すべてのファイルを表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-125">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="5e1e1-126">プロジェクト フォルダーで *bin/Release/netcoreapp3.1/publish* を展開します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-126">In the project folder, expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="発行されたファイルを表示しているソリューション エクスプローラー":::

   <span data-ttu-id="5e1e1-128">この図に示すように、発行された出力には次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-128">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="5e1e1-129">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="5e1e1-129">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="5e1e1-130">このファイルは、アプリケーションのランタイム依存関係ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-130">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="5e1e1-131">これは、アプリの実行に必要な .NET Core コンポーネントとライブラリ (アプリケーションが含まれる動的リンク ライブラリを含む) を定義します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-131">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="5e1e1-132">詳細については、「[ランタイム構成ファイル](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-132">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="5e1e1-133">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="5e1e1-133">*HelloWorld.dll*</span></span>

      <span data-ttu-id="5e1e1-134">これは、[フレームワークに依存する展開](../deploying/deploy-with-cli.md#framework-dependent-deployment)バージョンのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-134">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="5e1e1-135">このダイナミック リンク ライブラリを実行するには、コマンド プロンプトで`dotnet HelloWorld.dll` を入力します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-135">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="5e1e1-136">アプリ実行のこの方法は、.NET Core ランタイムがインストールされている任意のプラットフォームで動作します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-136">This method of running the app works on any platform that has the .NET Core runtime installed.</span></span>

   * <span data-ttu-id="5e1e1-137">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="5e1e1-137">*HelloWorld.exe*</span></span>

      <span data-ttu-id="5e1e1-138">これは、[フレームワークに依存する実行可能ファイル](../deploying/deploy-with-cli.md#framework-dependent-executable) バージョンのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-138">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="5e1e1-139">これを実行するには、コマンド プロンプトで `HelloWorld.exe` を入力します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-139">To run it, enter `HelloWorld.exe` at a command prompt.</span></span> <span data-ttu-id="5e1e1-140">ファイルはオペレーティング システム固有のものです。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-140">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="5e1e1-141">*HelloWorld.pdb* (配置は省略可能)</span><span class="sxs-lookup"><span data-stu-id="5e1e1-141">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="5e1e1-142">これは、デバッグ シンボル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-142">This is the debug symbols file.</span></span> <span data-ttu-id="5e1e1-143">このファイルはアプリケーションと一緒に配置する必要はありませんが、発行されるバージョンのアプリケーションをデバッグする必要がある場合に保存しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-143">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="5e1e1-144">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="5e1e1-144">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="5e1e1-145">これは、アプリケーションのランタイム構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-145">This is the application's run-time configuration file.</span></span> <span data-ttu-id="5e1e1-146">ビルドされたアプリケーションが実行時に基盤とする .NET Core のバージョンを識別します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-146">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="5e1e1-147">構成オプションを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-147">You can also add configuration options to it.</span></span> <span data-ttu-id="5e1e1-148">詳細については、「[.NET Core ランタイム構成設定](../run-time-config/index.md#runtimeconfigjson)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-148">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="5e1e1-149">発行済みアプリを実行する</span><span class="sxs-lookup"><span data-stu-id="5e1e1-149">Run the published app</span></span>

1. <span data-ttu-id="5e1e1-150">**ソリューション エクスプローラー**で、 *[publish]* フォルダーを右クリックし、 **[完全なパスのコピー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-150">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="5e1e1-151">コマンド プロンプトを開いて、*publish* フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-151">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="5e1e1-152">`cd` を入力し、完全なパスを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-152">Enter `cd` and then paste the full path.</span></span> <span data-ttu-id="5e1e1-153">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-153">For example:</span></span>

   ```
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="5e1e1-154">実行可能ファイルを使用してアプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-154">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="5e1e1-155">「`HelloWorld.exe`」と入力して、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-155">Enter `HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="5e1e1-156">プロンプトに応答して名前を入力し、任意のキーを押して終了します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-156">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="5e1e1-157">`dotnet` コマンドを使用して、アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-157">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="5e1e1-158">「`dotnet HelloWorld.dll`」と入力して、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-158">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="5e1e1-159">プロンプトに応答して名前を入力し、任意のキーを押して終了します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-159">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5e1e1-160">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="5e1e1-160">Additional resources</span></span>

- [<span data-ttu-id="5e1e1-161">.NET Core アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="5e1e1-161">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="5e1e1-162">次の手順</span><span class="sxs-lookup"><span data-stu-id="5e1e1-162">Next steps</span></span>

<span data-ttu-id="5e1e1-163">このチュートリアルでは、コンソール アプリを発行しました。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-163">In this tutorial, you published a console app.</span></span> <span data-ttu-id="5e1e1-164">次のチュートリアルでは、クラス ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e1e1-164">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5e1e1-165">Visual Studio で .NET Standard ライブラリを構築する</span><span class="sxs-lookup"><span data-stu-id="5e1e1-165">Create a .NET Standard library in Visual Studio</span></span>](library-with-visual-studio.md)
