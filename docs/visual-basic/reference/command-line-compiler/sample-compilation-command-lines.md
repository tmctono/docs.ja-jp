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
ms.openlocfilehash: 0771ed41d6c58ce7cc98435b405f5819e45393db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916761"
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="8f413-102">コンパイル コマンドラインのサンプル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f413-102">Sample compilation command lines (Visual Basic)</span></span>
<span data-ttu-id="8f413-103">Visual Studio 内から Visual Basic プログラムをコンパイルする代わりに、実行可能ファイル (.exe) ファイルまたはダイナミック リンク ライブラリ (.dll) ファイルを生成するためにコマンドラインからコンパイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="8f413-103">As an alternative to compiling Visual Basic programs from within Visual Studio, you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="8f413-104">Visual Basic のコマンド ライン コンパイラでは、入力を制御し、ファイル、アセンブリ、およびデバッグ、およびプリプロセッサ オプションの出力オプションの完全なセットをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8f413-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="8f413-105">各オプションは 2 つの交換形式で使用できます:`-option`と`/option`します。</span><span class="sxs-lookup"><span data-stu-id="8f413-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="8f413-106">このドキュメントの表示のみ、`-option`フォーム。</span><span class="sxs-lookup"><span data-stu-id="8f413-106">This documentation shows only the `-option` form.</span></span>  
  
 <span data-ttu-id="8f413-107">次の表では、独自の用途を変更するサンプルのコマンドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="8f413-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="8f413-108">目的</span><span class="sxs-lookup"><span data-stu-id="8f413-108">To</span></span>|<span data-ttu-id="8f413-109">用途</span><span class="sxs-lookup"><span data-stu-id="8f413-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="8f413-110">.Vb というファイルをコンパイルして File.exe を作成します。</span><span class="sxs-lookup"><span data-stu-id="8f413-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="8f413-111">.Vb というファイルをコンパイルして File.dll を作成します。</span><span class="sxs-lookup"><span data-stu-id="8f413-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|  
|<span data-ttu-id="8f413-112">.Vb というファイルをコンパイルして My.exe を作成します。</span><span class="sxs-lookup"><span data-stu-id="8f413-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|  
|<span data-ttu-id="8f413-113">.Vb というファイルをコンパイルし、ライブラリと File.dll をという名前の参照アセンブリの両方を作成</span><span class="sxs-lookup"><span data-stu-id="8f413-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="8f413-114">最適化で、現在のディレクトリ内のすべての Visual Basic ファイルをコンパイルして、 `DEBUG` File2.exe を生成するシンボルを定義するには、</span><span class="sxs-lookup"><span data-stu-id="8f413-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|<span data-ttu-id="8f413-115">ロゴや警告を表示せず、デバッグ バージョンの File2.dll を作成、現在のディレクトリ内のすべての Visual Basic ファイルをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="8f413-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|<span data-ttu-id="8f413-116">Something.dll に現在のディレクトリ内のすべての Visual Basic ファイルをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="8f413-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  <span data-ttu-id="8f413-117">関連付けられているに関する情報を表示するには、Visual Studio IDE を使用してプロジェクトをビルドするときに**vbc**出力 ウィンドウでのコンパイラ オプションがコマンド。</span><span class="sxs-lookup"><span data-stu-id="8f413-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="8f413-118">この情報を表示するには、開く、[オプション ダイアログ ボックス、プロジェクトとソリューションをビルドおよび実行](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)、し、設定、 **MSBuild プロジェクト ビルドの出力の詳細**に**標準**または、詳細度の高いレベル。</span><span class="sxs-lookup"><span data-stu-id="8f413-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="8f413-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f413-119">See also</span></span>

- [<span data-ttu-id="8f413-120">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="8f413-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8f413-121">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="8f413-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
