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
ms.openlocfilehash: 3df7e622f97a5a1291736180e3964b1b3deaea2f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005453"
---
# <a name="-netcf"></a><span data-ttu-id="70f4a-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="70f4a-102">-netcf</span></span>

<span data-ttu-id="70f4a-103">.NET Compact Framework を対象とするようにコンパイラを設定します。</span><span class="sxs-lookup"><span data-stu-id="70f4a-103">Sets the compiler to target the .NET Compact Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="70f4a-104">構文</span><span class="sxs-lookup"><span data-stu-id="70f4a-104">Syntax</span></span>

```console
-netcf
```

## <a name="remarks"></a><span data-ttu-id="70f4a-105">コメント</span><span class="sxs-lookup"><span data-stu-id="70f4a-105">Remarks</span></span>

<span data-ttu-id="70f4a-106">`-netcf` オプションを指定すると、Visual Basic コンパイラは完全な .NET Framework ではなく .NET Compact Framework を対象とします。</span><span class="sxs-lookup"><span data-stu-id="70f4a-106">The `-netcf` option causes the Visual Basic compiler to target the .NET Compact Framework rather than the full .NET Framework.</span></span> <span data-ttu-id="70f4a-107">完全な .NET Framework にのみ存在する言語機能は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="70f4a-107">Language functionality that is present only in the full .NET Framework is disabled.</span></span>

<span data-ttu-id="70f4a-108">`-netcf` オプションは、 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)と共に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="70f4a-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="70f4a-109">`-netcf` によって無効にされた言語機能は、`-sdkpath`の対象となるファイルには存在しないものと同じ言語機能です。</span><span class="sxs-lookup"><span data-stu-id="70f4a-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="70f4a-110">`-netcf` オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="70f4a-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="70f4a-111">`-netcf` オプションは、Visual Basic デバイスプロジェクトが読み込まれるときに設定されます。</span><span class="sxs-lookup"><span data-stu-id="70f4a-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="70f4a-112">`-netcf` オプションは、次の言語機能を変更します。</span><span class="sxs-lookup"><span data-stu-id="70f4a-112">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="70f4a-113">[End \<キーワード > Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md)キーワードは、プログラムの実行を終了しますが、無効になっています。</span><span class="sxs-lookup"><span data-stu-id="70f4a-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="70f4a-114">次のプログラムは `-netcf` せずにコンパイルして実行しますが、コンパイル時に `-netcf`で失敗します。</span><span class="sxs-lookup"><span data-stu-id="70f4a-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="70f4a-115">すべての形式の遅延バインディングは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="70f4a-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="70f4a-116">コンパイル時のエラーは、認識された遅延バインディングのシナリオが検出された場合に生成されます。</span><span class="sxs-lookup"><span data-stu-id="70f4a-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="70f4a-117">次のプログラムは `-netcf` せずにコンパイルして実行しますが、コンパイル時に `-netcf`で失敗します。</span><span class="sxs-lookup"><span data-stu-id="70f4a-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="70f4a-118">[Auto](../../../visual-basic/language-reference/modifiers/auto.md)、 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)、および[Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)の各修飾子は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="70f4a-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="70f4a-119">[Declare statement](../../../visual-basic/language-reference/statements/declare-statement.md)ステートメントの構文も `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`に変更されています。</span><span class="sxs-lookup"><span data-stu-id="70f4a-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="70f4a-120">次のコードは、コンパイル時の `-netcf` の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="70f4a-120">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="70f4a-121">Visual Basic から削除された Visual Basic 6.0 キーワードを使用すると、`-netcf` の使用時に別のエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="70f4a-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="70f4a-122">これは、次のキーワードのエラーメッセージに影響します。</span><span class="sxs-lookup"><span data-stu-id="70f4a-122">This affects the error messages for the following keywords:</span></span>

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

## <a name="example"></a><span data-ttu-id="70f4a-123">例</span><span class="sxs-lookup"><span data-stu-id="70f4a-123">Example</span></span>

<span data-ttu-id="70f4a-124">次のコードでは、C ドライブの .NET Compact Framework の既定のインストールディレクトリにある mscorlib.dll と Microsoft. .dll のバージョンを使用して、.NET Compact Framework で `Myfile.vb` をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="70f4a-124">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="70f4a-125">通常は、最新バージョンの .NET Compact Framework を使用します。</span><span class="sxs-lookup"><span data-stu-id="70f4a-125">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="70f4a-126">参照</span><span class="sxs-lookup"><span data-stu-id="70f4a-126">See also</span></span>

- [<span data-ttu-id="70f4a-127">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="70f4a-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="70f4a-128">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="70f4a-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="70f4a-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="70f4a-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
