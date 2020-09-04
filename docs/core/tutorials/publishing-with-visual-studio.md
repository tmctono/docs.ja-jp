---
title: Visual Studio を使用して .NET Core コンソール アプリケーションを発行する
description: 発行では、.NET Core アプリケーションを実行するために必要なファイルのセットを作成します。
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: e0033d52ab54259ce5e4ccf2a25bf4e3d4f244de
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867556"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio"></a><span data-ttu-id="35de0-103">チュートリアル: Visual Studio を使用して .NET Core コンソール アプリケーションを発行する</span><span class="sxs-lookup"><span data-stu-id="35de0-103">Tutorial: Publish a .NET Core console application using Visual Studio</span></span>

<span data-ttu-id="35de0-104">このチュートリアルでは、他のユーザーが実行できるコンソール アプリを発行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="35de0-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="35de0-105">発行では、アプリケーションを実行するために必要なファイルのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="35de0-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="35de0-106">ファイルを配置するには、それをターゲット マシンにコピーします。</span><span class="sxs-lookup"><span data-stu-id="35de0-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="35de0-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="35de0-107">Prerequisites</span></span>

- <span data-ttu-id="35de0-108">このチュートリアルでは、「[Visual Studio を使用して .NET Core コンソール アプリケーションを作成する](with-visual-studio.md)」で作成したコンソール アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="35de0-108">This tutorial works with the console app that you create in [Create a .NET Core console application using Visual Studio](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="35de0-109">アプリの発行</span><span class="sxs-lookup"><span data-stu-id="35de0-109">Publish the app</span></span>

1. <span data-ttu-id="35de0-110">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="35de0-110">Start Visual Studio.</span></span>

1. <span data-ttu-id="35de0-111">「[Visual Studio を使用して .NET Core コンソール アプリケーションを作成する](with-visual-studio.md)」で作成した *HelloWorld* プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="35de0-111">Open the *HelloWorld* project that you created in [Create a .NET Core console application using Visual Studio](with-visual-studio.md).</span></span>

1. <span data-ttu-id="35de0-112">Visual Studio でリリース ビルド構成が使用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="35de0-112">Make sure that Visual Studio is using the Release build configuration.</span></span> <span data-ttu-id="35de0-113">必要に応じて、ツール バーのビルド構成の設定を **[デバッグ]** から **[リリース]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="35de0-113">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![リリース ビルドが選択された Visual Studio のツールバー](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="35de0-115">**HelloWorld** プロジェクト (HelloWorld ソリューションではなく) を右クリックし、メニューから **[発行]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="35de0-115">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   ![Visual Studio の [発行] コンテキスト メニュー](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="35de0-117">**[発行]** ページの **[ターゲット]** タブで、 **[フォルダー]** 、 **[次へ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="35de0-117">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   ![Visual Studio で発行先を選択します](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="35de0-119">**[発行]** ページの **[場所]** タブで、 **[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35de0-119">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   ![Visual Studio の [発行] ページの [場所] タブ](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. <span data-ttu-id="35de0-121">**[発行]** ウィンドウの **[発行]** タブで、 **[発行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35de0-121">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   ![Visual Studio の [発行] ウィンドウ](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="35de0-123">ファイルを検査する</span><span class="sxs-lookup"><span data-stu-id="35de0-123">Inspect the files</span></span>

<span data-ttu-id="35de0-124">この発行プロセスでは、フレームワークに依存する配置が既定で作成されます。これは、.NET Core ランタイムがインストールされているコンピューター上で発行されたアプリケーションが実行される配置の種類です。</span><span class="sxs-lookup"><span data-stu-id="35de0-124">By default, the publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="35de0-125">ユーザーは、実行可能ファイルをダブルクリックするか、コマンドプロンプトから `dotnet HelloWorld.dll` コマンドを実行することで、発行されたアプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="35de0-125">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="35de0-126">次の手順で、発行プロセスによって作成されるファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="35de0-126">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="35de0-127">**ソリューション エクスプローラー**で、 **[すべてのファイルを表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35de0-127">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="35de0-128">プロジェクト フォルダーで *bin/Release/netcoreapp3.1/publish* を展開します。</span><span class="sxs-lookup"><span data-stu-id="35de0-128">In the project folder, expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="発行されたファイルを表示しているソリューション エクスプローラー":::

   <span data-ttu-id="35de0-130">この図に示すように、発行された出力には次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="35de0-130">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="35de0-131">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="35de0-131">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="35de0-132">このファイルは、アプリケーションのランタイム依存関係ファイルです。</span><span class="sxs-lookup"><span data-stu-id="35de0-132">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="35de0-133">これは、アプリの実行に必要な .NET Core コンポーネントとライブラリ (アプリケーションが含まれる動的リンク ライブラリを含む) を定義します。</span><span class="sxs-lookup"><span data-stu-id="35de0-133">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="35de0-134">詳細については、「[ランタイム構成ファイル](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35de0-134">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="35de0-135">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="35de0-135">*HelloWorld.dll*</span></span>

      <span data-ttu-id="35de0-136">これは、[フレームワークに依存する展開](../deploying/deploy-with-cli.md#framework-dependent-deployment)バージョンのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="35de0-136">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="35de0-137">このダイナミック リンク ライブラリを実行するには、コマンド プロンプトで`dotnet HelloWorld.dll` を入力します。</span><span class="sxs-lookup"><span data-stu-id="35de0-137">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="35de0-138">アプリ実行のこの方法は、.NET Core ランタイムがインストールされている任意のプラットフォームで動作します。</span><span class="sxs-lookup"><span data-stu-id="35de0-138">This method of running the app works on any platform that has the .NET Core runtime installed.</span></span>

   * <span data-ttu-id="35de0-139">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="35de0-139">*HelloWorld.exe*</span></span>

      <span data-ttu-id="35de0-140">これは、[フレームワークに依存する実行可能ファイル](../deploying/deploy-with-cli.md#framework-dependent-executable) バージョンのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="35de0-140">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="35de0-141">これを実行するには、コマンド プロンプトで `HelloWorld.exe` を入力します。</span><span class="sxs-lookup"><span data-stu-id="35de0-141">To run it, enter `HelloWorld.exe` at a command prompt.</span></span> <span data-ttu-id="35de0-142">ファイルはオペレーティング システム固有のものです。</span><span class="sxs-lookup"><span data-stu-id="35de0-142">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="35de0-143">*HelloWorld.pdb* (配置は省略可能)</span><span class="sxs-lookup"><span data-stu-id="35de0-143">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="35de0-144">これは、デバッグ シンボル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="35de0-144">This is the debug symbols file.</span></span> <span data-ttu-id="35de0-145">このファイルはアプリケーションと一緒に配置する必要はありませんが、発行されるバージョンのアプリケーションをデバッグする必要がある場合に保存しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="35de0-145">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="35de0-146">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="35de0-146">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="35de0-147">これは、アプリケーションのランタイム構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="35de0-147">This is the application's run-time configuration file.</span></span> <span data-ttu-id="35de0-148">ビルドされたアプリケーションが実行時に基盤とする .NET Core のバージョンを識別します。</span><span class="sxs-lookup"><span data-stu-id="35de0-148">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="35de0-149">構成オプションを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="35de0-149">You can also add configuration options to it.</span></span> <span data-ttu-id="35de0-150">詳細については、「[.NET Core ランタイム構成設定](../run-time-config/index.md#runtimeconfigjson)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35de0-150">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="35de0-151">発行済みアプリを実行する</span><span class="sxs-lookup"><span data-stu-id="35de0-151">Run the published app</span></span>

1. <span data-ttu-id="35de0-152">**ソリューション エクスプローラー**で、 *[publish]* フォルダーを右クリックし、 **[完全なパスのコピー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35de0-152">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="35de0-153">コマンド プロンプトを開いて、*publish* フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="35de0-153">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="35de0-154">これを行うには、「`cd`」と入力して、完全なパスを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="35de0-154">To do that, enter `cd` and then paste the full path.</span></span> <span data-ttu-id="35de0-155">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="35de0-155">For example:</span></span>

   ```console
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="35de0-156">実行可能ファイルを使用してアプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="35de0-156">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="35de0-157">「`HelloWorld.exe`」と入力して、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="35de0-157">Enter `HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="35de0-158">プロンプトに応答して名前を入力し、任意のキーを押して終了します。</span><span class="sxs-lookup"><span data-stu-id="35de0-158">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="35de0-159">`dotnet` コマンドを使用して、アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="35de0-159">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="35de0-160">「`dotnet HelloWorld.dll`」と入力して、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="35de0-160">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="35de0-161">プロンプトに応答して名前を入力し、任意のキーを押して終了します。</span><span class="sxs-lookup"><span data-stu-id="35de0-161">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="35de0-162">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="35de0-162">Additional resources</span></span>

- [<span data-ttu-id="35de0-163">.NET Core アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="35de0-163">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="35de0-164">次の手順</span><span class="sxs-lookup"><span data-stu-id="35de0-164">Next steps</span></span>

<span data-ttu-id="35de0-165">このチュートリアルでは、コンソール アプリを発行しました。</span><span class="sxs-lookup"><span data-stu-id="35de0-165">In this tutorial, you published a console app.</span></span> <span data-ttu-id="35de0-166">次のチュートリアルでは、クラス ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="35de0-166">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="35de0-167">Visual Studio を使用して .NET Standard ライブラリを作成する</span><span class="sxs-lookup"><span data-stu-id="35de0-167">Create a .NET Standard library using Visual Studio</span></span>](library-with-visual-studio.md)
