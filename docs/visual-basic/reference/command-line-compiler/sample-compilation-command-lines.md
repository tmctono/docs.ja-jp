---
title: コンパイル コマンド ラインのサンプル (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: b7879c23bc64269c793c21b61b84d6f0fd4bdc24
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046291"
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="8184d-102">コンパイルコマンドラインのサンプル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8184d-102">Sample compilation command lines (Visual Basic)</span></span>

<span data-ttu-id="8184d-103">Visual Studio 内から Visual Basic プログラムをコンパイルする代わりに、コマンドラインからコンパイルして、実行可能 (.exe) ファイルまたはダイナミックリンクライブラリ (.dll) ファイルを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8184d-103">As an alternative to compiling Visual Basic programs from within Visual Studio, you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>

<span data-ttu-id="8184d-104">Visual Basic のコマンドラインコンパイラは、入力ファイル、出力ファイル、アセンブリ、およびデバッグオプションとプリプロセッサオプションを制御するオプションの完全なセットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8184d-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="8184d-105">各オプションは`-option` 、と`/option`の2つの交換可能な形式で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8184d-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="8184d-106">このドキュメントでは、 `-option`フォームのみを示します。</span><span class="sxs-lookup"><span data-stu-id="8184d-106">This documentation shows only the `-option` form.</span></span>

<span data-ttu-id="8184d-107">次の表に、自分で使用するために変更できるサンプルコマンドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="8184d-107">The following table lists some sample command lines you can modify for your own use.</span></span>

|<span data-ttu-id="8184d-108">目的</span><span class="sxs-lookup"><span data-stu-id="8184d-108">To</span></span>|<span data-ttu-id="8184d-109">使用</span><span class="sxs-lookup"><span data-stu-id="8184d-109">Use</span></span>|
|--------|---------|
|<span data-ttu-id="8184d-110">ファイル .vb をコンパイルして、ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8184d-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|<span data-ttu-id="8184d-111">ファイル .vb をコンパイルし、ファイル .dll を作成します。</span><span class="sxs-lookup"><span data-stu-id="8184d-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|
|<span data-ttu-id="8184d-112">ファイル .vb をコンパイルして、.exe を作成します。</span><span class="sxs-lookup"><span data-stu-id="8184d-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|
|<span data-ttu-id="8184d-113">ファイル .vb をコンパイルし、ファイル .dll という名前のライブラリと参照アセンブリの両方を作成します。</span><span class="sxs-lookup"><span data-stu-id="8184d-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="8184d-114">最適化をオンにし`DEBUG` 、定義したシンボルを使用して、現在のディレクトリにあるすべての Visual Basic ファイルをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="8184d-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|<span data-ttu-id="8184d-115">現在のディレクトリにあるすべての Visual Basic ファイルをコンパイルし、ロゴまたは警告を表示せずに、File2 のデバッグバージョンを生成します。</span><span class="sxs-lookup"><span data-stu-id="8184d-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|<span data-ttu-id="8184d-116">現在のディレクトリにあるすべての Visual Basic ファイルを何らかの .dll にコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="8184d-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> <span data-ttu-id="8184d-117">Visual Studio IDE を使用してプロジェクトをビルドする場合、関連付けられている**vbc.exe**コマンドに関する情報を [出力] ウィンドウのコンパイラオプションと共に表示できます。</span><span class="sxs-lookup"><span data-stu-id="8184d-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="8184d-118">この情報を表示するには、[オプション] ダイアログボックス、[プロジェクトとソリューション]、[ビルドと実行](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)] の順に開き、 **MSBuild プロジェクトのビルド出力の詳細**レベルを **[標準]** または [高レベルの詳細 に設定します。</span><span class="sxs-lookup"><span data-stu-id="8184d-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>

## <a name="see-also"></a><span data-ttu-id="8184d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8184d-119">See also</span></span>

- [<span data-ttu-id="8184d-120">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="8184d-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8184d-121">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="8184d-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
