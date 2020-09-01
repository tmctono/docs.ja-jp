---
description: C# コンパイラ オプション
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
ms.openlocfilehash: bcb246055ecb553bbefad2a0d5c95bf6a083ee6f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125528"
---
# <a name="c-compiler-options"></a><span data-ttu-id="5e726-103">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="5e726-103">C# Compiler Options</span></span>

<span data-ttu-id="5e726-104">コンパイラは、実行可能ファイル (.exe)、ダイナミック リンク ライブラリ (.dll)、またはコード モジュール (.netmodule) を生成します。</span><span class="sxs-lookup"><span data-stu-id="5e726-104">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>

<span data-ttu-id="5e726-105">すべてのコンパイル オプションは、 **-option** および **/option** という 2 つの形で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5e726-105">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="5e726-106">このドキュメントでは、 **-option** のみを示しています。</span><span class="sxs-lookup"><span data-stu-id="5e726-106">The documentation only shows the **-option** form.</span></span>

<span data-ttu-id="5e726-107">Visual Studio では、コンパイラ オプションは *web.config* ファイルに設定します。</span><span class="sxs-lookup"><span data-stu-id="5e726-107">In Visual Studio, you set compiler options in the *web.config* file.</span></span> <span data-ttu-id="5e726-108">詳細については、[\<compiler> 要素](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e726-108">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="5e726-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5e726-109">In this section</span></span>

- <span data-ttu-id="5e726-110">コマンド ラインから Visual C# アプリケーションを構築する方法については、「[csc.exe を使用したコマンド ラインからのビルド](command-line-building-with-csc-exe.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e726-110">[Command-line Building With csc.exe](command-line-building-with-csc-exe.md) Information about building a Visual C# application from the command line.</span></span>

- <span data-ttu-id="5e726-111">「[方法: Visual Studio のコマンドラインのための環境変数を設定する](how-to-set-environment-variables-for-the-visual-studio-command-line.md)」には、*vsvars32.bat* を実行してコマンドライン ビルドを有効にする手順が記載されています。</span><span class="sxs-lookup"><span data-stu-id="5e726-111">[How to set environment variables for the Visual Studio Command Line](how-to-set-environment-variables-for-the-visual-studio-command-line.md) Provides steps for running *vsvars32.bat* to enable command-line builds.</span></span>

- <span data-ttu-id="5e726-112">[カテゴリ別の C# コンパイラ オプションの一覧](listed-by-category.md) コンパイラ オプションのカテゴリ別一覧。</span><span class="sxs-lookup"><span data-stu-id="5e726-112">[C# Compiler Options Listed by Category](listed-by-category.md) A categorical listing of the compiler options.</span></span>

- <span data-ttu-id="5e726-113">[アルファベット順の C# コンパイラ オプションの一覧](listed-alphabetically.md) コンパイラ オプションのアルファベット順一覧。</span><span class="sxs-lookup"><span data-stu-id="5e726-113">[C# Compiler Options Listed Alphabetically](listed-alphabetically.md) An alphabetical listing of the compiler options.</span></span>

## <a name="related-sections"></a><span data-ttu-id="5e726-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e726-114">Related sections</span></span>

- <span data-ttu-id="5e726-115">[プロジェクト デザイナーの [ビルド] ページ](/visualstudio/ide/reference/build-page-project-designer-csharp) プロジェクトのコンパイル、ビルド、デバッグ方法を制御するプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5e726-115">[Build Page, Project Designer](/visualstudio/ide/reference/build-page-project-designer-csharp) Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="5e726-116">Visual C# プロジェクトのカスタム ビルド手順に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e726-116">Includes information about custom build steps in Visual C# projects.</span></span>

- <span data-ttu-id="5e726-117">[既定のビルドとカスタム ビルド](/visualstudio/ide/compiling-and-building-in-visual-studio) ビルドの種類と構成に関する情報です。</span><span class="sxs-lookup"><span data-stu-id="5e726-117">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio) Information on build types and configurations.</span></span>

- <span data-ttu-id="5e726-118">[ビルドの準備と管理](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) Visual Studio 開発環境でビルドするための手順です。</span><span class="sxs-lookup"><span data-stu-id="5e726-118">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) Procedures for building within the Visual Studio development environment.</span></span>
