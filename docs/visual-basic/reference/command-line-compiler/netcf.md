---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 028fa148d0e5622648a5fdfff1789c3d0bfde057
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268288"
---
# <a name="-netcf"></a><span data-ttu-id="09268-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="09268-102">-netcf</span></span>

<span data-ttu-id="09268-103">.NET Compact Framework を対象とするコンパイラを設定します。</span><span class="sxs-lookup"><span data-stu-id="09268-103">Sets the compiler to target the .NET Compact Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="09268-104">構文</span><span class="sxs-lookup"><span data-stu-id="09268-104">Syntax</span></span>

```
-netcf
```

## <a name="remarks"></a><span data-ttu-id="09268-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="09268-105">Remarks</span></span>

<span data-ttu-id="09268-106">`-netcf`オプションは、完全な .NET Framework ではなく、.NET Compact Framework を対象とする Visual Basic コンパイラ。</span><span class="sxs-lookup"><span data-stu-id="09268-106">The `-netcf` option causes the Visual Basic compiler to target the .NET Compact Framework rather than the full .NET Framework.</span></span> <span data-ttu-id="09268-107">完全な .NET Framework でのみ存在する言語機能は無効です。</span><span class="sxs-lookup"><span data-stu-id="09268-107">Language functionality that is present only in the full .NET Framework is disabled.</span></span>

<span data-ttu-id="09268-108">`-netcf`オプションがと共に使用するように設計[-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)します。</span><span class="sxs-lookup"><span data-stu-id="09268-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="09268-109">無効になっている言語機能`-netcf`同じ言語機能を対象となるファイルに存在しない`-sdkpath`します。</span><span class="sxs-lookup"><span data-stu-id="09268-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="09268-110">`-netcf`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="09268-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="09268-111">`-netcf` Visual Basic プロジェクトのデバイスが読み込まれるときにオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="09268-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="09268-112">`-netcf`オプションは、次の言語機能を変更します。</span><span class="sxs-lookup"><span data-stu-id="09268-112">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="09268-113">[エンド\<キーワード > ステートメント](../../../visual-basic/language-reference/statements/end-keyword-statement.md)キーワードで、プログラムの実行を終了するが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="09268-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="09268-114">次のプログラムをコンパイルして実行なし`-netcf`がコンパイル時にでは失敗`-netcf`します。</span><span class="sxs-lookup"><span data-stu-id="09268-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="09268-115">遅延バインディングするには、すべての形式が無効です。</span><span class="sxs-lookup"><span data-stu-id="09268-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="09268-116">認識される遅延バインディング シナリオが発生した場合に、コンパイル時エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="09268-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="09268-117">次のプログラムをコンパイルして実行なし`-netcf`がコンパイル時にでは失敗`-netcf`します。</span><span class="sxs-lookup"><span data-stu-id="09268-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="09268-118">[自動](../../../visual-basic/language-reference/modifiers/auto.md)、 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)、および[Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)修飾子が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="09268-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="09268-119">構文、 [Declare ステートメント](../../../visual-basic/language-reference/statements/declare-statement.md)ステートメントが変更にも`Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`します。</span><span class="sxs-lookup"><span data-stu-id="09268-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="09268-120">次のコードは、の効果を示しています。 `-netcf` 、コンパイル時にします。</span><span class="sxs-lookup"><span data-stu-id="09268-120">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="09268-121">Visual Basic から削除された Visual Basic 6.0 のキーワードを使用して、別のエラーを生成時に`-netcf`使用されます。</span><span class="sxs-lookup"><span data-stu-id="09268-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="09268-122">これには、次のキーワードのエラー メッセージに影響します。</span><span class="sxs-lookup"><span data-stu-id="09268-122">This affects the error messages for the following keywords:</span></span>

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a><span data-ttu-id="09268-123">例</span><span class="sxs-lookup"><span data-stu-id="09268-123">Example</span></span>

<span data-ttu-id="09268-124">次のコードのコンパイル`Myfile.vb`C ドライブ上の .NET Compact Framework の既定のインストール ディレクトリで見つかった mscorlib.dll および Microsoft.VisualBasic.dll のバージョンを使用して、.NET Compact Framework を使用します。</span><span class="sxs-lookup"><span data-stu-id="09268-124">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="09268-125">通常、.NET Compact Framework の最新バージョンを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="09268-125">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="09268-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="09268-126">See also</span></span>

- [<span data-ttu-id="09268-127">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="09268-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="09268-128">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="09268-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="09268-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="09268-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
