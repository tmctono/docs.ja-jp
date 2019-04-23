---
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: f1dcc03a67880727893e55c13d65a804586b3f56
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59315505"
---
# <a name="-optioninfer"></a><span data-ttu-id="d163d-102">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="d163d-102">-optioninfer</span></span>
<span data-ttu-id="d163d-103">変数宣言でローカル型推論を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d163d-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d163d-104">構文</span><span class="sxs-lookup"><span data-stu-id="d163d-104">Syntax</span></span>  
  
```  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d163d-105">引数</span><span class="sxs-lookup"><span data-stu-id="d163d-105">Arguments</span></span>  
  
|<span data-ttu-id="d163d-106">用語</span><span class="sxs-lookup"><span data-stu-id="d163d-106">Term</span></span>|<span data-ttu-id="d163d-107">定義</span><span class="sxs-lookup"><span data-stu-id="d163d-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="d163d-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d163d-108">`+` &#124; `-`</span></span>|<span data-ttu-id="d163d-109">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d163d-109">Optional.</span></span> <span data-ttu-id="d163d-110">`-optioninfer+` を指定してローカル型推論を有効にするか、または `-optioninfer-` を指定してローカル型推論をブロックします。</span><span class="sxs-lookup"><span data-stu-id="d163d-110">Specify `-optioninfer+` to enable local type inference, or `-optioninfer-` to block it.</span></span> <span data-ttu-id="d163d-111">`-optioninfer` オプションは、何も値を指定しない場合、`-optioninfer+` と同じです。</span><span class="sxs-lookup"><span data-stu-id="d163d-111">The `-optioninfer` option, with no value specified, is the same as `-optioninfer+`.</span></span> <span data-ttu-id="d163d-112">`-optioninfer` スイッチが存在しない場合の既定値も `-optioninfer+` です。</span><span class="sxs-lookup"><span data-stu-id="d163d-112">The default value when the `-optioninfer` switch is not present is also `-optioninfer+`.</span></span> <span data-ttu-id="d163d-113">既定値は、Vbc.rsp 応答ファイル内に設定されています。</span><span class="sxs-lookup"><span data-stu-id="d163d-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="d163d-114">`-noconfig` オプションを使用すると、vbc.rsp に指定するのではなく、コンパイラの内部既定値を保持できます。</span><span class="sxs-lookup"><span data-stu-id="d163d-114">You can use the `-noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="d163d-115">このオプションのコンパイラの既定値は `-optioninfer-` です。</span><span class="sxs-lookup"><span data-stu-id="d163d-115">The compiler default for this option is `-optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d163d-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="d163d-116">Remarks</span></span>  
 <span data-ttu-id="d163d-117">ソース コード ファイルが含まれている場合、 [Option Infer ステートメント](../../../visual-basic/language-reference/statements/option-infer-statement.md)、ステートメントよりも優先、`-optioninfer`コマンド ライン コンパイラを設定します。</span><span class="sxs-lookup"><span data-stu-id="d163d-117">If the source code file contains an [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md), the statement overrides the `-optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="d163d-118">Visual Studio IDE で-optioninfer を設定するには</span><span class="sxs-lookup"><span data-stu-id="d163d-118">To set -optioninfer in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="d163d-119">プロジェクトを選択**ソリューション エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="d163d-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="d163d-120">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d163d-120">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="d163d-121">**コンパイル** タブで、値を変更、 **Option infer**ボックス。</span><span class="sxs-lookup"><span data-stu-id="d163d-121">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d163d-122">例</span><span class="sxs-lookup"><span data-stu-id="d163d-122">Example</span></span>  
 <span data-ttu-id="d163d-123">次のコードは、ローカル型推論を有効にした状態で `test.vb` をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="d163d-123">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d163d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d163d-124">See also</span></span>

- [<span data-ttu-id="d163d-125">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="d163d-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d163d-126">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="d163d-126">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="d163d-127">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="d163d-127">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="d163d-128">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="d163d-128">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="d163d-129">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="d163d-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="d163d-130">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="d163d-130">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="d163d-131">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="d163d-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- <span data-ttu-id="d163d-132">[[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト])](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="d163d-132">[Visual Basic Defaults, Projects, Options Dialog Box](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
- <span data-ttu-id="d163d-133">[[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="d163d-133">[Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span></span>
- [<span data-ttu-id="d163d-134">/noconfig</span><span class="sxs-lookup"><span data-stu-id="d163d-134">/noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="d163d-135">コマンド ラインからのビルド</span><span class="sxs-lookup"><span data-stu-id="d163d-135">Building from the Command Line</span></span>](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
