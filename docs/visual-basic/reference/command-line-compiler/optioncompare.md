---
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
ms.openlocfilehash: ac385880f8c13c23dffff67fc2a1ecc5609fd189
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581413"
---
# <a name="-optioncompare"></a><span data-ttu-id="76340-102">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="76340-102">-optioncompare</span></span>

<span data-ttu-id="76340-103">文字列比較の方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="76340-103">Specifies how string comparisons are made.</span></span>

## <a name="syntax"></a><span data-ttu-id="76340-104">構文</span><span class="sxs-lookup"><span data-stu-id="76340-104">Syntax</span></span>

```console
-optioncompare:{binary | text}
```

## <a name="remarks"></a><span data-ttu-id="76340-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="76340-105">Remarks</span></span>

<span data-ttu-id="76340-106">2つの形式のいずれかで `-optioncompare` を指定できます。バイナリ文字列比較を使用する場合は `-optioncompare:binary`、テキスト文字列比較を使用する場合は `-optioncompare:text` です。</span><span class="sxs-lookup"><span data-stu-id="76340-106">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="76340-107">既定では、コンパイラは `-optioncompare:binary` を使用します。</span><span class="sxs-lookup"><span data-stu-id="76340-107">By default, the compiler uses `-optioncompare:binary`.</span></span>

<span data-ttu-id="76340-108">Microsoft Windows では、現在のコードページによってバイナリ並べ替え順序が決定されます。</span><span class="sxs-lookup"><span data-stu-id="76340-108">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="76340-109">一般的なバイナリ並べ替え順序は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="76340-109">A typical binary sort order is as follows:</span></span>

`A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

<span data-ttu-id="76340-110">テキストベースの文字列比較は、システムのロケールによって決定される、大文字と小文字を区別しないテキストの並べ替え順序に基づいています。</span><span class="sxs-lookup"><span data-stu-id="76340-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="76340-111">一般的なテキストの並べ替え順序は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="76340-111">A typical text sort order is as follows:</span></span>

`(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`

### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="76340-112">Visual Studio IDE で-optioncompare を設定するには</span><span class="sxs-lookup"><span data-stu-id="76340-112">To set -optioncompare in the Visual Studio IDE</span></span>

1. <span data-ttu-id="76340-113">**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="76340-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="76340-114">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76340-114">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="76340-115">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="76340-115">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="76340-116">**[オプションの比較]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="76340-116">Modify the value in the **Option Compare** box.</span></span>

### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="76340-117">-Optioncompare プログラムを設定するには</span><span class="sxs-lookup"><span data-stu-id="76340-117">To set -optioncompare programmatically</span></span>

<span data-ttu-id="76340-118">[Option Compare ステートメント](../../../visual-basic/language-reference/statements/option-compare-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76340-118">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="76340-119">例</span><span class="sxs-lookup"><span data-stu-id="76340-119">Example</span></span>

<span data-ttu-id="76340-120">次のコードは `ProjFile.vb` をコンパイルし、バイナリ文字列比較を使用します。</span><span class="sxs-lookup"><span data-stu-id="76340-120">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>

```console
vbc -optioncompare:binary projFile.vb
```

## <a name="see-also"></a><span data-ttu-id="76340-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="76340-121">See also</span></span>

- [<span data-ttu-id="76340-122">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="76340-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="76340-123">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="76340-123">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="76340-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="76340-124">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="76340-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="76340-125">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="76340-126">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="76340-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="76340-127">Option Compare ステートメント</span><span class="sxs-lookup"><span data-stu-id="76340-127">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- <span data-ttu-id="76340-128">[[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト])](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="76340-128">[Visual Basic Defaults, Projects, Options Dialog Box](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
