---
title: C# コンパイラ オプション
ms.date: 07/20/2015
f1_keywords:
- cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
ms.openlocfilehash: dab91ddd1f2b9c91560329eeb1c51ca7f6f175bd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455251"
---
# <a name="c-compiler-options"></a><span data-ttu-id="f3ebd-102">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="f3ebd-102">C# Compiler Options</span></span>

<span data-ttu-id="f3ebd-103">コンパイラは、実行可能ファイル (.exe)、ダイナミック リンク ライブラリ (.dll)、またはコード モジュール (.netmodule) を生成します。</span><span class="sxs-lookup"><span data-stu-id="f3ebd-103">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>

<span data-ttu-id="f3ebd-104">すべてのコンパイル オプションは、 **-option** および **/option** という 2 つの形で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3ebd-104">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="f3ebd-105">このドキュメントでは、 **-option** のみを示しています。</span><span class="sxs-lookup"><span data-stu-id="f3ebd-105">The documentation only shows the **-option** form.</span></span>

<span data-ttu-id="f3ebd-106">Visual Studio では、コンパイラ オプションは *web.config* ファイルに設定します。</span><span class="sxs-lookup"><span data-stu-id="f3ebd-106">In Visual Studio, you set compiler options in the *web.config* file.</span></span> <span data-ttu-id="f3ebd-107">詳細については、「[\<compiler> 要素](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ebd-107">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f3ebd-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f3ebd-108">In this section</span></span>

- <span data-ttu-id="f3ebd-109">コマンド ラインから Visual C# アプリケーションを構築する方法については、「[csc.exe を使用したコマンド ラインからのビルド](command-line-building-with-csc-exe.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ebd-109">[Command-line Building With csc.exe](command-line-building-with-csc-exe.md) Information about building a Visual C# application from the command line.</span></span>

- <span data-ttu-id="f3ebd-110">[方法: Visual Studio のコマンドラインのための環境変数を設定する](how-to-set-environment-variables-for-the-visual-studio-command-line.md) *vsvars32.bat* を実行してコマンドライン ビルドを有効にする手順があります。</span><span class="sxs-lookup"><span data-stu-id="f3ebd-110">[How to: Set Environment Variables for the Visual Studio Command Line](how-to-set-environment-variables-for-the-visual-studio-command-line.md) Provides steps for running *vsvars32.bat* to enable command-line builds.</span></span>

- <span data-ttu-id="f3ebd-111">[カテゴリ別の C# コンパイラ オプションの一覧](listed-by-category.md) コンパイラ オプションのカテゴリ別一覧。</span><span class="sxs-lookup"><span data-stu-id="f3ebd-111">[C# Compiler Options Listed by Category](listed-by-category.md) A categorical listing of the compiler options.</span></span>

- <span data-ttu-id="f3ebd-112">[アルファベット順の C# コンパイラ オプションの一覧](listed-alphabetically.md) コンパイラ オプションのアルファベット順一覧。</span><span class="sxs-lookup"><span data-stu-id="f3ebd-112">[C# Compiler Options Listed Alphabetically](listed-alphabetically.md) An alphabetical listing of the compiler options.</span></span>

## <a name="related-sections"></a><span data-ttu-id="f3ebd-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3ebd-113">Related sections</span></span>

- <span data-ttu-id="f3ebd-114">[プロジェクト デザイナーの [ビルド] ページ](/visualstudio/ide/reference/build-page-project-designer-csharp) プロジェクトのコンパイル、ビルド、デバッグ方法を制御するプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f3ebd-114">[Build Page, Project Designer](/visualstudio/ide/reference/build-page-project-designer-csharp) Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="f3ebd-115">Visual C# プロジェクトのカスタム ビルド手順に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f3ebd-115">Includes information about custom build steps in Visual C# projects.</span></span>

- <span data-ttu-id="f3ebd-116">[既定のビルドとカスタム ビルド](/visualstudio/ide/compiling-and-building-in-visual-studio) ビルドの種類と構成に関する情報です。</span><span class="sxs-lookup"><span data-stu-id="f3ebd-116">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio) Information on build types and configurations.</span></span>

- <span data-ttu-id="f3ebd-117">[ビルドの準備と管理](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) Visual Studio 開発環境でビルドするための手順です。</span><span class="sxs-lookup"><span data-stu-id="f3ebd-117">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) Procedures for building within the Visual Studio development environment.</span></span>
