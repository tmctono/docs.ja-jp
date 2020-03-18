---
title: Visual Studio を使用して Hello World .NET Core アプリケーションをデバッグする
description: C# または Visual Basic で記述された Hello World アプリを、Visual Studio を使用してデバッグする方法についてご説明します。
ms.date: 12/05/2019
ms.custom: vs-dotnet
ms.openlocfilehash: b2ee1401fc89f990c5f930d80d1a510a117e63a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156674"
---
# <a name="debug-your-c-or-visual-basic-net-core-hello-world-application-using-visual-studio"></a><span data-ttu-id="009dd-103">Visual Studio を使用して C# または Visual Basic .NET Core の Hello World アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="009dd-103">Debug your C# or Visual Basic .NET Core Hello World application using Visual Studio</span></span>

<span data-ttu-id="009dd-104">ここまでは、「[Visual Studio 2019 で最初の .NET Core コンソール アプリケーションを作成する](with-visual-studio.md)」の手順に従って、簡単なコンソール アプリケーションを作成して実行しました。</span><span class="sxs-lookup"><span data-stu-id="009dd-104">So far, you've followed the steps in [Create your first .NET Core console application in Visual Studio 2019](with-visual-studio.md) to create and run a simple console application.</span></span> <span data-ttu-id="009dd-105">アプリケーションを記述してコンパイルしたら、テストを開始できます。</span><span class="sxs-lookup"><span data-stu-id="009dd-105">Once you've written and compiled your application, you can begin testing it.</span></span> <span data-ttu-id="009dd-106">Visual Studio には、アプリケーションのトラブルシューティングに使用できるデバッグ ツールの包括的なセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="009dd-106">Visual Studio includes a comprehensive set of debugging tools that you can use to troubleshoot your application.</span></span>

## <a name="debug-build-configuration"></a><span data-ttu-id="009dd-107">デバッグ ビルド構成</span><span class="sxs-lookup"><span data-stu-id="009dd-107">Debug build configuration</span></span>

<span data-ttu-id="009dd-108">"*デバッグ*" と "*リリース*" は、 Visual Studio に 2 つある既定のビルド構成です。</span><span class="sxs-lookup"><span data-stu-id="009dd-108">*Debug* and *Release* are two of Visual Studio's default build configurations.</span></span> <span data-ttu-id="009dd-109">現時点のビルド構成はツールバーに表示されています。</span><span class="sxs-lookup"><span data-stu-id="009dd-109">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="009dd-110">次のツール バーの画像では、アプリのデバッグ バージョンをコンパイルするように Visual Studio が構成されています。</span><span class="sxs-lookup"><span data-stu-id="009dd-110">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

![デバッグが強調表示された Visual Studio のツールバー](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

<span data-ttu-id="009dd-112">まず、アプリのデバッグ バージョンを実行します。</span><span class="sxs-lookup"><span data-stu-id="009dd-112">Begin by running the Debug version of your app.</span></span> <span data-ttu-id="009dd-113">デバッグ ビルド構成では、コンパイラのほとんどの最適化がオフになり、ビルド プロセスの間に豊富な情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-113">The Debug build configuration turns off most compiler optimizations and provides richer information during the build process.</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="009dd-114">ブレークポイントの設定</span><span class="sxs-lookup"><span data-stu-id="009dd-114">Set a breakpoint</span></span>

<span data-ttu-id="009dd-115">プログラムを実行して、デバッグ機能をいくつか試してみます。</span><span class="sxs-lookup"><span data-stu-id="009dd-115">Run your program and try a few debugging features:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="009dd-116">C#</span><span class="sxs-lookup"><span data-stu-id="009dd-116">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="009dd-117">*と表示されている行のコード ウィンドウの左側の余白をクリックして、その行に "* ブレークポイント`Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");`" 設定します。</span><span class="sxs-lookup"><span data-stu-id="009dd-117">Set a *breakpoint* on the line that reads `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="009dd-118">また、コードの行にキャレットを置き、**F9** キーを押すか、メニューバーから **[デバッグ]**  >  **[ブレークポイントの設定/解除]** を選択してブレークポイントを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="009dd-118">You can also set a breakpoint by placing the caret in the line of code and then pressing **F9** or choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="009dd-119">ブレークポイントが設定された行が実行される "*前*" に、アプリケーションの実行がブレークポイントにより一時的に中断されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-119">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

   <span data-ttu-id="009dd-120">次の図のとおり、Visual Studio では、ブレークポイントが設定された行を強調表示し、左端の余白に赤い円を表示することで、その行を示しています。</span><span class="sxs-lookup"><span data-stu-id="009dd-120">As the following image shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red circle in its left margin.</span></span>

   ![ブレークポイントが設定された Visual Studio のプログラム ウィンドウ](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. <span data-ttu-id="009dd-122">ツール バーで緑色の矢印が付いた **HelloWorld** ボタンを選ぶか、**F5** キーを押すか、 **[デバッグ]**  >  **[デバッグの開始]** の順に選ぶことにより、プログラムをデバッグ モードで実行します。</span><span class="sxs-lookup"><span data-stu-id="009dd-122">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar, pressing **F5**, or choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="009dd-123">プログラムが名前の入力を求めたら、コンソール ウィンドウに文字列を入力して、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-123">Enter a string in the console window when the program prompts for a name, and then press **Enter**.</span></span>

1. <span data-ttu-id="009dd-124">プログラムがブレークポイントに到達すると、プログラム実行は停止します。`Console.WriteLine` メソッドが実行される前にも停止します。</span><span class="sxs-lookup"><span data-stu-id="009dd-124">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="009dd-125">**[ローカル]** ウィンドウには、現在実行しているメソッドで定義されている変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-125">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

   ![Visual Studio でのブレークポイントのスクリーンショット](./media/debugging-with-visual-studio/breakpoint-hit.png)

1. <span data-ttu-id="009dd-127">**[イミディエイト]** ウィンドウでは、デバッグ中のアプリケーションと対話できます。</span><span class="sxs-lookup"><span data-stu-id="009dd-127">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="009dd-128">変数の値を対話的に変更して、プログラムにどのような影響があるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="009dd-128">You can interactively change the value of variables to see how it affects your program.</span></span>

   1. <span data-ttu-id="009dd-129">**[イミディエイト]** ウィンドウが表示されない場合は、 **[デバッグ]**  >  **[Windows]**  >  **[イミディエイト]** の順に選択して表示します。</span><span class="sxs-lookup"><span data-stu-id="009dd-129">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

   1. <span data-ttu-id="009dd-130">`name = "Gracie"`[イミディエイト] **ウィンドウに「** 」と入力して、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-130">Enter `name = "Gracie"` in the **Immediate** window and press the **Enter** key.</span></span>

   1. <span data-ttu-id="009dd-131">`date = DateTime.Parse("11/16/2019 5:25 PM")`[イミディエイト] **ウィンドウに「** 」と入力して、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-131">Enter `date = DateTime.Parse("11/16/2019 5:25 PM")` in the **Immediate** window and press the **Enter** key.</span></span>

   <span data-ttu-id="009dd-132">**[イミディエイト]** ウィンドウに、文字列変数の値と、<xref:System.DateTime> 値のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-132">The **Immediate** window displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="009dd-133">さらに、変数の値は **[ローカル]** ウィンドウで更新されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-133">In addition, the values of the variables are updated in the **Locals** window.</span></span>

   ![Visual Studio 2019 の [ローカル] と [イミディエイト] ウィンドウ](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. <span data-ttu-id="009dd-135">ツール バーの **[続行]** ボタンを選ぶか、 **[デバッグ]**  >  **[続行]** を選んで、プログラムの実行を続けます。</span><span class="sxs-lookup"><span data-stu-id="009dd-135">Continue program execution by selecting the **Continue** button in the toolbar or by selecting **Debug** > **Continue**.</span></span> <span data-ttu-id="009dd-136">コンソール ウィンドウに表示される値は、 **[イミディエイト]** ウィンドウで行った変更に対応しています。</span><span class="sxs-lookup"><span data-stu-id="009dd-136">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   ![入力した値が表示されているコンソール ウィンドウ](./media/debugging-with-visual-studio/console-window.png)

1. <span data-ttu-id="009dd-138">任意のキーを押してアプリケーションを終了し、デバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="009dd-138">Press any key to exit the application and stop debugging.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="009dd-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="009dd-139">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="009dd-140">*と表示されている行のコード ウィンドウの左側の余白をクリックして、その行に "* ブレークポイント`Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}!")`" 設定します。</span><span class="sxs-lookup"><span data-stu-id="009dd-140">Set a *breakpoint* on the line that reads `Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}!")` by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="009dd-141">また、目的の行にキャレットを置き、メニューバーから **[デバッグ]**  >  **[ブレークポイントの設定/解除]** を選択してブレークポイントを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="009dd-141">You can also set a breakpoint by placing the caret on the desired line and then choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="009dd-142">ブレークポイントが設定された行が実行される "*前*" に、アプリケーションの実行がブレークポイントにより一時的に中断されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-142">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

   <span data-ttu-id="009dd-143">次の図のとおり、Visual Studio ではブレークポイントを強調表示し、左端の余白に赤い円を表示することで、ブレークポイントがある行を示しています。</span><span class="sxs-lookup"><span data-stu-id="009dd-143">As the following figure shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red circle in its left margin.</span></span>

   ![ブレークポイントが設定された Visual Studio のプログラム ウィンドウ](./media/debugging-with-visual-studio/vb/set-breakpoint-in-editor.png)

1. <span data-ttu-id="009dd-145">ツール バーで緑色の矢印が付いた **HelloWorld** ボタンを選ぶか、**F5** キーを押すか、 **[デバッグ]**  >  **[デバッグの開始]** の順に選ぶことにより、プログラムをデバッグ モードで実行します。</span><span class="sxs-lookup"><span data-stu-id="009dd-145">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar, pressing **F5**, or choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="009dd-146">プログラムが名前の入力を求めたら、コンソール ウィンドウに文字列を入力して、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-146">Enter a string in the console window when the program prompts for a name and press **Enter**.</span></span>

1. <span data-ttu-id="009dd-147">プログラムがブレークポイントに到達すると、プログラム実行は停止します。`Console.WriteLine` メソッドが実行される前にも停止します。</span><span class="sxs-lookup"><span data-stu-id="009dd-147">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="009dd-148">**[ローカル]** ウィンドウには、現在実行しているメソッドで定義されている変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-148">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

1. <span data-ttu-id="009dd-149">**[イミディエイト]** ウィンドウでは、デバッグ中のアプリケーションと対話できます。</span><span class="sxs-lookup"><span data-stu-id="009dd-149">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="009dd-150">変数の値を対話的に変更して、プログラムにどのような影響があるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="009dd-150">You can interactively change the value of variables to see how it affects your program.</span></span>

   1. <span data-ttu-id="009dd-151">**[イミディエイト]** ウィンドウが表示されない場合は、 **[デバッグ]**  >  **[Windows]**  >  **[イミディエイト]** の順に選択して表示します。</span><span class="sxs-lookup"><span data-stu-id="009dd-151">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

   1. <span data-ttu-id="009dd-152">`name = "Gracie"`[イミディエイト] **ウィンドウに「** 」と入力して、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-152">Enter `name = "Gracie"` in the **Immediate** window and press the **Enter** key.</span></span>

   1. <span data-ttu-id="009dd-153">`date = DateTime.Parse("11/16/2019 5:25 PM")`[イミディエイト] **ウィンドウに「** 」と入力して、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-153">Enter `date = DateTime.Parse("11/16/2019 5:25 PM")` in the **Immediate** window and press the **Enter** key.</span></span>

   <span data-ttu-id="009dd-154">変数の値は **[ローカル]** ウィンドウで更新されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-154">The values of the variables are updated in the **Locals** window.</span></span>

1. <span data-ttu-id="009dd-155">ツール バーの **[続行]** ボタンを選ぶか、 **[デバッグ]**  >  **[続行]** メニュー項目を選んで、プログラムの実行を続けます。</span><span class="sxs-lookup"><span data-stu-id="009dd-155">Continue program execution by selecting the **Continue** button in the toolbar or by selecting the **Debug** > **Continue** menu item.</span></span> <span data-ttu-id="009dd-156">コンソール ウィンドウに表示される値は、 **[イミディエイト]** ウィンドウで行った変更に対応しています。</span><span class="sxs-lookup"><span data-stu-id="009dd-156">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   ![入力した値が表示されているコンソール ウィンドウ](./media/debugging-with-visual-studio/console-window.png)

1. <span data-ttu-id="009dd-158">任意のキーを押してアプリケーションを終了し、デバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="009dd-158">Press any key to exit the application and stop debugging.</span></span>

---

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="009dd-159">条件付きブレークポイントの設定</span><span class="sxs-lookup"><span data-stu-id="009dd-159">Set a conditional breakpoint</span></span>

<span data-ttu-id="009dd-160">プログラムは、ユーザーが入力した文字列を表示します。</span><span class="sxs-lookup"><span data-stu-id="009dd-160">Your program displays the string that the user enters.</span></span> <span data-ttu-id="009dd-161">ユーザーが何も入力しないとどうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="009dd-161">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="009dd-162">これは、"*条件付きブレークポイント*" と呼ばれる便利なデバッグ機能を使ってテストできます。この機能は、1 つまたは複数の条件が満たされたときにプログラムの実行をブレークします。</span><span class="sxs-lookup"><span data-stu-id="009dd-162">You can test this with a useful debugging feature called a *conditional breakpoint*, which breaks program execution when one or more conditions are met.</span></span>

<span data-ttu-id="009dd-163">条件付きブレークポイントを設定して、ユーザーが文字列の入力に失敗したときに何が起こるかをテストするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="009dd-163">To set a conditional breakpoint and test what happens when the user fails to enter a string, do the following:</span></span>

# <a name="c"></a>[<span data-ttu-id="009dd-164">C#</span><span class="sxs-lookup"><span data-stu-id="009dd-164">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="009dd-165">ブレークポイントを表す赤丸を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="009dd-165">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="009dd-166">コンテキスト メニューの **[条件]** を選んで、 **[ブレークポイント設定]** ダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="009dd-166">On the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="009dd-167">**[条件]** のチェック ボックスをオンにします (まだ選択されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="009dd-167">Check the box for **Conditions** if it's not already selected.</span></span>

   ![[ブレークポイント設定] パネルが表示されているエディター - C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. <span data-ttu-id="009dd-169">**[条件式]** で、「e.g. x == 5」を次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="009dd-169">For the **Conditional Expression**, replace "e.g. x == 5" with the following:</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="009dd-170">`String.IsNullOrEmpty(name)` に値が割り当てられていないため、またはその値が空の文字列 ("") であるために `true` メソッド呼び出しは `name` になるという、コード条件をテストします。</span><span class="sxs-lookup"><span data-stu-id="009dd-170">You're testing for a code condition, that the `String.IsNullOrEmpty(name)` method call is `true` either because `name` has not been assigned a value or because its value is an empty string ("").</span></span> <span data-ttu-id="009dd-171">条件式の代わりに、ステートメントが指定回数だけ実行される前にプログラムの実行を中断する "*ヒット カウント*"、 またはスレッド識別子、プロセス名、スレッド名などの属性に基づいてプログラムの実行を中断する "*フィルター条件*" を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="009dd-171">Instead of a conditional expression, you can also specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="009dd-172">**[閉じる]** を選択して、ダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="009dd-172">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="009dd-173">**F5** を押して、デバッグとともにプログラムを開始します。</span><span class="sxs-lookup"><span data-stu-id="009dd-173">Start the program with debugging by pressing **F5**.</span></span>

1. <span data-ttu-id="009dd-174">コンソール ウィンドウで、名前の入力を求められたら、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-174">In the console window, press the **Enter** key when prompted to enter your name.</span></span>

1. <span data-ttu-id="009dd-175">`name` が `null` または <xref:System.String.Empty?displayProperty=nameWithType> のどちらかであるという指定した条件が満たされたため、ブレークポイントに到達すると、`Console.WriteLine` メソッドが実行される前に、プログラムの実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="009dd-175">Because the condition you specified, `name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>, has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="009dd-176">**[ローカル]** ウィンドウを選ぶと、現在実行しているメソッドに対してローカルな変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-176">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="009dd-177">この場合、`Main` は現在実行中のメソッドです。</span><span class="sxs-lookup"><span data-stu-id="009dd-177">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="009dd-178">`name` 変数の値が `""` または <xref:System.String.Empty?displayProperty=nameWithType> であることを調べます。</span><span class="sxs-lookup"><span data-stu-id="009dd-178">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="009dd-179">**[イミディエイト]** ウィンドウに次のステートメントを入力し、**Enter** キーを押して、値が空の文字列であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="009dd-179">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing **Enter**.</span></span> <span data-ttu-id="009dd-180">結果は `true`です。</span><span class="sxs-lookup"><span data-stu-id="009dd-180">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ![ステートメントが実行された後で値 true を返す [イミディエイト ウィンドウ] - C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. <span data-ttu-id="009dd-182">ツール バーの **[続行]** を選んで、プログラムの実行を続けます。</span><span class="sxs-lookup"><span data-stu-id="009dd-182">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="009dd-183">任意のキーを押してコンソール ウィンドウを閉じ、デバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="009dd-183">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="009dd-184">コード ウィンドウの左端の余白にあるドットをクリックするか、コードの行を選択した状態で **[デバッグ] > [ブレークポイントの設定/解除]** を選んで、ブレークポイントをクリアします。</span><span class="sxs-lookup"><span data-stu-id="009dd-184">Clear the breakpoint by clicking on the dot in the left margin of the code window or by choosing **Debug > Toggle Breakpoint** while the line of code is selected.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="009dd-185">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="009dd-185">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="009dd-186">ブレークポイントを表す赤丸を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="009dd-186">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="009dd-187">コンテキスト メニューの **[条件]** を選んで、 **[ブレークポイント設定]** ダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="009dd-187">On the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="009dd-188">**[条件]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="009dd-188">Check the box for **Conditions**.</span></span>

   ![[ブレークポイント設定] パネルが表示されているエディター - Visual Basic](./media/debugging-with-visual-studio/vb-breakpointsettings.png)

1. <span data-ttu-id="009dd-190">**[条件式]** で、[例 x == 5] を次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="009dd-190">For the **Conditional Expression** replace "e.g. x = 5" with the following:</span></span>

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="009dd-191">`String.IsNullOrEmpty(name)` に値が割り当てられていないため、またはその値が空の文字列 ("") であるために `true` メソッド呼び出しは `name` になるという、コード条件をテストします。</span><span class="sxs-lookup"><span data-stu-id="009dd-191">You're testing for a code condition, that the `String.IsNullOrEmpty(name)` method call is `true` either because `name` has not been assigned a value or because its value is an empty string ("").</span></span> <span data-ttu-id="009dd-192">条件式の代わりに、ステートメントが指定回数だけ実行される前にプログラムの実行を中断する "*ヒット カウント*"、 またはスレッド識別子、プロセス名、スレッド名などの属性に基づいてプログラムの実行を中断する "*フィルター条件*" を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="009dd-192">Instead of a conditional expression, you can also specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="009dd-193">**[閉じる]** を選択して、ダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="009dd-193">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="009dd-194">**F5** を押して、デバッグとともにプログラムを開始します。</span><span class="sxs-lookup"><span data-stu-id="009dd-194">Start the program with debugging by pressing **F5**.</span></span>

1. <span data-ttu-id="009dd-195">コンソール ウィンドウで、名前の入力を求められたら、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-195">In the console window, press the **Enter** key when prompted to enter your name.</span></span>

1. <span data-ttu-id="009dd-196">`name` が `null` または <xref:System.String.Empty?displayProperty=nameWithType> のどちらかであるという指定した条件が満たされたため、ブレークポイントに到達すると、`Console.WriteLine` メソッドが実行される前に、プログラムの実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="009dd-196">Because the condition you specified, `name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>, has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="009dd-197">**[ローカル]** ウィンドウを選ぶと、現在実行しているメソッドに対してローカルな変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-197">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="009dd-198">この場合、`Main` は現在実行中のメソッドです。</span><span class="sxs-lookup"><span data-stu-id="009dd-198">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="009dd-199">`name` 変数の値が `""` または <xref:System.String.Empty?displayProperty=nameWithType> であることを調べます。</span><span class="sxs-lookup"><span data-stu-id="009dd-199">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="009dd-200">**[イミディエイト]** ウィンドウに次のステートメントを入力し、**Enter** キーを押して、値が空の文字列であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="009dd-200">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing **Enter**.</span></span> <span data-ttu-id="009dd-201">結果は `true`です。</span><span class="sxs-lookup"><span data-stu-id="009dd-201">The result is `true`.</span></span>

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   ![ステートメントが実行された後で値 true を返す [イミディエイト ウィンドウ] - Visual Basic](./media/debugging-with-visual-studio/vb/immediate-window-output.png)

1. <span data-ttu-id="009dd-203">ツール バーの **[続行]** を選んで、プログラムの実行を続けます。</span><span class="sxs-lookup"><span data-stu-id="009dd-203">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="009dd-204">任意のキーを押してコンソール ウィンドウを閉じ、デバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="009dd-204">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="009dd-205">コード ウィンドウの左端の余白のドットをクリックするか、行を選択して **[デバッグ] > [ブレークポイントの設定/解除]** メニュー項目を選んで、ブレークポイントをクリアします。</span><span class="sxs-lookup"><span data-stu-id="009dd-205">Clear the breakpoint by clicking on the dot in the left margin of the code window or by choosing the **Debug > Toggle Breakpoint** menu item with the row selected.</span></span>

---
## <a name="step-through-a-program"></a><span data-ttu-id="009dd-206">プログラムのステップ実行</span><span class="sxs-lookup"><span data-stu-id="009dd-206">Step through a program</span></span>

<span data-ttu-id="009dd-207">Visual Studio では、1 行ずつプログラムをステップ実行して、実行を監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="009dd-207">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="009dd-208">通常は、ブレークポイントを設定してこの機能を使用し、プログラム コードのごく一部を通じてプログラム フローに従います。</span><span class="sxs-lookup"><span data-stu-id="009dd-208">Ordinarily, you'd set a breakpoint and use this feature to follow program flow through a small part of your program code.</span></span> <span data-ttu-id="009dd-209">プログラムが小さいため、次の手順に従ってプログラム全体をステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="009dd-209">Since your program is small, you can step through the entire program:</span></span>

# <a name="c"></a>[<span data-ttu-id="009dd-210">C#</span><span class="sxs-lookup"><span data-stu-id="009dd-210">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="009dd-211">メニュー バーで **[デバッグ]**  >  **[ステップ イン]** を選ぶか、**F11** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-211">On the menu bar, choose **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="009dd-212">次に実行される行が強調表示されて、横に矢印が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-212">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   ![Visual Studio のステップ イン メソッド - C#](./media/debugging-with-visual-studio/step-into-method.png)

   <span data-ttu-id="009dd-214">この時点で **[ローカル]** ウィンドウには、このプログラムで変数が 1 つ (`args`) しか定義されていないことが示されています。</span><span class="sxs-lookup"><span data-stu-id="009dd-214">At this point, the **Locals** window shows that your program has defined only one variable, `args`.</span></span> <span data-ttu-id="009dd-215">プログラムにコマンド ライン引数を 1 つも渡していないので、値は空の文字列配列になっています。</span><span class="sxs-lookup"><span data-stu-id="009dd-215">Because you haven't passed any command-line arguments to the program, its value is an empty string array.</span></span> <span data-ttu-id="009dd-216">さらに、空のコンソール ウィンドウが開かれています。</span><span class="sxs-lookup"><span data-stu-id="009dd-216">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="009dd-217">**[デバッグ]**  >  **[ステップ イン]** を選ぶか、**F11** を押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-217">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="009dd-218">次に実行される行が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-218">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="009dd-219">図に示すように、直前のステートメントとこのステートメントの間のコードを実行するのにかかった時間は 1 ミリ秒未満です。</span><span class="sxs-lookup"><span data-stu-id="009dd-219">As the image shows, it has taken less than one millisecond to execute the code between the last statement and this one.</span></span> <span data-ttu-id="009dd-220">宣言された変数はまだ `args` しかなく、コンソール ウィンドウも空のままです。</span><span class="sxs-lookup"><span data-stu-id="009dd-220">`args` remains the only declared variable, and the console window remains blank.</span></span>

   ![Visual Studio のステップ イン メソッド ソース - C#](./media/debugging-with-visual-studio/step-into-source-method.png)

1. <span data-ttu-id="009dd-222">**[デバッグ]**  >  **[ステップ イン]** を選ぶか、**F11** を押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-222">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="009dd-223">`name` の変数代入を含むステートメントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-223">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="009dd-224">**[ローカル]** ウィンドウに `name` が `null` であると表示され、コンソール ウィンドウに "What is your name?" という文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-224">The **Locals** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="009dd-225">コンソール ウィンドウに文字列を入力し、**Enter** キーを押して、このプロンプトに応答します。</span><span class="sxs-lookup"><span data-stu-id="009dd-225">Respond to the prompt by entering a string in the console window and pressing **Enter**.</span></span> <span data-ttu-id="009dd-226">コンソールは応答せず、入力した文字列はコンソール ウィンドウに表示されませんが、それでも <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> メソッドにより入力が取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="009dd-226">The console is unresponsive, and the string you entered isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="009dd-227">**[デバッグ]**  >  **[ステップ イン]** を選ぶか、**F11** を押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-227">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="009dd-228">`date` の変数代入を含むステートメントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-228">Visual Studio highlights the statement that includes the `date` variable assignment.</span></span> <span data-ttu-id="009dd-229">**[ローカル]** ウィンドウには、<xref:System.Console.ReadLine%2A?displayProperty=nameWithType> メソッドの呼び出しによって返された値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-229">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="009dd-230">コンソール ウィンドウには、プロンプトで入力した文字列も表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-230">The console window also displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="009dd-231">**[デバッグ]**  >  **[ステップ イン]** を選ぶか、**F11** を押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-231">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="009dd-232">**[ローカル]** ウィンドウには、`date` プロパティから代入された後の <xref:System.DateTime.Now?displayProperty=nameWithType> 変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-232">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="009dd-233">コンソール ウィンドウに変更はありません。</span><span class="sxs-lookup"><span data-stu-id="009dd-233">The console window is unchanged.</span></span>

1. <span data-ttu-id="009dd-234">**[デバッグ]**  >  **[ステップ イン]** を選ぶか、**F11** を押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-234">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="009dd-235">Visual Studio は、<xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="009dd-235">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="009dd-236">コンソール ウィンドウには書式設定された文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-236">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="009dd-237">**[デバッグ]**  >  **[ステップ アウト]** の順に選ぶか、**Shift**+**F11** を押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-237">Select **Debug** > **Step Out** or press **Shift**+**F11**.</span></span> <span data-ttu-id="009dd-238">これによりステップ バイ ステップの実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="009dd-238">This stops step-by-step execution.</span></span> <span data-ttu-id="009dd-239">コンソール ウィンドウにメッセージが表示され、任意のキーを押すよう求められます。</span><span class="sxs-lookup"><span data-stu-id="009dd-239">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="009dd-240">任意のキーを押してコンソール ウィンドウを閉じ、デバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="009dd-240">Press any key to close the console window and stop debugging.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="009dd-241">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="009dd-241">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="009dd-242">メニュー バーで **[デバッグ]**  >  **[ステップ イン]** を選ぶか、**F11** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-242">On the menu bar, choose **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="009dd-243">次に実行される行が強調表示されて、横に矢印が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-243">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   ![Visual Studio のステップ イン メソッド - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   <span data-ttu-id="009dd-245">この時点で **[ローカル]** ウィンドウには、このプログラムで変数が 1 つ (`args`) しか定義されていないことが示されています。</span><span class="sxs-lookup"><span data-stu-id="009dd-245">At this point, the **Locals** window shows that your program has defined only one variable, `args`.</span></span> <span data-ttu-id="009dd-246">プログラムにコマンド ライン引数を 1 つも渡していないので、値は空の文字列配列になっています。</span><span class="sxs-lookup"><span data-stu-id="009dd-246">Because you haven't passed any command-line arguments to the program, its value is an empty string array.</span></span> <span data-ttu-id="009dd-247">さらに、空のコンソール ウィンドウが開かれています。</span><span class="sxs-lookup"><span data-stu-id="009dd-247">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="009dd-248">**[デバッグ]**  >  **[ステップ イン]** を選ぶか、**F11** を押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-248">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="009dd-249">次に実行される行が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-249">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="009dd-250">図に示すように、直前のステートメントとこのステートメントの間のコードを実行するのにかかった時間は 1 ミリ秒未満です。</span><span class="sxs-lookup"><span data-stu-id="009dd-250">As the figure shows, it has taken less than one millisecond to execute the code between the last statement and this one.</span></span> <span data-ttu-id="009dd-251">宣言された変数はまだ `args` しかなく、コンソール ウィンドウも空のままです。</span><span class="sxs-lookup"><span data-stu-id="009dd-251">`args` remains the only declared variable, and the console window remains blank.</span></span>

   ![Visual Studio のステップ イン メソッド ソース - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. <span data-ttu-id="009dd-253">**[デバッグ]**  >  **[ステップ イン]** を選ぶか、**F11** を押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-253">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="009dd-254">`name` の変数代入を含むステートメントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-254">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="009dd-255">**[ローカル]** ウィンドウに `name` が `Nothing` であると表示され、コンソール ウィンドウに "What is your name?" という文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-255">The **Locals** window shows that `name` is `Nothing`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="009dd-256">コンソール ウィンドウに文字列を入力し、**Enter** キーを押して、このプロンプトに応答します。</span><span class="sxs-lookup"><span data-stu-id="009dd-256">Respond to the prompt by entering a string in the console window and pressing **Enter**.</span></span> <span data-ttu-id="009dd-257">コンソールは応答しなくなり、入力した文字列はコンソール ウィンドウに表示されませんが、それでも <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> メソッドにより入力はキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="009dd-257">The console is unresponsive, and the string you enter isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="009dd-258">**[デバッグ]**  >  **[ステップ イン]** を選ぶか、**F11** を押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-258">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="009dd-259">`currentDate` の変数代入を含むステートメントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-259">Visual Studio highlights the statement that includes the `currentDate` variable assignment.</span></span> <span data-ttu-id="009dd-260">**[ローカル]** ウィンドウには、<xref:System.Console.ReadLine%2A?displayProperty=nameWithType> メソッドの呼び出しによって返された値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-260">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="009dd-261">コンソール ウィンドウには、コンソールにより求められて入力した文字列も表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-261">The console window also displays the string entered when the console prompted for input.</span></span>

1. <span data-ttu-id="009dd-262">**[デバッグ]**  >  **[ステップ イン]** を選ぶか、**F11** を押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-262">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="009dd-263">コンソール ウィンドウに変更はありません。</span><span class="sxs-lookup"><span data-stu-id="009dd-263">The console window is unchanged.</span></span>

1. <span data-ttu-id="009dd-264">**[デバッグ]**  >  **[ステップ イン]** を選ぶか、**F11** を押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-264">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="009dd-265">Visual Studio は、<xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="009dd-265">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="009dd-266">コンソール ウィンドウには書式設定された文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009dd-266">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="009dd-267">**[デバッグ]**  >  **[ステップ アウト]** の順に選ぶか、**Shift**+**F11** を押します。</span><span class="sxs-lookup"><span data-stu-id="009dd-267">Select **Debug** > **Step Out** or press **Shift**+**F11**.</span></span> <span data-ttu-id="009dd-268">これによりステップ バイ ステップの実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="009dd-268">This stops step-by-step execution.</span></span> <span data-ttu-id="009dd-269">コンソール ウィンドウにメッセージが表示され、任意のキーを押すよう求められます。</span><span class="sxs-lookup"><span data-stu-id="009dd-269">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="009dd-270">任意のキーを押してコンソール ウィンドウを閉じ、デバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="009dd-270">Press any key to close the console window and stop debugging.</span></span>

---

## <a name="build-a-release-version"></a><span data-ttu-id="009dd-271">リリース バージョンのビルド</span><span class="sxs-lookup"><span data-stu-id="009dd-271">Build a Release version</span></span>

<span data-ttu-id="009dd-272">アプリケーションのデバッグ バージョンのテストが終了したら、リリース バージョンもコンパイルしてテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="009dd-272">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="009dd-273">リリース バージョンには、アプリケーションの動作に悪影響を与える可能性があるコンパイラの最適化が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="009dd-273">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="009dd-274">たとえば、パフォーマンスを向上させるように設計されたコンパイラの最適化では、マルチスレッド アプリケーションで競合状態が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="009dd-274">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="009dd-275">コンソール アプリケーションのリリース バージョンをビルドしてテストするには、ツール バーのビルド構成を **[デバッグ]** から **[リリース]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="009dd-275">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

![デバッグが強調表示された Visual Studio の既定のツールバー](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

<span data-ttu-id="009dd-277">**F5** キーを押すか、 **[ビルド]** メニューの **[ソリューションのビルド]** を選ぶと、アプリケーションのリリース バージョンが Visual Studio でコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="009dd-277">When you press **F5** or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of the application.</span></span> <span data-ttu-id="009dd-278">それをデバッグ バージョンと同様にテストできます。</span><span class="sxs-lookup"><span data-stu-id="009dd-278">You can test it as you did the Debug version.</span></span>

## <a name="next-steps"></a><span data-ttu-id="009dd-279">次のステップ</span><span class="sxs-lookup"><span data-stu-id="009dd-279">Next steps</span></span>

<span data-ttu-id="009dd-280">アプリケーションをデバッグしたら、次の手順ではアプリの配置可能なバージョンを発行します。</span><span class="sxs-lookup"><span data-stu-id="009dd-280">Once you've debugged your application, the next step is to publish a deployable version of the app.</span></span> <span data-ttu-id="009dd-281">この方法については、「[Visual Studio での .NET Core Hello World アプリケーションの発行](publishing-with-visual-studio.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="009dd-281">For information on how to do this, see [Publish your .NET Core Hello World application with Visual Studio](publishing-with-visual-studio.md).</span></span>
