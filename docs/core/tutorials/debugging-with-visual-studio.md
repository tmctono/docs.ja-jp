---
title: Visual Studio を使用して .NET Core コンソール アプリケーションをデバッグする
description: Visual Studio を使用して .NET Core コンソール アプリをデバッグする方法について説明します。
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4bd2a8a0e4b3cea55e209306dd3788552e4b61f3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005415"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio"></a><span data-ttu-id="6246c-103">チュートリアル: Visual Studio を使用して .NET Core コンソール アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="6246c-103">Tutorial: Debug a .NET Core console application using Visual Studio</span></span>

<span data-ttu-id="6246c-104">このチュートリアルでは、Visual Studio で使用できるデバッグ ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6246c-104">This tutorial introduces the debugging tools available in Visual Studio.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6246c-105">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6246c-105">Prerequisites</span></span>

- <span data-ttu-id="6246c-106">このチュートリアルでは、[Visual Studio 2019 での .NET Core コンソール アプリケーションの作成](with-visual-studio.md)に関するページで作成した、コンソール アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="6246c-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="debug-build-configuration"></a><span data-ttu-id="6246c-107">デバッグ ビルド構成</span><span class="sxs-lookup"><span data-stu-id="6246c-107">Debug build configuration</span></span>

<span data-ttu-id="6246c-108">"*デバッグ*" と "*リリース*" は、 Visual Studio に 2 つある既定のビルド構成です。</span><span class="sxs-lookup"><span data-stu-id="6246c-108">*Debug* and *Release* are two of Visual Studio's default build configurations.</span></span> <span data-ttu-id="6246c-109">現時点のビルド構成はツールバーに表示されています。</span><span class="sxs-lookup"><span data-stu-id="6246c-109">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="6246c-110">次のツール バーの画像では、アプリのデバッグ バージョンをコンパイルするように Visual Studio が構成されています。</span><span class="sxs-lookup"><span data-stu-id="6246c-110">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

![デバッグが強調表示された Visual Studio のツールバー](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

<span data-ttu-id="6246c-112">まず、アプリのデバッグ バージョンを実行します。</span><span class="sxs-lookup"><span data-stu-id="6246c-112">Begin by running the Debug version of the app.</span></span> <span data-ttu-id="6246c-113">デバッグ ビルド構成では、コンパイラのほとんどの最適化がオフになり、ビルド プロセスの間に豊富な情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-113">The Debug build configuration turns off most compiler optimizations and provides richer information during the build process.</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="6246c-114">ブレークポイントの設定</span><span class="sxs-lookup"><span data-stu-id="6246c-114">Set a breakpoint</span></span>

<!-- markdownlint-disable MD025 -->

1. <span data-ttu-id="6246c-115">名前、日付、時刻を表示する行のコード ウィンドウの左側の余白をクリックして、その行に "*ブレークポイント*" 設定します。</span><span class="sxs-lookup"><span data-stu-id="6246c-115">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="6246c-116">ブレークポイントを設定するもう 1 つの方法は、コード行にカーソルを置き、**F9** キーを押すか、メニュー バーから **[デバッグ]**  >  **[ブレークポイントの設定/解除]** を選択することです。</span><span class="sxs-lookup"><span data-stu-id="6246c-116">Another way to set a breakpoint is by placing the cursor in the line of code and then pressing **F9** or choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="6246c-117">ブレークポイントが設定された行が実行される "*前*" に、アプリケーションの実行がブレークポイントにより一時的に中断されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-117">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

   <span data-ttu-id="6246c-118">次の図のとおり、Visual Studio では、ブレークポイントが設定された行を強調表示し、左端の余白に赤い点を表示することで、その行を示しています。</span><span class="sxs-lookup"><span data-stu-id="6246c-118">As the following image shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   ![ブレークポイントが設定された Visual Studio のプログラム ウィンドウ](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. <span data-ttu-id="6246c-120">ツールバー上の緑色の矢印の付いた **[HelloWorld]** ボタンを選択して、プログラムをデバッグ モードで実行します。</span><span class="sxs-lookup"><span data-stu-id="6246c-120">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar.</span></span> <span data-ttu-id="6246c-121">デバッグを開始するその他の方法は、**F5** キーを押すか、 **[デバッグ]**  >  **[デバッグの開始]** を選択することです。</span><span class="sxs-lookup"><span data-stu-id="6246c-121">Other ways to start debugging are by pressing **F5** or by choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="6246c-122">プログラムが名前の入力を求めたら、コンソール ウィンドウに文字列を入力して、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6246c-122">Enter a string in the console window when the program prompts for a name, and then press **Enter**.</span></span>

1. <span data-ttu-id="6246c-123">プログラムがブレークポイントに到達すると、プログラム実行は停止します。`Console.WriteLine` メソッドが実行される前にも停止します。</span><span class="sxs-lookup"><span data-stu-id="6246c-123">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="6246c-124">**[ローカル]** ウィンドウには、現在実行しているメソッドで定義されている変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-124">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

   ![Visual Studio でのブレークポイントのスクリーンショット](./media/debugging-with-visual-studio/breakpoint-hit.png)

1. <span data-ttu-id="6246c-126">**[イミディエイト]** ウィンドウでは、デバッグ中のアプリケーションと対話できます。</span><span class="sxs-lookup"><span data-stu-id="6246c-126">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="6246c-127">変数の値を対話的に変更して、プログラムにどのような影響があるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6246c-127">You can interactively change the value of variables to see how it affects your program.</span></span>

   1. <span data-ttu-id="6246c-128">**[イミディエイト]** ウィンドウが表示されない場合は、 **[デバッグ]**  >  **[Windows]**  >  **[イミディエイト]** の順に選択して表示します。</span><span class="sxs-lookup"><span data-stu-id="6246c-128">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

   1. <span data-ttu-id="6246c-129">**[イミディエイト]** ウィンドウに「`name = "Gracie"`」と入力して、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6246c-129">Enter `name = "Gracie"` in the **Immediate** window and press the **Enter** key.</span></span>

   1. <span data-ttu-id="6246c-130">**[イミディエイト]** ウィンドウに「`date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()`」と入力して、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6246c-130">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` in the **Immediate** window and press the **Enter** key.</span></span>

   <span data-ttu-id="6246c-131">**[イミディエイト]** ウィンドウに、文字列変数の値と、<xref:System.DateTime> 値のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-131">The **Immediate** window displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="6246c-132">さらに、変数の値は **[ローカル]** ウィンドウで更新されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-132">In addition, the values of the variables are updated in the **Locals** window.</span></span>

   ![Visual Studio 2019 の [ローカル] と [イミディエイト] ウィンドウ](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. <span data-ttu-id="6246c-134">ツール バーの **[続行]** ボタンを選択して、プログラムの実行を続けます。</span><span class="sxs-lookup"><span data-stu-id="6246c-134">Continue program execution by selecting the **Continue** button in the toolbar.</span></span> <span data-ttu-id="6246c-135">続行するもう 1 つの方法は、 **[デバッグ]**  >  **[続行]** を選択することです。</span><span class="sxs-lookup"><span data-stu-id="6246c-135">Another way to continue is by choosing **Debug** > **Continue**.</span></span>

   <span data-ttu-id="6246c-136">コンソール ウィンドウに表示される値は、 **[イミディエイト]** ウィンドウで行った変更に対応しています。</span><span class="sxs-lookup"><span data-stu-id="6246c-136">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   ![入力した値が表示されているコンソール ウィンドウ](./media/debugging-with-visual-studio/console-window.png)

1. <span data-ttu-id="6246c-138">任意のキーを押してアプリケーションを終了し、デバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="6246c-138">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="6246c-139">条件付きブレークポイントの設定</span><span class="sxs-lookup"><span data-stu-id="6246c-139">Set a conditional breakpoint</span></span>

<span data-ttu-id="6246c-140">プログラムによって、ユーザーが入力した文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-140">The program displays the string that the user enters.</span></span> <span data-ttu-id="6246c-141">ユーザーが何も入力しないとどうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="6246c-141">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="6246c-142">これは、"*条件付きブレークポイント*" と呼ばれる便利なデバッグ機能を使ってテストできます。この機能は、1 つまたは複数の条件が満たされたときにプログラムの実行をブレークします。</span><span class="sxs-lookup"><span data-stu-id="6246c-142">You can test this with a useful debugging feature called a *conditional breakpoint*, which breaks program execution when one or more conditions are met.</span></span>

<span data-ttu-id="6246c-143">条件付きブレークポイントを設定して、ユーザーが文字列の入力に失敗したときに何が起こるかをテストするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6246c-143">To set a conditional breakpoint and test what happens when the user fails to enter a string, do the following:</span></span>

1. <span data-ttu-id="6246c-144">ブレークポイントを表す赤丸を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="6246c-144">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="6246c-145">コンテキスト メニューで **[条件]** を選んで、 **[ブレークポイント設定]** ダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="6246c-145">In the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="6246c-146">**[条件]** のチェック ボックスをオンにします (まだオンになっていない場合)。</span><span class="sxs-lookup"><span data-stu-id="6246c-146">Select the box for **Conditions** if it's not already selected.</span></span>

   ![[ブレークポイント設定] パネルが表示されているエディター - C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. <span data-ttu-id="6246c-148">**[条件式]** には、`x` が 5 かどうかをテストするコード例を示す次のコードをフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="6246c-148">For the **Conditional Expression**, enter the following code in the field that shows example code that tests if `x` is 5.</span></span> <span data-ttu-id="6246c-149">使用する言語が表示されていない場合は、ページの上部にある言語セレクターを変更します。</span><span class="sxs-lookup"><span data-stu-id="6246c-149">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="6246c-150">ブレークポイントにヒットするたびに、デバッガーは `String.IsNullOrEmpty(name)` メソッドを呼び出し、メソッド呼び出しが `true` を返す場合にのみ、この行で中断します。</span><span class="sxs-lookup"><span data-stu-id="6246c-150">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="6246c-151">条件式の代わりに、ステートメントが指定回数だけ実行される前にプログラムの実行を中断する "*ヒット カウント*"、またはスレッド識別子、プロセス名、スレッド名などの属性に基づいてプログラムの実行を中断する "*フィルター条件*" を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="6246c-151">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="6246c-152">**[閉じる]** を選択して、ダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6246c-152">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="6246c-153">**F5** を押して、デバッグとともにプログラムを開始します。</span><span class="sxs-lookup"><span data-stu-id="6246c-153">Start the program with debugging by pressing **F5**.</span></span>

1. <span data-ttu-id="6246c-154">コンソール ウィンドウで、名前の入力を求められたら、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6246c-154">In the console window, press the **Enter** key when prompted to enter your name.</span></span>

1. <span data-ttu-id="6246c-155">指定した条件 (`name` は `null` または <xref:System.String.Empty?displayProperty=nameWithType> のどちらか) が満たされたため、ブレークポイントに到達すると、`Console.WriteLine` メソッドが実行される前に、プログラムの実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="6246c-155">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="6246c-156">**[ローカル]** ウィンドウを選ぶと、現在実行しているメソッドに対してローカルな変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-156">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="6246c-157">この場合、`Main` は現在実行中のメソッドです。</span><span class="sxs-lookup"><span data-stu-id="6246c-157">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="6246c-158">`name` 変数の値が `""` または <xref:System.String.Empty?displayProperty=nameWithType> であることを調べます。</span><span class="sxs-lookup"><span data-stu-id="6246c-158">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="6246c-159">**[イミディエイト]** ウィンドウに次のステートメントを入力し、**Enter** キーを押して、値が空の文字列であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6246c-159">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing **Enter**.</span></span> <span data-ttu-id="6246c-160">結果は `true` になります。</span><span class="sxs-lookup"><span data-stu-id="6246c-160">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="6246c-161">疑問符は、イミディエイト ウィンドウに、[式を評価](/visualstudio/ide/reference/immediate-window#enter-commands)するように指示します。</span><span class="sxs-lookup"><span data-stu-id="6246c-161">The question mark directs the immediate window to [evaluate an expression](/visualstudio/ide/reference/immediate-window#enter-commands).</span></span>

   ![ステートメントが実行された後で値 true を返す [イミディエイト ウィンドウ] - C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. <span data-ttu-id="6246c-163">ツール バーの **[続行]** を選んで、プログラムの実行を続けます。</span><span class="sxs-lookup"><span data-stu-id="6246c-163">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="6246c-164">任意のキーを押してコンソール ウィンドウを閉じ、デバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="6246c-164">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="6246c-165">コード ウィンドウの左端の余白のドットをクリックして、ブレークポイントをクリアします。</span><span class="sxs-lookup"><span data-stu-id="6246c-165">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="6246c-166">ブレークポイントをクリアするもう 1 つの方法は、コード行が選択されている間に **[デバッグ] > [ブレークポイントの設定/解除]** を選択することです。</span><span class="sxs-lookup"><span data-stu-id="6246c-166">Another way to clear a breakpoint is by choosing **Debug > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="6246c-167">プログラムのステップ実行</span><span class="sxs-lookup"><span data-stu-id="6246c-167">Step through a program</span></span>

<span data-ttu-id="6246c-168">Visual Studio では、1 行ずつプログラムをステップ実行して、実行を監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="6246c-168">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="6246c-169">通常は、ブレークポイントを設定して、プログラム コードのごく一部を通じてプログラム フローに従います。</span><span class="sxs-lookup"><span data-stu-id="6246c-169">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="6246c-170">プログラムが小さいため、次の手順に従ってプログラム全体をステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="6246c-170">Since your program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="6246c-171">**[デバッグ]**  >  **[ステップ イン]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="6246c-171">Choose **Debug** > **Step Into**.</span></span> <span data-ttu-id="6246c-172">1 つのステートメントを一度にデバッグするもう 1 つの方法は、**F11** キーを押すことです。</span><span class="sxs-lookup"><span data-stu-id="6246c-172">Another way to debug one statement at a time is by pressing **F11**.</span></span>

   <span data-ttu-id="6246c-173">次に実行される行が強調表示されて、横に矢印が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-173">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   <span data-ttu-id="6246c-174">C#</span><span class="sxs-lookup"><span data-stu-id="6246c-174">C#</span></span>

   ![Visual Studio のステップ イン メソッド - C#](./media/debugging-with-visual-studio/step-into-method.png)

   <span data-ttu-id="6246c-176">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6246c-176">Visual Basic</span></span>

   ![Visual Studio のステップ イン メソッド - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   <span data-ttu-id="6246c-178">この時点で、 **[ローカル]** ウィンドウに `args` 配列が空であることが示され、`name` と `date` には既定値が設定されています。</span><span class="sxs-lookup"><span data-stu-id="6246c-178">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="6246c-179">さらに、空のコンソール ウィンドウが開かれています。</span><span class="sxs-lookup"><span data-stu-id="6246c-179">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="6246c-180">**F11** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6246c-180">Press **F11**.</span></span> <span data-ttu-id="6246c-181">次に実行される行が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-181">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="6246c-182">**[ローカル]** ウィンドウは変更されず、コンソール ウィンドウは空白のままになります。</span><span class="sxs-lookup"><span data-stu-id="6246c-182">The **Locals** window is unchanged, and the console window remains blank.</span></span>

   <span data-ttu-id="6246c-183">C#</span><span class="sxs-lookup"><span data-stu-id="6246c-183">C#</span></span>

   ![Visual Studio のステップ イン メソッド ソース - C#](./media/debugging-with-visual-studio/step-into-source-method.png)

   <span data-ttu-id="6246c-185">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6246c-185">Visual Basic</span></span>

   ![Visual Studio のステップ イン メソッド ソース - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. <span data-ttu-id="6246c-187">**F11** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6246c-187">Press **F11**.</span></span> <span data-ttu-id="6246c-188">`name` の変数代入を含むステートメントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-188">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="6246c-189">**[ローカル]** ウィンドウに `name` が `null` であると表示され、コンソール ウィンドウに "What is your name?" という文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-189">The **Locals** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="6246c-190">コンソール ウィンドウに文字列を入力し、**Enter** キーを押して、このプロンプトに応答します。</span><span class="sxs-lookup"><span data-stu-id="6246c-190">Respond to the prompt by entering a string in the console window and pressing **Enter**.</span></span> <span data-ttu-id="6246c-191">コンソールは応答せず、入力した文字列はコンソール ウィンドウに表示されませんが、それでも <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> メソッドにより入力が取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="6246c-191">The console is unresponsive, and the string you entered isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="6246c-192">**F11** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6246c-192">Press **F11**.</span></span> <span data-ttu-id="6246c-193">Visual Studio によって、`date` 変数代入 (Visual Basic では `currentDate`) を含むステートメントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-193">Visual Studio highlights the statement that includes the `date` variable assignment (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="6246c-194">**[ローカル]** ウィンドウには、<xref:System.Console.ReadLine%2A?displayProperty=nameWithType> メソッドの呼び出しによって返された値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-194">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6246c-195">コンソール ウィンドウには、プロンプトで入力した文字列も表示されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-195">The console window also displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="6246c-196">**F11** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6246c-196">Press **F11**.</span></span> <span data-ttu-id="6246c-197">**[ローカル]** ウィンドウには、<xref:System.DateTime.Now?displayProperty=nameWithType> プロパティから代入された後の `date` 変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-197">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="6246c-198">コンソール ウィンドウに変更はありません。</span><span class="sxs-lookup"><span data-stu-id="6246c-198">The console window is unchanged.</span></span>

1. <span data-ttu-id="6246c-199">**F11** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6246c-199">Press **F11**.</span></span> <span data-ttu-id="6246c-200">Visual Studio は、<xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6246c-200">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6246c-201">コンソール ウィンドウには書式設定された文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6246c-201">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="6246c-202">**[デバッグ]**  >  **[ステップ アウト]** の順に選択します。ステップ バイ ステップの実行を停止するもう 1 つの方法は、**Shift**+**F11** キーを押すことです。</span><span class="sxs-lookup"><span data-stu-id="6246c-202">Choose **Debug** > **Step Out**. Another way to stop step-by-step execution is by pressing **Shift**+**F11**.</span></span>

   <span data-ttu-id="6246c-203">コンソール ウィンドウにメッセージが表示され、任意のキーを押すよう求められます。</span><span class="sxs-lookup"><span data-stu-id="6246c-203">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="6246c-204">任意のキーを押してコンソール ウィンドウを閉じ、デバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="6246c-204">Press any key to close the console window and stop debugging.</span></span>

## <a name="build-a-release-version"></a><span data-ttu-id="6246c-205">リリース バージョンのビルド</span><span class="sxs-lookup"><span data-stu-id="6246c-205">Build a Release version</span></span>

<span data-ttu-id="6246c-206">アプリケーションのデバッグ バージョンのテストが終了したら、リリース バージョンもコンパイルしてテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6246c-206">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="6246c-207">リリース バージョンには、アプリケーションの動作に悪影響を与える可能性があるコンパイラの最適化が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="6246c-207">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="6246c-208">たとえば、パフォーマンスを向上させるように設計されたコンパイラの最適化では、マルチスレッド アプリケーションで競合状態が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6246c-208">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="6246c-209">コンソール アプリケーションのリリース バージョンをビルドしてテストするには、ツール バーのビルド構成を **[デバッグ]** から **[リリース]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="6246c-209">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

![デバッグが強調表示された Visual Studio の既定のツールバー](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

<span data-ttu-id="6246c-211">**F5** キーを押すか、 **[ビルド]** メニューの **[ソリューションのビルド]** を選ぶと、アプリケーションのリリース バージョンが Visual Studio でコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="6246c-211">When you press **F5** or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of the application.</span></span> <span data-ttu-id="6246c-212">それをデバッグ バージョンと同様にテストできます。</span><span class="sxs-lookup"><span data-stu-id="6246c-212">You can test it as you did the Debug version.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6246c-213">次の手順</span><span class="sxs-lookup"><span data-stu-id="6246c-213">Next steps</span></span>

<span data-ttu-id="6246c-214">このチュートリアルでは、Visual Studio のデバッグ ツールを使用しました。</span><span class="sxs-lookup"><span data-stu-id="6246c-214">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="6246c-215">次のチュートリアルでは、アプリの展開可能なバージョンを発行します。</span><span class="sxs-lookup"><span data-stu-id="6246c-215">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6246c-216">Visual Studio での .NET Core コンソール アプリケーションの発行</span><span class="sxs-lookup"><span data-stu-id="6246c-216">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
