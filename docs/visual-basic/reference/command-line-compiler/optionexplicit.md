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
ms.openlocfilehash: 65cc3fb1b2fa9daa04013caa2b93a3949d0a15b9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098937"
---
# <a name="-optionexplicit"></a><span data-ttu-id="0e309-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="0e309-102">-optionexplicit</span></span>

<span data-ttu-id="0e309-103">変数が使用される前に宣言されていない場合、コンパイラによってエラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="0e309-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e309-104">構文</span><span class="sxs-lookup"><span data-stu-id="0e309-104">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0e309-105">引数</span><span class="sxs-lookup"><span data-stu-id="0e309-105">Arguments</span></span>  

 <span data-ttu-id="0e309-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="0e309-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="0e309-107">任意。</span><span class="sxs-lookup"><span data-stu-id="0e309-107">Optional.</span></span> <span data-ttu-id="0e309-108">変数の明示的な宣言を要求するには、`-optionexplicit+` を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e309-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="0e309-109">`-optionexplicit+` オプションは既定値であり、`-optionexplicit` と同じです。</span><span class="sxs-lookup"><span data-stu-id="0e309-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="0e309-110">`-optionexplicit-` オプションを使用すると、変数の暗黙的な宣言を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0e309-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e309-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="0e309-111">Remarks</span></span>  

 <span data-ttu-id="0e309-112">ソース コード ファイルに [Option Explicit ステートメント](../../language-reference/statements/option-explicit-statement.md)が含まれている場合、そのステートメントによって `-optionexplicit` コマンドライン コンパイラ設定がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="0e309-112">If the source code file contains an [Option Explicit statement](../../language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="0e309-113">Visual Studio IDE で -optionexplicit を設定するには</span><span class="sxs-lookup"><span data-stu-id="0e309-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="0e309-114">**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="0e309-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0e309-115">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e309-115">On the **Project** menu, click **Properties**.</span></span>
  
2. <span data-ttu-id="0e309-116">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e309-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="0e309-117">**[Option Explicit]** ボックスで値を変更します。</span><span class="sxs-lookup"><span data-stu-id="0e309-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e309-118">例</span><span class="sxs-lookup"><span data-stu-id="0e309-118">Example</span></span>  

 <span data-ttu-id="0e309-119">`-optionexplicit-` が使用されている場合、次のコードがコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="0e309-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="0e309-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e309-120">See also</span></span>

- [<span data-ttu-id="0e309-121">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="0e309-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="0e309-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="0e309-122">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="0e309-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="0e309-123">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="0e309-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="0e309-124">-optioninfer</span></span>](optioninfer.md)
- [<span data-ttu-id="0e309-125">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="0e309-125">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="0e309-126">Option Explicit ステートメント</span><span class="sxs-lookup"><span data-stu-id="0e309-126">Option Explicit Statement</span></span>](../../language-reference/statements/option-explicit-statement.md)
- <span data-ttu-id="0e309-127">[[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト])](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="0e309-127">[Visual Basic Defaults, Projects, Options Dialog Box](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
