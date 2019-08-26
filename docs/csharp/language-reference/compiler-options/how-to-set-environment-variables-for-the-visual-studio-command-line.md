---
title: '方法: Visual Studio のコマンドラインのための環境変数を設定する'
ms.date: 09/29/2017
f1_keywords:
- cs.build.commandline
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
ms.openlocfilehash: 9b26f6b80488ad4043054cd23f0f351773e8d6d1
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602859"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="abd9e-102">方法: Visual Studio のコマンドラインのための環境変数を設定する</span><span class="sxs-lookup"><span data-stu-id="abd9e-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="abd9e-103">VsDevCmd.bat ファイルは、適切な環境変数を設定してコマンド ライン ビルドを有効にします。</span><span class="sxs-lookup"><span data-stu-id="abd9e-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span>

> [!NOTE]
> <span data-ttu-id="abd9e-104">VsDevCmd.bat ファイルは、Visual Studio 2017 で提供される新しいファイルです。</span><span class="sxs-lookup"><span data-stu-id="abd9e-104">The VsDevCmd.bat file is a new file delivered with Visual Studio 2017.</span></span> <span data-ttu-id="abd9e-105">Visual Studio 2015 とそれ以前のバージョンでは、同じ目的で VSVARS32.bat を使用しました。</span><span class="sxs-lookup"><span data-stu-id="abd9e-105">Visual Studio 2015 and earlier versions used VSVARS32.bat for the same purpose.</span></span> <span data-ttu-id="abd9e-106">このファイルは \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools または Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools に格納されていました。</span><span class="sxs-lookup"><span data-stu-id="abd9e-106">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>

<span data-ttu-id="abd9e-107">以前のバージョンの Visual Studio と最新バージョンの Visual Studio の両方がコンピューターにインストールされている場合は、同じコマンド プロンプト ウィンドウから異なるバージョンの VsDevCmd.bat または VSVARS32.BAT を実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="abd9e-107">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="abd9e-108">代わりに、独自のウィンドウで、各バージョンのコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abd9e-108">Instead, you should run the command for each version in its own window.</span></span>

### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="abd9e-109">VsDevCmd.BAT を実行するには</span><span class="sxs-lookup"><span data-stu-id="abd9e-109">To run VsDevCmd.BAT</span></span>

1. <span data-ttu-id="abd9e-110">**[スタート]** メニューから、**VS2017 の開発者コマンド プロンプト**を開きます。</span><span class="sxs-lookup"><span data-stu-id="abd9e-110">From the **Start** menu, open the **Developer Command Prompt for VS 2017**.</span></span>  <span data-ttu-id="abd9e-111">これは、 **[Visual Studio 2017]** フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="abd9e-111">It's in the **Visual Studio 2017** folder.</span></span>

2. <span data-ttu-id="abd9e-112">インストールの \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools または \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools サブディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="abd9e-112">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="abd9e-113">(*Version* は最新バージョンの *2017* です。</span><span class="sxs-lookup"><span data-stu-id="abd9e-113">(*Version* is *2017* for the current version.</span></span> <span data-ttu-id="abd9e-114">*Offering* は *Enterprise*、*Professional* または *Community* のいずれかです。)</span><span class="sxs-lookup"><span data-stu-id="abd9e-114">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>

3. <span data-ttu-id="abd9e-115">「**VsDevCmd**」と入力して、VsDevCmd.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="abd9e-115">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="abd9e-116">VsDevCmd.bat の場所は、コンピューターによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="abd9e-116">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="abd9e-117">VsDevCmd.bat ファイルが見つからない場合や破損している場合でも、別のコンピューターの VsDevCmd.bat と置き換えないでください。</span><span class="sxs-lookup"><span data-stu-id="abd9e-117">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="abd9e-118">その場合は、セットアップ プログラムを再実行してファイルを置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="abd9e-118">Instead, rerun setup to replace the missing file.</span></span>

### <a name="available-options-for-vsdevcmdbat"></a><span data-ttu-id="abd9e-119">VsDevCmd.BAT に使用できるオプション</span><span class="sxs-lookup"><span data-stu-id="abd9e-119">Available options for VsDevCmd.BAT</span></span>

<span data-ttu-id="abd9e-120">VsDevCmd.BAT に使用できるオプションを確認するには、`-help` オプションを使ってコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="abd9e-120">To see the available options for VsDevCmd.BAT, run the command with the `-help` option:</span></span>

```console
VsDevCmd.bat -help
```

## <a name="see-also"></a><span data-ttu-id="abd9e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="abd9e-121">See also</span></span>

- [<span data-ttu-id="abd9e-122">csc.exe を使用したコマンド ラインからのビルド</span><span class="sxs-lookup"><span data-stu-id="abd9e-122">Command-line Building With csc.exe</span></span>](./command-line-building-with-csc-exe.md)
