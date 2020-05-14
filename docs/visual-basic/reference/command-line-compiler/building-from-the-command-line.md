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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344793"
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="a8f6d-102">コマンド ラインからのビルド (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8f6d-102">Building from the Command Line (Visual Basic)</span></span>

<span data-ttu-id="a8f6d-103">Visual Basic プロジェクトは、1 つ以上の個別のソース ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-103">A Visual Basic project is made up of one or more separate source files.</span></span> <span data-ttu-id="a8f6d-104">コンパイルと呼ばれるプロセス中に、これらのファイルが 1 つのパッケージ (アプリケーションとして実行できる 1 つの実行可能ファイル) にまとめられます。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>

<span data-ttu-id="a8f6d-105">Visual Basic では、Visual Studio 統合開発環境 (IDE) 内からプログラムをコンパイルするための代替手段として、コマンドライン コンパイラが提供されています。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-105">Visual Basic provides a command-line compiler as an alternative to compiling programs from within the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="a8f6d-106">コマンドライン コンパイラは、たとえば、システム メモリや記憶域スペースが制限されているコンピューターを使用したり、書き込みを行ったりする場合など、IDE のすべての機能を必要としない場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>

<span data-ttu-id="a8f6d-107">Visual Studio IDE 内からソース ファイルをコンパイルするには、 **[ビルド]** メニューから **[ビルド]** コマンドを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-107">To compile source files from within the Visual Studio IDE, choose the **Build** command from the **Build** menu.</span></span>

> [!TIP]
> <span data-ttu-id="a8f6d-108">Visual Studio IDE を使用してプロジェクト ファイルをビルドする場合、関連する **vbc** コマンドとそのスイッチに関する情報を出力ウィンドウに表示できます。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-108">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="a8f6d-109">この情報を表示するには、[[オプション] ダイアログ ボックス、[プロジェクトおよびソリューション]、[ビルド/実行]](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run) の順に開き、 **[MSBuild プロジェクト ビルドの出力の詳細]** を **[通常]** またはそれ以上の詳細レベルに設定します。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-109">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="a8f6d-110">詳細については、[ビルド ログ ファイルを表示、保存、および構成する](/visualstudio/ide/how-to-view-save-and-configure-build-log-files)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-110">For more information, see [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span></span>

<span data-ttu-id="a8f6d-111">MSBuild を使用して、コマンド プロンプトでプロジェクト (.vbproj) ファイルをコンパイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-111">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="a8f6d-112">詳細については、「[コマンド ライン リファレンス](/visualstudio/msbuild/msbuild-command-line-reference)」と「[チュートリアル:MSBuild の使用](/visualstudio/msbuild/walkthrough-using-msbuild)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-112">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a8f6d-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a8f6d-113">In This Section</span></span>

<span data-ttu-id="a8f6d-114">[方法: コマンド ライン コンパイラを起動する](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) </span><span class="sxs-lookup"><span data-stu-id="a8f6d-114">[How to: Invoke the Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) </span></span>\
<span data-ttu-id="a8f6d-115">MS-DOS プロンプトで、または特定のサブディレクトリからコマンドライン コンパイラを起動する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-115">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>

<span data-ttu-id="a8f6d-116">[コンパイル コマンド ラインのサンプル](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="a8f6d-116">[Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>\
<span data-ttu-id="a8f6d-117">独自に使用するために変更できるサンプル コマンド ラインの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-117">Provides a list of sample command lines that you can modify for your own use.</span></span>

## <a name="related-sections"></a><span data-ttu-id="a8f6d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8f6d-118">Related Sections</span></span>

<span data-ttu-id="a8f6d-119">[Visual Basic のコマンド ライン コンパイラ](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="a8f6d-119">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>\
<span data-ttu-id="a8f6d-120">アルファベット順または目的別に構成された、コンパイラ オプションの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-120">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>

<span data-ttu-id="a8f6d-121">[条件付きコンパイル](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="a8f6d-121">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span></span>\
<span data-ttu-id="a8f6d-122">コードの特定のセクションをコンパイルする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-122">Describes how to compile particular sections of code.</span></span>

<span data-ttu-id="a8f6d-123">[Visual Studio でのプロジェクトとソリューションのビルドおよびクリーン](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="a8f6d-123">[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) </span></span>\
<span data-ttu-id="a8f6d-124">さまざまなビルドに含まれる内容を整理し、プロジェクトのプロパティを選択し、プロジェクトが確実に正しい順序でビルドされるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8f6d-124">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
