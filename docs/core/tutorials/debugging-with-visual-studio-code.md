---
title: Visual Studio Code を使用して .NET Core コンソール アプリケーションをデバッグする
description: Visual Studio Code を使用して .NET Core コンソール アプリをデバッグする方法について説明します。
ms.date: 05/26/2020
ms.openlocfilehash: 82b2798397d702aa2a50c04bf6e4d569b97e3666
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241514"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-code"></a><span data-ttu-id="b0f32-103">チュートリアル: Visual Studio Code を使用して .NET Core コンソール アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="b0f32-103">Tutorial: Debug a .NET Core console application using Visual Studio Code</span></span>

<span data-ttu-id="b0f32-104">このチュートリアルでは、.NET Core アプリを操作するために Visual Studio Code で使用できるデバッグ ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-104">This tutorial introduces the debugging tools available in Visual Studio Code for working with .NET Core apps.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b0f32-105">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b0f32-105">Prerequisites</span></span>

- <span data-ttu-id="b0f32-106">このチュートリアルでは、[Visual Studio Code での .NET Core コンソール アプリケーションの作成](with-visual-studio-code.md)に関するページで作成した、コンソール アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="b0f32-107">デバッグ ビルド構成の使用</span><span class="sxs-lookup"><span data-stu-id="b0f32-107">Use Debug build configuration</span></span>

<span data-ttu-id="b0f32-108">"*デバッグ*" と "*リリース*" は、.NET Core のビルド構成うちの 2 つです。</span><span class="sxs-lookup"><span data-stu-id="b0f32-108">*Debug* and *Release* are two of .NET Core's build configurations.</span></span> <span data-ttu-id="b0f32-109">デバッグ用のデバッグ ビルド構成と、最終リリース配布用のリリース構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="b0f32-110">デバッグ構成では、プログラムのコンパイルにシンボリック デバッグ情報が完全に含まれ、最適化は行われません。</span><span class="sxs-lookup"><span data-stu-id="b0f32-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="b0f32-111">ソース コードと生成された命令の関係は非常に複雑であり、最適化を行うとデバッグが困難になるためです。</span><span class="sxs-lookup"><span data-stu-id="b0f32-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="b0f32-112">プログラムのリリース構成は、シンボリック デバッグ情報を含まず、完全に最適化されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

 <span data-ttu-id="b0f32-113">既定では、Visual Studio Code ではデバッグ ビルド構成が使用されるため、デバッグの前に変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b0f32-113">By default, Visual Studio Code uses the Debug build configuration, so you don't need to change it before debugging.</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="b0f32-114">ブレークポイントの設定</span><span class="sxs-lookup"><span data-stu-id="b0f32-114">Set a breakpoint</span></span>

<span data-ttu-id="b0f32-115">ブレークポイントが設定された行が実行される "*前*" に、アプリケーションの実行がブレークポイントにより一時的に中断されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-115">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="b0f32-116">Visual Studio Code を開きます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-116">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="b0f32-117">[Visual Studio Code での .NET Core コンソール アプリケーションの作成](with-visual-studio-code.md)に関する記事で作成した *HelloWorld* プロジェクト フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-117">Open the *HelloWorld* project folder that you created in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

1. <span data-ttu-id="b0f32-118">*Program.cs* ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-118">Open the *Program.cs* file.</span></span>

1. <span data-ttu-id="b0f32-119">コード ウィンドウの左側の余白をクリックして、名前、日付、時刻を表示する行に "*ブレークポイント*" を設定します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-119">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window.</span></span> <span data-ttu-id="b0f32-120">左余白は、行番号の左側にあります。</span><span class="sxs-lookup"><span data-stu-id="b0f32-120">The left margin is to the left of the line numbers.</span></span> <span data-ttu-id="b0f32-121">ブレークポイントを設定するもう 1 つの方法は、コード行にカーソルを置き、<kbd>F9</kbd> キーを押すことです。</span><span class="sxs-lookup"><span data-stu-id="b0f32-121">Another way to set a breakpoint is by placing the cursor in the line of code and then pressing <kbd>F9</kbd>.</span></span>

   <span data-ttu-id="b0f32-122">次の図に示すように、Visual Studio Code では左余白に赤い点を表示することで、ブレークポイントが設定されている行を示しています。</span><span class="sxs-lookup"><span data-stu-id="b0f32-122">As the following image shows, Visual Studio Code indicates the line on which the breakpoint is set by displaying a red dot in the left margin.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-set.png" alt-text="ブレークポイントの設定":::

## <a name="set-up-for-terminal-input"></a><span data-ttu-id="b0f32-124">ターミナル入力用の設定</span><span class="sxs-lookup"><span data-stu-id="b0f32-124">Set up for terminal input</span></span>

<span data-ttu-id="b0f32-125">ブレークポイントは、`Console.ReadLine` メソッドの呼び出しの後に配置されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-125">The breakpoint is located after a `Console.ReadLine` method call.</span></span> <span data-ttu-id="b0f32-126">**デバッグ コンソール** は、実行中のプログラムのターミナル入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="b0f32-126">The **Debug Console** doesn't accept terminal input for a running program.</span></span> <span data-ttu-id="b0f32-127">デバッグ中にターミナル入力を処理するには、統合ターミナル (Visual Studio Code ウィンドウの 1 つ) または外部ターミナルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-127">To handle terminal input while debugging, you can use the integrated terminal (one of the Visual Studio Code windows) or an external terminal.</span></span> <span data-ttu-id="b0f32-128">このチュートリアルでは、統合ターミナルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-128">For this tutorial, you use the integrated terminal.</span></span>

1. <span data-ttu-id="b0f32-129">*.vscode/launch.json* を開きます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-129">Open *.vscode/launch.json*.</span></span>

1. <span data-ttu-id="b0f32-130">`console` 設定を `integratedTerminal` に変更します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-130">Change the `console` setting to `integratedTerminal`.</span></span>

   <span data-ttu-id="b0f32-131">差出人:</span><span class="sxs-lookup"><span data-stu-id="b0f32-131">From:</span></span>

   ```
   "console": "internalConsole",
   ```

   <span data-ttu-id="b0f32-132">移動先:</span><span class="sxs-lookup"><span data-stu-id="b0f32-132">To:</span></span>

   ```
   "console": "integratedTerminal",
   ```

1. <span data-ttu-id="b0f32-133">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-133">Save your changes.</span></span>

## <a name="start-debugging"></a><span data-ttu-id="b0f32-134">[デバッグ開始]</span><span class="sxs-lookup"><span data-stu-id="b0f32-134">Start debugging</span></span>

1. <span data-ttu-id="b0f32-135">左側のメニューにある [デバッグ] アイコンを選択して、デバッグ ビューを開きます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-135">Open the Debug view by selecting the Debugging icon on the left side menu.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/select-debug-pane.png" alt-text="Visual Studio Code で [デバッグ] タブを開く":::

1. <span data-ttu-id="b0f32-137">ペインの上部にある **[.NET Core Launch (console)]\(.NET Core の起動 (コンソール)\)** の横の緑色の矢印を選択してデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-137">Start debugging by selecting the green arrow at the top of the pane, next to **.NET Core Launch (console)**.</span></span>  <span data-ttu-id="b0f32-138">デバッグを開始するもう 1 つの方法は、<kbd>F5</kbd> キーを押すことです。</span><span class="sxs-lookup"><span data-stu-id="b0f32-138">Another way to start debugging is by pressing <kbd>F5</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/start-debugging.png" alt-text="デバッグの開始":::

1. <span data-ttu-id="b0f32-140">**[ターミナル]** タブを選択すると、"What is your name?" (あなたのお名前は?) の</span><span class="sxs-lookup"><span data-stu-id="b0f32-140">Select the **Terminal** tab to see the "What is your name?"</span></span> <span data-ttu-id="b0f32-141">プロンプトが表示されます。これは応答を待機する前にプログラムによって表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-141">prompt that the program displays before waiting for a response.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/select-terminal.png" alt-text="[ターミナル] タブを選択":::

1. <span data-ttu-id="b0f32-143">名前のプロンプトに応答する文字列を **[ターミナル]** ウィンドウに入力し、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-143">Enter a string in the **Terminal** window in response to the prompt for a name, and then press <kbd>Enter</kbd>.</span></span>

   <span data-ttu-id="b0f32-144">プログラムがブレークポイントに到達すると、プログラム実行は停止します。`Console.WriteLine` メソッドが実行される前にも停止します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-144">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="b0f32-145">**[変数]** ウィンドウの **[ローカル]** セクションには、現在実行しているメソッドで定義されている変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-145">The **Locals** section of the **Variables** window displays the values of variables that are defined in the currently executing method.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-hit.png" alt-text="ブレークポイントのヒット、ローカルの表示":::

## <a name="change-variable-values"></a><span data-ttu-id="b0f32-147">変数の値の変更</span><span class="sxs-lookup"><span data-stu-id="b0f32-147">Change variable values</span></span>

<span data-ttu-id="b0f32-148">**[デバッグ コンソール]** ウィンドウでは、デバッグ中のアプリケーションと対話できます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-148">The **Debug Console** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="b0f32-149">変数の値を変更して、プログラムにどのような影響があるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-149">You can change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="b0f32-150">**[デバッグ コンソール]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-150">Select the **Debug Console** tab.</span></span>

1. <span data-ttu-id="b0f32-151">**[デバッグ コンソール]** ウィンドウの下部にあるプロンプトで `name = "Gracie"` を入力し、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-151">Enter `name = "Gracie"` at the prompt at the bottom of the **Debug Console** window and press the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/change-variable-values.png" alt-text="変数の値の変更":::

1. <span data-ttu-id="b0f32-153">**[デバッグ コンソール]** ウィンドウの下部に `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` を入力し、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-153">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` at the bottom of the **Debug Console** window and press the <kbd>Enter</kbd> key.</span></span>

   <span data-ttu-id="b0f32-154">**[変数]** ウィンドウには、`name` 変数と `date` 変数の新しい値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-154">The **Variables** window displays the new values of the `name` and `date` variables.</span></span>

1. <span data-ttu-id="b0f32-155">ツール バーの **[続行]** ボタンを選択して、プログラムの実行を続けます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-155">Continue program execution by selecting the **Continue** button in the toolbar.</span></span> <span data-ttu-id="b0f32-156">続行するもう 1 つの方法は、<kbd>F5</kbd> キーを押すことです。</span><span class="sxs-lookup"><span data-stu-id="b0f32-156">Another way to continue is by pressing <kbd>F5</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/continue-debugging.png" alt-text="デバッグの続行":::

1. <span data-ttu-id="b0f32-158">もう一度 **[ターミナル]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-158">Select the **Terminal** tab again.</span></span>

   <span data-ttu-id="b0f32-159">コンソール ウィンドウに表示される値は、 **[デバッグ コンソール]** で行った変更に対応しています。</span><span class="sxs-lookup"><span data-stu-id="b0f32-159">The values displayed in the console window correspond to the changes you made in the **Debug Console**.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/changed-variable-values.png" alt-text="入力した値を示すターミナル":::

1. <span data-ttu-id="b0f32-161">任意のキーを押してアプリケーションを終了し、デバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-161">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="b0f32-162">条件付きブレークポイントの設定</span><span class="sxs-lookup"><span data-stu-id="b0f32-162">Set a conditional breakpoint</span></span>

<span data-ttu-id="b0f32-163">プログラムによって、ユーザーが入力した文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-163">The program displays the string that the user enters.</span></span> <span data-ttu-id="b0f32-164">ユーザーが何も入力しないとどうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="b0f32-164">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="b0f32-165">これは、"*条件付きブレークポイント*" と呼ばれる便利なデバッグ機能を使用してテストできます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-165">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="b0f32-166">ブレークポイントを表す赤い点を右クリック (macOS では <kbd>Ctrl</kbd> キーを押しながらクリック) します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-166">Right-click (<kbd>Ctrl</kbd>+click on macOS) on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="b0f32-167">コンテキスト メニューで **[ブレークポイントの編集]** を選択して、条件式を入力するためのダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-167">In the context menu, select **Edit Breakpoint** to open a dialog that lets you enter a conditional expression.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-context-menu.png" alt-text="ブレークポイント コンテキスト メニュー":::

1. <span data-ttu-id="b0f32-169">ドロップダウン リストで [`Expression`] を選択し、次の条件式を入力して、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-169">Select `Expression` in the drop-down, enter the following conditional expression, and press <kbd>Enter</kbd>.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/conditional-expression.png" alt-text="条件式の入力":::

   <span data-ttu-id="b0f32-171">ブレークポイントにヒットするたびに、デバッガーは `String.IsNullOrEmpty(name)` メソッドを呼び出し、メソッド呼び出しが `true` を返す場合にのみ、この行で中断します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-171">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="b0f32-172">条件式の代わりに、ステートメントが指定回数だけ実行される前にプログラムの実行を中断する "*ヒット カウント*"、またはスレッド識別子、プロセス名、スレッド名などの属性に基づいてプログラムの実行を中断する "*フィルター条件*" を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-172">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="b0f32-173"><kbd>F5</kbd> を押して、デバッグとともにプログラムを開始します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-173">Start the program with debugging by pressing <kbd>F5</kbd>.</span></span>

1. <span data-ttu-id="b0f32-174">**[ターミナル]** タブで、自分の名前を入力するように求められたら、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-174">In the **Terminal** tab, press the <kbd>Enter</kbd> key when prompted to enter your name.</span></span>

   <span data-ttu-id="b0f32-175">指定した条件 (`name` が `null` または <xref:System.String.Empty?displayProperty=nameWithType>) が満たされたため、ブレークポイントに到達すると、`Console.WriteLine` メソッドが実行される前に、プログラムの実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-175">Because the condition you specified (`name` is `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

   <span data-ttu-id="b0f32-176">**[変数]** ウィンドウには、`name` 変数の値が `""` または <xref:System.String.Empty?displayProperty=nameWithType> であることが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-176">The **Variables** window shows that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="b0f32-177">**デバッグ コンソール** プロンプトで次のステートメントを入力し、<kbd>Enter</kbd> キーを押して、値が空の文字列であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-177">Confirm the value is an empty string by entering the following statement at the **Debug Console** prompt and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="b0f32-178">結果は `true` になります。</span><span class="sxs-lookup"><span data-stu-id="b0f32-178">The result is `true`.</span></span>

   ```csharp
   name == String.Empty
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/expression-in-debug-console.png" alt-text="ステートメントの実行後に true の値を返すデバッグ コンソール":::

1. <span data-ttu-id="b0f32-180">ツール バーの **[続行]** を選んで、プログラムの実行を続けます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-180">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="b0f32-181">**[ターミナル]** タブを選択し、任意のキーを押してプログラムを終了し、デバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-181">Select the **Terminal** tab, and press any key to exit the program and stop debugging.</span></span>

1. <span data-ttu-id="b0f32-182">コード ウィンドウの左余白のドットをクリックして、ブレークポイントをクリアします。</span><span class="sxs-lookup"><span data-stu-id="b0f32-182">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="b0f32-183">ブレークポイントをクリアするもう 1 つの方法は、コード行が選択されている間に <kbd>F9</kbd> キーを押すことです。</span><span class="sxs-lookup"><span data-stu-id="b0f32-183">Another way to clear a breakpoint is by pressing <kbd>F9</kbd> while the line of code is selected.</span></span>

1. <span data-ttu-id="b0f32-184">ブレークポイントの条件が失われることを示す警告が表示された場合は、 **[ブレークポイントの削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-184">If you get a warning that the breakpoint condition will be lost, select **Remove Breakpoint**.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="b0f32-185">プログラムのステップ実行</span><span class="sxs-lookup"><span data-stu-id="b0f32-185">Step through a program</span></span>

<span data-ttu-id="b0f32-186">Visual Studio Code では、1 行ずつプログラムをステップ実行して、実行を監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-186">Visual Studio Code also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="b0f32-187">通常は、ブレークポイントを設定して、プログラム コードのごく一部を通じてプログラム フローに従います。</span><span class="sxs-lookup"><span data-stu-id="b0f32-187">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="b0f32-188">このプログラムは小さいため、次の手順に従ってプログラム全体をステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-188">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="b0f32-189">`Main` メソッドの左中かっこにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-189">Set a breakpoint on the opening curly brace of the `Main` method.</span></span>

1. <span data-ttu-id="b0f32-190"><kbd>F5</kbd> キーを押してデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-190">Press <kbd>F5</kbd> to start debugging.</span></span>

   <span data-ttu-id="b0f32-191">Visual Studio Code では、ブレークポイント行が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-191">Visual Studio Code highlights the breakpoint line.</span></span>

   <span data-ttu-id="b0f32-192">この時点で、 **[変数]** ウィンドウに `args` 配列が空であることが示され、`name` と `date` には既定値が設定されています。</span><span class="sxs-lookup"><span data-stu-id="b0f32-192">At this point, the **Variables** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span>

1. <span data-ttu-id="b0f32-193">**[ステップ イン]** を選ぶか、<kbd>F11</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-193">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/step-into.png" alt-text="[ステップイン] ボタン":::

   <span data-ttu-id="b0f32-195">Visual Studio Code では次の行が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-195">Visual Studio Code highlights the next line.</span></span>

1. <span data-ttu-id="b0f32-196">**[ステップ イン]** を選ぶか、<kbd>F11</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-196">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="b0f32-197">Visual Studio Code では、名前プロンプトの `Console.WriteLine` が実行され、次に実行される行が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-197">Visual Studio Code executes the `Console.WriteLine` for the name prompt and highlights the next line of execution.</span></span> <span data-ttu-id="b0f32-198">次の行は、`name` の `Console.ReadLine` です。</span><span class="sxs-lookup"><span data-stu-id="b0f32-198">The next line is the `Console.ReadLine` for the `name`.</span></span> <span data-ttu-id="b0f32-199">**[変数]** ウィンドウは変更されず、 **[ターミナル]** タブに "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="b0f32-199">The **Variables** window is unchanged, and the **Terminal** tab shows the "What is your name?"</span></span> <span data-ttu-id="b0f32-200">プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-200">prompt.</span></span>

1. <span data-ttu-id="b0f32-201">**[ステップ イン]** を選ぶか、<kbd>F11</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-201">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="b0f32-202">Visual Studio によって、`name` 変数代入が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-202">Visual Studio highlights the `name` variable assignment.</span></span> <span data-ttu-id="b0f32-203">**[変数]** ウィンドウに、`name` がまだ `null` であることが示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-203">The **Variables** window shows that `name` is still `null`.</span></span>

1. <span data-ttu-id="b0f32-204">[ターミナル] タブに文字列を入力し、<kbd>Enter</kbd> キーを押して、このプロンプトに応答します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-204">Respond to the prompt by entering a string in the Terminal tab and pressing <kbd>Enter</kbd>.</span></span>

   <span data-ttu-id="b0f32-205">**[ターミナル]** タブには、入力時に入力した文字列が表示されない場合がありますが、<xref:System.Console.ReadLine%2A?displayProperty=nameWithType> メソッドによって入力がキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-205">The **Terminal** tab might not display the string you enter while you're entering it, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will capture your input.</span></span>

1. <span data-ttu-id="b0f32-206">**[ステップ イン]** を選ぶか、<kbd>F11</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-206">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="b0f32-207">Visual Studio Code によって、`date` 変数代入が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-207">Visual Studio Code highlights the `date` variable assignment.</span></span> <span data-ttu-id="b0f32-208">**[変数]** ウィンドウには、<xref:System.Console.ReadLine%2A?displayProperty=nameWithType> メソッドの呼び出しによって返された値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-208">The **Variables** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b0f32-209">**[ターミナル]** タブには、プロンプトで入力した文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-209">The **Terminal** tab displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="b0f32-210">**[ステップ イン]** を選ぶか、<kbd>F11</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-210">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="b0f32-211">**[変数]** ウィンドウには、<xref:System.DateTime.Now?displayProperty=nameWithType> プロパティから代入された後の `date` 変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-211">The **Variables** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span>

1. <span data-ttu-id="b0f32-212">**[ステップ イン]** を選ぶか、<kbd>F11</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-212">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="b0f32-213">Visual Studio Code によって <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-213">Visual Studio Code calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b0f32-214">コンソール ウィンドウには書式設定された文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-214">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="b0f32-215">**[ステップ アウト]** を選択するか、<kbd>Shift</kbd>+<kbd>F11</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-215">Select **Step Out** or press <kbd>Shift</kbd>+<kbd>F11</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/step-out.png" alt-text="[ステップアウト] ボタン":::

1. <span data-ttu-id="b0f32-217">**[ターミナル]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-217">Select the **Terminal** tab.</span></span>

   <span data-ttu-id="b0f32-218">ターミナルに、"Press any key to exit..." (終了するには何かキーを押してください...) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0f32-218">The terminal displays "Press any key to exit..."</span></span>

1. <span data-ttu-id="b0f32-219">任意のキーを押してプログラムを終了します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-219">Press any key to exit the program.</span></span>

## <a name="select-release-build-configuration"></a><span data-ttu-id="b0f32-220">リリース ビルド構成の選択</span><span class="sxs-lookup"><span data-stu-id="b0f32-220">Select Release build configuration</span></span>

<span data-ttu-id="b0f32-221">アプリケーションのデバッグ バージョンのテストが終了したら、リリース バージョンもコンパイルしてテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0f32-221">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="b0f32-222">リリース バージョンには、アプリケーションの動作に影響を与える可能性があるコンパイラの最適化が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="b0f32-222">The Release version incorporates compiler optimizations that can affect the behavior of an application.</span></span> <span data-ttu-id="b0f32-223">たとえば、パフォーマンスを向上させるように設計されたコンパイラの最適化では、マルチスレッド アプリケーションで競合状態が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b0f32-223">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="b0f32-224">コンソール アプリケーションのリリース バージョンをビルドしてテストするには、**ターミナル**を開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-224">To build and test the Release version of your console application, open the **Terminal** and run the following command:</span></span>

```dotnetcli
dotnet run --configuration Release
```

## <a name="additional-resources"></a><span data-ttu-id="b0f32-225">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="b0f32-225">Additional resources</span></span>

* [<span data-ttu-id="b0f32-226">Visual Studio Code でのデバッグ</span><span class="sxs-lookup"><span data-stu-id="b0f32-226">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/docs/editor/debugging)

## <a name="next-steps"></a><span data-ttu-id="b0f32-227">次の手順</span><span class="sxs-lookup"><span data-stu-id="b0f32-227">Next steps</span></span>

<span data-ttu-id="b0f32-228">このチュートリアルでは、Visual Studio Code のデバッグ ツールを使用しました。</span><span class="sxs-lookup"><span data-stu-id="b0f32-228">In this tutorial, you used Visual Studio Code debugging tools.</span></span> <span data-ttu-id="b0f32-229">次のチュートリアルでは、アプリの展開可能なバージョンを発行します。</span><span class="sxs-lookup"><span data-stu-id="b0f32-229">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b0f32-230">Visual Studio Code を使用して .NET Core コンソール アプリケーションを発行する</span><span class="sxs-lookup"><span data-stu-id="b0f32-230">Publish a .NET Core console application with Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
