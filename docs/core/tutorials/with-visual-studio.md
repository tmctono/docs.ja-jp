---
title: Visual Studio で .NET Core を使用してコンソール アプリケーションを作成する
description: Visual Studio を使用して、C# または Visual Basic で.NET Core コンソール アプリケーションを作成する方法について説明します。
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 9c3456cd8c940e53e8a70c1d3a7c3b09de77c21d
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201584"
---
# <a name="tutorial-create-a-net-core-console-application-in-visual-studio-2019"></a><span data-ttu-id="26396-103">チュートリアル: Visual Studio 2019 で .NET Core コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="26396-103">Tutorial: Create a .NET Core console application in Visual Studio 2019</span></span>

<span data-ttu-id="26396-104">このチュートリアルでは、Visual Studio 2019 で .NET Core コンソール アプリケーションを作成して実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="26396-104">This tutorial shows how to create and run a .NET Core console application in Visual Studio 2019.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="26396-105">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="26396-105">Prerequisites</span></span>

- <span data-ttu-id="26396-106">**.NET Core クロスプラットフォーム開発**ワークロードがインストールされている [Visual Studio 2019 バージョン 16.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="26396-106">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="26396-107">このワークロードを選択すると、.NET Core 3.1 SDK が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="26396-107">The .NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="26396-108">詳細については、記事「[.NET Core SDK をインストールする](../install/sdk.md?pivots=os-windows)」の「[Visual Studio を使用してインストールする](../install/sdk.md?pivots=os-windows#install-with-visual-studio)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="26396-108">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="26396-109">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="26396-109">Create the app</span></span>

<!-- markdownlint-disable MD025 -->

1. <span data-ttu-id="26396-110">Visual Studio 2019 を開きます。</span><span class="sxs-lookup"><span data-stu-id="26396-110">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="26396-111">"HelloWorld" という名前の新しい .NET Core コンソール アプリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="26396-111">Create a new .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="26396-112">スタート ページで、 **[新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="26396-112">On the start page, choose **Create a new project**.</span></span>

      ![Visual Studio のスタート ページで [新しいプロジェクトの作成] ボタンが選択されている](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="26396-114">**[新しいプロジェクトの作成]** ページで、検索ボックスに「**コンソール**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="26396-114">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="26396-115">次に、言語の一覧から **[C#]** または **[Visual Basic]** を選択してから、プラットフォームの一覧から **[すべてのプラットフォーム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="26396-115">Next, choose **C#** or **Visual Basic** from the language list, and then choose **All platforms** from the platform list.</span></span> <span data-ttu-id="26396-116">**[コンソール アプリ (.NET Core)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="26396-116">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![フィルターが選択された状態の [新しいプロジェクトの作成] ウィンドウ](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="26396-118">.NET Core テンプレートが表示されない場合は、必要なワークロードが不足している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26396-118">If you don't see the .NET Core templates, you're probably missing the required workload.</span></span> <span data-ttu-id="26396-119">**[お探しの情報が見つかりませんでしたか?]** メッセージで、 **[さらにツールと機能をインストールする]** リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="26396-119">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="26396-120">Visual Studio インストーラーが開きます。</span><span class="sxs-lookup"><span data-stu-id="26396-120">The Visual Studio Installer opens.</span></span> <span data-ttu-id="26396-121">**.NET Core クロスプラットフォーム開発**ワークロードがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="26396-121">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="26396-122">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**HelloWorld**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="26396-122">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="26396-123">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="26396-123">Then choose **Create**.</span></span>

      ![プロジェクト名、場所、およびソリューション名のフィールドを使用して新しいプロジェクト ウィンドウを構成します](./media/with-visual-studio/configure-new-project.png)

   <span data-ttu-id="26396-125">.NET Core のコンソール アプリケーション テンプレートで、`Program` というクラスが、<xref:System.String> 配列を引数として必要とする単一のメソッド `Main` とともに定義されます。</span><span class="sxs-lookup"><span data-stu-id="26396-125">The Console Application template for .NET Core defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="26396-126">`Main` はアプリケーションのエントリ ポイントで、アプリケーションを起動するときに、ランタイムによって自動的に呼び出されるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="26396-126">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="26396-127">アプリケーションが起動されるときに提供されるコマンドライン引数はすべて *args* 配列にあります。</span><span class="sxs-lookup"><span data-stu-id="26396-127">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   <span data-ttu-id="26396-128">使用する言語が表示されていない場合は、ページの上部にある言語セレクターを変更します。</span><span class="sxs-lookup"><span data-stu-id="26396-128">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

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

   ```vb
   Imports System

   Module Program
       Sub Main(args As String())
           Console.WriteLine("Hello World!")
       End Sub
   End Module
   ```

   <span data-ttu-id="26396-129">このテンプレートでは、シンプルな "Hello World" アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="26396-129">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="26396-130"><xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> メソッドを呼び出し、"Hello World!" を</span><span class="sxs-lookup"><span data-stu-id="26396-130">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="26396-131">コンソール ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="26396-131">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="26396-132">アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="26396-132">Run the app</span></span>

1. <span data-ttu-id="26396-133">プログラムを実行するには、ツール バーで **[HelloWorld]** を選択するか、**F5** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="26396-133">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

   ![HelloWorld の実行ボタンが選択された Visual Studio ツールバー](./media/with-visual-studio/run-program.png)

   <span data-ttu-id="26396-135">コンソール ウィンドウが開き、"Hello World!" というテキストが</span><span class="sxs-lookup"><span data-stu-id="26396-135">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="26396-136">画面に出力され、Visual Studio のデバッグ情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26396-136">printed on the screen and some Visual Studio debug information.</span></span>

   ![Hello World Press any key to continue と表示されているコンソール ウィンドウ](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="26396-138">任意のキーを押して、コンソール ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="26396-138">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="26396-139">アプリを拡張する</span><span class="sxs-lookup"><span data-stu-id="26396-139">Enhance the app</span></span>

<span data-ttu-id="26396-140">アプリケーションを拡張し、ユーザーに名前の入力を求め、日付と時刻と共にそれを表示するようにします。</span><span class="sxs-lookup"><span data-stu-id="26396-140">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="26396-141">次の手順では、アプリを変更してから再度実行します。</span><span class="sxs-lookup"><span data-stu-id="26396-141">The following instructions modify the app and run it again:</span></span>

1. <span data-ttu-id="26396-142">`Main` メソッド (現在は `Console.WriteLine` を呼び出す行のみ) の内容を以下のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="26396-142">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="Snippet1":::

   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="Snippet1":::

   <span data-ttu-id="26396-143">このコードは、"What is your name?" と</span><span class="sxs-lookup"><span data-stu-id="26396-143">This code displays "What is your name?"</span></span> <span data-ttu-id="26396-144">コンソール ウィンドウに表示して、ユーザーが文字列を入力して Enter キーを押すまで待機します。</span><span class="sxs-lookup"><span data-stu-id="26396-144">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="26396-145">これはこの文字列を `name` という変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="26396-145">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="26396-146">さらに現在の現地時刻を含む <xref:System.DateTime.Now?displayProperty=nameWithType> プロパティの値を取得して、それを `date` という変数に代入します (Visual Basic では `currentDate`)。</span><span class="sxs-lookup"><span data-stu-id="26396-146">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date` (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="26396-147">最後に、これらの値がコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="26396-147">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="26396-148">`\n` (Visual Basic では `vbCrLf`) は、改行文字を表します。</span><span class="sxs-lookup"><span data-stu-id="26396-148">The `\n` (`vbCrLf` in Visual Basic) represents a newline character.</span></span>

   <span data-ttu-id="26396-149">文字列の前にドル記号 (`$`) を付けると、変数名などの式を文字列で中かっこで囲むことができます。</span><span class="sxs-lookup"><span data-stu-id="26396-149">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="26396-150">式の値が、式の代わりに文字列に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="26396-150">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="26396-151">この構文は、[補間された文字列](../../csharp/language-reference/tokens/interpolated.md)と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="26396-151">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="26396-152">プログラムを実行するには、ツール バーで **[HelloWorld]** を選択するか、**F5** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="26396-152">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="26396-153">プロンプトに対し、名前を入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="26396-153">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![プログラムの出力が変更されたコンソール ウィンドウ](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="26396-155">任意のキーを押して、コンソール ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="26396-155">Press any key to close the console window.</span></span>

## <a name="next-steps"></a><span data-ttu-id="26396-156">次の手順</span><span class="sxs-lookup"><span data-stu-id="26396-156">Next steps</span></span>

<span data-ttu-id="26396-157">このチュートリアルでは、.NET Core アプリケーションを作成しました。</span><span class="sxs-lookup"><span data-stu-id="26396-157">In this tutorial, you created a .NET Core application.</span></span> <span data-ttu-id="26396-158">次のチュートリアルでは、アプリをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="26396-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="26396-159">Visual Studio で .NET Core コンソール アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="26396-159">Debug a .NET Core console application in Visual Studio</span></span>](debugging-with-visual-studio.md)
