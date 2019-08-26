---
title: Hello World -- 最初のプログラム - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 9a50de0bb583a1dfccfa609be1cca732868505ba
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589374"
---
# <a name="hello-world----your-first-program-c-programming-guide"></a><span data-ttu-id="8f0d0-102">Hello World -- 最初のプログラム (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="8f0d0-102">Hello World -- Your first program (C# Programming Guide)</span></span>

<span data-ttu-id="8f0d0-103">次の手順では、従来の "Hello World!" プログラムの C# バージョンを</span><span class="sxs-lookup"><span data-stu-id="8f0d0-103">The following procedure creates a C# version of the traditional "Hello World!"</span></span> <span data-ttu-id="8f0d0-104">作成します。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-104">program.</span></span> <span data-ttu-id="8f0d0-105">このプログラムでは `Hello World!` という文字列を表示します。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-105">The program displays the string `Hello World!`</span></span>

<span data-ttu-id="8f0d0-106">基本概念の例については、「[Visual C# と Visual Basic の概要](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-106">For more examples of introductory concepts, see [Getting Started with Visual C# and Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-and-run-a-console-application"></a><span data-ttu-id="8f0d0-107">コンソール アプリケーションを作成し、実行するには</span><span class="sxs-lookup"><span data-stu-id="8f0d0-107">To create and run a console application</span></span>

1. <span data-ttu-id="8f0d0-108">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-108">Start Visual Studio.</span></span>

2. <span data-ttu-id="8f0d0-109">メニュー バーで、 **[ファイル]** 、 **[新規作成]** 、 **[プロジェクト]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>

     <span data-ttu-id="8f0d0-110">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-110">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="8f0d0-111">**[インストール済み]** 、 **[テンプレート]** 、 **[Visual C#]** の順に展開し、 **[コンソール アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>

4. <span data-ttu-id="8f0d0-112">**[名前]** ボックスにプロジェクト名を指定し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-112">In the **Name** box, specify a name for your project, and then choose the **OK** button.</span></span>

     <span data-ttu-id="8f0d0-113">**ソリューション エクスプローラー**に新しいプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-113">The new project appears in **Solution Explorer**.</span></span>

5. <span data-ttu-id="8f0d0-114">**コード エディター**で Program.cs が開いていない場合は、**ソリューション エクスプローラー**で **Program.cs** のショートカットメニューを開き、 **[コードの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-114">If Program.cs isn't open in the **Code Editor**, open the shortcut menu for **Program.cs** in **Solution Explorer**, and then choose **View Code**.</span></span>

6. <span data-ttu-id="8f0d0-115">Program.cs の内容を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-115">Replace the contents of Program.cs with the following code.</span></span>

     [!code-csharp[csProgGuide#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#21)]

7. <span data-ttu-id="8f0d0-116">F5 キーを押してプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-116">Choose the F5 key to run the project.</span></span> <span data-ttu-id="8f0d0-117">`Hello World!` という行を含むコマンド プロンプト ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-117">A Command Prompt window appears that contains the line `Hello World!`</span></span>

<span data-ttu-id="8f0d0-118">次に、このプログラムの重要な部分を調べます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-118">Next, the important parts of this program are examined.</span></span>

## <a name="comments"></a><span data-ttu-id="8f0d0-119">説明</span><span class="sxs-lookup"><span data-stu-id="8f0d0-119">Comments</span></span>

<span data-ttu-id="8f0d0-120">最初の行はコメントになっています。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-120">The first line contains a comment.</span></span> <span data-ttu-id="8f0d0-121">「`//`」という文字があると、これ以降その行はコメントになります。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-121">The characters `//` convert the rest of the line to a comment.</span></span>

 [!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

<span data-ttu-id="8f0d0-122">テキスト ブロックを `/*` 文字と `*/` 文字で囲んでコメントにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-122">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="8f0d0-123">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-123">This is shown in the following example.</span></span>

 [!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

## <a name="main-method"></a><span data-ttu-id="8f0d0-124">Main メソッド</span><span class="sxs-lookup"><span data-stu-id="8f0d0-124">Main method</span></span>

<span data-ttu-id="8f0d0-125">C# コンソールアプリケーションには、`Main` メソッドが必要です。このメソッドの中で制御を開始して終了します。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-125">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="8f0d0-126">`Main` メソッドでは、オブジェクトを作成し、ほかのメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-126">The `Main` method is where you create objects and execute other methods.</span></span>

<span data-ttu-id="8f0d0-127">`Main` メソッドはクラスまたは構造体の中に存在する [static](../../language-reference/keywords/static.md) メソッドです。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-127">The `Main` method is a [static](../../language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="8f0d0-128">前の "Hello World!" の</span><span class="sxs-lookup"><span data-stu-id="8f0d0-128">In the previous "Hello World!"</span></span> <span data-ttu-id="8f0d0-129">例では、`Hello` という名前のクラスに存在していました。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-129">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="8f0d0-130">次の方法のいずれかで `Main` メソッドを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-130">You can declare the `Main` method in one of the following ways:</span></span>

- <span data-ttu-id="8f0d0-131">`void` 型を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-131">It can return `void`.</span></span>

     [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- <span data-ttu-id="8f0d0-132">整数を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-132">It can also return an integer.</span></span>

     [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- <span data-ttu-id="8f0d0-133">どちらの戻り値の型でも、次のように引数を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-133">With either of the return types, it can take arguments.</span></span>

     [!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

     <span data-ttu-id="8f0d0-134">または</span><span class="sxs-lookup"><span data-stu-id="8f0d0-134">-or-</span></span>

     [!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

<span data-ttu-id="8f0d0-135">`Main` メソッドのパラメーターである `args` は、`string` の配列で、プログラムの実行時に使用したコマンドライン引数を含みます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-135">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span> <span data-ttu-id="8f0d0-136">C++ とは異なり、この配列には実行可能 (exe) ファイルの名前は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-136">Unlike in C++, the array does not include the name of the executable (exe) file.</span></span>

<span data-ttu-id="8f0d0-137">コマンドライン引数の使用方法の詳細については、「[Main() とコマンドライン引数](../main-and-command-args/index.md)」および「[方法: コマンドラインを使用してアセンブリを作成および使用する](../concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)」に記載されている例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-137">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../main-and-command-args/index.md) and [How to: Create and Use Assemblies Using the Command Line](../concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span></span>

<span data-ttu-id="8f0d0-138"><xref:System.Console.ReadKey%2A> メソッドの末尾で `Main` を呼び出すと、F5 キーを押してデバッグモードでプログラムを実行するときに、出力を読み取る前にコンソールウィンドウが終了することを回避できます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-138">The call to <xref:System.Console.ReadKey%2A> at the end of the `Main` method prevents the console window from closing before you have a chance to read the output when you run your program in debug mode, by pressing F5.</span></span>

## <a name="input-and-output"></a><span data-ttu-id="8f0d0-139">入出力</span><span class="sxs-lookup"><span data-stu-id="8f0d0-139">Input and output</span></span>

<span data-ttu-id="8f0d0-140">C# プログラムは、普通、.NET Framework のランタイムライブラリが提供する入出力サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-140">C# programs generally use the input/output services provided by the run-time library of the .NET Framework.</span></span> <span data-ttu-id="8f0d0-141">`System.Console.WriteLine("Hello World!");` 命令文では、<xref:System.Console.WriteLine%2A> メソッドを使用しています。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-141">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="8f0d0-142">これは、ランタイム ライブラリの <xref:System.Console> クラスの出力メソッドの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-142">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="8f0d0-143">文字列パラメーターを標準出力ストリームに出力し、最後に改行を付け加えます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-143">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="8f0d0-144">別の入出力操作には、他の <xref:System.Console> メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-144">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="8f0d0-145">`using System;` ディレクティブをプログラムの開始時にインクルードした場合は、完全に修飾せずに <xref:System> クラスおよびメソッドを直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-145">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="8f0d0-146">たとえば、`Console.WriteLine` の代わりに `System.Console.WriteLine` を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-146">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>

 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

 [!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="8f0d0-147">入出力メソッドの詳細については、「<xref:System.IO>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-147">For more information about input/output methods, see <xref:System.IO>.</span></span>

## <a name="command-line-compilation-and-execution"></a><span data-ttu-id="8f0d0-148">コマンドラインコンパイルと実行</span><span class="sxs-lookup"><span data-stu-id="8f0d0-148">Command-line compilation and execution</span></span>

<span data-ttu-id="8f0d0-149">"Hello World!" プログラムは、</span><span class="sxs-lookup"><span data-stu-id="8f0d0-149">You can compile the "Hello World!"</span></span> <span data-ttu-id="8f0d0-150">Visual Studio 統合開発環境 (IDE) の代わりに、コマンドラインを使用してコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-150">program by using the command line instead of the Visual Studio Integrated Development Environment (IDE).</span></span>

### <a name="to-compile-and-run-from-a-command-prompt"></a><span data-ttu-id="8f0d0-151">コマンドプロンプトからコンパイルおよび実行するには</span><span class="sxs-lookup"><span data-stu-id="8f0d0-151">To compile and run from a command prompt</span></span>

1. <span data-ttu-id="8f0d0-152">前の手順のコードをテキスト エディターに貼り付け、テキスト ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-152">Paste the code from the preceding procedure into any text editor, and then save the file as a text file.</span></span> <span data-ttu-id="8f0d0-153">そのファイルに `Hello.cs` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-153">Name the file `Hello.cs`.</span></span> <span data-ttu-id="8f0d0-154">C# のソース コード ファイルでは、`.cs` という拡張子を使います。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-154">C# source code files use the extension `.cs`.</span></span>

2. <span data-ttu-id="8f0d0-155">次のいずれかの手順を実行してコマンド プロンプト ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-155">Perform one of the following steps to open a command-prompt window:</span></span>

    - <span data-ttu-id="8f0d0-156">Windows 10 の場合、 **[スタート]** メニューで `Developer Command Prompt` を検索し、 **[開発者コマンド プロンプト for VS 2017]** をタップまたは選択します。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-156">In Windows 10, on the **Start** menu, search for `Developer Command Prompt`, and then tap or choose **Developer Command Prompt for VS 2017**.</span></span>

         <span data-ttu-id="8f0d0-157">[開発者コマンド プロンプト] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-157">A Developer Command Prompt window appears.</span></span>

    - <span data-ttu-id="8f0d0-158">Windows 7 の場合、 **[スタート]** メニューを開き、Visual Studio の現在のバージョンのフォルダーを展開し、 **[Visual Studio Tools]** のショートカット メニューを開いて、 **[開発者コマンド プロンプト for VS 2017]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-158">In Windows 7, open the **Start** menu, expand the folder for the current version of Visual Studio, open the shortcut menu for **Visual Studio Tools**, and then choose **Developer Command Prompt for VS 2017**.</span></span>

         <span data-ttu-id="8f0d0-159">[開発者コマンド プロンプト] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-159">A Developer Command Prompt window appears.</span></span>

    - <span data-ttu-id="8f0d0-160">標準のコマンドプロンプトウィンドウからコマンド ライン ビルドを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-160">Enable command-line builds from a standard Command Prompt window.</span></span>

         <span data-ttu-id="8f0d0-161">「[方法 : Visual Studio のコマンドラインのための環境変数を設定する](../../language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-161">See [How to: Set Environment Variables for the Visual Studio Command Line](../../language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>

3. <span data-ttu-id="8f0d0-162">コマンドプロンプトウィンドウで、`Hello.cs` ファイルが格納されているフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-162">In the command-prompt window, navigate to the folder that contains your `Hello.cs` file.</span></span>

4. <span data-ttu-id="8f0d0-163">`Hello.cs` をコンパイルするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-163">Enter the following command to compile `Hello.cs`.</span></span>

     `csc Hello.cs`

     <span data-ttu-id="8f0d0-164">プログラムにコンパイル エラーがない場合、`Hello.exe` という名前の実行可能ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-164">If your program has no compilation errors, an executable file that is named `Hello.exe` is created.</span></span>

5. <span data-ttu-id="8f0d0-165">コマンド プロンプトで、次のコマンドを入力してプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-165">In the command-prompt window, enter the following command to run the program:</span></span>

     `Hello`

 <span data-ttu-id="8f0d0-166">C# コンパイラとそのオプションの詳細については、「[C# コンパイラ オプション](../../language-reference/compiler-options/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0d0-166">For more information about the C# compiler and its options, see [C# Compiler Options](../../language-reference/compiler-options/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f0d0-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f0d0-167">See also</span></span>

- [<span data-ttu-id="8f0d0-168">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="8f0d0-168">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8f0d0-169">インサイド C# プログラム</span><span class="sxs-lookup"><span data-stu-id="8f0d0-169">Inside a C# Program</span></span>](./index.md)
- [<span data-ttu-id="8f0d0-170">文字列</span><span class="sxs-lookup"><span data-stu-id="8f0d0-170">Strings</span></span>](../strings/index.md)
- [<span data-ttu-id="8f0d0-171">サンプルおよびチュートリアル</span><span class="sxs-lookup"><span data-stu-id="8f0d0-171">Samples and tutorials</span></span>](../../../samples-and-tutorials/index.md)
- [<span data-ttu-id="8f0d0-172">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="8f0d0-172">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="8f0d0-173">Main() とコマンドライン引数</span><span class="sxs-lookup"><span data-stu-id="8f0d0-173">Main() and Command-Line Arguments</span></span>](../main-and-command-args/index.md)
- [<span data-ttu-id="8f0d0-174">Visual C# と Visual Basic の概要</span><span class="sxs-lookup"><span data-stu-id="8f0d0-174">Getting Started with Visual C# and Visual Basic</span></span>](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)
