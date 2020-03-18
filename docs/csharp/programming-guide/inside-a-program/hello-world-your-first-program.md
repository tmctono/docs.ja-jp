---
title: Hello World -- Windows または Mac 上での Visual Studio を使用する最初のプログラム -C# プログラミング ガイド
ms.date: 09/12/2019
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 910fa4af1b4e45ce627b589a06910dc168490047
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712144"
---
# <a name="hello-world----your-first-program"></a><span data-ttu-id="5b6ba-102">Hello World -- 最初のプログラム</span><span class="sxs-lookup"><span data-stu-id="5b6ba-102">Hello World -- Your first program</span></span>

<span data-ttu-id="5b6ba-103">この記事では、Visual Studio を使用して従来の "Hello World!" プログラムを</span><span class="sxs-lookup"><span data-stu-id="5b6ba-103">In this article, you'll use Visual Studio to create the traditional "Hello World!"</span></span> <span data-ttu-id="5b6ba-104">作成します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-104">program.</span></span> <span data-ttu-id="5b6ba-105">Visual Studio は、.NET 開発向けに設計された多くの機能を備えた、本格的な統合開発環境 (IDE) です。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-105">Visual Studio is a professional Integrated Development Environment (IDE) with many features designed for .NET development.</span></span> <span data-ttu-id="5b6ba-106">Visual Studio の一部の機能のみを使用して、このプログラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-106">You'll use only a few of the features in Visual Studio to create this program.</span></span> <span data-ttu-id="5b6ba-107">Visual Studio の詳細については、[Visual C# の概要](/visualstudio/ide/quickstart-csharp-console)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-107">To learn more about Visual Studio, see [Getting Started with Visual C#](/visualstudio/ide/quickstart-csharp-console).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="create-a-new-application"></a><span data-ttu-id="5b6ba-108">新しいアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="5b6ba-108">Create a new application</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="5b6ba-109">Windows</span><span class="sxs-lookup"><span data-stu-id="5b6ba-109">Windows</span></span>](#tab/windows)

<span data-ttu-id="5b6ba-110">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-110">Start Visual Studio.</span></span> <span data-ttu-id="5b6ba-111">Windows 上に次のようなイメージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-111">You'll see the following image on Windows:</span></span>

![Windows 上の Visual Studio のようこそ画面](./media/hello-world-your-first-program/visual-studio-windows-start-screen.png)

<span data-ttu-id="5b6ba-113">イメージの右下隅にある **[新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-113">Select **Create a new project** in the lower right corner of the image.</span></span> <span data-ttu-id="5b6ba-114">Visual Studio で、 **[新しいプロジェクト]** ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-114">Visual Studio displays the **New Project** dialog:</span></span>

![Windows 上の Visual Studio の [新しいプロジェクト] 画面](./media/hello-world-your-first-program/visual-studio-windows-new-project.png)

> [!NOTE]
> <span data-ttu-id="5b6ba-116">初めて Visual Studio を起動した場合、 **[最近使用したプロジェクト テンプレート]** の一覧は空の状態です。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-116">If this is the first time you've started Visual Studio, the **Recent project templates** list is empty.</span></span>

<span data-ttu-id="5b6ba-117">[新しいプロジェクト] ダイアログで、[コンソールアプリ (.NET Core)] を選択し、 **[次へ]** を押します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-117">On the new project dialog, choose "Console App (.NET Core)" and then press **Next**.</span></span> <span data-ttu-id="5b6ba-118">「HelloWorld」などプロジェクトの名前を指定して、 **[OK]** を押します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-118">Give your project a name, such as "HelloWorld", then press **Create**.</span></span>

<span data-ttu-id="5b6ba-119">Visual Studio でプロジェクトが開かれます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-119">Visual Studio opens your project.</span></span> <span data-ttu-id="5b6ba-120">これが既に、基本的な "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="5b6ba-120">It's already a basic "Hello World!"</span></span> <span data-ttu-id="5b6ba-121">の例です。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-121">example.</span></span> <span data-ttu-id="5b6ba-122">`Ctrl` + `F5` を押してプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-122">Press `Ctrl` + `F5` to run your project.</span></span> <span data-ttu-id="5b6ba-123">Visual Studio によってプロジェクトがビルドされ、ソース コードが実行可能ファイルに変換されます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-123">Visual Studio builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="5b6ba-124">次に、新しいアプリケーションを実行するコマンド ウィンドウが起動されます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-124">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="5b6ba-125">ウィンドウには次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-125">You should see the following text in the window:</span></span>

```console
Hello World!

C:\Program Files\dotnet\dotnet.exe (process 11964) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="5b6ba-126">任意のキーを押して、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-126">Press a key to close the window.</span></span>

# <a name="macos"></a>[<span data-ttu-id="5b6ba-127">macOS</span><span class="sxs-lookup"><span data-stu-id="5b6ba-127">macOS</span></span>](#tab/macos)

<span data-ttu-id="5b6ba-128">Visual Studio for Mac を起動します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-128">Start Visual Studio for Mac.</span></span> <span data-ttu-id="5b6ba-129">Mac 上に次のようなイメージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-129">You'll see the following image on Mac:</span></span>

![Mac 上の Visual Studio のようこそ画面](./media/hello-world-your-first-program/visual-studio-mac-start-screen.png)

> [!NOTE]
> <span data-ttu-id="5b6ba-131">初めて Visual Studio for Mac を起動した場合、 **[最近使用したプロジェクト]** の一覧は空の状態です。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-131">If this is the first time you've started Visual Studio for Mac, the **Recent projects** list is empty.</span></span>

<span data-ttu-id="5b6ba-132">イメージの右上隅にある **[新規]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-132">Select **New** in the upper right corner of the image.</span></span> <span data-ttu-id="5b6ba-133">Visual Studio for Mac で、 **[新しいプロジェクト]** ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-133">Visual Studio for Mac displays the **New Project** dialog:</span></span>

![Mac 上の Visual Studio の [新しいプロジェクト] 画面](./media/hello-world-your-first-program/visual-studio-mac-new-project.png)

<span data-ttu-id="5b6ba-135">[新しいプロジェクト] ダイアログで、[.NET Core]、[コンソール アプリ] の順に選択し、 **[次へ]** を押します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-135">On the new project dialog, choose ".NET Core", and "Console App" and then press **Next**.</span></span> <span data-ttu-id="5b6ba-136">ターゲット フレームワークを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-136">You'll need to select the target framework.</span></span> <span data-ttu-id="5b6ba-137">既定値で問題ありませんので、[次へ] を押します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-137">The default is fine, so press next.</span></span> <span data-ttu-id="5b6ba-138">「HelloWorld」などプロジェクトの名前を指定して、 **[OK]** を押します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-138">Give your project a name, such as "HelloWorld", then press **Create**.</span></span> <span data-ttu-id="5b6ba-139">既定のプロジェクトの場所を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-139">You can use the default project location.</span></span> <span data-ttu-id="5b6ba-140">ソース管理にこのプロジェクトを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-140">Don't add this project to source control.</span></span>

<span data-ttu-id="5b6ba-141">Visual Studio for Mac でプロジェクトが開かれます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-141">Visual Studio for Mac opens your project.</span></span> <span data-ttu-id="5b6ba-142">これが既に、基本的な "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="5b6ba-142">It's already a basic "Hello World!"</span></span> <span data-ttu-id="5b6ba-143">の例です。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-143">example.</span></span> <span data-ttu-id="5b6ba-144">`Ctrl` + `Fn` + `F5` を押してプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-144">Press `Ctrl` + `Fn` + `F5` to run your project.</span></span> <span data-ttu-id="5b6ba-145">Visual Studio for Mac によってプロジェクトがビルドされ、ソース コードが実行可能ファイルに変換されます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-145">Visual Studio for Mac builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="5b6ba-146">次に、新しいアプリケーションを実行するコマンド ウィンドウが起動されます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-146">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="5b6ba-147">ウィンドウには次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-147">You should see the following text in the window:</span></span>

```console
Hello World!

Press any key to close this window . . .
```

<span data-ttu-id="5b6ba-148">任意のキーを押して、セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-148">Press a key to end the session.</span></span>

---

## <a name="elements-of-a-c-program"></a><span data-ttu-id="5b6ba-149">C# プログラムの要素</span><span class="sxs-lookup"><span data-stu-id="5b6ba-149">Elements of a C# program</span></span>

<span data-ttu-id="5b6ba-150">このプログラムの重要な部分を調べてみましょう。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-150">Let's examine the important parts of this program.</span></span> <span data-ttu-id="5b6ba-151">最初の行はコメントになっています。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-151">The first line contains a comment.</span></span> <span data-ttu-id="5b6ba-152">「`//`」という文字があると、これ以降その行はコメントになります。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-152">The characters `//` convert the rest of the line to a comment.</span></span>

[!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

<span data-ttu-id="5b6ba-153">テキスト ブロックを `/*` 文字と `*/` 文字で囲んでコメントにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-153">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="5b6ba-154">次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-154">This is shown in the following example.</span></span>

[!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

<span data-ttu-id="5b6ba-155">C# コンソールアプリケーションには、`Main` メソッドが必要です。このメソッドの中で制御を開始して終了します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-155">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="5b6ba-156">`Main` メソッドでは、オブジェクトを作成し、ほかのメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-156">The `Main` method is where you create objects and execute other methods.</span></span>

<span data-ttu-id="5b6ba-157">`Main` メソッドはクラスまたは構造体の中に存在する [static](../../language-reference/keywords/static.md) メソッドです。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-157">The `Main` method is a [static](../../language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="5b6ba-158">前の "Hello World!" の</span><span class="sxs-lookup"><span data-stu-id="5b6ba-158">In the previous "Hello World!"</span></span> <span data-ttu-id="5b6ba-159">例では、`Hello` という名前のクラスに存在していました。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-159">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="5b6ba-160">次の方法のいずれかで `Main` メソッドを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-160">You can declare the `Main` method in one of the following ways:</span></span>

- <span data-ttu-id="5b6ba-161">`void` 型を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-161">It can return `void`.</span></span> <span data-ttu-id="5b6ba-162">これは、プログラムが値を返さないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-162">That means your program doesn't return a value.</span></span>

[!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- <span data-ttu-id="5b6ba-163">整数を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-163">It can also return an integer.</span></span> <span data-ttu-id="5b6ba-164">整数は、アプリケーションの**終了コード**です。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-164">The integer is the **exit code** for your application.</span></span>

[!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- <span data-ttu-id="5b6ba-165">どちらの戻り値の型でも、次のように引数を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-165">With either of the return types, it can take arguments.</span></span>

[!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

<span data-ttu-id="5b6ba-166">または</span><span class="sxs-lookup"><span data-stu-id="5b6ba-166">-or-</span></span>

[!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

<span data-ttu-id="5b6ba-167">`Main` メソッドのパラメーターである `args` は、`string` の配列で、プログラムの実行時に使用したコマンドライン引数を含みます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-167">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span>

<span data-ttu-id="5b6ba-168">コマンドライン引数の使用方法の詳細については、「[Main() とコマンドライン引数](../main-and-command-args/index.md)」にある例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-168">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../main-and-command-args/index.md).</span></span>

## <a name="input-and-output"></a><span data-ttu-id="5b6ba-169">入力と出力</span><span class="sxs-lookup"><span data-stu-id="5b6ba-169">Input and output</span></span>

<span data-ttu-id="5b6ba-170">C# プログラムは、普通、.NET Framework のランタイムライブラリが提供する入出力サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-170">C# programs generally use the input/output services provided by the run-time library of the .NET Framework.</span></span> <span data-ttu-id="5b6ba-171">`System.Console.WriteLine("Hello World!");` 命令文では、<xref:System.Console.WriteLine%2A> メソッドを使用しています。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-171">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="5b6ba-172">これは、ランタイムライブラリの <xref:System.Console> クラスの出力メソッドの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-172">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="5b6ba-173">文字列パラメーターを標準出力ストリームに出力し、最後に改行を付け加えます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-173">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="5b6ba-174">別の入出力操作には、他の <xref:System.Console> メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-174">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="5b6ba-175">`using System;` ディレクティブをプログラムの開始時にインクルードした場合は、完全に修飾せずに <xref:System> クラスおよびメソッドを直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-175">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="5b6ba-176">たとえば、`Console.WriteLine` の代わりに `System.Console.WriteLine` を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-176">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="5b6ba-177">入出力メソッドの詳細については、「<xref:System.IO>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b6ba-177">For more information about input/output methods, see <xref:System.IO>.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b6ba-178">参照</span><span class="sxs-lookup"><span data-stu-id="5b6ba-178">See also</span></span>

- [<span data-ttu-id="5b6ba-179">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="5b6ba-179">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5b6ba-180">サンプルおよびチュートリアル</span><span class="sxs-lookup"><span data-stu-id="5b6ba-180">Samples and tutorials</span></span>](../../../samples-and-tutorials/index.md)
- [<span data-ttu-id="5b6ba-181">Main() とコマンドライン引数</span><span class="sxs-lookup"><span data-stu-id="5b6ba-181">Main() and Command-Line Arguments</span></span>](../main-and-command-args/index.md)
- [<span data-ttu-id="5b6ba-182">Visual C# 入門</span><span class="sxs-lookup"><span data-stu-id="5b6ba-182">Getting Started with Visual C#</span></span>](/visualstudio/ide/quickstart-csharp-console)
