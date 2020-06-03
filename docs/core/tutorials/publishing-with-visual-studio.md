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
ms.openlocfilehash: e4ef8c12f3e52faa7cf09058a98abae65b0dcfce
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005106"
---
# <a name="tutorial-publish-a-net-core-console-application-with-visual-studio"></a><span data-ttu-id="08ef2-103">チュートリアル: Visual Studio での .NET Core コンソール アプリケーションの発行</span><span class="sxs-lookup"><span data-stu-id="08ef2-103">Tutorial: Publish a .NET Core console application with Visual Studio</span></span>

<span data-ttu-id="08ef2-104">このチュートリアルでは、他のユーザーが実行できるコンソール アプリを発行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="08ef2-105">発行では、アプリケーションを実行するために必要なファイルのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="08ef2-106">ファイルを配置するには、それをターゲット マシンにコピーします。</span><span class="sxs-lookup"><span data-stu-id="08ef2-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="08ef2-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="08ef2-107">Prerequisites</span></span>

- <span data-ttu-id="08ef2-108">このチュートリアルでは、[Visual Studio 2019 での .NET Core コンソール アプリケーションの作成](with-visual-studio.md)に関するページで作成した、コンソール アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-108">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="08ef2-109">アプリの発行</span><span class="sxs-lookup"><span data-stu-id="08ef2-109">Publish the app</span></span>

1. <span data-ttu-id="08ef2-110">Visual Studio がアプリケーションのリリース バージョンをビルドしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="08ef2-111">必要に応じて、ツール バーのビルド構成の設定を **[デバッグ]** から **[リリース]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![リリース ビルドが選択された Visual Studio のツールバー](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="08ef2-113">**HelloWorld** プロジェクト (HelloWorld ソリューションではなく) を右クリックし、メニューから **[発行]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="08ef2-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   ![Visual Studio の [発行] コンテキスト メニュー](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="08ef2-115">**[発行]** ページの **[ターゲット]** タブで、 **[フォルダー]** 、 **[次へ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-115">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   ![Visual Studio で発行先を選択します](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="08ef2-117">**[発行]** ページの **[場所]** タブで、 **[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-117">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   ![Visual Studio の [発行] ページの [場所] タブ](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. <span data-ttu-id="08ef2-119">**[発行]** ウィンドウの **[発行]** タブで、 **[発行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-119">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   ![Visual Studio の [発行] ウィンドウ](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="08ef2-121">ファイルを検査する</span><span class="sxs-lookup"><span data-stu-id="08ef2-121">Inspect the files</span></span>

<span data-ttu-id="08ef2-122">この発行プロセスでは、フレームワークに依存する配置が作成されます。つまり、.NET Core のランタイムがインストールされているコンピューターで、発行されたアプリケーションが実行される配置の種類です。</span><span class="sxs-lookup"><span data-stu-id="08ef2-122">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="08ef2-123">ユーザーは、実行可能ファイルをダブルクリックするか、コマンドプロンプトから `dotnet HelloWorld.dll` コマンドを実行することで、発行されたアプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="08ef2-123">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="08ef2-124">次の手順で、発行プロセスによって作成されるファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-124">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="08ef2-125">**ソリューション エクスプローラー**で、 **[すべてのファイルを表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-125">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="08ef2-126">プロジェクト フォルダーで *bin/Release/netcoreapp3.1/publish* を展開します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-126">In the project folder, expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="発行されたファイルを表示しているソリューション エクスプローラー":::

   <span data-ttu-id="08ef2-128">この図に示すように、発行された出力には次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="08ef2-128">As the image shows, the published output includes the following files:</span></span>

      * <span data-ttu-id="08ef2-129">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="08ef2-129">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="08ef2-130">このファイルは、アプリケーションのランタイム依存関係ファイルです。</span><span class="sxs-lookup"><span data-stu-id="08ef2-130">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="08ef2-131">これは、アプリの実行に必要な .NET Core コンポーネントとライブラリ (アプリケーションが含まれる動的リンク ライブラリを含む) を定義します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-131">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="08ef2-132">詳細については、「[ランタイム構成ファイル](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08ef2-132">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

      * <span data-ttu-id="08ef2-133">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="08ef2-133">*HelloWorld.dll*</span></span>

         <span data-ttu-id="08ef2-134">これは、[フレームワークに依存する展開](../deploying/deploy-with-cli.md#framework-dependent-deployment)バージョンのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="08ef2-134">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="08ef2-135">このダイナミック リンク ライブラリを実行するには、コマンド プロンプトで`dotnet HelloWorld.dll` を入力します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-135">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span>

      * <span data-ttu-id="08ef2-136">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="08ef2-136">*HelloWorld.exe*</span></span>

         <span data-ttu-id="08ef2-137">これは、[フレームワークに依存する実行可能ファイル](../deploying/deploy-with-cli.md#framework-dependent-executable) バージョンのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="08ef2-137">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="08ef2-138">これを実行するには、コマンド プロンプトで `HelloWorld.exe` を入力します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-138">To run it, enter `HelloWorld.exe` at a command prompt.</span></span>

      * <span data-ttu-id="08ef2-139">*HelloWorld.pdb* (配置は省略可能)</span><span class="sxs-lookup"><span data-stu-id="08ef2-139">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="08ef2-140">これは、デバッグ シンボル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="08ef2-140">This is the debug symbols file.</span></span> <span data-ttu-id="08ef2-141">このファイルはアプリケーションと一緒に配置する必要はありませんが、発行されるバージョンのアプリケーションをデバッグする必要がある場合に保存しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="08ef2-141">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="08ef2-142">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="08ef2-142">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="08ef2-143">これは、アプリケーションのランタイム構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="08ef2-143">This is the application's run-time configuration file.</span></span> <span data-ttu-id="08ef2-144">ビルドされたアプリケーションが実行時に基盤とする .NET Core のバージョンを識別します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-144">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="08ef2-145">構成オプションを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="08ef2-145">You can also add configuration options to it.</span></span> <span data-ttu-id="08ef2-146">詳細については、「[.NET Core ランタイム構成設定](../run-time-config/index.md#runtimeconfigjson)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08ef2-146">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="08ef2-147">発行済みアプリを実行する</span><span class="sxs-lookup"><span data-stu-id="08ef2-147">Run the published app</span></span>

1. <span data-ttu-id="08ef2-148">**ソリューション エクスプローラー**で、 *[publish]* フォルダーを右クリックし、 **[完全なパスのコピー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-148">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="08ef2-149">コマンド プロンプトを開いて、*publish* フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-149">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="08ef2-150">`cd` を入力し、完全なパスを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="08ef2-150">Enter `cd` and then paste the full path.</span></span> <span data-ttu-id="08ef2-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-151">For example:</span></span>

   ```
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="08ef2-152">実行可能ファイルを使用してアプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-152">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="08ef2-153">「`HelloWorld.exe`」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-153">Enter `HelloWorld.exe` and press Enter.</span></span>

   1. <span data-ttu-id="08ef2-154">プロンプトに応答して名前を入力し、任意のキーを押して終了します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-154">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="08ef2-155">`dotnet` コマンドを使用して、アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-155">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="08ef2-156">「`dotnet HelloWorld.dll`」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-156">Enter `dotnet HelloWorld.dll` and press Enter.</span></span>

   1. <span data-ttu-id="08ef2-157">プロンプトに応答して名前を入力し、任意のキーを押して終了します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-157">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="08ef2-158">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="08ef2-158">Additional resources</span></span>

- [<span data-ttu-id="08ef2-159">.NET Core アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="08ef2-159">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="08ef2-160">次の手順</span><span class="sxs-lookup"><span data-stu-id="08ef2-160">Next steps</span></span>

<span data-ttu-id="08ef2-161">このチュートリアルでは、コンソール アプリを発行しました。</span><span class="sxs-lookup"><span data-stu-id="08ef2-161">In this tutorial, you published a console app.</span></span> <span data-ttu-id="08ef2-162">次のチュートリアルでは、クラス ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="08ef2-162">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="08ef2-163">Visual Studio で .NET Standard ライブラリを構築する</span><span class="sxs-lookup"><span data-stu-id="08ef2-163">Create a .NET Standard library in Visual Studio</span></span>](library-with-visual-studio.md)
