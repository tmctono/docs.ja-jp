---
title: C# および Visual Studio Code の使用を開始する
description: Visual Studio Code を使用した、C# で初めての .NET Core アプリケーションを作成してデバッグする方法について説明します。
author: kendrahavens
ms.date: 12/05/2018
ms.custom: seodec18
ms.openlocfilehash: 4e283f631f463953185a37bf196a1a9b706eee2b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002325"
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="c543e-103">C# および Visual Studio Code の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="c543e-103">Get started with C# and Visual Studio Code</span></span>

<span data-ttu-id="c543e-104">.NET Core は、Windows、Linux および macOS で実行されるアプリケーションを作成するための、高速でモジュール型のプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="c543e-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="c543e-105">Visual Studio Code を C# 拡張機能とともに使用して、C# IntelliSense の完全サポート (スマート コード補完) とデバッグによる強力な編集機能をご活用ください。</span><span class="sxs-lookup"><span data-stu-id="c543e-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c543e-106">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c543e-106">Prerequisites</span></span>

1. <span data-ttu-id="c543e-107">[Visual Studio Code](https://code.visualstudio.com/) のインストール。</span><span class="sxs-lookup"><span data-stu-id="c543e-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="c543e-108">[.NET Core SDK](https://dotnet.microsoft.com/download) のインストール。</span><span class="sxs-lookup"><span data-stu-id="c543e-108">Install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>
3. <span data-ttu-id="c543e-109">Visual Studio Code の [C# 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)のインストール。</span><span class="sxs-lookup"><span data-stu-id="c543e-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="c543e-110">Visual Studio Code に拡張機能をインストールする方法については、[VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c543e-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="c543e-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="c543e-111">Hello World</span></span>

<span data-ttu-id="c543e-112">.NET Core でシンプルな "Hello World" プログラムを作成してみましょう。</span><span class="sxs-lookup"><span data-stu-id="c543e-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="c543e-113">プロジェクトを開く</span><span class="sxs-lookup"><span data-stu-id="c543e-113">Open a project:</span></span>

    - <span data-ttu-id="c543e-114">Visual Studio Code を開きます。</span><span class="sxs-lookup"><span data-stu-id="c543e-114">Open Visual Studio Code.</span></span>
    - <span data-ttu-id="c543e-115">左側のメニューで [エクスプローラー] アイコンをクリックし、 **[フォルダーを開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c543e-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    - <span data-ttu-id="c543e-116">メイン メニューから **[ファイル]** 、 **[フォルダーを開く]** の順に選択し、C# プロジェクトを保存するフォルダーを開き、 **[フォルダーの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c543e-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="c543e-117">ここで、*Hello World* という名前のプロジェクトのフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c543e-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![Visual Studio Code の [フォルダーを開く]](media/with-visual-studio-code/vs-code-open-folder.png)

2. <span data-ttu-id="c543e-119">C# プロジェクトを初期化する</span><span class="sxs-lookup"><span data-stu-id="c543e-119">Initialize a C# project:</span></span>

    - <span data-ttu-id="c543e-120">Visual Studio Code から統合ターミナルを開きます。メイン メニューで **[表示]** 、 **[統合端末]** の順に選択してください。</span><span class="sxs-lookup"><span data-stu-id="c543e-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    - <span data-ttu-id="c543e-121">ターミナル ウィンドウで、`dotnet new console` と入力します。</span><span class="sxs-lookup"><span data-stu-id="c543e-121">In the terminal window, type `dotnet new console`.</span></span>
    - <span data-ttu-id="c543e-122">このコマンドは、*HelloWorld.csproj* という名前の C# プロジェクト ファイルと共に、単純な "Hello World" プログラムが既に書き込まれた *Program.cs* ファイルをフォルダーに作成します。</span><span class="sxs-lookup"><span data-stu-id="c543e-122">This command creates a *Program.cs* file in your folder with a simple "Hello World" program already written, along with a C# project file named *HelloWorld.csproj*.</span></span>

      ![dotnet new コマンド](media/with-visual-studio-code/dotnet-new-command.png)

3. <span data-ttu-id="c543e-124">ビルド資産を解決する</span><span class="sxs-lookup"><span data-stu-id="c543e-124">Resolve the build assets:</span></span>

    - <span data-ttu-id="c543e-125">**.NET Core 1.x** の場合、「`dotnet restore`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c543e-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="c543e-126">`dotnet restore` を実行すると、プロジェクトのビルドに必要な .NET Core パッケージにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c543e-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![dotnet restore コマンド](media/with-visual-studio-code/dotnet-restore-command.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="c543e-128">"Hello World" プログラムを実行する</span><span class="sxs-lookup"><span data-stu-id="c543e-128">Run the "Hello World" program:</span></span>

    - <span data-ttu-id="c543e-129">「`dotnet run`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c543e-129">Type `dotnet run`.</span></span>

      ![dotnet run コマンド](media/with-visual-studio-code/dotnet-run-command.png)

<span data-ttu-id="c543e-131">[Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core)、[macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS)、または [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) での詳細設定については、簡単なビデオ チュートリアルを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="c543e-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="c543e-132">デバッグ</span><span class="sxs-lookup"><span data-stu-id="c543e-132">Debug</span></span>

1. <span data-ttu-id="c543e-133">*Program.cs* をクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="c543e-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="c543e-134">Visual Studio Code で初めて C# ファイルを開くと、[OmniSharp](https://www.omnisharp.net/) がエディターに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c543e-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

    ![Program.cs ファイルを開く](media/with-visual-studio-code/open-program-cs.png)

2. <span data-ttu-id="c543e-136">Visual Studio Code で、アプリのビルドとデバッグに必要なアセットの追加を求められます。</span><span class="sxs-lookup"><span data-stu-id="c543e-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="c543e-137">**[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c543e-137">Select **Yes**.</span></span>

    ![足りない資産の入力を求める](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="c543e-139">デバッグ ビューを開くには、左側のメニューにある [デバッグ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c543e-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Visual Studio Code で [デバッグ] タブを開く](media/with-visual-studio-code/open-debug-tab.png)

4. <span data-ttu-id="c543e-141">ウィンドウの上部で緑色の矢印を探します。</span><span class="sxs-lookup"><span data-stu-id="c543e-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="c543e-142">その横にあるドロップダウン リストで **[.NET Core Launch (console)]** \(.NET Core の起動 (コンソール)\) が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c543e-142">Make sure the drop-down next to it has **.NET Core Launch (console)** selected.</span></span>

    ![Visual Studio Code で .NET Core を選択する](media/with-visual-studio-code/select-net-core.png)

5. <span data-ttu-id="c543e-144">9 行目の横にある**エディター余白** (エディター内の行番号の左側の領域) をクリックして、プロジェクトにブレークポイントを追加するか、またはエディター内でテキスト カーソルを 9 行目に移動して <kbd>F9</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c543e-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9, or move the text cursor onto line 9 in the editor and  press <kbd>F9</kbd>.</span></span>

    ![ブレークポイントの設定](media/with-visual-studio-code/set-breakpoint-vs-code.png)

6. <span data-ttu-id="c543e-146">デバッグを開始するには、<kbd>F5</kbd> キーを押すか、緑色の矢印を選択します。</span><span class="sxs-lookup"><span data-stu-id="c543e-146">To start debugging, press <kbd>F5</kbd> or select the green arrow.</span></span> <span data-ttu-id="c543e-147">デバッガーは、前述の手順で設定したブレークポイントに達すると、プログラムの実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="c543e-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    - <span data-ttu-id="c543e-148">デバッグ中は左上のペインにローカル変数が表示され、デバッグ コンソールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c543e-148">While debugging, you can view your local variables in the top left pane or use the debug console.</span></span>

7. <span data-ttu-id="c543e-149">上部にある青色の矢印を選択してデバッグを継続するか、上部にある赤色の四角形を選択して停止します。</span><span class="sxs-lookup"><span data-stu-id="c543e-149">Select the blue arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

    ![Visual Studio Code の実行とデバッグ](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> <span data-ttu-id="c543e-151">Visual Studio Code で OmniSharp を使用した .NET Core のデバッグの詳細とトラブルシューティングのヒントについては、「[Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)」 (.NET Core デバッガーの設定に関する指示) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c543e-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="add-a-class"></a><span data-ttu-id="c543e-152">クラスを追加する</span><span class="sxs-lookup"><span data-stu-id="c543e-152">Add a class</span></span>

1. <span data-ttu-id="c543e-153">新しいクラスを追加するには、VSCode エクスプローラーを右クリックし、 **[新しいファイル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c543e-153">To add a new class, right click in the VSCode Explorer and select **New File**.</span></span> <span data-ttu-id="c543e-154">これで、新しいファイルが VSCode で開いたフォルダーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c543e-154">This adds a new file to the folder you have open in VSCode.</span></span>
2. <span data-ttu-id="c543e-155">ファイルに *MyClass.cs* という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c543e-155">Name your file *MyClass.cs*.</span></span> <span data-ttu-id="c543e-156">csharp ファイルとして認識されるには、最後に `.cs` 拡張子を付けて保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c543e-156">You must save it with a `.cs` extension at the end for it to be recognized as a csharp file.</span></span>
3. <span data-ttu-id="c543e-157">次のコードを追加して、1 つ目のクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c543e-157">Add the code below to create your first class.</span></span> <span data-ttu-id="c543e-158">*Program.cs* ファイルから参照できるように、正しい名前空間を含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="c543e-158">Make sure to include the correct namespace so you can reference it from your *Program.cs* file:</span></span>

    ``` csharp
    using System;

    namespace HelloWorld
    {
        public class MyClass
        {
            public string ReturnMessage()
            {
                return "Happy coding!";
            }
        }
    }
    ```

4. <span data-ttu-id="c543e-159">次のコードを追加して、*Program.cs* のメイン メソッドから新しいクラスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c543e-159">Call your new class from your main method in *Program.cs* by adding the code below:</span></span>

    ```csharp
    using System;
    
    namespace HelloWorld
    {
        class Program
        {
            static void Main(string[] args)
            {
                var c1 = new MyClass();
                Console.WriteLine($"Hello World! {c1.ReturnMessage()}");
            }
        }
    }
    ```

5. <span data-ttu-id="c543e-160">変更を保存し、プログラムを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="c543e-160">Save your changes and run your program again.</span></span> <span data-ttu-id="c543e-161">新しいメッセージと共に追加した文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c543e-161">The new message should appear with the appended string.</span></span>

    ```console
    > dotnet run
    Hello World! Happy coding!
    ```

## <a name="faq"></a><span data-ttu-id="c543e-162">よくあるご質問</span><span class="sxs-lookup"><span data-stu-id="c543e-162">FAQ</span></span>

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a><span data-ttu-id="c543e-163">Visual Studio Code 内で C# をビルドおよびデバッグするのに必要な資産が欠落しています。</span><span class="sxs-lookup"><span data-stu-id="c543e-163">I'm missing required assets to build and debug C# in Visual Studio Code.</span></span> <span data-ttu-id="c543e-164">デバッガーには、"構成がありません" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="c543e-164">My debugger says "No Configuration."</span></span>

<span data-ttu-id="c543e-165">Visual Studio Code C# の拡張機能では、ビルドおよびデバッグする資産を自動的に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="c543e-165">The Visual Studio Code C# extension can generate assets to build and debug for you.</span></span> <span data-ttu-id="c543e-166">C# プロジェクトを初めて開くと、これらの資産を作成するように Visual Studio Code から求められます。</span><span class="sxs-lookup"><span data-stu-id="c543e-166">Visual Studio Code prompts you to generate these assets when you first open a C# project.</span></span> <span data-ttu-id="c543e-167">資産を作成しなかった場合でも、このコマンドを実行する方法はあります。コマンド パレットを開き ( **[表示] > [コマンド パレット]** )、「>.NET:Generate Assets for Build and Debug」 と入力します。</span><span class="sxs-lookup"><span data-stu-id="c543e-167">If you didn't generate assets then, you can still run this command by opening the Command Palette (**View > Command Palette**) and typing ">.NET: Generate Assets for Build and Debug".</span></span> <span data-ttu-id="c543e-168">これを選択すると、必要としている *.vscode*、*launch.json* および *tasks.json* の各構成ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c543e-168">Selecting this generates the *.vscode*, *launch.json*, and *tasks.json* configuration files that you need.</span></span>

## <a name="see-also"></a><span data-ttu-id="c543e-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="c543e-169">See also</span></span>

- [<span data-ttu-id="c543e-170">Visual Studio Code の設定</span><span class="sxs-lookup"><span data-stu-id="c543e-170">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)
- [<span data-ttu-id="c543e-171">Visual Studio Code でのデバッグ</span><span class="sxs-lookup"><span data-stu-id="c543e-171">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)
