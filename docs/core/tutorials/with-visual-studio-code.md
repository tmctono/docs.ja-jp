---
title: Visual Studio Code を使用して .NET Core コンソール アプリケーションを作成する
description: Visual Studio Code と .NET Core CLI を使用して .NET Core コンソール アプリケーションを作成する方法について説明します。
ms.date: 05/22/2020
ms.openlocfilehash: 466a1353b574711a73570428569b58eab7ad8135
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "84811695"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio-code"></a><span data-ttu-id="8d828-103">チュートリアル: Visual Studio Code を使用して .NET Core コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="8d828-103">Tutorial: Create a .NET Core console application using Visual Studio Code</span></span>

<span data-ttu-id="8d828-104">このチュートリアルでは、Visual Studio Code と .NET Core CLI を使用して .NET Core コンソール アプリケーションを作成して実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d828-104">This tutorial shows how to create and run a .NET Core console application by using Visual Studio Code and the .NET Core CLI.</span></span> <span data-ttu-id="8d828-105">プロジェクトの作成、コンパイル、実行などのプロジェクト タスクは、.NET Core CLI を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="8d828-105">Project tasks, such as creating, compiling, and running a project are done by using the .NET Core CLI.</span></span> <span data-ttu-id="8d828-106">必要に応じて、別のコード エディターを使用してこのチュートリアルに従い、ターミナルでコマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8d828-106">You can follow this tutorial with a different code editor and run commands in a terminal if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8d828-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8d828-107">Prerequisites</span></span>

1. <span data-ttu-id="8d828-108">[C# 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)がインストールされている [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="8d828-108">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="8d828-109">Visual Studio Code に拡張機能をインストールする方法については、[VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d828-109">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="8d828-110">[.Net Core 3.1 SDK 以降](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="8d828-110">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-the-app"></a><span data-ttu-id="8d828-111">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="8d828-111">Create the app</span></span>

<span data-ttu-id="8d828-112">"HelloWorld" という名前の .NET Core コンソール アプリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d828-112">Create a .NET Core console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="8d828-113">Visual Studio Code を開始します。</span><span class="sxs-lookup"><span data-stu-id="8d828-113">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="8d828-114">メイン メニューから **[ファイル]**  >  **[フォルダーを開く]** (macOS では **[ファイル]**  >  **[開く...]** ) の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8d828-114">Select **File** > **Open Folder** (**File** > **Open...** on macOS) from the main menu.</span></span>

1. <span data-ttu-id="8d828-115">**[フォルダーを開く]** ダイアログで、*HelloWorld* フォルダーを作成し、 **[フォルダーの選択]** (macOS では **[開く]** ) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d828-115">In the **Open Folder** dialog, create a *HelloWorld* folder and click **Select Folder** (**Open** on macOS).</span></span>

   <span data-ttu-id="8d828-116">フォルダー名は既定でプロジェクト名と名前空間名になります。</span><span class="sxs-lookup"><span data-stu-id="8d828-116">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="8d828-117">このチュートリアルでは後でコードを追加しますが、プロジェクト名前空間は `HelloWorld` にします。</span><span class="sxs-lookup"><span data-stu-id="8d828-117">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

1. <span data-ttu-id="8d828-118">メイン メニューで **[表示]**  >  **[ターミナル]** の順に選択して、Visual Studio Code で**ターミナル**を開きます。</span><span class="sxs-lookup"><span data-stu-id="8d828-118">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="8d828-119">**ターミナル**が開き、*HelloWorld* フォルダーにコマンド プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d828-119">The **Terminal** opens with the command prompt in the *HelloWorld* folder.</span></span>

1. <span data-ttu-id="8d828-120">**ターミナル**で、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="8d828-120">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new console
   ```

<span data-ttu-id="8d828-121">このテンプレートでは、シンプルな "Hello World" アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d828-121">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="8d828-122"><xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> メソッドを呼び出し、"Hello World!" を</span><span class="sxs-lookup"><span data-stu-id="8d828-122">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="8d828-123">コンソール ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="8d828-123">in the console window.</span></span>

<span data-ttu-id="8d828-124">テンプレート コードでは、引数として <xref:System.String> 配列を受け取る単一のメソッド `Main` を含む、`Program` というクラスが定義されます。</span><span class="sxs-lookup"><span data-stu-id="8d828-124">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="8d828-125">`Main` はアプリケーションのエントリ ポイントで、アプリケーションを起動するときに、ランタイムによって自動的に呼び出されるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="8d828-125">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="8d828-126">アプリケーションが起動されるときに提供されるコマンドライン引数はすべて *args* 配列にあります。</span><span class="sxs-lookup"><span data-stu-id="8d828-126">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="8d828-127">アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="8d828-127">Run the app</span></span>

<span data-ttu-id="8d828-128">**ターミナル**で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d828-128">Run the following command in the **Terminal**:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="8d828-129">プログラムによって "Hello World!" が表示されて</span><span class="sxs-lookup"><span data-stu-id="8d828-129">The program displays "Hello World!"</span></span> <span data-ttu-id="8d828-130">終了します。</span><span class="sxs-lookup"><span data-stu-id="8d828-130">and ends.</span></span>

![dotnet run コマンド](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a><span data-ttu-id="8d828-132">アプリを拡張する</span><span class="sxs-lookup"><span data-stu-id="8d828-132">Enhance the app</span></span>

<span data-ttu-id="8d828-133">アプリケーションを拡張し、ユーザーに名前の入力を求め、日付と時刻と共にそれを表示するようにします。</span><span class="sxs-lookup"><span data-stu-id="8d828-133">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="8d828-134">*Program.cs* をクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="8d828-134">Open *Program.cs* by clicking on it.</span></span>

   <span data-ttu-id="8d828-135">Visual Studio Code で初めて C# ファイルを開くと、[OmniSharp](https://www.omnisharp.net/) がエディターに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="8d828-135">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

   ![Program.cs ファイルを開く](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="8d828-137">Visual Studio Code で、アプリのビルドとデバッグに必要なアセットの追加を求められたら、 **[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d828-137">Select **Yes** when Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span>

   ![足りない資産の入力を求める](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="8d828-139">*Program.cs* の `Main` メソッドの内容 (`Console.WriteLine` を呼び出す行) を以下のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8d828-139">Replace the contents of the `Main` method in *Program.cs*, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="8d828-140">このコードは、"What is your name?" と</span><span class="sxs-lookup"><span data-stu-id="8d828-140">This code displays "What is your name?"</span></span> <span data-ttu-id="8d828-141">コンソール ウィンドウに表示して、ユーザーが文字列を入力して <kbd>Enter</kbd> キーを押すまで待機します。</span><span class="sxs-lookup"><span data-stu-id="8d828-141">in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="8d828-142">これはこの文字列を `name` という変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="8d828-142">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="8d828-143">さらに現在の現地時刻を含む <xref:System.DateTime.Now?displayProperty=nameWithType> プロパティの値を取得して、それを `date` という変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="8d828-143">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="8d828-144">最後に、これらの値がコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d828-144">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="8d828-145">`\n` は、改行文字を表します。</span><span class="sxs-lookup"><span data-stu-id="8d828-145">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="8d828-146">文字列の前にドル記号 (`$`) を付けると、変数名などの式を文字列で中かっこで囲むことができます。</span><span class="sxs-lookup"><span data-stu-id="8d828-146">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="8d828-147">式の値が、式の代わりに文字列に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="8d828-147">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="8d828-148">この構文は、[補間された文字列](../../csharp/language-reference/tokens/interpolated.md)と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8d828-148">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="8d828-149">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="8d828-149">Save your changes.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="8d828-150">Visual Studio Code では、変更を明示的に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d828-150">In Visual Studio Code, you have to explicitly save changes.</span></span> <span data-ttu-id="8d828-151">Visual Studio とは異なり、アプリをビルドして実行してもファイルの変更は自動的には保存されません。</span><span class="sxs-lookup"><span data-stu-id="8d828-151">Unlike Visual Studio, file changes are not automatically saved when you build and run an app.</span></span>

1. <span data-ttu-id="8d828-152">もう一度プログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d828-152">Run the program again:</span></span>

   ```dotnetcli
   dotnet run
   ```

1. <span data-ttu-id="8d828-153">プロンプトに対し、名前を入力し、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8d828-153">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="プログラムの出力が変更されたターミナル ウィンドウ":::

1. <span data-ttu-id="8d828-155">任意のキーを押してプログラムを終了します。</span><span class="sxs-lookup"><span data-stu-id="8d828-155">Press any key to exit the program.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8d828-156">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="8d828-156">Additional resources</span></span>

- [<span data-ttu-id="8d828-157">Visual Studio Code の設定</span><span class="sxs-lookup"><span data-stu-id="8d828-157">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)

## <a name="next-steps"></a><span data-ttu-id="8d828-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="8d828-158">Next steps</span></span>

<span data-ttu-id="8d828-159">このチュートリアルでは、.NET Core コンソール アプリケーションを作成しました。</span><span class="sxs-lookup"><span data-stu-id="8d828-159">In this tutorial, you created a .NET Core console application.</span></span> <span data-ttu-id="8d828-160">次のチュートリアルでは、アプリをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="8d828-160">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8d828-161">Visual Studio Code を使用して .NET Core コンソール アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="8d828-161">Debug a .NET Core console application using Visual Studio Code</span></span>](debugging-with-visual-studio-code.md)
