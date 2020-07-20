---
title: Visual Studio Code を使用して .NET Standard クラス ライブラリを作成する
description: Visual Studio Code を使用して .NET Standard クラス ライブラリを作成する方法について説明します。
ms.date: 06/08/2020
ms.openlocfilehash: 714b5cf2125f1d296adc4a4dc7d1b6c9420417ed
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "86308885"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-code"></a><span data-ttu-id="a31cd-103">チュートリアル: Visual Studio Code を使用して .NET Standard ライブラリを作成する</span><span class="sxs-lookup"><span data-stu-id="a31cd-103">Tutorial: Create a .NET Standard library using Visual Studio Code</span></span>

<span data-ttu-id="a31cd-104">このチュートリアルでは、1 つの文字列処理メソッドを含む簡単なユーティリティ ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-104">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="a31cd-105">それを[拡張メソッド](../../csharp/programming-guide/classes-and-structs/extension-methods.md)として実装し、<xref:System.String> クラスのメンバーと同じように呼び出すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="a31cd-105">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

<span data-ttu-id="a31cd-106">"*クラス ライブラリ*" は、アプリケーションから呼び出される型とメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-106">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="a31cd-107">.NET Standard 2.0 をターゲットとするクラス ライブラリでは、お使いのライブラリを、そのバージョンの .NET Standard をサポートする任意の .NET 実装によって呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a31cd-107">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="a31cd-108">クラス ライブラリが完成したら、サードパーティ製のコンポーネントとして配布するか、1 つ以上のアプリケーションを含むバンドルされたコンポーネントとして配布することができます。</span><span class="sxs-lookup"><span data-stu-id="a31cd-108">When you finish your class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a31cd-109">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a31cd-109">Prerequisites</span></span>

1. <span data-ttu-id="a31cd-110">[C# 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)がインストールされている [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="a31cd-110">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="a31cd-111">Visual Studio Code に拡張機能をインストールする方法については、[VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a31cd-111">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="a31cd-112">[.Net Core 3.1 SDK 以降](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="a31cd-112">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="a31cd-113">ソリューションを作成する</span><span class="sxs-lookup"><span data-stu-id="a31cd-113">Create a solution</span></span>

<span data-ttu-id="a31cd-114">まず、クラス ライブラリ プロジェクトを配置する空のソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-114">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="a31cd-115">ソリューションは、1 つまたは複数のプロジェクトのコンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-115">A solution serves as a container for one or more projects.</span></span> <span data-ttu-id="a31cd-116">さらに関連するプロジェクトを同じソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-116">You'll add additional, related projects to the same solution.</span></span>

1. <span data-ttu-id="a31cd-117">Visual Studio Code を開始します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-117">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="a31cd-118">メイン メニューから **[ファイル]**  >  **[フォルダーを開く]** (macOS では **[開く...]** ) の順に選択します</span><span class="sxs-lookup"><span data-stu-id="a31cd-118">Select **File** > **Open Folder** (**Open...** on macOS) from the main menu</span></span>

1. <span data-ttu-id="a31cd-119">**[フォルダーを開く]** ダイアログで、*ClassLibraryProjects* フォルダーを作成し、 **[フォルダーの選択]** (macOS では **[開く]** ) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a31cd-119">In the **Open Folder** dialog, create a *ClassLibraryProjects* folder and click **Select Folder** (**Open** on macOS).</span></span>

1. <span data-ttu-id="a31cd-120">メイン メニューで **[表示]**  >  **[ターミナル]** の順に選択して、Visual Studio Code で**ターミナル**を開きます。</span><span class="sxs-lookup"><span data-stu-id="a31cd-120">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="a31cd-121">コマンド プロンプトで *ClassLibraryProjects* フォルダーが表示され、**ターミナル**が開きます。</span><span class="sxs-lookup"><span data-stu-id="a31cd-121">The **Terminal** opens with the command prompt in the *ClassLibraryProjects* folder.</span></span>

1. <span data-ttu-id="a31cd-122">**ターミナル**で、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-122">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new sln
   ```

   <span data-ttu-id="a31cd-123">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="a31cd-123">The terminal output looks like the following example:</span></span>

   ```
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a><span data-ttu-id="a31cd-124">クラス ライブラリ プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="a31cd-124">Create a class library project</span></span>

<span data-ttu-id="a31cd-125">"StringLibrary" という名前の新しい .NET Standard クラス ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-125">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

1. <span data-ttu-id="a31cd-126">次のコマンドをターミナルで実行して、ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-126">In the terminal, run the following command to create the library project:</span></span>

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   <span data-ttu-id="a31cd-127">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="a31cd-127">The terminal output looks like the following example:</span></span>

   ```
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restore completed in 328.13 ms for C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj.
   Restore succeeded.
   ```

1. <span data-ttu-id="a31cd-128">次のコマンドを実行して、ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-128">Run the following command to add the library project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="a31cd-129">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="a31cd-129">The terminal output looks like the following example:</span></span>

   ```
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. <span data-ttu-id="a31cd-130">ライブラリが正しいバージョンの .NET Standard をターゲットにしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-130">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="a31cd-131">**エクスプローラー**で、*StringLibrary/StringLibrary .csproj* を開きます。</span><span class="sxs-lookup"><span data-stu-id="a31cd-131">In **Explorer**, open *StringLibrary/StringLibrary.csproj*.</span></span>

   <span data-ttu-id="a31cd-132">`TargetFramework` 要素に、プロジェクトが .NET Standard 2.0 をターゲットとしていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="a31cd-132">The `TargetFramework` element shows that the project targets .NET Standard 2.0.</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>netstandard2.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="a31cd-133">*Class1.cs* を開き、このコードを次のものと置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a31cd-133">Open *Class1.cs* and replace the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   <span data-ttu-id="a31cd-134">クラス ライブラリ `UtilityLibraries.StringLibrary` には、`StartsWithUpper` という名前のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a31cd-134">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="a31cd-135">このメソッドによって、現在の文字列のインスタンスが大文字で始まるかどうかを示す <xref:System.Boolean> 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="a31cd-135">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="a31cd-136">Unicode 規格では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="a31cd-136">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="a31cd-137"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> メソッドは文字が大文字の場合に `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-137">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="a31cd-138">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-138">Save the file.</span></span>

1. <span data-ttu-id="a31cd-139">次のコマンドを実行してソリューションをビルドし、エラーなしでプロジェクトがコンパイルされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-139">Run the following command to build the solution and verify that the project compiles without error.</span></span>

   ```dotnetcli
   dotnet build
   ```

   <span data-ttu-id="a31cd-140">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="a31cd-140">The terminal output looks like the following example:</span></span>

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

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="a31cd-141">ソリューションにコンソール アプリを追加する</span><span class="sxs-lookup"><span data-stu-id="a31cd-141">Add a console app to the solution</span></span>

<span data-ttu-id="a31cd-142">このクラス ライブラリを使用するコンソール アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-142">Add a console application that uses the class library.</span></span> <span data-ttu-id="a31cd-143">アプリによって、ユーザーに文字列の入力が求められ、文字列が大文字で始まるかどうかが報告されます。</span><span class="sxs-lookup"><span data-stu-id="a31cd-143">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="a31cd-144">次のコマンドをターミナルで実行して、コンソール アプリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-144">In the terminal, run the following command to create the console app project:</span></span>

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   <span data-ttu-id="a31cd-145">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="a31cd-145">The terminal output looks like the following example:</span></span>

   ```
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restore completed in 210.78 ms for C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj.
   Restore succeeded.
   ```

1. <span data-ttu-id="a31cd-146">次のコマンドを実行して、ソリューションにコンソール アプリ プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-146">Run the following command to add the console app project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   <span data-ttu-id="a31cd-147">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="a31cd-147">The terminal output looks like the following example:</span></span>

   ```
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. <span data-ttu-id="a31cd-148">*ShowCase/Program.cs* を開き、すべてのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a31cd-148">Open *ShowCase/Program.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="a31cd-149">このコードでは、`row` 変数を使って、コンソール ウィンドウに書き込まれるデータの行数のカウントを維持します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-149">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="a31cd-150">これが 25 以上になると、コードによってコンソール ウィンドウがクリアされ、ユーザーにメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a31cd-150">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="a31cd-151">プログラムは、ユーザーに文字列の入力を要求し、</span><span class="sxs-lookup"><span data-stu-id="a31cd-151">The program prompts the user to enter a string.</span></span> <span data-ttu-id="a31cd-152">文字列が大文字で始まるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-152">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="a31cd-153">ユーザーが文字列を入力せずに <kbd>Enter</kbd> キーを押すと、アプリケーションが終了し、コンソール ウィンドウが閉じます。</span><span class="sxs-lookup"><span data-stu-id="a31cd-153">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="a31cd-154">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-154">Save your changes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="a31cd-155">プロジェクト参照を追加する</span><span class="sxs-lookup"><span data-stu-id="a31cd-155">Add a project reference</span></span>

<span data-ttu-id="a31cd-156">最初は、新しいコンソール アプリ プロジェクトにクラス ライブラリへのアクセス権はありません。</span><span class="sxs-lookup"><span data-stu-id="a31cd-156">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="a31cd-157">クラス ライブラリでメソッドを呼び出せるようにするには、クラス ライブラリ プロジェクトへのプロジェクト参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-157">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="a31cd-158">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-158">Run the following command:</span></span>

   ```dotnetcli
   dotnet add ShowCase/ShowCase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="a31cd-159">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="a31cd-159">The terminal output looks like the following example:</span></span>

   ```
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

## <a name="run-the-app"></a><span data-ttu-id="a31cd-160">アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="a31cd-160">Run the app</span></span>

1. <span data-ttu-id="a31cd-161">ターミナルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-161">Run the following command in the terminal:</span></span>

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. <span data-ttu-id="a31cd-162">文字列を入力して <kbd>Enter</kbd> キーを押してプログラムを実行し、<kbd>Enter</kbd> キーを押して終了します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-162">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   <span data-ttu-id="a31cd-163">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="a31cd-163">The terminal output looks like the following example:</span></span>

   ```
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   A string that starts with a lowercase letter
   Input: A string that starts with a lowercase letter
   Begins with uppercase? : Yes
   ```

## <a name="additional-resources"></a><span data-ttu-id="a31cd-164">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="a31cd-164">Additional resources</span></span>

* [<span data-ttu-id="a31cd-165">.NET Core CLI を使用したライブラリの開発</span><span class="sxs-lookup"><span data-stu-id="a31cd-165">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="a31cd-166">[.NET Standard のバージョンとそれらでサポートされているプラットフォーム](../../standard/net-standard.md)。</span><span class="sxs-lookup"><span data-stu-id="a31cd-166">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a31cd-167">次の手順</span><span class="sxs-lookup"><span data-stu-id="a31cd-167">Next steps</span></span>

<span data-ttu-id="a31cd-168">このチュートリアルでは、ソリューションを作成し、ライブラリ プロジェクトを追加し、ライブラリを使用するコンソール アプリ プロジェクトを追加しました。</span><span class="sxs-lookup"><span data-stu-id="a31cd-168">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="a31cd-169">次のチュートリアルでは、ソリューションに単体テスト プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="a31cd-169">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a31cd-170">Visual Studio Code を使用して .NET Core で .NET Standard ライブラリをテストする</span><span class="sxs-lookup"><span data-stu-id="a31cd-170">Test a .NET Standard library with .NET Core using Visual Studio Code</span></span>](testing-library-with-visual-studio-code.md)
