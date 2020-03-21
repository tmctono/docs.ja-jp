---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 37ccd14dae0ebba2535185f2646e312d9bb70390
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266730"
---
# <a name="-optionexplicit"></a><span data-ttu-id="c6ab2-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="c6ab2-102">-optionexplicit</span></span>
<span data-ttu-id="c6ab2-103">変数が使用される前に宣言されていない場合、コンパイラがエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="c6ab2-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6ab2-104">構文</span><span class="sxs-lookup"><span data-stu-id="c6ab2-104">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c6ab2-105">引数</span><span class="sxs-lookup"><span data-stu-id="c6ab2-105">Arguments</span></span>  
 <span data-ttu-id="c6ab2-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c6ab2-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="c6ab2-107">省略可能。</span><span class="sxs-lookup"><span data-stu-id="c6ab2-107">Optional.</span></span> <span data-ttu-id="c6ab2-108">変数`-optionexplicit+`の明示的な宣言を要求するように指定します。</span><span class="sxs-lookup"><span data-stu-id="c6ab2-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="c6ab2-109">この`-optionexplicit+`オプションはデフォルトで、 と同じです`-optionexplicit`。</span><span class="sxs-lookup"><span data-stu-id="c6ab2-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="c6ab2-110">この`-optionexplicit-`オプションは、変数の暗黙的な宣言を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c6ab2-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6ab2-111">解説</span><span class="sxs-lookup"><span data-stu-id="c6ab2-111">Remarks</span></span>  
 <span data-ttu-id="c6ab2-112">ソース コード ファイルに[Option Explicit ステートメント](../../../visual-basic/language-reference/statements/option-explicit-statement.md)が含まれている場合`-optionexplicit`、このステートメントはコマンド ライン コンパイラ設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="c6ab2-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="c6ab2-113">オプションを明示的に設定するには</span><span class="sxs-lookup"><span data-stu-id="c6ab2-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="c6ab2-114">**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6ab2-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c6ab2-115">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6ab2-115">On the **Project** menu, click **Properties**.</span></span>
  
2. <span data-ttu-id="c6ab2-116">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6ab2-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="c6ab2-117">**[オプションの明示的なオプション**] ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="c6ab2-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6ab2-118">例</span><span class="sxs-lookup"><span data-stu-id="c6ab2-118">Example</span></span>  
 <span data-ttu-id="c6ab2-119">次のコードは、使用`-optionexplicit-`時にコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="c6ab2-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="c6ab2-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6ab2-120">See also</span></span>

- [<span data-ttu-id="c6ab2-121">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="c6ab2-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c6ab2-122">オプション比較</span><span class="sxs-lookup"><span data-stu-id="c6ab2-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="c6ab2-123">-オプションストリクト</span><span class="sxs-lookup"><span data-stu-id="c6ab2-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="c6ab2-124">-オプションインファー</span><span class="sxs-lookup"><span data-stu-id="c6ab2-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="c6ab2-125">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="c6ab2-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="c6ab2-126">Option Explicit ステートメント</span><span class="sxs-lookup"><span data-stu-id="c6ab2-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- <span data-ttu-id="c6ab2-127">[[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト])](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="c6ab2-127">[Visual Basic Defaults, Projects, Options Dialog Box](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
