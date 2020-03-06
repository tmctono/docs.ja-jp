---
title: 'チュートリアル: .NET Core グローバル ツールをインストールして使用する'
description: .NET ツールをグローバル ツールとしてインストールして使用する方法について説明します。
ms.date: 02/12/2020
ms.openlocfilehash: 9f8378e50fd2544eedbbaaeffb89d67800ec6880
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156739"
---
# <a name="tutorial-install-and-use-a-net-core-global-tool-using-the-net-core-cli"></a><span data-ttu-id="84cc1-103">チュートリアル: .NET Core CLI を使って .NET Core グローバル ツールをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="84cc1-103">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>

<span data-ttu-id="84cc1-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="84cc1-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="84cc1-105">このチュートリアルでは、グローバル ツールをインストールして使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="84cc1-105">This tutorial teaches you how to install and use a global tool.</span></span> <span data-ttu-id="84cc1-106">[このシリーズの最初のチュートリアル](global-tools-how-to-create.md)で作成されるツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="84cc1-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="84cc1-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="84cc1-107">Prerequisites</span></span>

* <span data-ttu-id="84cc1-108">[このシリーズの最初のチュートリアル](global-tools-how-to-create.md)を完了します。</span><span class="sxs-lookup"><span data-stu-id="84cc1-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="use-the-tool-as-a-global-tool"></a><span data-ttu-id="84cc1-109">グローバル ツールとしてツールを使用する</span><span class="sxs-lookup"><span data-stu-id="84cc1-109">Use the tool as a global tool</span></span>

1. <span data-ttu-id="84cc1-110">*microsoft.botsay* プロジェクト フォルダーに [dotnet tool install](dotnet-tool-install.md) コマンドを実行して、パッケージからツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84cc1-110">Install the tool from the package by running the [dotnet tool install](dotnet-tool-install.md) command in the *microsoft.botsay* project folder:</span></span>

   ```dotnetcli
   dotnet tool install --global --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="84cc1-111">`--global` パラメーターでは、PATH 環境変数に自動的に追加される既定の場所にツール バイナリをインストールするように、.NET Core CLI に指示します。</span><span class="sxs-lookup"><span data-stu-id="84cc1-111">The `--global` parameter tells the .NET Core CLI to install the tool binaries in a default location that is automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="84cc1-112">`--add-source` パラメーターでは、NuGet パッケージへの追加のソース フィードとして *./nupkg* ディレクトリを一時的に使用するように、.NET Core CLI に指示します。</span><span class="sxs-lookup"><span data-stu-id="84cc1-112">The `--add-source` parameter tells the .NET Core CLI to temporarily use the *./nupkg* directory as an additional source feed for NuGet packages.</span></span> <span data-ttu-id="84cc1-113">Nuget.org サイト上ではなく、必ず *./nupkg* ディレクトリ内だけで見つかるように、パッケージには一意の名前を付けました。</span><span class="sxs-lookup"><span data-stu-id="84cc1-113">You gave your package a unique name to make sure that it will only be found in the *./nupkg* directory, not on the Nuget.org site.</span></span>

   <span data-ttu-id="84cc1-114">出力には、ツールの呼び出しに使用されたコマンドと、インストールされているバージョンが示されます。</span><span class="sxs-lookup"><span data-stu-id="84cc1-114">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="84cc1-115">ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="84cc1-115">Invoke the tool:</span></span>

   ```console
   botsay hello from the bot
   ```

   > [!NOTE]
   > <span data-ttu-id="84cc1-116">このコマンドが失敗すると、新しいターミナルを開いて PATH を更新することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="84cc1-116">If this command fails, you may need to open a new terminal to refresh the PATH.</span></span>

1. <span data-ttu-id="84cc1-117">[dotnet tool uninstall](dotnet-tool-uninstall.md) コマンドを実行して、ツールを削除します。</span><span class="sxs-lookup"><span data-stu-id="84cc1-117">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   ```dotnetcli
   dotnet tool uninstall -g microsoft.botsay
   ```

## <a name="use-the-tool-as-a-global-tool-installed-in-a-custom-location"></a><span data-ttu-id="84cc1-118">カスタムの場所にインストールされているグローバル ツールとしてツールを使用する</span><span class="sxs-lookup"><span data-stu-id="84cc1-118">Use the tool as a global tool installed in a custom location</span></span>

1. <span data-ttu-id="84cc1-119">パッケージからツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84cc1-119">Install the tool from the package.</span></span>

   <span data-ttu-id="84cc1-120">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="84cc1-120">On Windows:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path c:\dotnet-tools --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="84cc1-121">Linux または macOS の場合:</span><span class="sxs-lookup"><span data-stu-id="84cc1-121">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path ~/bin --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="84cc1-122">`--tool-path` パラメーターでは、指定された場所にツール バイナリをインストールするように、.NET Core CLI に指示します。</span><span class="sxs-lookup"><span data-stu-id="84cc1-122">The `--tool-path` parameter tells the .NET Core CLI to install the tool binaries in the specified location.</span></span> <span data-ttu-id="84cc1-123">ディレクトリが存在しなければ、作成されます。</span><span class="sxs-lookup"><span data-stu-id="84cc1-123">If the directory doesn't exist, it is created.</span></span> <span data-ttu-id="84cc1-124">このディレクトリは、PATH 環境変数に自動的に追加されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="84cc1-124">This directory is not automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="84cc1-125">出力には、ツールの呼び出しに使用されたコマンドと、インストールされているバージョンが示されます。</span><span class="sxs-lookup"><span data-stu-id="84cc1-125">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="84cc1-126">ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="84cc1-126">Invoke the tool:</span></span>

   <span data-ttu-id="84cc1-127">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="84cc1-127">On Windows:</span></span>

   ```console
   c:\dotnet-tools\botsay hello from the bot
   ```

   <span data-ttu-id="84cc1-128">Linux または macOS の場合:</span><span class="sxs-lookup"><span data-stu-id="84cc1-128">On Linux or macOS:</span></span>

   ```console
   ~/bin/botsay hello from the bot
   ```

1. <span data-ttu-id="84cc1-129">[dotnet tool uninstall](dotnet-tool-uninstall.md) コマンドを実行して、ツールを削除します。</span><span class="sxs-lookup"><span data-stu-id="84cc1-129">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   <span data-ttu-id="84cc1-130">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="84cc1-130">On Windows:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path c:\dotnet-tools microsoft.botsay
   ```

   <span data-ttu-id="84cc1-131">Linux または macOS の場合:</span><span class="sxs-lookup"><span data-stu-id="84cc1-131">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path ~/bin microsoft.botsay
   ```

## <a name="troubleshoot"></a><span data-ttu-id="84cc1-132">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="84cc1-132">Troubleshoot</span></span>

<span data-ttu-id="84cc1-133">チュートリアルの実行中にエラー メッセージが表示された場合は、「[.NET Core ツールの使用に関する問題のトラブルシューティング](troubleshoot-usage-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cc1-133">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="84cc1-134">次の手順</span><span class="sxs-lookup"><span data-stu-id="84cc1-134">Next steps</span></span>

<span data-ttu-id="84cc1-135">このチュートリアルでは、ツールをグローバル ツールとしてインストールして使用しました。</span><span class="sxs-lookup"><span data-stu-id="84cc1-135">In this tutorial, you installed and used a tool as a global tool.</span></span> <span data-ttu-id="84cc1-136">ローカル ツールと同じツールをインストールして使用するには、次のチュートリアルに進んでください。</span><span class="sxs-lookup"><span data-stu-id="84cc1-136">To install and use the same tool as a local tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="84cc1-137">ローカル ツールをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="84cc1-137">Install and use local tools</span></span>](local-tools-how-to-use.md)
