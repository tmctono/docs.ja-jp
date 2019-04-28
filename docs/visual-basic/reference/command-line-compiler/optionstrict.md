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
ms.openlocfilehash: e18fe451ea4a80ac959ed61b66394920f8bf177f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788935"
---
# <a name="-optionstrict"></a><span data-ttu-id="dbf59-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="dbf59-102">-optionstrict</span></span>
<span data-ttu-id="dbf59-103">暗黙の型変換を制限するための厳密な型のセマンティクスを適用します。</span><span class="sxs-lookup"><span data-stu-id="dbf59-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbf59-104">構文</span><span class="sxs-lookup"><span data-stu-id="dbf59-104">Syntax</span></span>  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="dbf59-105">引数</span><span class="sxs-lookup"><span data-stu-id="dbf59-105">Arguments</span></span>  
 <span data-ttu-id="dbf59-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="dbf59-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="dbf59-107">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="dbf59-107">Optional.</span></span> <span data-ttu-id="dbf59-108">`-optionstrict+`オプションは、暗黙的な型変換を制限します。</span><span class="sxs-lookup"><span data-stu-id="dbf59-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="dbf59-109">このオプションの既定値は`-optionstrict-`します。</span><span class="sxs-lookup"><span data-stu-id="dbf59-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="dbf59-110">`-optionstrict+`オプションは、同じ`-optionstrict`します。</span><span class="sxs-lookup"><span data-stu-id="dbf59-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="dbf59-111">制限の緩やかな型のセマンティクスの両方を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="dbf59-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="dbf59-112">必須。</span><span class="sxs-lookup"><span data-stu-id="dbf59-112">Required.</span></span> <span data-ttu-id="dbf59-113">厳密な言語セマンティクスが守られていない場合に警告します。</span><span class="sxs-lookup"><span data-stu-id="dbf59-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbf59-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="dbf59-114">Remarks</span></span>  
 <span data-ttu-id="dbf59-115">ときに`-optionstrict+`は実際には拡大の唯一の型変換は暗黙的に行われたことができます。</span><span class="sxs-lookup"><span data-stu-id="dbf59-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="dbf59-116">暗黙的な縮小の割り当てなどの型変換を`Decimal`オブジェクトを整数型のオブジェクトを入力、エラーとして報告されます。</span><span class="sxs-lookup"><span data-stu-id="dbf59-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="dbf59-117">暗黙的な縮小の型変換の警告を生成する`-optionstrict:custom`します。</span><span class="sxs-lookup"><span data-stu-id="dbf59-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="dbf59-118">使用`-nowarn:numberlist`特定の警告を無視して`-warnaserror:numberlist`特定の警告をエラーとして処理します。</span><span class="sxs-lookup"><span data-stu-id="dbf59-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="dbf59-119">Visual Studio IDE で-optionstrict を設定するには</span><span class="sxs-lookup"><span data-stu-id="dbf59-119">To set -optionstrict in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="dbf59-120">**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbf59-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="dbf59-121">**プロジェクト** メニューのをクリックして**プロパティ。**</span><span class="sxs-lookup"><span data-stu-id="dbf59-121">On the **Project** menu, click **Properties.**</span></span>   
  
2. <span data-ttu-id="dbf59-122">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbf59-122">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="dbf59-123">値を変更、 **Option Strict**ボックス。</span><span class="sxs-lookup"><span data-stu-id="dbf59-123">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="dbf59-124">-Optionstrict をプログラムで設定するには</span><span class="sxs-lookup"><span data-stu-id="dbf59-124">To set -optionstrict programmatically</span></span>  
  
- <span data-ttu-id="dbf59-125">参照してください[Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="dbf59-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbf59-126">例</span><span class="sxs-lookup"><span data-stu-id="dbf59-126">Example</span></span>  
 <span data-ttu-id="dbf59-127">次のコードのコンパイル`Test.vb`厳密な型のセマンティクスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="dbf59-127">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="dbf59-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbf59-128">See also</span></span>

- [<span data-ttu-id="dbf59-129">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="dbf59-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="dbf59-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="dbf59-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="dbf59-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="dbf59-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="dbf59-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="dbf59-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="dbf59-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="dbf59-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="dbf59-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dbf59-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="dbf59-135">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="dbf59-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="dbf59-136">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="dbf59-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- <span data-ttu-id="dbf59-137">[[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト])](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="dbf59-137">[Visual Basic Defaults, Projects, Options Dialog Box](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
