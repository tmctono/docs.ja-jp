---
title: Visual Studio Code での F# の概要します。
description: Visual Studio Code および ionide の概要のプラグインのスイートで F# を使用する方法について説明します。
ms.date: 12/23/2018
ms.openlocfilehash: 7c2ecab14b3351d441249e7fc7cb3188a4ee7eba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949553"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="69b9f-103">Visual Studio Code での F# の概要します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="69b9f-104">書き込めるF#で[Visual Studio Code](https://code.visualstudio.com)で、 [Ionide プラグイン](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)クロス プラットフォームの軽量な統合開発環境 (IDE) ですばらしい体験を IntelliSense および基本的なコードを取得するにはリファクタリング。</span><span class="sxs-lookup"><span data-stu-id="69b9f-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="69b9f-105">参照してください[Ionide.io](http://ionide.io)プラグインの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="69b9f-106">作業を開始できることを確認します。 [F# および ionide の概要プラグインが正しくインストールされている](install-fsharp.md#install-f-with-visual-studio-code)します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

> [!NOTE]
> <span data-ttu-id="69b9f-107">Ionide の概要では、.NET Framework を生成します。F#プロジェクト、dotnet core ではなく、クロス プラットフォームの互換性の問題があることができます。</span><span class="sxs-lookup"><span data-stu-id="69b9f-107">Ionide will generate .NET Framework F# projects, not dotnet core, which can have cross-platform compatibility issues.</span></span> <span data-ttu-id="69b9f-108">実行している場合**Linux**または**OSX**、開始する簡単な方法は使用する、[コマンド ライン ツール](https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-command-line)します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-108">If you are running on **Linux** or **OSX**, a simpler way to get started is to use the [command line tools](https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-command-line).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="69b9f-109">Ionide の概要と、最初のプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-109">Creating your first project with Ionide</span></span>

<span data-ttu-id="69b9f-110">新しい F# プロジェクトを作成するには、新しいフォルダー (することができます、どのような名前) に Visual Studio Code を開きます。</span><span class="sxs-lookup"><span data-stu-id="69b9f-110">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="69b9f-111">次に、コマンド パレットを開いて (**ビュー > コマンド パレット**) と入力します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-111">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="69b9f-112">これで電源がオン、[偽造](https://github.com/fsharp-editing/Forge)プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="69b9f-112">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
> <span data-ttu-id="69b9f-113">テンプレート オプションが表示されない場合は、コマンド パレットで、次のコマンドを実行してテンプレートを更新してください:`>F#: Refresh Project Templates`します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-113">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="69b9f-114">選択"F#:新しいプロジェクト を押して**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-114">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="69b9f-115">プロジェクト テンプレートを選択するためには、次の手順に移動します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-115">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="69b9f-116">選択、`classlib`テンプレートとヒット**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-116">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="69b9f-117">次でプロジェクトを作成するディレクトリを選択します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-117">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="69b9f-118">空のまま、現在のディレクトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-118">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="69b9f-119">最後に、最後の手順で、プロジェクトの名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="69b9f-119">Finally, name your project in the final step.</span></span> <span data-ttu-id="69b9f-120">F#使用して[パスカル ケース](http://c2.com/cgi/wiki?PascalCase)プロジェクト名にします。</span><span class="sxs-lookup"><span data-stu-id="69b9f-120">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="69b9f-121">この記事では`ClassLibraryDemo`名として。</span><span class="sxs-lookup"><span data-stu-id="69b9f-121">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="69b9f-122">プロジェクトの名前を入力したら後のヒット**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-122">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="69b9f-123">前の手順を実行する場合に次のように表示される、左側にある Visual Studio コード ワークスペースを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69b9f-123">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="69b9f-124">F#プロジェクト自体の下に、`ClassLibraryDemo`フォルダー。</span><span class="sxs-lookup"><span data-stu-id="69b9f-124">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="69b9f-125">使用してパッケージを追加するための適切なディレクトリ構造[ `Paket`](https://fsprojects.github.io/Paket/)します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-125">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="69b9f-126">クロス プラットフォーム ビルド スクリプトを[ `FAKE`](https://fsharp.github.io/FAKE/)します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-126">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="69b9f-127">`paket.exe`実行可能ファイルをパッケージのフェッチし、の依存関係を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="69b9f-127">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="69b9f-128">A`.gitignore`ファイルを Git ベースのソース管理にこのプロジェクトを追加する場合。</span><span class="sxs-lookup"><span data-stu-id="69b9f-128">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="69b9f-129">コードの作成</span><span class="sxs-lookup"><span data-stu-id="69b9f-129">Writing some code</span></span>

<span data-ttu-id="69b9f-130">開く、 *ClassLibraryDemo*フォルダー。</span><span class="sxs-lookup"><span data-stu-id="69b9f-130">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="69b9f-131">次のファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69b9f-131">You should see the following files:</span></span>

1. <span data-ttu-id="69b9f-132">`ClassLibraryDemo.fs`で定義されているクラスを使用して F# 実装ファイルです。</span><span class="sxs-lookup"><span data-stu-id="69b9f-132">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="69b9f-133">`ClassLibraryDemo.fsproj`、F# プロジェクト ファイルをこのプロジェクトをビルドするために使用します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-133">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="69b9f-134">`Script.fsx`、ソース ファイルを読み込む F# スクリプト ファイル。</span><span class="sxs-lookup"><span data-stu-id="69b9f-134">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="69b9f-135">`paket.references`、パケット ファイルをプロジェクトの依存関係を指定します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-135">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="69b9f-136">開いている`Script.fsx`の末尾に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-136">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="69b9f-137">この関数は、単語の形式に変換します[Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin)します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-137">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="69b9f-138">次の手順では、F# Interactive (FSI) を使用して評価です。</span><span class="sxs-lookup"><span data-stu-id="69b9f-138">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="69b9f-139">(11 行である必要があります) 関数全体を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-139">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="69b9f-140">強調表示され後の保持、 **Alt**キーとヒット **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-140">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="69b9f-141">以下に、ポップアップ ウィンドウがわかり、このようなものが表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69b9f-141">You'll notice a window pop up below, and it should show something like this:</span></span>

![Ionide の概要で F# Interactive の出力の例](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="69b9f-143">これは、次の 3 つを行いました。</span><span class="sxs-lookup"><span data-stu-id="69b9f-143">This did three things:</span></span>

1. <span data-ttu-id="69b9f-144">FSI プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-144">It started the FSI process.</span></span>
2. <span data-ttu-id="69b9f-145">強調表示したコードは、FSI プロセス上で送信します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-145">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="69b9f-146">FSI プロセス経由で送信するコードを評価します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-146">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="69b9f-147">経由で送信するため、[関数](../language-reference/functions/index.md)FSI でその関数を呼び出すようになりましたことができます。</span><span class="sxs-lookup"><span data-stu-id="69b9f-147">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="69b9f-148">対話型のウィンドウで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-148">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="69b9f-149">次の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69b9f-149">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="69b9f-150">ここで、最初の文字としての母音を試してみましょう。</span><span class="sxs-lookup"><span data-stu-id="69b9f-150">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="69b9f-151">次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-151">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="69b9f-152">次の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69b9f-152">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="69b9f-153">関数は、想定どおりに動作するが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69b9f-153">The function appears to be working as expected.</span></span> <span data-ttu-id="69b9f-154">これで、先ほど Visual Studio Code で初めての F# 関数を記述し、FSI を使用して評価すること。</span><span class="sxs-lookup"><span data-stu-id="69b9f-154">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="69b9f-155">FSI の明細行がで終了しましたように気付き、`;;`します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-155">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="69b9f-156">これは、FSI では、複数の行を入力できるためです。</span><span class="sxs-lookup"><span data-stu-id="69b9f-156">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="69b9f-157">`;;`により FSI 確認コードが完了すると、最後にします。</span><span class="sxs-lookup"><span data-stu-id="69b9f-157">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="69b9f-158">コードの説明</span><span class="sxs-lookup"><span data-stu-id="69b9f-158">Explaining the code</span></span>

<span data-ttu-id="69b9f-159">コードが実際に何のことを確認していない場合は、次に、順を追って示します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-159">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="69b9f-160">ご覧のとおり、`toPigLatin`関数は、単語の入力として受け取り、その単語の Pig Latin 表現に変換します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-160">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="69b9f-161">このルールは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="69b9f-161">The rules for this are as follows:</span></span>

<span data-ttu-id="69b9f-162">単語の最初の文字が母音で始まる場合は、単語の末尾に"yay"を追加します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-162">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="69b9f-163">、母音で開始しない場合は、その最初の文字を単語の末尾に移動し、を「なります」に追加します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-163">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="69b9f-164">FSI では、次お気付きかもしれません。</span><span class="sxs-lookup"><span data-stu-id="69b9f-164">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="69b9f-165">示すこの`toPigLatin`で受け取る関数には、`string`入力として (と呼ばれる`word`)、戻って別`string`。</span><span class="sxs-lookup"><span data-stu-id="69b9f-165">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="69b9f-166">呼ばれます、[関数の型シグネチャ](https://fsharpforfunandprofit.com/posts/function-signatures/)、基本的な F# コードを理解する鍵は、F# です。</span><span class="sxs-lookup"><span data-stu-id="69b9f-166">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="69b9f-167">また、この場合、Visual Studio Code で関数ポインターを合わせます。</span><span class="sxs-lookup"><span data-stu-id="69b9f-167">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="69b9f-168">関数の本文で、2 つの異なる部分がわかります。</span><span class="sxs-lookup"><span data-stu-id="69b9f-168">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="69b9f-169">呼ばれる、内部関数`isVowel`、特定の文字を決定する (`c`) を使用して指定されたパターンのいずれかと一致する場合にチェックして、母音は、[パターン マッチング](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="69b9f-169">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="69b9f-170">[ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md)かどうかは、最初の文字は、母音と場合、最初の文字ベースの構造は、入力文字列からの戻り値をチェックする式、母音であるか。</span><span class="sxs-lookup"><span data-stu-id="69b9f-170">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="69b9f-171">フローの`toPigLatin`なります。</span><span class="sxs-lookup"><span data-stu-id="69b9f-171">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="69b9f-172">入力の単語の最初の文字の母音であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-172">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="69b9f-173">場合は、"yay"という単語の末尾にアタッチします。</span><span class="sxs-lookup"><span data-stu-id="69b9f-173">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="69b9f-174">それ以外の場合、その最初の文字を単語の末尾に移動し、それを「なります」に追加します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-174">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="69b9f-175">1 つの最後にこれに関する注意: その他の多くの言語とは異なり、関数から返される明示的な命令はありません。</span><span class="sxs-lookup"><span data-stu-id="69b9f-175">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="69b9f-176">これは、ためF#が式に基づいて、関数の本体の最後の式は、戻り値。</span><span class="sxs-lookup"><span data-stu-id="69b9f-176">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="69b9f-177">`if..then..else`自体、式の本体では、`then`ブロックまたはの本文、`else`ブロックが入力値によって返されます。</span><span class="sxs-lookup"><span data-stu-id="69b9f-177">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="69b9f-178">スクリプト コードを実装ファイルに移動</span><span class="sxs-lookup"><span data-stu-id="69b9f-178">Moving your script code into the implementation file</span></span>

<span data-ttu-id="69b9f-179">この記事では、前のセクションには、F# コードの記述の一般的な最初の手順が示されています。 最初の関数の記述と、FSI 使用して対話的に実行します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-179">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="69b9f-180">これは、REPL 駆動型開発と呼ばれます、 [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) 「読み取り評価印刷ループ」を意味します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-180">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="69b9f-181">機能を試して動作ものがある場合する優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="69b9f-181">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="69b9f-182">REPL 駆動型開発の次の手順では、作業コード F# 実装ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-182">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="69b9f-183">これは、実行可能なアセンブリの F# コンパイラによってコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="69b9f-183">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="69b9f-184">まず、開きます`ClassLibraryDemo.fs`します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-184">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="69b9f-185">いくつかのコードが既にに存在することがわかります。</span><span class="sxs-lookup"><span data-stu-id="69b9f-185">You'll notice that some code is already in there.</span></span> <span data-ttu-id="69b9f-186">前方に移動し、クラス定義を削除しますがのままにすることを確認、 [ `namespace` ](../language-reference/namespaces.md)上部にある宣言します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-186">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="69b9f-187">次に、作成、新しい[ `module` ](../language-reference/modules.md)と呼ばれる`PigLatin`をコピーし、`toPigLatin`ように関数。</span><span class="sxs-lookup"><span data-stu-id="69b9f-187">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="69b9f-188">次に、開く、`Script.fsx`ファイルを再び、および全体を削除`toPigLatin`ファイルに次の 2 つの行を保持することを確認しますが、機能します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-188">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="69b9f-189">テキストの両方の行を選択して、FSI でこれらの行を実行するには、Alt + Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-189">Select both lines of text and press Alt+Enter to execute these lines in FSI.</span></span> <span data-ttu-id="69b9f-190">FSI のプロセスに Pig Latin ライブラリのコンテンツを読み込むこれらと`open`、`ClassLibraryDemo`名前空間の機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="69b9f-190">These will load the contents of the Pig Latin library into the FSI process and `open` the `ClassLibraryDemo` namespace so that you have access to the functionality.</span></span>

<span data-ttu-id="69b9f-191">次に、FSI ウィンドウで、使用して、関数を呼び出して、`PigLatin`前に定義したモジュール。</span><span class="sxs-lookup"><span data-stu-id="69b9f-191">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="69b9f-192">正常に完了</span><span class="sxs-lookup"><span data-stu-id="69b9f-192">Success!</span></span> <span data-ttu-id="69b9f-193">取得する前に、同じ結果が、F# 実装ファイルから読み込まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="69b9f-193">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="69b9f-194">ここでの主な違いは、F# ソース ファイルが FSI 内だけでなく、どこにでも実行できるアセンブリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="69b9f-194">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="69b9f-195">まとめ</span><span class="sxs-lookup"><span data-stu-id="69b9f-195">Summary</span></span>

<span data-ttu-id="69b9f-196">この記事では、次の学習できました。</span><span class="sxs-lookup"><span data-stu-id="69b9f-196">In this article, you've learned:</span></span>

1. <span data-ttu-id="69b9f-197">Ionide の概要を使用して Visual Studio Code を設定する方法。</span><span class="sxs-lookup"><span data-stu-id="69b9f-197">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="69b9f-198">Ionide の概要で初めての F# プロジェクトを作成する方法。</span><span class="sxs-lookup"><span data-stu-id="69b9f-198">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="69b9f-199">F# スクリプトを使用して、ionide の概要で初めての F# 関数を記述し、FSI で実行する方法。</span><span class="sxs-lookup"><span data-stu-id="69b9f-199">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="69b9f-200">スクリプトを移行する方法を使用して、F# ソース コード、FSI からそのコードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-200">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="69b9f-201">コードより F# Visual Studio Code および ionide の概要を使用して書き込むが組み込まれました。</span><span class="sxs-lookup"><span data-stu-id="69b9f-201">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="69b9f-202">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="69b9f-202">Troubleshooting</span></span>

<span data-ttu-id="69b9f-203">次に遭遇する可能性のある特定の問題のトラブルシューティングを行うことがいくつかの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-203">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="69b9f-204">Ionide の概要の編集機能をコードを取得するには、F# ファイルはディスク、および Visual Studio Code ワークスペースで開いているフォルダー内に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69b9f-204">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="69b9f-205">場合は、システムを変更または開いている Visual Studio のコードと共に ionide の概要の前提条件をインストールしたら、Visual Studio Code を再起動します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-205">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="69b9f-206">使用できることを確認、F#コンパイラとF#完全修飾パスを使用せずにコマンドラインから対話型です。</span><span class="sxs-lookup"><span data-stu-id="69b9f-206">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="69b9f-207">」と入力して行うことができます`fsc`、F# コンパイラのコマンドラインで、`fsi`または`fsharpi`の Visual F# ツールの Windows、Mac または Linux での Mono でそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="69b9f-207">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="69b9f-208">プロジェクトのディレクトリで無効な文字があれば、ionide の概要が動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69b9f-208">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="69b9f-209">これに該当する場合、プロジェクト ディレクトリの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-209">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="69b9f-210">Ionide コマンドのいずれも作業している場合、 [Visual Studio Code の keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts)を誤って上書きしているかどうかを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69b9f-210">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="69b9f-211">Ionide の概要は、コンピューターに分割すると、上記のいずれが問題を修正、削除してみてください、`ionide-fsharp`コンピューターにディレクトリ プラグイン スイートを再インストールします。</span><span class="sxs-lookup"><span data-stu-id="69b9f-211">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="69b9f-212">Ionide の概要とは、構築および F# コミュニティのメンバーによって管理されるオープン ソース プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="69b9f-212">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="69b9f-213">問題を報告し、気軽に投稿にしてください、 [Ionide VSCode:FSharp GitHub リポジトリ](https://github.com/ionide/ionide-vscode-fsharp)します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-213">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="69b9f-214">レポートに問題がある場合に従ってください[問題を報告するときに使用するログを取得するための指示](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting)します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-214">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="69b9f-215">Ionide の概要開発者および F# コミュニティからさらにヘルプを求めることも、 [Ionide Gitter チャネル](https://gitter.im/ionide/ionide-project)します。</span><span class="sxs-lookup"><span data-stu-id="69b9f-215">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="69b9f-216">次の手順</span><span class="sxs-lookup"><span data-stu-id="69b9f-216">Next steps</span></span>

<span data-ttu-id="69b9f-217">F# と言語の機能の詳細については、[F# のツアー](../tour.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69b9f-217">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
