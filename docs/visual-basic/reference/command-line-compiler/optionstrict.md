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
ms.openlocfilehash: 469e22aef9d746fc55e04ba884d17d60d8baa85a
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583076"
---
# <a name="-optionstrict"></a><span data-ttu-id="73d65-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="73d65-102">-optionstrict</span></span>

<span data-ttu-id="73d65-103">厳密な型のセマンティクスを適用して、暗黙的な型変換を制限します。</span><span class="sxs-lookup"><span data-stu-id="73d65-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>

## <a name="syntax"></a><span data-ttu-id="73d65-104">構文</span><span class="sxs-lookup"><span data-stu-id="73d65-104">Syntax</span></span>

```console
-optionstrict[+ | -]
-optionstrict[:custom]
```

## <a name="arguments"></a><span data-ttu-id="73d65-105">引数</span><span class="sxs-lookup"><span data-stu-id="73d65-105">Arguments</span></span>

<span data-ttu-id="73d65-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="73d65-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="73d65-107">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="73d65-107">Optional.</span></span> <span data-ttu-id="73d65-108">@No__t_0 オプションは、暗黙的な型変換を制限します。</span><span class="sxs-lookup"><span data-stu-id="73d65-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="73d65-109">このオプションの既定値は `-optionstrict-` です。</span><span class="sxs-lookup"><span data-stu-id="73d65-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="73d65-110">@No__t_0 オプションは `-optionstrict` と同じです。</span><span class="sxs-lookup"><span data-stu-id="73d65-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="73d65-111">寛容な型指定規則では、どちらも使用できます。</span><span class="sxs-lookup"><span data-stu-id="73d65-111">You can use both for permissive type semantics.</span></span>

`custom`  
<span data-ttu-id="73d65-112">必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="73d65-112">Required.</span></span> <span data-ttu-id="73d65-113">厳密な言語規則が守られていない場合に警告します。</span><span class="sxs-lookup"><span data-stu-id="73d65-113">Warn when strict language semantics are not respected.</span></span>

## <a name="remarks"></a><span data-ttu-id="73d65-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="73d65-114">Remarks</span></span>

<span data-ttu-id="73d65-115">@No__t_0 が有効な場合は、拡張型の変換のみを暗黙的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="73d65-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="73d65-116">10 進型 (`Decimal`) のオブジェクトを整数型(`Integer`) のオブジェクトに代入するなど、縮小による暗黙の型変換はエラーとして報告されます。</span><span class="sxs-lookup"><span data-stu-id="73d65-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>

<span data-ttu-id="73d65-117">暗黙の縮小変換で警告を生成するには、`-optionstrict:custom` を使用します。</span><span class="sxs-lookup"><span data-stu-id="73d65-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="73d65-118">特定の警告を無視し、特定の警告をエラーとして扱う `-warnaserror:numberlist` には、`-nowarn:numberlist` を使用します。</span><span class="sxs-lookup"><span data-stu-id="73d65-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>

### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="73d65-119">Visual Studio IDE で-optionstrict を設定するには</span><span class="sxs-lookup"><span data-stu-id="73d65-119">To set -optionstrict in the Visual Studio IDE</span></span>

1. <span data-ttu-id="73d65-120">**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="73d65-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="73d65-121">**プロジェクト** メニューの プロパティ をクリックし**ます。**</span><span class="sxs-lookup"><span data-stu-id="73d65-121">On the **Project** menu, click **Properties.**</span></span>

2. <span data-ttu-id="73d65-122">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="73d65-122">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="73d65-123">**[Option Strict]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="73d65-123">Modify the value in the **Option Strict** box.</span></span>

### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="73d65-124">プログラムによって-optionstrict を設定するには</span><span class="sxs-lookup"><span data-stu-id="73d65-124">To set -optionstrict programmatically</span></span>

<span data-ttu-id="73d65-125">「[Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73d65-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="73d65-126">例</span><span class="sxs-lookup"><span data-stu-id="73d65-126">Example</span></span>

<span data-ttu-id="73d65-127">次のコードは、厳密な型のセマンティクスを使用して `Test.vb` をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="73d65-127">The following code compiles `Test.vb` using strict type semantics.</span></span>

```console
vbc -optionstrict+ test.vb
```

## <a name="see-also"></a><span data-ttu-id="73d65-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="73d65-128">See also</span></span>

- [<span data-ttu-id="73d65-129">Visual Basic コマンドラインコンパイラ</span><span class="sxs-lookup"><span data-stu-id="73d65-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="73d65-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="73d65-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="73d65-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="73d65-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="73d65-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="73d65-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="73d65-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="73d65-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="73d65-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73d65-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="73d65-135">コンパイルコマンドラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="73d65-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="73d65-136">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="73d65-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- <span data-ttu-id="73d65-137">[[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト])](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="73d65-137">[Visual Basic Defaults, Projects, Options Dialog Box](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
