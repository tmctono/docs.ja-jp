---
ms.openlocfilehash: 85f50b221e7ecb1ebd6fa539894ab7aabed8d362
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2019
ms.locfileid: "67540111"
---
### <a name="install-the-global-tool"></a><span data-ttu-id="d58a2-101">グローバル ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="d58a2-101">Install the global tool</span></span>

<span data-ttu-id="d58a2-102">パッケージ アセットは `--tool-path` オプションを使用して保護された場所にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d58a2-102">Package assets should be installed in a protected location using the `--tool-path` option.</span></span> <span data-ttu-id="d58a2-103">このように分けることにより、制限付きユーザー環境が特権環境と共有されることを回避できす。</span><span class="sxs-lookup"><span data-stu-id="d58a2-103">This separation avoids sharing a restricted user environment with an elevated environment.</span></span>

```bash
sudo dotnet tool install PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

<span data-ttu-id="d58a2-104">`/usr/local/share/dotnet-tools` は `drwxr-xr-x` アクセス許可で作成されます。</span><span class="sxs-lookup"><span data-stu-id="d58a2-104">`/usr/local/share/dotnet-tools` will be created with permission `drwxr-xr-x`.</span></span> <span data-ttu-id="d58a2-105">ディレクトリが既に存在する場合は、`ls -l` コマンドを使用して、制限付きユーザーにディレクトリを編集するアクセス許可がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d58a2-105">If the directory already exists, use the `ls -l` command to verify the restricted user doesn't have permission to edit the directory.</span></span> <span data-ttu-id="d58a2-106">ある場合は、`sudo chmod o-w -R /usr/share/dotnet-tools` コマンドを使用してそのアクセス許可を削除します。</span><span class="sxs-lookup"><span data-stu-id="d58a2-106">If so, use the `sudo chmod o-w -R /usr/share/dotnet-tools` command to remove the access.</span></span>

### <a name="run-the-global-tool"></a><span data-ttu-id="d58a2-107">グローバル ツールを実行する</span><span class="sxs-lookup"><span data-stu-id="d58a2-107">Run the global tool</span></span>

<span data-ttu-id="d58a2-108">**オプション 1** sudo で完全なパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d58a2-108">**Option 1** Use the full path with sudo:</span></span>

```bash
sudo /usr/local/share/dotnet-tools/TOOLCOMMAND
```

<span data-ttu-id="d58a2-109">**オプション 2** ツールごとに 1 回、ツールのシンボルのリンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="d58a2-109">**Option 2** Add the symbol link of the tool, once per tool:</span></span>

```bash
sudo ln -s /usr/local/share/dotnet-tools/TOOLCOMMAND /usr/local/bin/TOOLCOMMAND
```

<span data-ttu-id="d58a2-110">次で実行します。</span><span class="sxs-lookup"><span data-stu-id="d58a2-110">And run with:</span></span>

```bash
sudo TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a><span data-ttu-id="d58a2-111">グローバル ツールをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="d58a2-111">Uninstall the global tool</span></span>

```bash
sudo dotnet tool uninstall PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

<span data-ttu-id="d58a2-112">シンボルのリンクを作成した場合は、それも削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d58a2-112">If you made a symbol link, you also need to remove it:</span></span>

```bash
sudo rm /usr/local/bin/TOOLCOMMAND
```
