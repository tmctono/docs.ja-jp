---
title: 対話形式のオプション
description: F# インタラクティブ、fsi.exe でサポートされているコマンドラインオプションについて説明します。
ms.date: 08/15/2020
ms.openlocfilehash: da2251c1d2e57090ed926e501cebf3c53ac58052
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558609"
---
# <a name="f-interactive-options"></a><span data-ttu-id="b29c7-103">F# インタラクティブオプション</span><span class="sxs-lookup"><span data-stu-id="b29c7-103">F# Interactive options</span></span>

<span data-ttu-id="b29c7-104">この記事では F# インタラクティブでサポートされるコマンドラインオプションについて説明し `fsi.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-104">This article describes the command-line options supported by F# Interactive, `fsi.exe`.</span></span> <span data-ttu-id="b29c7-105">F# インタラクティブは、F # コンパイラと同じコマンドラインオプションの多くを受け入れますが、いくつかの追加オプションも受け入れます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-105">F# Interactive accepts many of the same command-line options as the F# compiler, but also accepts some additional options.</span></span>

## <a name="use-f-interactive-for-scripting"></a><span data-ttu-id="b29c7-106">スクリプトに F# インタラクティブを使用する</span><span class="sxs-lookup"><span data-stu-id="b29c7-106">Use F# Interactive for scripting</span></span>

<span data-ttu-id="b29c7-107">F# インタラクティブ、は `dotnet fsi` 対話形式で起動できます。また、コマンドラインから起動してスクリプトを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-107">F# Interactive, `dotnet fsi`, can be launched interactively, or it can be launched from the command line to run a script.</span></span> <span data-ttu-id="b29c7-108">コマンドラインの構文はです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-108">The command-line syntax is</span></span>

```dotnetcli
dotnet fsi [options] [ script-file [arguments] ]
```

<span data-ttu-id="b29c7-109">F# スクリプト ファイルのファイル拡張子は `.fsx` です。</span><span class="sxs-lookup"><span data-stu-id="b29c7-109">The file extension for F# script files is `.fsx`.</span></span>

## <a name="table-of-f-interactive-options"></a><span data-ttu-id="b29c7-110">F# Interactive のオプションの表</span><span class="sxs-lookup"><span data-stu-id="b29c7-110">Table of F# Interactive Options</span></span>

<span data-ttu-id="b29c7-111">次の表は、F# Interactive でサポートされるオプションの一覧です。</span><span class="sxs-lookup"><span data-stu-id="b29c7-111">The following table summarizes the options supported by F# Interactive.</span></span> <span data-ttu-id="b29c7-112">これらのオプションは、コマンドラインまたは Visual Studio IDE を使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-112">You can set these options on the command line or through the Visual Studio IDE.</span></span> <span data-ttu-id="b29c7-113">Visual Studio IDE でこれらのオプションを設定するには、[ **ツール** ] メニューを開き、[ **オプション**] を選択し、[ **F # ツール** ] ノードを展開して、[ **F# インタラクティブ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-113">To set these options in the Visual Studio IDE, open the **Tools** menu, select **Options**, expand the **F# Tools** node, and then select **F# Interactive**.</span></span>

<span data-ttu-id="b29c7-114">F# Interactive オプションの引数でリストを指定する場合は、リストの要素をセミコロン (`;`) で区切ります。</span><span class="sxs-lookup"><span data-stu-id="b29c7-114">Where lists appear in F# Interactive option arguments, list elements are separated by semicolons (`;`).</span></span>

|<span data-ttu-id="b29c7-115">オプション</span><span class="sxs-lookup"><span data-stu-id="b29c7-115">Option</span></span>|<span data-ttu-id="b29c7-116">説明</span><span class="sxs-lookup"><span data-stu-id="b29c7-116">Description</span></span>|
|------|-----------|
|**--**|<span data-ttu-id="b29c7-117">残りの引数をコマンドライン引数として F # プログラムまたはスクリプトに F# インタラクティブように指示するために使用されます。これは、 **fsi.exe**リストを使用してコード内でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-117">Used to instruct F# Interactive to treat remaining arguments as command-line arguments to the F# program or script, which you can access in code by using the list **fsi.CommandLineArgs**.</span></span>|
|<span data-ttu-id="b29c7-118">**--checked**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b29c7-118">**--checked**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b29c7-119">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-119">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-120">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-120">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b29c7-121">**--codepage: &lt; int&gt;**</span><span class="sxs-lookup"><span data-stu-id="b29c7-121">**--codepage:&lt;int&gt;**</span></span>|<span data-ttu-id="b29c7-122">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-122">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-123">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-123">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b29c7-124">**--consolecolors**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b29c7-124">**--consolecolors**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b29c7-125">警告およびエラーメッセージを色で出力します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-125">Outputs warning and error messages in color.</span></span>|
|<span data-ttu-id="b29c7-126">**--クロス最適化**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b29c7-126">**--crossoptimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b29c7-127">モジュール間の最適化を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="b29c7-127">Enable or disable cross-module optimizations.</span></span>|
|<span data-ttu-id="b29c7-128">**--debug**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b29c7-128">**--debug**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="b29c7-129">**--debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span><span class="sxs-lookup"><span data-stu-id="b29c7-129">**--debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span><br /><br /><span data-ttu-id="b29c7-130">**-g**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b29c7-130">**-g**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="b29c7-131">**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span><span class="sxs-lookup"><span data-stu-id="b29c7-131">**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span>|<span data-ttu-id="b29c7-132">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-132">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-133">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-133">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b29c7-134">**--define: &lt; 文字列&gt;**</span><span class="sxs-lookup"><span data-stu-id="b29c7-134">**--define:&lt;string&gt;**</span></span>|<span data-ttu-id="b29c7-135">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-135">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-136">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-136">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b29c7-137">**--決定的**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b29c7-137">**--deterministic**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b29c7-138">決定的なアセンブリ (モジュールのバージョン GUID とタイムスタンプを含む) を生成します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-138">Produces a deterministic assembly (including module version GUID and timestamp).</span></span>|
|<span data-ttu-id="b29c7-139">**--exec**</span><span class="sxs-lookup"><span data-stu-id="b29c7-139">**--exec**</span></span>|<span data-ttu-id="b29c7-140">ファイルを読み込んだ後、またはコマンド ラインで指定したスクリプトを実行した後に F# Interactive を終了するように指示します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-140">Instructs F# interactive to exit after loading the files or running the script file given on the command line.</span></span>|
|<span data-ttu-id="b29c7-141">**--fullpaths**</span><span class="sxs-lookup"><span data-stu-id="b29c7-141">**--fullpaths**</span></span>|<span data-ttu-id="b29c7-142">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-142">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-143">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-143">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b29c7-144">**--gui**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b29c7-144">**--gui**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b29c7-145">Windows フォーム イベントのループを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="b29c7-145">Enables or disables the Windows Forms event loop.</span></span> <span data-ttu-id="b29c7-146">既定値は有効です。</span><span class="sxs-lookup"><span data-stu-id="b29c7-146">The default is enabled.</span></span>|
|<span data-ttu-id="b29c7-147">**--help**</span><span class="sxs-lookup"><span data-stu-id="b29c7-147">**--help**</span></span><br /><br /><span data-ttu-id="b29c7-148">**-?**</span><span class="sxs-lookup"><span data-stu-id="b29c7-148">**-?**</span></span>|<span data-ttu-id="b29c7-149">コマンドライン構文と各オプションの簡単な説明を表示するために使用します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-149">Used to display the command-line syntax and a brief description of each option.</span></span>|
|<span data-ttu-id="b29c7-150">**--lib: &lt; フォルダー一覧&gt;**</span><span class="sxs-lookup"><span data-stu-id="b29c7-150">**--lib:&lt;folder-list&gt;**</span></span><br /><br /><span data-ttu-id="b29c7-151">**-I: &lt; フォルダー一覧&gt;**</span><span class="sxs-lookup"><span data-stu-id="b29c7-151">**-I:&lt;folder-list&gt;**</span></span>|<span data-ttu-id="b29c7-152">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-152">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-153">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-153">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b29c7-154">**--load: &lt; ファイル名&gt;**</span><span class="sxs-lookup"><span data-stu-id="b29c7-154">**--load:&lt;filename&gt;**</span></span>|<span data-ttu-id="b29c7-155">指定したソース コードを起動時にコンパイルし、コンパイルされた F# の構成要素をセッションに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-155">Compiles the given source code at startup and loads the compiled F# constructs into the session.</span></span>|
|<span data-ttu-id="b29c7-156">**--mlcompatibility**</span><span class="sxs-lookup"><span data-stu-id="b29c7-156">**--mlcompatibility**</span></span>|<span data-ttu-id="b29c7-157">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-157">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-158">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-158">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b29c7-159">**--noframework**</span><span class="sxs-lookup"><span data-stu-id="b29c7-159">**--noframework**</span></span>|<span data-ttu-id="b29c7-160">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-160">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-161">詳細については、「[コンパイラオプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-161">For more information, see [Compiler Options](compiler-options.md)</span></span>|
|<span data-ttu-id="b29c7-162">**--nologo**</span><span class="sxs-lookup"><span data-stu-id="b29c7-162">**--nologo**</span></span>|<span data-ttu-id="b29c7-163">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-163">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-164">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-164">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b29c7-165">**--nowarn: &lt; warning-list&gt;**</span><span class="sxs-lookup"><span data-stu-id="b29c7-165">**--nowarn:&lt;warning-list&gt;**</span></span>|<span data-ttu-id="b29c7-166">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-166">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-167">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-167">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b29c7-168">**--optimize**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b29c7-168">**--optimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b29c7-169">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-169">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-170">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-170">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b29c7-171">**--preferreduilang: &lt; lang&gt;**</span><span class="sxs-lookup"><span data-stu-id="b29c7-171">**--preferreduilang:&lt;lang&gt;**</span></span>| <span data-ttu-id="b29c7-172">優先する出力言語のカルチャ名を指定します (例: es、ja-jp)。</span><span class="sxs-lookup"><span data-stu-id="b29c7-172">Specifies the preferred output language culture name (for example, es-ES, ja-JP).</span></span> |
|<span data-ttu-id="b29c7-173">**--quiet**</span><span class="sxs-lookup"><span data-stu-id="b29c7-173">**--quiet**</span></span>|<span data-ttu-id="b29c7-174">**Stdout**ストリームへの F# インタラクティブの出力を抑制します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-174">Suppress F# Interactive's output to the **stdout** stream.</span></span>|
|<span data-ttu-id="b29c7-175">**--引用符-デバッグ**</span><span class="sxs-lookup"><span data-stu-id="b29c7-175">**--quotations-debug**</span></span>|<span data-ttu-id="b29c7-176">追加のデバッグ情報が F# 引用符リテラルとリフレクション定義から派生した式に対して生成されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-176">Specifies that extra debugging information should be emitted for expressions that are derived from F# quotation literals and reflected definitions.</span></span> <span data-ttu-id="b29c7-177">デバッグ情報は F# 式ツリー ノードのカスタム属性に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-177">The debug information is added to the custom attributes of an F# expression tree node.</span></span> <span data-ttu-id="b29c7-178">「 [コード引用符](code-quotations.md) 」と「 [Expr. customattributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-178">See [Code Quotations](code-quotations.md) and [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).</span></span>|
|<span data-ttu-id="b29c7-179">**--readline**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b29c7-179">**--readline**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b29c7-180">対話モードでのタブ補完を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="b29c7-180">Enable or disable tab completion in interactive mode.</span></span>|
|<span data-ttu-id="b29c7-181">**--reference: &lt; ファイル名&gt;**</span><span class="sxs-lookup"><span data-stu-id="b29c7-181">**--reference:&lt;filename&gt;**</span></span><br /><br /><span data-ttu-id="b29c7-182">**-r: &lt; ファイル名&gt;**</span><span class="sxs-lookup"><span data-stu-id="b29c7-182">**-r:&lt;filename&gt;**</span></span>|<span data-ttu-id="b29c7-183">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-183">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-184">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-184">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b29c7-185">**--tail**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b29c7-185">**--tailcalls**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b29c7-186">tail IL 命令の使用を有効または無効にします。有効にすると、スタック フレームが tail 再帰関数で再利用されます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-186">Enable or disable the use of the tail IL instruction, which causes the stack frame to be reused for tail recursive functions.</span></span> <span data-ttu-id="b29c7-187">このオプションは、既定で有効です。</span><span class="sxs-lookup"><span data-stu-id="b29c7-187">This option is enabled by default.</span></span>|
|<span data-ttu-id="b29c7-188">**--targetprofile: &lt; 文字列&gt;**</span><span class="sxs-lookup"><span data-stu-id="b29c7-188">**--targetprofile:&lt;string&gt;**</span></span>|<span data-ttu-id="b29c7-189">このアセンブリのターゲットフレームワークプロファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-189">Specifies target framework profile of this assembly.</span></span> <span data-ttu-id="b29c7-190">有効な値は、`mscorlib`、`netcore`、または `netstandard` です。</span><span class="sxs-lookup"><span data-stu-id="b29c7-190">Valid values are `mscorlib`, `netcore`, or `netstandard`.</span></span> <span data-ttu-id="b29c7-191">既定では、 `mscorlib`です。</span><span class="sxs-lookup"><span data-stu-id="b29c7-191">The default is `mscorlib`.</span></span>|
|<span data-ttu-id="b29c7-192">**--使用: &lt; ファイル名&gt;**</span><span class="sxs-lookup"><span data-stu-id="b29c7-192">**--use:&lt;filename&gt;**</span></span>|<span data-ttu-id="b29c7-193">指定したファイルを起動時に最初の入力として使用するよう、インタープリターに指示します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-193">Tells the interpreter to use the given file on startup as initial input.</span></span>|
|<span data-ttu-id="b29c7-194">**--utf8output**</span><span class="sxs-lookup"><span data-stu-id="b29c7-194">**--utf8output**</span></span>|<span data-ttu-id="b29c7-195">fsc.exe コンパイラ オプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-195">Same as the fsc.exe compiler option.</span></span> <span data-ttu-id="b29c7-196">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-196">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b29c7-197">**--warn: &lt; 警告レベル&gt;**</span><span class="sxs-lookup"><span data-stu-id="b29c7-197">**--warn:&lt;warning-level&gt;**</span></span>|<span data-ttu-id="b29c7-198">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-198">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-199">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-199">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b29c7-200">**--warnaserror**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="b29c7-200">**--warnaserror**[**+**&#124;**-**]</span></span>|<span data-ttu-id="b29c7-201">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-201">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-202">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-202">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="b29c7-203">**--warnaserror**[ **+**&#124;**-** ]:\*\* &lt; int-list &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="b29c7-203">**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**</span></span>|<span data-ttu-id="b29c7-204">**fsc.exe**コンパイラオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-204">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="b29c7-205">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29c7-205">For more information, see [Compiler Options](compiler-options.md).</span></span>|

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="b29c7-206">構造化された印刷の F# インタラクティブ</span><span class="sxs-lookup"><span data-stu-id="b29c7-206">F# Interactive structured printing</span></span>

<span data-ttu-id="b29c7-207">F# インタラクティブ ( `dotnet fsi` ) では、構造化された [プレーンテキストの書式設定](plaintext-formatting.md) を使用して値を報告します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-207">F# Interactive (`dotnet fsi`) uses an extended version of [structured plain text formatting](plaintext-formatting.md) to report values.</span></span>

1. <span data-ttu-id="b29c7-208">プレーンテキスト形式のすべての機能がサポートされて `%A` おり、さらにカスタマイズも可能です。</span><span class="sxs-lookup"><span data-stu-id="b29c7-208">All features of `%A` plain text formatting are supported, and some are additionally customizable.</span></span>

2. <span data-ttu-id="b29c7-209">出力コンソールで色がサポートされている場合、印刷は色分けされます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-209">Printing is colorized if colors are supported by the output console.</span></span>

3. <span data-ttu-id="b29c7-210">文字列を明示的に評価しない限り、表示される文字列の長さに制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-210">A limit is placed on the length of strings shown, unless you explicitly evaluate that string.</span></span>

4. <span data-ttu-id="b29c7-211">ユーザー定義可能な一連の設定は、オブジェクトを介して使用でき `fsi` ます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-211">A set of user-definable settings is available via the `fsi` object.</span></span>

<span data-ttu-id="b29c7-212">報告される値のプレーンテキスト印刷をカスタマイズするために使用できる設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-212">The available settings to customize plain text printing for reported values are:</span></span>

```fsharp
open System.Globalization

fsi.FormatProvider <- CultureInfo("de-DE")  // control the default culture for primitives

fsi.PrintWidth <- 120        // Control the width used for structured printing

fsi.PrintDepth <- 10         // Control the maximum depth of nested printing

fsi.PrintLength <- 10        // Control the length of lists and arrays

fsi.PrintSize <- 100         // Control the maximum overall object count

fsi.ShowProperties <- false  // Control whether properties of .NET objects are shown by default

fsi.ShowIEnumerable <- false // Control whether sequence values are expanded by default

fsi.ShowDeclarationValues <- false // Control whether values are shown for declaration outputs
```

### <a name="customize-with-addprinter-and-addprinttransformer"></a><span data-ttu-id="b29c7-213">およびを使用してカスタマイズする `AddPrinter``AddPrintTransformer`</span><span class="sxs-lookup"><span data-stu-id="b29c7-213">Customize with `AddPrinter` and `AddPrintTransformer`</span></span>

<span data-ttu-id="b29c7-214">およびを使用して F# インタラクティブ出力の印刷をカスタマイズでき `fsi.AddPrinter` `fsi.AddPrintTransformer` ます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-214">Printing in F# Interactive outputs can be customized by using `fsi.AddPrinter` and `fsi.AddPrintTransformer`.</span></span>
<span data-ttu-id="b29c7-215">最初の関数は、オブジェクトの印刷を置き換えるテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-215">The first function gives text to replace the printing of an object.</span></span> <span data-ttu-id="b29c7-216">2番目の関数は、代わりに表示するサロゲートオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-216">The second function returns a surrogate object to display instead.</span></span> <span data-ttu-id="b29c7-217">たとえば、次の F # コードについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-217">For example, consider the following F# code:</span></span>

```fsharp
open System

fsi.AddPrinter<DateTime>(fun dt -> dt.ToString("s"))

type DateAndLabel =
    { Date: DateTime
      Label: string  }

let newYearsDay1999 =
    { Date = DateTime(1999, 1, 1)
      Label = "New Year" }
```

<span data-ttu-id="b29c7-218">F# インタラクティブで例を実行すると、書式設定オプションセットに基づいて出力されます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-218">If you execute the example in F# Interactive, it outputs based on the formatting option set.</span></span> <span data-ttu-id="b29c7-219">この場合、日付と時刻の書式設定に影響します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-219">In this case, it affects the formatting of date and time:</span></span>

```console
type DateAndLabel =
  { Date: DateTime
    Label: string }
val newYearsDay1999 : DateAndLabel = { Date = 1999-01-01T00:00:00
                                       Label = "New Year" }
```

<span data-ttu-id="b29c7-220">`fsi.AddPrintTransformer` を使用して、印刷する代理オブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-220">`fsi.AddPrintTransformer` can be used to give a surrogate object for printing:</span></span>

```fsharp
type MyList(values: int list) =
    member _.Values = values

fsi.AddPrintTransformer(fun (x:MyList) -> box x.Values)

let x = MyList([1..10])
```

<span data-ttu-id="b29c7-221">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-221">This outputs:</span></span>

```console
val x : MyList = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

<span data-ttu-id="b29c7-222">に渡されたトランスフォーマー関数がを `fsi.AddPrintTransformer` 返す場合 `null` 、印刷トランスフォーマーは無視されます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-222">If the transformer function passed to `fsi.AddPrintTransformer` returns `null`, then the print transformer is ignored.</span></span>
<span data-ttu-id="b29c7-223">これは、型で始まる入力値をフィルター処理するために使用でき `obj` ます。</span><span class="sxs-lookup"><span data-stu-id="b29c7-223">This can be used to filter any input value by starting with type `obj`.</span></span>  <span data-ttu-id="b29c7-224">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-224">For example:</span></span>

```fsharp
fsi.AddPrintTransformer(fun (x:obj) ->
    match x with
    | :? string as s when s = "beep" -> box ["quack"; "quack"; "quack"]
    | _ -> null)

let y = "beep"
```

<span data-ttu-id="b29c7-225">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b29c7-225">This outputs:</span></span>

```console
val y : string = ["quack"; "quack"; "quack"]
```

## <a name="related-topics"></a><span data-ttu-id="b29c7-226">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b29c7-226">Related topics</span></span>

|<span data-ttu-id="b29c7-227">Title</span><span class="sxs-lookup"><span data-stu-id="b29c7-227">Title</span></span>|<span data-ttu-id="b29c7-228">説明</span><span class="sxs-lookup"><span data-stu-id="b29c7-228">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="b29c7-229">コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="b29c7-229">Compiler Options</span></span>](compiler-options.md)|<span data-ttu-id="b29c7-230">F # コンパイラ、 **fsc.exe**で使用できるコマンドラインオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b29c7-230">Describes command-line options available for the F# compiler, **fsc.exe**.</span></span>|
