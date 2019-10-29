---
title: Visual Studio Code で F# をはじめる
description: Visual Studio Code および ionide の概要のプラグインのスイートで F# を使用する方法について説明します。
ms.date: 12/23/2018
ms.openlocfilehash: 2fa0518488d37b2130aaba96028ac92dac77eb97
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082984"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="45a36-103">Visual Studio Code で F# をはじめる</span><span class="sxs-lookup"><span data-stu-id="45a36-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="45a36-104">[Ionide プラグイン](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) を使用して [Visual Studio Code](https://code.visualstudio.com)で F# を記述すると、IntelliSense と基本的なコードリファクタリングを使用して、優れたクロスプラットフォームで軽量の統合開発環境 (IDE) エクスペリエンスを実現できます。</span><span class="sxs-lookup"><span data-stu-id="45a36-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="45a36-105">プラグインの詳細については、 [Ionide.io](http://ionide.io) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45a36-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="45a36-106">作業を開始できることを確認します。 [F# および ionide の概要プラグインが正しくインストールされている](install-fsharp.md#install-f-with-visual-studio-code)します。</span><span class="sxs-lookup"><span data-stu-id="45a36-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

> [!NOTE]
> <span data-ttu-id="45a36-107">Ionide は dotnet coreではなく、クロスプラットフォームでの互換性の問題が発生する可能性がある .NET Framework プロジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="45a36-107">Ionide will generate .NET Framework F# projects, not dotnet core, which can have cross-platform compatibility issues.</span></span> <span data-ttu-id="45a36-108">**Linux** または **OSX** を実行している場合は、[コマンドラインツール](get-started-command-line.md)を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="45a36-108">If you are running on **Linux** or **OSX**, a simpler way to get started is to use the [command-line tools](get-started-command-line.md).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="45a36-109">Ionide で最初のプロジェクトを生成する</span><span class="sxs-lookup"><span data-stu-id="45a36-109">Creating your first project with Ionide</span></span>

<span data-ttu-id="45a36-110">新しい F# プロジェクトを作成するには、新しいフォルダーで Visual Studio Code を開きます(任意の名前をつけることができます)。</span><span class="sxs-lookup"><span data-stu-id="45a36-110">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="45a36-111">次に、コマンドパレット (**View > コマンドパレット**) を開き、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="45a36-111">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```console
> F# new project
```

<span data-ttu-id="45a36-112">これは [FORGE](https://github.com/fsharp-editing/Forge) プロジェクトによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="45a36-112">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
> <span data-ttu-id="45a36-113">テンプレートオプションが表示されない場合は、コマンドパレットで次のコマンドを実行して`>F#: Refresh Project Templates`テンプレートを更新してみてください。</span><span class="sxs-lookup"><span data-stu-id="45a36-113">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="45a36-114">F#:**Enter キー**を押して、新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="45a36-114">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="45a36-115">これにより、次の手順に進みます。これは、プロジェクトテンプレートを選択するためのものです。</span><span class="sxs-lookup"><span data-stu-id="45a36-115">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="45a36-116">テンプレートを選択し、 **Enter キー**を押します。 `classlib`</span><span class="sxs-lookup"><span data-stu-id="45a36-116">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="45a36-117">次に、プロジェクトを作成するディレクトリを選択します。</span><span class="sxs-lookup"><span data-stu-id="45a36-117">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="45a36-118">空白のままにすると、現在のディレクトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="45a36-118">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="45a36-119">最後の手順でプロジェクトに名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="45a36-119">Finally, name your project in the final step.</span></span> <span data-ttu-id="45a36-120">F#プロジェクト名として[Pascal](http://c2.com/cgi/wiki?PascalCase)形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="45a36-120">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="45a36-121">この記事で`ClassLibraryDemo`は、を名前として使用します。</span><span class="sxs-lookup"><span data-stu-id="45a36-121">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="45a36-122">プロジェクトに使用する名前を入力したら、 **Enter キー**を押します。</span><span class="sxs-lookup"><span data-stu-id="45a36-122">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="45a36-123">これらの手順に従えば、左側に Visual Studio Code ワークスペースが表示され、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="45a36-123">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="45a36-124">`ClassLibraryDemo`フォルダーの下にある F# プロジェクトそのもの。</span><span class="sxs-lookup"><span data-stu-id="45a36-124">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="45a36-125">[`Paket`](https://fsprojects.github.io/Paket/) を介してパッケージを追加するための正しいディレクトリ構造。</span><span class="sxs-lookup"><span data-stu-id="45a36-125">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="45a36-126">[`FAKE`](https://fsharp.github.io/FAKE/) を使用したクロスプラットフォームのビルドスクリプト。</span><span class="sxs-lookup"><span data-stu-id="45a36-126">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="45a36-127">パッケージをフェッチし、依存関係を解決できる実行可能ファイル。`paket.exe`</span><span class="sxs-lookup"><span data-stu-id="45a36-127">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="45a36-128">このプロジェクトを Git ベースのソース管理に追加する場合は、`.gitignore`ファイル。</span><span class="sxs-lookup"><span data-stu-id="45a36-128">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="45a36-129">コードの記述</span><span class="sxs-lookup"><span data-stu-id="45a36-129">Writing some code</span></span>

<span data-ttu-id="45a36-130">*Classlibrarydemo*フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="45a36-130">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="45a36-131">次のファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45a36-131">You should see the following files:</span></span>

1. <span data-ttu-id="45a36-132">`ClassLibraryDemo.fs`、クラスが定義された F# 実装ファイル。</span><span class="sxs-lookup"><span data-stu-id="45a36-132">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="45a36-133">`ClassLibraryDemo.fsproj`、このプロジェクトをビルドするために使用される F# プロジェクトファイル。</span><span class="sxs-lookup"><span data-stu-id="45a36-133">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="45a36-134">`Script.fsx`、ソース ファイルを読み込む F# スクリプトファイル。</span><span class="sxs-lookup"><span data-stu-id="45a36-134">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="45a36-135">`paket.references`、プロジェクトの依存関係を指定する Packet ファイル。</span><span class="sxs-lookup"><span data-stu-id="45a36-135">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="45a36-136">`Script.fsx`を開き、最後に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="45a36-136">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="45a36-137">この関数は、単語を [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin) 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="45a36-137">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="45a36-138">次の手順では、F# インタラクティブ(FSI) を使用して評価します。</span><span class="sxs-lookup"><span data-stu-id="45a36-138">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="45a36-139">関数全体をハイライト表示します (11 行の長さである必要があります)。</span><span class="sxs-lookup"><span data-stu-id="45a36-139">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="45a36-140">ハイライト表示されたら、 **Alt** キーを押しながら **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="45a36-140">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="45a36-141">下にウィンドウがポップアップ表示され、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="45a36-141">You'll notice a window pop up below, and it should show something like this:</span></span>

![Ionide の概要での F# Interactive の出力例](./media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="45a36-143">これは次の 3 つのことを行いました。</span><span class="sxs-lookup"><span data-stu-id="45a36-143">This did three things:</span></span>

1. <span data-ttu-id="45a36-144">FSI.EXE プロセスを開始しました。</span><span class="sxs-lookup"><span data-stu-id="45a36-144">It started the FSI process.</span></span>
2. <span data-ttu-id="45a36-145">FSI.EXE プロセスでハイライト表示したコードが送信されました。</span><span class="sxs-lookup"><span data-stu-id="45a36-145">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="45a36-146">FSI.EXE プロセスは、送信したコードを評価しました。</span><span class="sxs-lookup"><span data-stu-id="45a36-146">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="45a36-147">送信したのは[関数](../language-reference/functions/index.md)だったので、fsi.exe! を使用してその関数を呼び出すことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="45a36-147">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="45a36-148">対話型ウィンドウで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="45a36-148">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="45a36-149">次の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45a36-149">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="45a36-150">では、母音を最初の文字として試してみましょう。</span><span class="sxs-lookup"><span data-stu-id="45a36-150">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="45a36-151">次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="45a36-151">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="45a36-152">次の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45a36-152">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="45a36-153">関数が期待どおりに動作しているようです。</span><span class="sxs-lookup"><span data-stu-id="45a36-153">The function appears to be working as expected.</span></span> <span data-ttu-id="45a36-154">Visual Studio Code で最初の F# 関数を作成し、FSI で評価しました。</span><span class="sxs-lookup"><span data-stu-id="45a36-154">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="45a36-155">ご存知かもしれませんが、FSI の行は`;;`で終了します。</span><span class="sxs-lookup"><span data-stu-id="45a36-155">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="45a36-156">これは、FSI で複数の行を入力できるためです。</span><span class="sxs-lookup"><span data-stu-id="45a36-156">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="45a36-157">最後`;;`は、コードが終了したことを FSI に知らせます。</span><span class="sxs-lookup"><span data-stu-id="45a36-157">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="45a36-158">コードの説明</span><span class="sxs-lookup"><span data-stu-id="45a36-158">Explaining the code</span></span>

<span data-ttu-id="45a36-159">実際にコードが何をしているかわからない場合は、次のステップで説明します。</span><span class="sxs-lookup"><span data-stu-id="45a36-159">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="45a36-160">ご覧のように、`toPigLatin`は単語を入力として受け取り、その単語を Pig 表現に変換する関数です。</span><span class="sxs-lookup"><span data-stu-id="45a36-160">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="45a36-161">この規則は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="45a36-161">The rules for this are as follows:</span></span>

<span data-ttu-id="45a36-162">単語の最初の文字が母音で始まる場合は、単語の末尾に "yay" を追加します。</span><span class="sxs-lookup"><span data-stu-id="45a36-162">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="45a36-163">母音で始まらない場合は、その最初の文字を単語の末尾に移動し、それに "ay" を追加します。</span><span class="sxs-lookup"><span data-stu-id="45a36-163">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="45a36-164">FSI で以下の行があることに気づいたと思います。</span><span class="sxs-lookup"><span data-stu-id="45a36-164">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="45a36-165">これは、`toPigLatin`が`string`を入力として受け取り (`word`と呼ぶ) 、別の`string`を返す関数であることを示します。</span><span class="sxs-lookup"><span data-stu-id="45a36-165">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="45a36-166">これは[関数の型シグネチャ](https://fsharpforfunandprofit.com/posts/function-signatures/) と呼ばれ、F# の基本的な部分でコードを理解する鍵となるものです。</span><span class="sxs-lookup"><span data-stu-id="45a36-166">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="45a36-167">Visual Studio Code で関数名をクリックした場合もこれが表示されることに気づくと思います。</span><span class="sxs-lookup"><span data-stu-id="45a36-167">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="45a36-168">関数の本体には、次の 2 つの異なる部分があります。</span><span class="sxs-lookup"><span data-stu-id="45a36-168">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="45a36-169">指定した文字 ( `isVowel`) が、指定されたパターン`c`のいずれかと一致するかどうかをチェックすることによって、特定の文字 () が母音であるかどうかを判断する内部[関数。](../language-reference/pattern-matching.md)</span><span class="sxs-lookup"><span data-stu-id="45a36-169">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="45a36-170">最初の文字が母音であるかどうかを確認し、最初の文字が母音であるかどうかに基づいて、入力文字から戻り値を構築する[式。`if..then..else`](../language-reference/conditional-expressions-if-then-else.md)</span><span class="sxs-lookup"><span data-stu-id="45a36-170">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="45a36-171">したがって、 `toPigLatin`のフローは次の通りです。</span><span class="sxs-lookup"><span data-stu-id="45a36-171">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="45a36-172">入力単語の最初の文字が母音であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="45a36-172">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="45a36-173">の場合は、単語の末尾に "yay" を付加します。</span><span class="sxs-lookup"><span data-stu-id="45a36-173">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="45a36-174">それ以外の場合は、最初の文字を単語の末尾に移動し、それに "ay" を追加します。</span><span class="sxs-lookup"><span data-stu-id="45a36-174">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="45a36-175">この点については最後に説明します。他の多くの言語とは異なり、関数から戻る明示的な命令はありません。</span><span class="sxs-lookup"><span data-stu-id="45a36-175">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="45a36-176">これは、 F# が式ベースであり、関数本体の最後の式が戻り値であるためです。</span><span class="sxs-lookup"><span data-stu-id="45a36-176">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="45a36-177">`if..then..else`はそれ自体が式であるため、`then`ブロックの本体または`else`ブロックの本体の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="45a36-177">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="45a36-178">スクリプトコードを実装ファイルへ移動する</span><span class="sxs-lookup"><span data-stu-id="45a36-178">Moving your script code into the implementation file</span></span>

<span data-ttu-id="45a36-179">この記事では、前のセクションには、F# コードの記述の一般的な最初の手順が示されています。 最初の関数の記述と、FSI 使用して対話的に実行します。</span><span class="sxs-lookup"><span data-stu-id="45a36-179">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="45a36-180">これは REPL ドリブン開発と呼ばれます。 [repl](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)は "Read Evaluate-Print Loop" を表します。</span><span class="sxs-lookup"><span data-stu-id="45a36-180">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="45a36-181">機能を使用するには、機能を試してみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="45a36-181">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="45a36-182">REPL 駆動型開発の次に、作業コードを F# 実装ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="45a36-182">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="45a36-183">その後、F# コンパイラによって実行可能なアセンブリにコンパイルする事ができます。</span><span class="sxs-lookup"><span data-stu-id="45a36-183">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="45a36-184">まず、`ClassLibraryDemo.fs`を開きます。</span><span class="sxs-lookup"><span data-stu-id="45a36-184">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="45a36-185">いくつかのコードが既にあることがわかるでしょう。</span><span class="sxs-lookup"><span data-stu-id="45a36-185">You'll notice that some code is already in there.</span></span> <span data-ttu-id="45a36-186">先に進み、クラス定義を削除しますが、[`namespace`](../language-reference/namespaces.md) 宣言は上部に残しておいてください。</span><span class="sxs-lookup"><span data-stu-id="45a36-186">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="45a36-187">次に、`PigLatin`という新しい[`module`](../language-reference/modules.md) を作成し、`toPigLatin`関数を次のようにコピーします。</span><span class="sxs-lookup"><span data-stu-id="45a36-187">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="45a36-188">そして、`Script.fsx`ファイルをもう一度開き、`toPigLatin`関数全体を削除します。ただし、ファイルには次の 2 行を必ず残してください。</span><span class="sxs-lookup"><span data-stu-id="45a36-188">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="45a36-189">両方のテキスト行を選択し、Alt + Enter キーを押して、FSI でこれらの行を実行します。</span><span class="sxs-lookup"><span data-stu-id="45a36-189">Select both lines of text and press Alt+Enter to execute these lines in FSI.</span></span> <span data-ttu-id="45a36-190">これにより、Pig Latin ライブラリの内容が FSI プロセスに読み込まれ、`ClassLibraryDemo`名前空間を`open`することでその機能にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="45a36-190">These will load the contents of the Pig Latin library into the FSI process and `open` the `ClassLibraryDemo` namespace so that you have access to the functionality.</span></span>

<span data-ttu-id="45a36-191">次に、[FSI] ウィンドウで前に定義した`PigLatin`モジュールの関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="45a36-191">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```console
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="45a36-192">正常に完了</span><span class="sxs-lookup"><span data-stu-id="45a36-192">Success!</span></span> <span data-ttu-id="45a36-193">取得する前に、同じ結果が、F# 実装ファイルから読み込まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="45a36-193">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="45a36-194">ここでの主な違いは、F# ソース ファイルが FSI 内だけでなく、どこにでも実行できるアセンブリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="45a36-194">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="45a36-195">まとめ</span><span class="sxs-lookup"><span data-stu-id="45a36-195">Summary</span></span>

<span data-ttu-id="45a36-196">この記事では、次のことを学習しました。</span><span class="sxs-lookup"><span data-stu-id="45a36-196">In this article, you've learned:</span></span>

1. <span data-ttu-id="45a36-197">Ionide を使用して Visual Studio Code を設定する方法</span><span class="sxs-lookup"><span data-stu-id="45a36-197">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="45a36-198">Ionide で初めての F# プロジェクトを作成する方法</span><span class="sxs-lookup"><span data-stu-id="45a36-198">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="45a36-199">Ionide で初めての F# 関数を記述し、FSI で実行する方法</span><span class="sxs-lookup"><span data-stu-id="45a36-199">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="45a36-200">スクリプトから F# ソースコードへ移行し、FSI からそのコードを呼び出す方法</span><span class="sxs-lookup"><span data-stu-id="45a36-200">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="45a36-201">これで、Visual Studio Code と Ionide を使用してより多くの F# コードを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="45a36-201">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="45a36-202">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="45a36-202">Troubleshooting</span></span>

<span data-ttu-id="45a36-203">発生する可能性のある特定の問題をトラブルシューティングする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="45a36-203">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="45a36-204">Ionide の概要の編集機能をコードを取得するには、F# ファイルはディスク、および Visual Studio Code ワークスペースで開いているフォルダー内に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45a36-204">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="45a36-205">システムに変更を加えた場合、または Visual Studio Code を開いた状態で Ionide の前提条件をインストールした場合は、Visual Studio Code を再起動します。</span><span class="sxs-lookup"><span data-stu-id="45a36-205">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="45a36-206">完全修飾パスなしでコマンドラインから F# コンパイラと F# 対話式を使用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45a36-206">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="45a36-207">これを行うには、F# コンパイラのコマンドラインに`fsc`を入力し、Windows の Visual F# ツールの`fsi`または`fsharpi`をそれぞれ入力し、Mac/Linux 上のモノラルを入力します。</span><span class="sxs-lookup"><span data-stu-id="45a36-207">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="45a36-208">プロジェクトディレクトリに無効な文字が含まれていると、Ionide が機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45a36-208">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="45a36-209">この場合は、プロジェクトディレクトリの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="45a36-209">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="45a36-210">Ionide コマンドがいずれも動作しない場合、 [Visual Studio Code キーバインド](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) を調べて、誤って上書きされていないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="45a36-210">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="45a36-211">Ionide がコンピューター上で破損していて、上記のいずれも問題を解決しな場合、コンピューター上の`ionide-fsharp`ディレクトリを削除し、プラグインスイートを再インストールしてみてください。</span><span class="sxs-lookup"><span data-stu-id="45a36-211">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="45a36-212">Ionide の概要とは、構築および F# コミュニティのメンバーによって管理されるオープン ソース プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="45a36-212">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="45a36-213">問題を報告して、 [Ionide-vscode に投稿してください。Fsharp.core GitHub リポジトリ](https://github.com/ionide/ionide-vscode-fsharp)。</span><span class="sxs-lookup"><span data-stu-id="45a36-213">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="45a36-214">何か問題が発生した場合は、[問題発生時のログ取得手順](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting) に従って下さい。</span><span class="sxs-lookup"><span data-stu-id="45a36-214">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="45a36-215">[Ionide Gitter チャネル](https://gitter.im/ionide/ionide-project) で、Ionide 開発者および F# コミュニティからさらに助けを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="45a36-215">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="45a36-216">次のステップ</span><span class="sxs-lookup"><span data-stu-id="45a36-216">Next steps</span></span>

<span data-ttu-id="45a36-217">F# と言語機能の詳細について学ぶには、[F# のツアー](../tour.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45a36-217">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
