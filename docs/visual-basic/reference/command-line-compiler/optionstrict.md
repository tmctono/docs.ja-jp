---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: 6d281fe07754f0471f8d6c0e31cf3ea890060504
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005349"
---
# <a name="-optionstrict"></a><span data-ttu-id="b1cba-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="b1cba-102">-optionstrict</span></span>
<span data-ttu-id="b1cba-103">厳密な型のセマンティクスを適用して、暗黙的な型変換を制限します。</span><span class="sxs-lookup"><span data-stu-id="b1cba-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1cba-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1cba-104">Syntax</span></span>  
  
```console  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="b1cba-105">引数</span><span class="sxs-lookup"><span data-stu-id="b1cba-105">Arguments</span></span>  
 <span data-ttu-id="b1cba-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="b1cba-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="b1cba-107">任意。</span><span class="sxs-lookup"><span data-stu-id="b1cba-107">Optional.</span></span> <span data-ttu-id="b1cba-108">@No__t-0 オプションを指定すると、暗黙的な型変換が制限されます。</span><span class="sxs-lookup"><span data-stu-id="b1cba-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="b1cba-109">このオプションの既定値は `-optionstrict-` です。</span><span class="sxs-lookup"><span data-stu-id="b1cba-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="b1cba-110">@No__t-0 オプションは `-optionstrict` と同じです。</span><span class="sxs-lookup"><span data-stu-id="b1cba-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="b1cba-111">寛容な型のセマンティクスには、両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b1cba-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="b1cba-112">必須。</span><span class="sxs-lookup"><span data-stu-id="b1cba-112">Required.</span></span> <span data-ttu-id="b1cba-113">厳密な言語セマンティクスが守られていない場合に警告します。</span><span class="sxs-lookup"><span data-stu-id="b1cba-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1cba-114">コメント</span><span class="sxs-lookup"><span data-stu-id="b1cba-114">Remarks</span></span>  
 <span data-ttu-id="b1cba-115">@No__t-0 が有効な場合は、拡張型の変換のみを暗黙的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b1cba-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="b1cba-116">整数型のオブジェクトへの @no__t 0 型オブジェクトの割り当てなど、暗黙的な縮小型変換は、エラーとして報告されます。</span><span class="sxs-lookup"><span data-stu-id="b1cba-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="b1cba-117">暗黙的な縮小の型変換に関する警告を生成するには、`-optionstrict:custom` を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1cba-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="b1cba-118">@No__t-0 を使用して特定の警告を無視し、`-warnaserror:numberlist` を使用すると、特定の警告をエラーとして扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="b1cba-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="b1cba-119">Visual Studio IDE で-optionstrict を設定するには</span><span class="sxs-lookup"><span data-stu-id="b1cba-119">To set -optionstrict in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="b1cba-120">**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1cba-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b1cba-121">**プロジェクト** メニューの プロパティ をクリックし**ます。**</span><span class="sxs-lookup"><span data-stu-id="b1cba-121">On the **Project** menu, click **Properties.**</span></span>   
  
2. <span data-ttu-id="b1cba-122">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1cba-122">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="b1cba-123">**[Option Strict]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="b1cba-123">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="b1cba-124">プログラムによって-optionstrict を設定するには</span><span class="sxs-lookup"><span data-stu-id="b1cba-124">To set -optionstrict programmatically</span></span>  
  
- <span data-ttu-id="b1cba-125">「 [Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1cba-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1cba-126">例</span><span class="sxs-lookup"><span data-stu-id="b1cba-126">Example</span></span>  
 <span data-ttu-id="b1cba-127">次のコードは、厳密な型のセマンティクスを使用して `Test.vb` をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="b1cba-127">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1cba-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1cba-128">See also</span></span>

- [<span data-ttu-id="b1cba-129">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="b1cba-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b1cba-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="b1cba-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="b1cba-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="b1cba-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="b1cba-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="b1cba-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="b1cba-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="b1cba-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="b1cba-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1cba-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="b1cba-135">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="b1cba-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="b1cba-136">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="b1cba-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- <span data-ttu-id="b1cba-137">[[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト])](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="b1cba-137">[Visual Basic Defaults, Projects, Options Dialog Box](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
