---
title: コマンド ラインからのビルド
ms.date: 07/20/2015
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
ms.openlocfilehash: c7219c0497bb87f0cc44f27229eaf25f9b3eebce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344793"
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="bb603-102">コマンド ラインからのビルド (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb603-102">Building from the Command Line (Visual Basic)</span></span>

<span data-ttu-id="bb603-103">Visual Basic のプロジェクトは、1つまたは複数の個別のソースファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bb603-103">A Visual Basic project is made up of one or more separate source files.</span></span> <span data-ttu-id="bb603-104">コンパイルと呼ばれるプロセスでは、これらのファイルが1つのパッケージ (アプリケーションとして実行できる1つの実行可能ファイル) にまとめられます。</span><span class="sxs-lookup"><span data-stu-id="bb603-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>

<span data-ttu-id="bb603-105">Visual Basic は、Visual Studio 統合開発環境 (IDE) 内からプログラムをコンパイルする代わりに、コマンドラインコンパイラを提供します。</span><span class="sxs-lookup"><span data-stu-id="bb603-105">Visual Basic provides a command-line compiler as an alternative to compiling programs from within the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="bb603-106">コマンドラインコンパイラは、システムメモリまたは記憶域スペースが制限されているコンピューターを使用したり、書き込みを行ったりする場合など、IDE のすべての機能を必要としない場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="bb603-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>

<span data-ttu-id="bb603-107">Visual Studio IDE 内からソースファイルをコンパイルするには、[**ビルド**] メニューの [**ビルド**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb603-107">To compile source files from within the Visual Studio IDE, choose the **Build** command from the **Build** menu.</span></span>

> [!TIP]
> <span data-ttu-id="bb603-108">Visual Studio IDE を使用してプロジェクトファイルをビルドする場合、関連付けられている**vbc.exe**コマンドとそのスイッチに関する情報を出力ウィンドウに表示できます。</span><span class="sxs-lookup"><span data-stu-id="bb603-108">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="bb603-109">この情報を表示するには、[[オプション] ダイアログボックス、[プロジェクトとソリューション]、[ビルドと実行](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)] の順に開き、 **MSBuild プロジェクトのビルド出力の詳細**レベルを [**標準**] または [高レベルの詳細] に設定します。</span><span class="sxs-lookup"><span data-stu-id="bb603-109">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="bb603-110">詳細については、「[方法 :ビルドログファイルを表示、保存、および構成します](/visualstudio/ide/how-to-view-save-and-configure-build-log-files)。</span><span class="sxs-lookup"><span data-stu-id="bb603-110">For more information, see [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span></span>

<span data-ttu-id="bb603-111">MSBuild を使用してコマンド プロンプトで、プロジェクト (.vbproj) ファイルをコンパイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="bb603-111">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="bb603-112">詳細については、次を参照してください。[コマンド ライン リファレンス](/visualstudio/msbuild/msbuild-command-line-reference)と[チュートリアル:MSBuild の使用](/visualstudio/msbuild/walkthrough-using-msbuild)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb603-112">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bb603-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bb603-113">In This Section</span></span>

<span data-ttu-id="bb603-114">[方法: コマンドラインコンパイラ](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)を起動し  </span><span class="sxs-lookup"><span data-stu-id="bb603-114">[How to: Invoke the Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) </span></span>\
<span data-ttu-id="bb603-115">MS-DOS プロンプトまたは特定のサブディレクトリからコマンドラインコンパイラを呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb603-115">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>

<span data-ttu-id="bb603-116">[コンパイルコマンドラインのサンプル](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="bb603-116">[Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>\
<span data-ttu-id="bb603-117">独自に使用するために変更できるサンプルコマンドラインの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="bb603-117">Provides a list of sample command lines that you can modify for your own use.</span></span>

## <a name="related-sections"></a><span data-ttu-id="bb603-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb603-118">Related Sections</span></span>

<span data-ttu-id="bb603-119">[Visual Basic のコマンド ライン コンパイラ](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb603-119">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>\
<span data-ttu-id="bb603-120">アルファベット順または目的別に構成された、コンパイラオプションの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="bb603-120">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>

<span data-ttu-id="bb603-121">[条件付きコンパイル](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)の </span><span class="sxs-lookup"><span data-stu-id="bb603-121">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span></span>\
<span data-ttu-id="bb603-122">コードの特定のセクションをコンパイルする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb603-122">Describes how to compile particular sections of code.</span></span>

<span data-ttu-id="bb603-123">[Visual Studio でのプロジェクトとソリューションのビルドおよびクリーン](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="bb603-123">[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) </span></span>\
<span data-ttu-id="bb603-124">さまざまなビルドに含まれる内容を整理し、プロジェクトのプロパティを選択し、プロジェクトが正しい順序でビルドされるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb603-124">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
