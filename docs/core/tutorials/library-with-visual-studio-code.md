---
title: Visual Studio Code で .NET Standard クラス ライブラリを作成する
description: Visual Studio Code を使用して .NET Standard クラス ライブラリを作成する方法について説明します。
ms.date: 05/29/2020
ms.openlocfilehash: 5720ac374d50ef27a07d463e57af1bd95a352d83
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446953"
---
# <a name="tutorial-create-a-net-standard-library-in-visual-studio-code"></a><span data-ttu-id="3b5d4-103">チュートリアル: Visual Studio Code で .NET Standard ライブラリを作成する</span><span class="sxs-lookup"><span data-stu-id="3b5d4-103">Tutorial: Create a .NET Standard library in Visual Studio Code</span></span>

<span data-ttu-id="3b5d4-104">"*クラス ライブラリ*" は、アプリケーションから呼び出される型とメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="3b5d4-105">.NET Standard 2.0 をターゲットとするクラス ライブラリでは、お使いのライブラリを、そのバージョンの .NET Standard をサポートする任意の .NET 実装によって呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-105">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="3b5d4-106">ご自分のクラス ライブラリを完了させたら、それを NuGet パッケージとして配布するか、あるいは 1 つ以上のアプリケーションにコンポーネントとしてバンドルして含めるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-106">When you finish your class library, you can decide whether you want to distribute it as a NuGet package or include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="3b5d4-107">.NET Standard のバージョンとそれらがサポートするプラットフォームの一覧は、「[.NET Standard](../../standard/net-standard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-107">For a list of .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="3b5d4-108">このチュートリアルでは、1 つの文字列処理メソッドを含む簡単なユーティリティ ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-108">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="3b5d4-109">それを[拡張メソッド](../../csharp/programming-guide/classes-and-structs/extension-methods.md)として実装し、<xref:System.String> クラスのメンバーと同じように呼び出すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-109">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3b5d4-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3b5d4-110">Prerequisites</span></span>

1. <span data-ttu-id="3b5d4-111">[C# 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)がインストールされている [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-111">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="3b5d4-112">Visual Studio Code に拡張機能をインストールする方法については、[VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-112">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="3b5d4-113">[.Net Core 3.1 SDK 以降](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="3b5d4-113">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="3b5d4-114">ソリューションを作成する</span><span class="sxs-lookup"><span data-stu-id="3b5d4-114">Create a solution</span></span>

<span data-ttu-id="3b5d4-115">まず、クラス ライブラリ プロジェクトを配置する空のソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-115">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="3b5d4-116">ソリューションは、1 つまたは複数のプロジェクトのコンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-116">A solution serves as a container for one or more projects.</span></span> <span data-ttu-id="3b5d4-117">さらに関連するプロジェクトを同じソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-117">You'll add additional, related projects to the same solution.</span></span>

1. <span data-ttu-id="3b5d4-118">Visual Studio Code を開きます。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-118">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="3b5d4-119">メイン メニューから **[ファイル]**  >  **[フォルダーを開く]** / **[開く...]** の順に選択し、*ClassLibraryProjects* フォルダーを作成して、 **[フォルダーの選択]** / **[開く]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-119">Select **File** > **Open Folder**/**Open...** from the main menu, create a *ClassLibraryProjects* folder, and click **Select Folder**/**Open**.</span></span>

1. <span data-ttu-id="3b5d4-120">メイン メニューで **[表示]**  >  **[ターミナル]** の順に選択して、Visual Studio Code で**ターミナル**を開きます。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-120">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="3b5d4-121">コマンド プロンプトで *ClassLibraryProjects* フォルダーが表示され、**ターミナル**が開きます。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-121">The **Terminal** opens with the command prompt in the *ClassLibraryProjects* folder.</span></span>

1. <span data-ttu-id="3b5d4-122">**ターミナル**で、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-122">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new sln
   ```

   <span data-ttu-id="3b5d4-123">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-123">The terminal output looks like the following example:</span></span>

   ```
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a><span data-ttu-id="3b5d4-124">クラス ライブラリ プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="3b5d4-124">Create a class library project</span></span>

<span data-ttu-id="3b5d4-125">"StringLibrary" という名前の新しい .NET Standard クラス ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-125">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

1. <span data-ttu-id="3b5d4-126">次のコマンドをターミナルで実行して、ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-126">In the terminal, run the following command to create the library project:</span></span>

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   <span data-ttu-id="3b5d4-127">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-127">The terminal output looks like the following example:</span></span>

   ```
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restore completed in 328.13 ms for C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj.
   Restore succeeded.
   ```

1. <span data-ttu-id="3b5d4-128">次のコマンドを実行して、ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-128">Run the following command to add the library project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="3b5d4-129">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-129">The terminal output looks like the following example:</span></span>

   ```
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. <span data-ttu-id="3b5d4-130">ライブラリが正しいバージョンの .NET Standard をターゲットにしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-130">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="3b5d4-131">**エクスプローラー**で、*StringLibrary/StringLibrary .csproj* を開きます。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-131">In **Explorer**, open *StringLibrary/StringLibrary.csproj*.</span></span>

   <span data-ttu-id="3b5d4-132">`TargetFramework` 要素に、プロジェクトが .NET Standard 2.0 をターゲットとしていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-132">The `TargetFramework` element shows that the project targets .NET Standard 2.0.</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>netstandard2.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="3b5d4-133">*Class1.cs* を開き、このコードを次のものと置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-133">Open *Class1.cs* and replace the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   <span data-ttu-id="3b5d4-134">クラス ライブラリ `UtilityLibraries.StringLibrary` には、`StartsWithUpper` という名前のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-134">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="3b5d4-135">このメソッドによって、現在の文字列のインスタンスが大文字で始まるかどうかを示す <xref:System.Boolean> 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-135">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="3b5d4-136">Unicode 規格では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-136">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="3b5d4-137"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> メソッドは文字が大文字の場合に `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-137">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="3b5d4-138">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-138">Save the file.</span></span>

1. <span data-ttu-id="3b5d4-139">次のコマンドを実行してソリューションをビルドし、エラーなしでプロジェクトがコンパイルされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-139">Run the following command to build the solution and verify that the project compiles without error.</span></span>

   ```dotnetcli
   dotnet build
   ```

   <span data-ttu-id="3b5d4-140">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-140">The terminal output looks like the following example:</span></span>

   ```
   Microsoft (R) Build Engine version 16.6.0 for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     You are using a preview version of .NET Core. See: https://aka.ms/dotnet-core-preview
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\netstandard2.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="3b5d4-141">ソリューションにコンソール アプリを追加する</span><span class="sxs-lookup"><span data-stu-id="3b5d4-141">Add a console app to the solution</span></span>

<span data-ttu-id="3b5d4-142">このクラス ライブラリを使用するコンソール アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-142">Add a console application that uses the class library.</span></span> <span data-ttu-id="3b5d4-143">アプリによって、ユーザーに文字列の入力が求められ、文字列が大文字で始まるかどうかが報告されます。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-143">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="3b5d4-144">次のコマンドをターミナルで実行して、コンソール アプリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-144">In the terminal, run the following command to create the console app project:</span></span>

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   <span data-ttu-id="3b5d4-145">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-145">The terminal output looks like the following example:</span></span>

   ```
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restore completed in 210.78 ms for C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj.
   Restore succeeded.
   ```

1. <span data-ttu-id="3b5d4-146">次のコマンドを実行して、ソリューションにコンソール アプリ プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-146">Run the following command to add the console app project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   <span data-ttu-id="3b5d4-147">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-147">The terminal output looks like the following example:</span></span>

   ```
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. <span data-ttu-id="3b5d4-148">最初は、新しいコンソール アプリ プロジェクトにクラス ライブラリへのアクセス権はありません。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-148">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="3b5d4-149">クラス ライブラリでメソッドを呼び出せるようにするには、次のコマンドを実行して、クラス ライブラリ プロジェクトへのプロジェクト参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-149">To allow it to call methods in the class library, create a project reference to the class library project by running the following command:</span></span>

   ```dotnetcli
   dotnet add ShowCase/Showcase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="3b5d4-150">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-150">The terminal output looks like the following example:</span></span>

   ```
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

1. <span data-ttu-id="3b5d4-151">*ShowCase/Program.cs* を開き、すべてのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-151">Open *ShowCase/Program.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="3b5d4-152">このコードでは、`row` 変数を使って、コンソール ウィンドウに書き込まれるデータの行数のカウントを維持します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-152">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="3b5d4-153">これが 25 以上になると、コードによってコンソール ウィンドウがクリアされ、ユーザーにメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-153">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="3b5d4-154">プログラムは、ユーザーに文字列の入力を要求し、</span><span class="sxs-lookup"><span data-stu-id="3b5d4-154">The program prompts the user to enter a string.</span></span> <span data-ttu-id="3b5d4-155">文字列が大文字で始まるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-155">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="3b5d4-156">ユーザーが文字列を入力せずに Enter キーを押すと、アプリケーションが終了し、コンソール ウィンドウが閉じます。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-156">If the user presses the Enter key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="3b5d4-157">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-157">Save your changes.</span></span>

1. <span data-ttu-id="3b5d4-158">プログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-158">Run the program.</span></span>

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. <span data-ttu-id="3b5d4-159">文字列を入力して <kbd>Enter</kbd> キーを押してプログラムを実行し、<kbd>Enter</kbd> キーを押して終了します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-159">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   <span data-ttu-id="3b5d4-160">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-160">The terminal output looks like the following example:</span></span>

   ```
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   A string that starts with a lowercase letter
   Input: A string that starts with a lowercase letter
   Begins with uppercase? : Yes
   ```

## <a name="additional-resources"></a><span data-ttu-id="3b5d4-161">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="3b5d4-161">Additional resources</span></span>

* [<span data-ttu-id="3b5d4-162">.NET Core CLI を使用したライブラリの開発</span><span class="sxs-lookup"><span data-stu-id="3b5d4-162">Develop libraries with the .NET Core CLI</span></span>](libraries.md)

## <a name="next-steps"></a><span data-ttu-id="3b5d4-163">次の手順</span><span class="sxs-lookup"><span data-stu-id="3b5d4-163">Next steps</span></span>

<span data-ttu-id="3b5d4-164">このチュートリアルでは、ソリューションを作成し、ライブラリ プロジェクトを追加し、ライブラリを使用するコンソール アプリ プロジェクトを追加しました。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-164">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="3b5d4-165">次のチュートリアルでは、ソリューションに単体テスト プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="3b5d4-165">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3b5d4-166">Visual Studio Code での .NET Core を使用した .NET Standard ライブラリのテスト</span><span class="sxs-lookup"><span data-stu-id="3b5d4-166">Test a .NET Standard library with .NET Core in Visual Studio Code</span></span>](testing-library-with-visual-studio-code.md)
