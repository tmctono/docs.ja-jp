---
title: コンパイラ ディレクティブ
description: 言語プリF#プロセッサディレクティブ、条件付きコンパイルディレクティブ、行ディレクティブ、およびコンパイラディレクティブについて説明します。
ms.date: 12/10/2018
ms.openlocfilehash: 16db2efb2fee2c2c5e94aa98eb0a13183a4e0e0b
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630403"
---
# <a name="compiler-directives"></a><span data-ttu-id="e25da-103">コンパイラ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="e25da-103">Compiler Directives</span></span>

<span data-ttu-id="e25da-104">このトピックでは、プロセッサ ディレクティブとコンパイラ ディレクティブについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e25da-104">This topic describes processor directives and compiler directives.</span></span>

## <a name="preprocessor-directives"></a><span data-ttu-id="e25da-105">プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="e25da-105">Preprocessor Directives</span></span>

<span data-ttu-id="e25da-106">プリプロセッサ ディレクティブは、# シンボルで始まり、独立した行に記述されます。</span><span class="sxs-lookup"><span data-stu-id="e25da-106">A preprocessor directive is prefixed with the # symbol and appears on a line by itself.</span></span> <span data-ttu-id="e25da-107">プリプロセッサ ディレクティブは、コンパイラ自体の前に実行されるプリプロセッサにより解釈されます。</span><span class="sxs-lookup"><span data-stu-id="e25da-107">It is interpreted by the preprocessor, which runs before the compiler itself.</span></span>

<span data-ttu-id="e25da-108">次の表に、F# で使用できるプリプロセッサ ディレクティブの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e25da-108">The following table lists the preprocessor directives that are available in F#.</span></span>

|<span data-ttu-id="e25da-109">ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="e25da-109">Directive</span></span>|<span data-ttu-id="e25da-110">説明</span><span class="sxs-lookup"><span data-stu-id="e25da-110">Description</span></span>|
|---------|-----------|
|<span data-ttu-id="e25da-111">`#if` *symbol*</span><span class="sxs-lookup"><span data-stu-id="e25da-111">`#if` *symbol*</span></span>|<span data-ttu-id="e25da-112">条件付きコンパイルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e25da-112">Supports conditional compilation.</span></span> <span data-ttu-id="e25da-113">シンボルが定義されて`#if`いる場合、の後にあるセクションのコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e25da-113">Code in the section after the `#if` is included if the *symbol* is defined.</span></span> <span data-ttu-id="e25da-114">記号は、で`!`否定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e25da-114">The symbol can also be negated with `!`.</span></span>|
|`#else`|<span data-ttu-id="e25da-115">条件付きコンパイルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e25da-115">Supports conditional compilation.</span></span> <span data-ttu-id="e25da-116">前の `#if` で使用したシンボルが定義されていない場合に含めるコードのセクションをマークします。</span><span class="sxs-lookup"><span data-stu-id="e25da-116">Marks a section of code to include if the symbol used with the previous `#if` is not defined.</span></span>|
|`#endif`|<span data-ttu-id="e25da-117">条件付きコンパイルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e25da-117">Supports conditional compilation.</span></span> <span data-ttu-id="e25da-118">コードの条件付きセクションの末尾をマークします。</span><span class="sxs-lookup"><span data-stu-id="e25da-118">Marks the end of a conditional section of code.</span></span>|
|<span data-ttu-id="e25da-119">`#`直線*int*、</span><span class="sxs-lookup"><span data-stu-id="e25da-119">`#`[line] *int*,</span></span><br/><span data-ttu-id="e25da-120">`#`[line] *int* *string*,</span><span class="sxs-lookup"><span data-stu-id="e25da-120">`#`[line] *int* *string*,</span></span><br/><span data-ttu-id="e25da-121">`#`[line] *int* *verbatim-string*</span><span class="sxs-lookup"><span data-stu-id="e25da-121">`#`[line] *int* *verbatim-string*</span></span>|<span data-ttu-id="e25da-122">デバッグ用に、元のソース コードの行とファイル名を示します。</span><span class="sxs-lookup"><span data-stu-id="e25da-122">Indicates the original source code line and file name, for debugging.</span></span> <span data-ttu-id="e25da-123">この機能は、F# ソース コードを生成するツール用に用意されています。</span><span class="sxs-lookup"><span data-stu-id="e25da-123">This feature is provided for tools that generate F# source code.</span></span>|
|<span data-ttu-id="e25da-124">`#nowarn` *warningcode*</span><span class="sxs-lookup"><span data-stu-id="e25da-124">`#nowarn` *warningcode*</span></span>|<span data-ttu-id="e25da-125">コンパイラ警告を無効にします。</span><span class="sxs-lookup"><span data-stu-id="e25da-125">Disables a compiler warning or warnings.</span></span> <span data-ttu-id="e25da-126">警告を無効にするには、コンパイラ出力で警告の番号を確認し、その番号を引用符で囲んで指定します。</span><span class="sxs-lookup"><span data-stu-id="e25da-126">To disable a warning, find its number from the compiler output and include it in quotation marks.</span></span> <span data-ttu-id="e25da-127">"FS" プレフィックスを省略します。</span><span class="sxs-lookup"><span data-stu-id="e25da-127">Omit the "FS" prefix.</span></span> <span data-ttu-id="e25da-128">1 つの行で複数の警告番号を無効にするには、それぞれの番号を引用符で囲んだうえで各文字列をスペースで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e25da-128">To disable multiple warning numbers on the same line, include each number in quotation marks, and separate each string by a space.</span></span> <span data-ttu-id="e25da-129">例:</span><span class="sxs-lookup"><span data-stu-id="e25da-129">For example:</span></span>

`#nowarn "9" "40"`

<span data-ttu-id="e25da-130">警告を無効にした場合の影響は、ファイル全体 (ディレクティブの前にあるファイルの部分を含む) に適用されます |。</span><span class="sxs-lookup"><span data-stu-id="e25da-130">The effect of disabling a warning applies to the entire file, including portions of the file that precede the directive.|</span></span>

## <a name="conditional-compilation-directives"></a><span data-ttu-id="e25da-131">条件付きコンパイル ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="e25da-131">Conditional Compilation Directives</span></span>

<span data-ttu-id="e25da-132">これらのディレクティブのいずれかによって非アクティブ化されたコードは、Visual Studio Code エディターでは淡色表示になります。</span><span class="sxs-lookup"><span data-stu-id="e25da-132">Code that is deactivated by one of these directives appears dimmed in the Visual Studio Code Editor.</span></span>

> [!NOTE]
> <span data-ttu-id="e25da-133">条件付きコンパイル ディレクティブの動作は、他の言語と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="e25da-133">The behavior of the conditional compilation directives is not the same as it is in other languages.</span></span> <span data-ttu-id="e25da-134">たとえば、シンボルを含むブール式を使用することはできません。また、`true` および `false` には特別な意味はありません。</span><span class="sxs-lookup"><span data-stu-id="e25da-134">For example, you cannot use Boolean expressions involving symbols, and `true` and `false` have no special meaning.</span></span> <span data-ttu-id="e25da-135">`if` ディレクティブで使用するシンボルは、コマンド ラインまたはプロジェクト設定で定義する必要があります。`define` プリプロセッサ ディレクティブは存在しません。</span><span class="sxs-lookup"><span data-stu-id="e25da-135">Symbols that you use in the `if` directive must be defined by the command line or in the project settings; there is no `define` preprocessor directive.</span></span>

<span data-ttu-id="e25da-136">次のコードは、`#if` ディレクティブ、`#else` ディレクティブ、および `#endif` ディレクティブの使用例を示しています。</span><span class="sxs-lookup"><span data-stu-id="e25da-136">The following code illustrates the use of the `#if`, `#else`, and `#endif` directives.</span></span> <span data-ttu-id="e25da-137">この例では、`function1` の定義の 2 つのバージョンがコードに含まれています。</span><span class="sxs-lookup"><span data-stu-id="e25da-137">In this example, the code contains two versions of the definition of `function1`.</span></span> <span data-ttu-id="e25da-138">[-Define コンパイラオプション](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04)を使用してを定義すると`#if` `VERSION1` 、ディレクティブと`#else`ディレクティブの間のコードがアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="e25da-138">When `VERSION1` is defined by using the [-define compiler option](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04), the code between the `#if` directive and the `#else` directive is activated.</span></span> <span data-ttu-id="e25da-139">それ以外の場合、`#else` と `#endif` の間にあるコードがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="e25da-139">Otherwise, the code between `#else` and `#endif` is activated.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7301.fs)]

<span data-ttu-id="e25da-140">F# には、`#define` プリプロセッサ ディレクティブはありません。</span><span class="sxs-lookup"><span data-stu-id="e25da-140">There is no `#define` preprocessor directive in F#.</span></span> <span data-ttu-id="e25da-141">`#if` ディレクティブで使用するシンボルを定義するには、コンパイラ オプションまたはプロジェクト設定を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e25da-141">You must use the compiler option or project settings to define the symbols used by the `#if` directive.</span></span>

<span data-ttu-id="e25da-142">条件付きコンパイル ディレクティブは、入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e25da-142">Conditional compilation directives can be nested.</span></span> <span data-ttu-id="e25da-143">プリプロセッサ ディレクティブでは、インデントに意味はありません。</span><span class="sxs-lookup"><span data-stu-id="e25da-143">Indentation is not significant for preprocessor directives.</span></span>

<span data-ttu-id="e25da-144">また、シンボルをで`!`反転させることもできます。</span><span class="sxs-lookup"><span data-stu-id="e25da-144">You can also negate a symbol with `!`.</span></span> <span data-ttu-id="e25da-145">この例では、文字列の値は、デバッグ_されていない_場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="e25da-145">In this example, a string's value is something only when _not_ debugging:</span></span>

```fsharp
#if !DEBUG
let str = "Not debugging!"
#else
let str = "Debugging!"
#endif
```

## <a name="line-directives"></a><span data-ttu-id="e25da-146">行ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="e25da-146">Line Directives</span></span>

<span data-ttu-id="e25da-147">ビルド時にコンパイラは、各エラーが発生した行番号を参照して、F# コード内のエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="e25da-147">When building, the compiler reports errors in F# code by referencing line numbers on which each error occurs.</span></span> <span data-ttu-id="e25da-148">これらの行番号は、ファイル内の最初の行から 1 で始まります。</span><span class="sxs-lookup"><span data-stu-id="e25da-148">These line numbers start at 1 for the first line in a file.</span></span> <span data-ttu-id="e25da-149">ただし、別のツールから F# ソース コードを生成している場合、生成されたコードの行番号は、通常、重要ではありません。これは、生成された F# コード内のエラーは、別のソースから発生する可能性が高いためです。</span><span class="sxs-lookup"><span data-stu-id="e25da-149">However, if you are generating F# source code from another tool, the line numbers in the generated code are generally not of interest, because the errors in the generated F# code most likely arise from another source.</span></span> <span data-ttu-id="e25da-150">`#line` ディレクティブを使用すると、F# ソース コードを生成するツールの作成者が、元の行番号およびソース ファイルに関する情報を、生成された F# コードに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="e25da-150">The `#line` directive provides a way for authors of tools that generate F# source code to pass information about the original line numbers and source files to the generated F# code.</span></span>

<span data-ttu-id="e25da-151">`#line` ディレクティブを使用する場合、ファイル名を引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e25da-151">When you use the `#line` directive, file names must be enclosed in quotation marks.</span></span> <span data-ttu-id="e25da-152">パスでバックスラッシュ文字を使用するには、文字列の前に逐語的トークン (`@`) がある場合を除き、バックスラッシュ文字をエスケープする必要があります。エスケープするには、バックスラッシュ文字を 1 つではなく、2 つ使用します。</span><span class="sxs-lookup"><span data-stu-id="e25da-152">Unless the verbatim token (`@`) appears in front of the string, you must escape backslash characters by using two backslash characters instead of one in order to use them in the path.</span></span> <span data-ttu-id="e25da-153">有効な行トークンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e25da-153">The following are valid line tokens.</span></span> <span data-ttu-id="e25da-154">これらの例では、ツールを使用して元のファイル `Script1` を実行したときに F# コード ファイルが自動生成され、これらのディレクティブがある位置のコードが `Script1` ファイルの 25 行目のトークンから生成されるものと仮定します。</span><span class="sxs-lookup"><span data-stu-id="e25da-154">In these examples, assume that the original file `Script1` results in an automatically generated F# code file when it is run through a tool, and that the code at the location of these directives is generated from some tokens at line 25 in file `Script1`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7303.fs)]

<span data-ttu-id="e25da-155">これらのトークンは、この場所で生成された F# コードが、`Script1` 内の行 `25` またはその近くにあるなんらかの構成要素から派生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="e25da-155">These tokens indicate that the F# code generated at this location is derived from some constructs at or near line `25` in `Script1`.</span></span>

## <a name="compiler-directives"></a><span data-ttu-id="e25da-156">コンパイラ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="e25da-156">Compiler Directives</span></span>

<span data-ttu-id="e25da-157">コンパイラ ディレクティブは、# 記号で始まるという点でプリプロセッサ ディレクティブに似ていますが、プリプロセッサが解釈するのではなく、コンパイラが解釈して対応できるように放置されます。</span><span class="sxs-lookup"><span data-stu-id="e25da-157">Compiler directives resemble preprocessor directives, because they are prefixed with a # sign, but instead of being interpreted by the preprocessor, they are left for the compiler to interpret and act on.</span></span>

<span data-ttu-id="e25da-158">次の表に、F# で使用できるコンパイラ ディレクティブの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e25da-158">The following table lists the compiler directive that is available in F#.</span></span>

|<span data-ttu-id="e25da-159">ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="e25da-159">Directive</span></span>|<span data-ttu-id="e25da-160">説明</span><span class="sxs-lookup"><span data-stu-id="e25da-160">Description</span></span>|
|---------|-----------|
|<span data-ttu-id="e25da-161">`#light` ["on"&#124;"off"]</span><span class="sxs-lookup"><span data-stu-id="e25da-161">`#light` ["on"&#124;"off"]</span></span>|<span data-ttu-id="e25da-162">他のバージョンの ML との互換性を保つために、軽量構文を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="e25da-162">Enables or disables lightweight syntax, for compatibility with other versions of ML.</span></span> <span data-ttu-id="e25da-163">既定では、軽量構文は有効です。</span><span class="sxs-lookup"><span data-stu-id="e25da-163">By default, lightweight syntax is enabled.</span></span> <span data-ttu-id="e25da-164">冗語構文は常に有効です。</span><span class="sxs-lookup"><span data-stu-id="e25da-164">Verbose syntax is always enabled.</span></span> <span data-ttu-id="e25da-165">したがって、軽量構文と冗語構文の両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e25da-165">Therefore, you can use both lightweight syntax and verbose syntax.</span></span> <span data-ttu-id="e25da-166">ディレクティブ `#light` は `#light "on"` と同等です。</span><span class="sxs-lookup"><span data-stu-id="e25da-166">The directive `#light` by itself is equivalent to `#light "on"`.</span></span> <span data-ttu-id="e25da-167">`#light "off"` を指定した場合は、すべての言語構成要素に冗語構文を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e25da-167">If you specify `#light "off"`, you must use verbose syntax for all language constructs.</span></span> <span data-ttu-id="e25da-168">F# のドキュメント内の構文は、軽量構文の使用を前提として記述されています。</span><span class="sxs-lookup"><span data-stu-id="e25da-168">Syntax in the documentation for F# is presented with the assumption that you are using lightweight syntax.</span></span> <span data-ttu-id="e25da-169">詳細については、「 [Verbose 構文](verbose-syntax.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e25da-169">For more information, see [Verbose Syntax](verbose-syntax.md).</span></span>|

<span data-ttu-id="e25da-170">インタープリター (fsi.exe) ディレクティブでは、[F# を使用した対話型プログラミング](../tutorials/fsharp-interactive/index.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e25da-170">For interpreter (fsi.exe) directives, see [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e25da-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="e25da-171">See also</span></span>

- [<span data-ttu-id="e25da-172">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="e25da-172">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="e25da-173">コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="e25da-173">Compiler Options</span></span>](compiler-options.md)
