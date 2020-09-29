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
ms.openlocfilehash: 3edb1f74ab63497aeda0d72847bce92ad315a1a5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098918"
---
# <a name="-optioninfer"></a><span data-ttu-id="f795c-102">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="f795c-102">-optioninfer</span></span>

<span data-ttu-id="f795c-103">変数宣言でローカル型推論を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f795c-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f795c-104">構文</span><span class="sxs-lookup"><span data-stu-id="f795c-104">Syntax</span></span>  
  
```console  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f795c-105">引数</span><span class="sxs-lookup"><span data-stu-id="f795c-105">Arguments</span></span>  
  
|<span data-ttu-id="f795c-106">用語</span><span class="sxs-lookup"><span data-stu-id="f795c-106">Term</span></span>|<span data-ttu-id="f795c-107">定義</span><span class="sxs-lookup"><span data-stu-id="f795c-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="f795c-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="f795c-108">`+` &#124; `-`</span></span>|<span data-ttu-id="f795c-109">任意。</span><span class="sxs-lookup"><span data-stu-id="f795c-109">Optional.</span></span> <span data-ttu-id="f795c-110">`-optioninfer+` を指定してローカル型推論を有効にするか、または `-optioninfer-` を指定してローカル型推論をブロックします。</span><span class="sxs-lookup"><span data-stu-id="f795c-110">Specify `-optioninfer+` to enable local type inference, or `-optioninfer-` to block it.</span></span> <span data-ttu-id="f795c-111">`-optioninfer` オプションは、何も値を指定しない場合、`-optioninfer+` と同じです。</span><span class="sxs-lookup"><span data-stu-id="f795c-111">The `-optioninfer` option, with no value specified, is the same as `-optioninfer+`.</span></span> <span data-ttu-id="f795c-112">`-optioninfer` スイッチが存在しない場合の既定値も `-optioninfer+` です。</span><span class="sxs-lookup"><span data-stu-id="f795c-112">The default value when the `-optioninfer` switch is not present is also `-optioninfer+`.</span></span> <span data-ttu-id="f795c-113">既定値は、Vbc.rsp 応答ファイル内に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f795c-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="f795c-114">`-noconfig` オプションを使用すると、vbc.rsp に指定するのではなく、コンパイラの内部既定値を保持できます。</span><span class="sxs-lookup"><span data-stu-id="f795c-114">You can use the `-noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="f795c-115">このオプションのコンパイラの既定値は `-optioninfer-` です。</span><span class="sxs-lookup"><span data-stu-id="f795c-115">The compiler default for this option is `-optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f795c-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="f795c-116">Remarks</span></span>  

 <span data-ttu-id="f795c-117">ソース コード ファイルに [Option Infer](../../language-reference/statements/option-infer-statement.md) ステートメントが含まれている場合、そのステートメントによって `-optioninfer` コマンド ライン コンパイラ設定がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="f795c-117">If the source code file contains an [Option Infer Statement](../../language-reference/statements/option-infer-statement.md), the statement overrides the `-optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="f795c-118">Visual Studio IDE で -optioninfer を設定するには</span><span class="sxs-lookup"><span data-stu-id="f795c-118">To set -optioninfer in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="f795c-119">**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="f795c-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="f795c-120">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f795c-120">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="f795c-121">**[コンパイル]** タブで、 **[Option infer]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="f795c-121">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f795c-122">例</span><span class="sxs-lookup"><span data-stu-id="f795c-122">Example</span></span>  

 <span data-ttu-id="f795c-123">次のコードは、ローカル型推論を有効にした状態で `test.vb` をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="f795c-123">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f795c-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="f795c-124">See also</span></span>

- [<span data-ttu-id="f795c-125">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="f795c-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="f795c-126">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="f795c-126">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="f795c-127">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="f795c-127">-optionexplicit</span></span>](optionexplicit.md)
- [<span data-ttu-id="f795c-128">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="f795c-128">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="f795c-129">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="f795c-129">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="f795c-130">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="f795c-130">Option Infer Statement</span></span>](../../language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="f795c-131">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="f795c-131">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- <span data-ttu-id="f795c-132">[[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト])](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="f795c-132">[Visual Basic Defaults, Projects, Options Dialog Box](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
- <span data-ttu-id="f795c-133">[[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="f795c-133">[Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span></span>
- [<span data-ttu-id="f795c-134">-noconfig</span><span class="sxs-lookup"><span data-stu-id="f795c-134">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="f795c-135">コマンド ラインからのビルド</span><span class="sxs-lookup"><span data-stu-id="f795c-135">Building from the Command Line</span></span>](building-from-the-command-line.md)
