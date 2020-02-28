---
title: 'チュートリアル: .NET Core ローカル ツールをインストールして使用する'
description: .NET ツールをローカル ツールとしてインストールして使用する方法について説明します。
ms.date: 02/12/2020
ms.openlocfilehash: 6de620772cec1e9d1b1f57380b72c0163d68337c
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543816"
---
# <a name="tutorial-install-and-use-a-net-core-local-tool-using-the-net-core-cli"></a><span data-ttu-id="e6185-103">チュートリアル: .NET Core CLI を使って .NET Core ローカル ツールをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="e6185-103">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>

<span data-ttu-id="e6185-104">**この記事の対象:** ✔️ .NET Core 3.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="e6185-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

<span data-ttu-id="e6185-105">このチュートリアルでは、ローカル ツールをインストールして使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6185-105">This tutorial teaches you how to install and use a local tool.</span></span> <span data-ttu-id="e6185-106">[このシリーズの最初のチュートリアル](global-tools-how-to-create.md)で作成されるツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="e6185-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6185-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e6185-107">Prerequisites</span></span>

* <span data-ttu-id="e6185-108">[このシリーズの最初のチュートリアル](global-tools-how-to-create.md)を完了します。</span><span class="sxs-lookup"><span data-stu-id="e6185-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>
* <span data-ttu-id="e6185-109">.NET Core 2.1 ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e6185-109">Install the .NET Core 2.1 runtime.</span></span>

  <span data-ttu-id="e6185-110">このチュートリアルでは、.NET Core 2.1 を対象とするツールをインストールして使用するため、お使いのコンピューター上に該当のランタイムがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6185-110">For this tutorial you install and use a tool that targets .NET Core 2.1, so you need to have that runtime installed on your machine.</span></span> <span data-ttu-id="e6185-111">2\.1 ランタイムをインストールするには、[.NET Core 2.1 のダウンロード ページ](https://dotnet.microsoft.com/download/dotnet-core/2.1)にアクセスして、 **[Run apps - Runtime]\(アプリの実行 - ランタイム\)** 列でランタイム インストールのリンクを見つけます。</span><span class="sxs-lookup"><span data-stu-id="e6185-111">To install the 2.1 runtime, go to the [.NET Core 2.1 download page](https://dotnet.microsoft.com/download/dotnet-core/2.1) and find the runtime installation link in the **Run apps - Runtime** column.</span></span>

## <a name="create-a-manifest-file"></a><span data-ttu-id="e6185-112">マニフェスト ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="e6185-112">Create a manifest file</span></span>

<span data-ttu-id="e6185-113">ローカル アクセス専用のツール (現在のディレクトリとサブディレクトリ用) をインストールするには、マニフェスト ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6185-113">To install a tool for local access only (for the current directory and subdirectories), it has to be added to a manifest file.</span></span> 

<span data-ttu-id="e6185-114">*botsay-\<name>* フォルダーから、1 つ上のレベルの *repository* フォルダーへ移動します。</span><span class="sxs-lookup"><span data-stu-id="e6185-114">From the *botsay-\<name>* folder, navigate up one level to the *repository* folder:</span></span>

```console
cd ..
```

<span data-ttu-id="e6185-115">[dotnet new](dotnet-new.md) コマンドを実行して、マニフェスト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e6185-115">Create a manifest file by running the [dotnet new](dotnet-new.md) command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="e6185-116">出力によって、ファイルが正常に作成されたことが示されます。</span><span class="sxs-lookup"><span data-stu-id="e6185-116">The output indicates successful creation of the file.</span></span>

```console
The template "Dotnet local tool manifest file" was created successfully.
```

<span data-ttu-id="e6185-117">*.config/dotnet-tools.json* ファイル内には、まだツールはありません。</span><span class="sxs-lookup"><span data-stu-id="e6185-117">The *.config/dotnet-tools.json* file has no tools in it yet:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

<span data-ttu-id="e6185-118">マニフェスト ファイルに示されているツールは、現在のディレクトリとサブディレクトリで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6185-118">The tools listed in a manifest file are available to the current directory and subdirectories.</span></span> <span data-ttu-id="e6185-119">現在のディレクトリは、マニフェスト ファイルがある *.config* ディレクトリが含まれているディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="e6185-119">The current directory is the one that contains the *.config* directory with the manifest file.</span></span>

<span data-ttu-id="e6185-120">ローカル ツールを参照する CLI コマンドを使用すると、SDK では現在のディレクトリおよび親ディレクトリ内でマニフェスト ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="e6185-120">When you use a CLI command that refers to a local tool, the SDK searches for a manifest file in the current directory and parent directories.</span></span> <span data-ttu-id="e6185-121">マニフェスト ファイルが見つかっても、参照されたツールがファイルに含まれていない場合は、親ディレクトリを遡って引き続き検索されます。</span><span class="sxs-lookup"><span data-stu-id="e6185-121">If it finds a manifest file, but the file doesn't include the referenced tool, it continues the search up through parent directories.</span></span> <span data-ttu-id="e6185-122">検索は、参照されたツールが見つかったとき、または `isRoot` が `true` に設定されているマニフェスト ファイルが見つかったときに終了します。</span><span class="sxs-lookup"><span data-stu-id="e6185-122">The search ends when it finds the referenced tool or it finds a manifest file with `isRoot` set to `true`.</span></span>

## <a name="install-botsay-as-a-local-tool"></a><span data-ttu-id="e6185-123">ローカル ツールとして botsay をインストールする</span><span class="sxs-lookup"><span data-stu-id="e6185-123">Install botsay as a local tool</span></span>

<span data-ttu-id="e6185-124">最初のチュートリアルで作成したパッケージからツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e6185-124">Install the tool from the package that you created in the first tutorial:</span></span>

```dotnetcli
dotnet tool install --add-source ./botsay-<name>/nupkg botsay-<name>
```

<span data-ttu-id="e6185-125">このコマンドでは、前の手順で作成したマニフェスト ファイルにツールを追加します。</span><span class="sxs-lookup"><span data-stu-id="e6185-125">This command adds the tool to the manifest file that you created in the preceding step.</span></span> <span data-ttu-id="e6185-126">コマンドの出力は、新しくインストールされたツールがどのマニフェスト ファイルに含まれているかを示しています。</span><span class="sxs-lookup"><span data-stu-id="e6185-126">The command output shows which manifest file the newly installed tool is in:</span></span>

 ```console
 You can invoke the tool from this directory using the following command:
 'dotnet tool run botsay' or 'dotnet botsay'
 Tool 'botsay-<name>' (version '1.0.0') was successfully installed.
 Entry is added to the manifest file /home/name/repository/.config/dotnet-tools.json
 ```

<span data-ttu-id="e6185-127">*.config/dotnet-tools.json* ファイルには現在、1 つのツールがあります。</span><span class="sxs-lookup"><span data-stu-id="e6185-127">The *.config/dotnet-tools.json* file now has one tool:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "botsay-<name>": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    }
  }
}
```

## <a name="use-the-tool"></a><span data-ttu-id="e6185-128">ツールの使用</span><span class="sxs-lookup"><span data-stu-id="e6185-128">Use the tool</span></span>

<span data-ttu-id="e6185-129">*repository* フォルダーから `dotnet tool run` コマンドを実行して、ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="e6185-129">Invoke the tool by running the `dotnet tool run` command from the *repository* folder:</span></span>

```dotnetcli
dotnet tool run botsay hello from the bot
```

## <a name="restore-a-local-tool-installed-by-others"></a><span data-ttu-id="e6185-130">他のユーザーによってインストールされたローカル ツールを復元する</span><span class="sxs-lookup"><span data-stu-id="e6185-130">Restore a local tool installed by others</span></span>

<span data-ttu-id="e6185-131">通常は、リポジトリのルート ディレクトリにローカル ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e6185-131">You typically install a local tool in the root directory of the repository.</span></span> <span data-ttu-id="e6185-132">マニフェスト ファイルをリポジトリにチェックインすると、他の開発者が最新のマニフェスト ファイルを取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e6185-132">After you check in the manifest file to the repository, other developers can get the latest manifest file.</span></span> <span data-ttu-id="e6185-133">マニフェスト ファイルに一覧表示されたすべてのツールをインストールするには、単一の `dotnet tool restore` コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e6185-133">To install all of the tools listed in the manifest file, they can run a single `dotnet tool restore` command.</span></span>

1. <span data-ttu-id="e6185-134">*.config/dotnet-tools.json* ファイルを開き、内容を次の JSON に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e6185-134">Open the *.config/dotnet-tools.json* file, and replace the contents with the following JSON:</span></span>

   ```json
   {
     "version": 1,
     "isRoot": true,
     "tools": {
       "botsay-<name>": {
         "version": "1.0.0",
         "commands": [
           "botsay"
         ]
       },
       "dotnetsay": {
         "version": "2.1.3",
         "commands": [
           "dotnetsay"
         ]
       }
     }
   }
   ```

1. <span data-ttu-id="e6185-135">`<name>` をプロジェクトの作成に使用した名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e6185-135">Replace `<name>` with the name you used to create the project.</span></span>

1. <span data-ttu-id="e6185-136">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="e6185-136">Save your changes.</span></span>

   <span data-ttu-id="e6185-137">この変更を行うことは、他のユーザーがプロジェクト ディレクトリに対してパッケージ `dotnetsay` をインストールした後に、リポジトリから最新バージョンを取得することと同じです。</span><span class="sxs-lookup"><span data-stu-id="e6185-137">Making this change is the same as getting the latest version from the repository after someone else installed the package `dotnetsay` for the project directory.</span></span> 

1. <span data-ttu-id="e6185-138">`dotnet tool restore` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6185-138">Run the `dotnet tool restore` command.</span></span>

   ```dotnetcli
   dotnet tool restore
   ```

   <span data-ttu-id="e6185-139">コマンドによって、次の例のような出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e6185-139">The command produces output like the following example:</span></span>

   ```console
   Tool 'botsay-<name>' (version '1.0.0') was restored. Available commands: botsay
   Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
   Restore was successful.
   ```

1. <span data-ttu-id="e6185-140">ツールが使用可能であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6185-140">Verify that the tools are available:</span></span>

   ```dotnetcli
   dotnet tool list
   ```

   <span data-ttu-id="e6185-141">次の例のように、出力はパッケージとコマンドの一覧になります。</span><span class="sxs-lookup"><span data-stu-id="e6185-141">The output is a list of packages and commands, similar to the following example:</span></span>

   ```console
   Package Id      Version      Commands       Manifest
   -------------------------------------------------------------------------------------------
   botsay-<name>   1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
   dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
   ```

1. <span data-ttu-id="e6185-142">ツールをテストします。</span><span class="sxs-lookup"><span data-stu-id="e6185-142">Test the tools:</span></span>

   ```dotnetcli
   dotnet tool run dotnetsay hello from dotnetsay
   dotnet tool run botsay hello from botsay
   ```

## <a name="update-a-local-tool"></a><span data-ttu-id="e6185-143">ローカル ツールを更新する</span><span class="sxs-lookup"><span data-stu-id="e6185-143">Update a local tool</span></span>

<span data-ttu-id="e6185-144">インストールされているローカルツール `dotnetsay` のバージョンは 2.1.3 です。</span><span class="sxs-lookup"><span data-stu-id="e6185-144">The installed version of local tool `dotnetsay` is 2.1.3.</span></span>  <span data-ttu-id="e6185-145">最新バージョンは 2.1.4 です。</span><span class="sxs-lookup"><span data-stu-id="e6185-145">The latest version is 2.1.4.</span></span> <span data-ttu-id="e6185-146">[dotnet tool update](dotnet-tool-update.md) コマンドを使用して、ツールを最新バージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="e6185-146">Use the [dotnet tool update](dotnet-tool-update.md) command to update the tool to the latest version.</span></span>

```dotnetcli
dotnet tool update dotnetsay
```

<span data-ttu-id="e6185-147">出力には、新しいバージョン番号が示されます。</span><span class="sxs-lookup"><span data-stu-id="e6185-147">The output indicates the new version number:</span></span>

```console
Tool 'dotnetsay' was successfully updated from version '2.1.3' to version '2.1.4'
(manifest file /home/name/repository/.config/dotnet-tools.json).
```

<span data-ttu-id="e6185-148">update コマンドでは、パッケージ ID を含む最初のマニフェスト ファイルを検索して、それを更新します。</span><span class="sxs-lookup"><span data-stu-id="e6185-148">The update command finds the first manifest file that contains the package ID and updates it.</span></span> <span data-ttu-id="e6185-149">検索のスコープ内にあるマニフェスト ファイルにこのようなパッケージ ID がない場合、SDK では最も近いマニフェスト ファイルに新しいエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="e6185-149">If there is no such package ID in any manifest file that is in the scope of the search, the SDK adds a new entry to the closest manifest file.</span></span> <span data-ttu-id="e6185-150">`isRoot = true` のマニフェスト ファイルが見つかるまで、検索のスコープとして親ディレクトリを遡ります。</span><span class="sxs-lookup"><span data-stu-id="e6185-150">The search scope is up through parent directories until a manifest file with `isRoot = true` is found.</span></span>

## <a name="remove-local-tools"></a><span data-ttu-id="e6185-151">ローカル ツールを削除する</span><span class="sxs-lookup"><span data-stu-id="e6185-151">Remove local tools</span></span>

<span data-ttu-id="e6185-152">[dotnet tool uninstall](dotnet-tool-uninstall.md) コマンドを実行して、インストールされたツールを削除します。</span><span class="sxs-lookup"><span data-stu-id="e6185-152">Remove the installed tools by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

```dotnetcli
dotnet tool uninstall botsay-<name>
```

```dotnetcli
dotnet tool uninstall dotnetsay
```

## <a name="troubleshoot"></a><span data-ttu-id="e6185-153">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e6185-153">Troubleshoot</span></span>

<span data-ttu-id="e6185-154">チュートリアルの実行中にエラー メッセージが表示された場合は、「[.NET Core ツールの使用に関する問題のトラブルシューティング](troubleshoot-usage-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6185-154">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e6185-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6185-155">See also</span></span>

<span data-ttu-id="e6185-156">詳細については、[.NET Core ツール](global-tools.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6185-156">For more information, see [.NET Core tools](global-tools.md)</span></span>
