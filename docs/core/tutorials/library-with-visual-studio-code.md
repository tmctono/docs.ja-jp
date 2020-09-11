---
title: Visual Studio Code を使用して .NET Standard クラス ライブラリを作成する
description: Visual Studio Code を使用して .NET Standard クラス ライブラリを作成する方法について説明します。
ms.date: 06/08/2020
ms.openlocfilehash: 966b9b0b48f67809e82d9133c523995cd97b6015
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495513"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-code"></a><span data-ttu-id="4b65f-103">チュートリアル: Visual Studio Code を使用して .NET Standard ライブラリを作成する</span><span class="sxs-lookup"><span data-stu-id="4b65f-103">Tutorial: Create a .NET Standard library using Visual Studio Code</span></span>

<span data-ttu-id="4b65f-104">このチュートリアルでは、1 つの文字列処理メソッドを含む簡単なユーティリティ ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-104">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="4b65f-105">それを[拡張メソッド](../../csharp/programming-guide/classes-and-structs/extension-methods.md)として実装し、<xref:System.String> クラスのメンバーと同じように呼び出すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="4b65f-105">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

<span data-ttu-id="4b65f-106">"*クラス ライブラリ*" は、アプリケーションから呼び出される型とメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-106">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="4b65f-107">.NET Standard 2.0 をターゲットとするクラス ライブラリでは、お使いのライブラリを、そのバージョンの .NET Standard をサポートする任意の .NET 実装によって呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4b65f-107">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="4b65f-108">クラス ライブラリが完成したら、サードパーティ製のコンポーネントとして配布するか、1 つ以上のアプリケーションを含むバンドルされたコンポーネントとして配布することができます。</span><span class="sxs-lookup"><span data-stu-id="4b65f-108">When you finish your class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4b65f-109">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4b65f-109">Prerequisites</span></span>

1. <span data-ttu-id="4b65f-110">[C# 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)がインストールされている [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="4b65f-110">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="4b65f-111">Visual Studio Code に拡張機能をインストールする方法については、[VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b65f-111">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="4b65f-112">[.Net Core 3.1 SDK 以降](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="4b65f-112">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="4b65f-113">ソリューションを作成する</span><span class="sxs-lookup"><span data-stu-id="4b65f-113">Create a solution</span></span>

<span data-ttu-id="4b65f-114">まず、クラス ライブラリ プロジェクトを配置する空のソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-114">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="4b65f-115">ソリューションは、1 つまたは複数のプロジェクトのコンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-115">A solution serves as a container for one or more projects.</span></span> <span data-ttu-id="4b65f-116">さらに関連するプロジェクトを同じソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-116">You'll add additional, related projects to the same solution.</span></span>

1. <span data-ttu-id="4b65f-117">Visual Studio Code を開始します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-117">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="4b65f-118">メイン メニューから **[ファイル]**  >  **[フォルダーを開く]** (macOS では **[開く...]** ) の順に選択します</span><span class="sxs-lookup"><span data-stu-id="4b65f-118">Select **File** > **Open Folder** (**Open...** on macOS) from the main menu</span></span>

1. <span data-ttu-id="4b65f-119">**[フォルダーを開く]** ダイアログで、*ClassLibraryProjects* フォルダーを作成し、 **[フォルダーの選択]** (macOS では **[開く]** ) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b65f-119">In the **Open Folder** dialog, create a *ClassLibraryProjects* folder and click **Select Folder** (**Open** on macOS).</span></span>

1. <span data-ttu-id="4b65f-120">メイン メニューで **[表示]**  >  **[ターミナル]** の順に選択して、Visual Studio Code で**ターミナル**を開きます。</span><span class="sxs-lookup"><span data-stu-id="4b65f-120">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="4b65f-121">コマンド プロンプトで *ClassLibraryProjects* フォルダーが表示され、**ターミナル**が開きます。</span><span class="sxs-lookup"><span data-stu-id="4b65f-121">The **Terminal** opens with the command prompt in the *ClassLibraryProjects* folder.</span></span>

1. <span data-ttu-id="4b65f-122">**ターミナル**で、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-122">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new sln
   ```

   <span data-ttu-id="4b65f-123">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="4b65f-123">The terminal output looks like the following example:</span></span>

   ```output
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a><span data-ttu-id="4b65f-124">クラス ライブラリ プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="4b65f-124">Create a class library project</span></span>

<span data-ttu-id="4b65f-125">"StringLibrary" という名前の新しい .NET Standard クラス ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-125">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

1. <span data-ttu-id="4b65f-126">次のコマンドをターミナルで実行して、ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-126">In the terminal, run the following command to create the library project:</span></span>

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   <span data-ttu-id="4b65f-127">`-o` コマンドまたは `--output` コマンドによって、生成された出力を配置する場所が指定されます。</span><span class="sxs-lookup"><span data-stu-id="4b65f-127">The `-o` or `--output` command specifies the location to place the generated output.</span></span>

   <span data-ttu-id="4b65f-128">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="4b65f-128">The terminal output looks like the following example:</span></span>

   ```output
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restored C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj (in 328 ms).
   Restore succeeded.
   ```

1. <span data-ttu-id="4b65f-129">次のコマンドを実行して、ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-129">Run the following command to add the library project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="4b65f-130">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="4b65f-130">The terminal output looks like the following example:</span></span>

   ```output
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. <span data-ttu-id="4b65f-131">ライブラリが正しいバージョンの .NET Standard をターゲットにしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-131">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="4b65f-132">**エクスプローラー**で、*StringLibrary/StringLibrary .csproj* を開きます。</span><span class="sxs-lookup"><span data-stu-id="4b65f-132">In **Explorer**, open *StringLibrary/StringLibrary.csproj*.</span></span>

   <span data-ttu-id="4b65f-133">`TargetFramework` 要素に、プロジェクトが .NET Standard 2.0 をターゲットとしていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="4b65f-133">The `TargetFramework` element shows that the project targets .NET Standard 2.0.</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>netstandard2.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="4b65f-134">*Class1.cs* を開き、このコードを次のものと置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4b65f-134">Open *Class1.cs* and replace the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   <span data-ttu-id="4b65f-135">クラス ライブラリ `UtilityLibraries.StringLibrary` には、`StartsWithUpper` という名前のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b65f-135">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="4b65f-136">このメソッドによって、現在の文字列のインスタンスが大文字で始まるかどうかを示す <xref:System.Boolean> 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="4b65f-136">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="4b65f-137">Unicode 規格では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="4b65f-137">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="4b65f-138"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> メソッドは文字が大文字の場合に `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-138">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="4b65f-139">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-139">Save the file.</span></span>

1. <span data-ttu-id="4b65f-140">次のコマンドを実行してソリューションをビルドし、エラーなしでプロジェクトがコンパイルされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-140">Run the following command to build the solution and verify that the project compiles without error.</span></span>

   ```dotnetcli
   dotnet build
   ```

   <span data-ttu-id="4b65f-141">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="4b65f-141">The terminal output looks like the following example:</span></span>

   ```output
   Microsoft (R) Build Engine version 16.7.0+b89cb5fde for .NET
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\netstandard2.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="4b65f-142">ソリューションにコンソール アプリを追加する</span><span class="sxs-lookup"><span data-stu-id="4b65f-142">Add a console app to the solution</span></span>

<span data-ttu-id="4b65f-143">このクラス ライブラリを使用するコンソール アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-143">Add a console application that uses the class library.</span></span> <span data-ttu-id="4b65f-144">アプリによって、ユーザーに文字列の入力が求められ、文字列が大文字で始まるかどうかが報告されます。</span><span class="sxs-lookup"><span data-stu-id="4b65f-144">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="4b65f-145">次のコマンドをターミナルで実行して、コンソール アプリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-145">In the terminal, run the following command to create the console app project:</span></span>

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   <span data-ttu-id="4b65f-146">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="4b65f-146">The terminal output looks like the following example:</span></span>

   ```output
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restored C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj (in 210 ms).
   Restore succeeded.
   ```

1. <span data-ttu-id="4b65f-147">次のコマンドを実行して、ソリューションにコンソール アプリ プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-147">Run the following command to add the console app project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   <span data-ttu-id="4b65f-148">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="4b65f-148">The terminal output looks like the following example:</span></span>

   ```output
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. <span data-ttu-id="4b65f-149">*ShowCase/Program.cs* を開き、すべてのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4b65f-149">Open *ShowCase/Program.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="4b65f-150">このコードでは、`row` 変数を使って、コンソール ウィンドウに書き込まれるデータの行数のカウントを維持します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-150">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="4b65f-151">これが 25 以上になると、コードによってコンソール ウィンドウがクリアされ、ユーザーにメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b65f-151">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="4b65f-152">プログラムは、ユーザーに文字列の入力を要求し、</span><span class="sxs-lookup"><span data-stu-id="4b65f-152">The program prompts the user to enter a string.</span></span> <span data-ttu-id="4b65f-153">文字列が大文字で始まるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-153">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="4b65f-154">ユーザーが文字列を入力せずに <kbd>Enter</kbd> キーを押すと、アプリケーションが終了し、コンソール ウィンドウが閉じます。</span><span class="sxs-lookup"><span data-stu-id="4b65f-154">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="4b65f-155">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-155">Save your changes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="4b65f-156">プロジェクト参照を追加する</span><span class="sxs-lookup"><span data-stu-id="4b65f-156">Add a project reference</span></span>

<span data-ttu-id="4b65f-157">最初は、新しいコンソール アプリ プロジェクトにクラス ライブラリへのアクセス権はありません。</span><span class="sxs-lookup"><span data-stu-id="4b65f-157">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="4b65f-158">クラス ライブラリでメソッドを呼び出せるようにするには、クラス ライブラリ プロジェクトへのプロジェクト参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-158">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="4b65f-159">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-159">Run the following command:</span></span>

   ```dotnetcli
   dotnet add ShowCase/ShowCase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="4b65f-160">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="4b65f-160">The terminal output looks like the following example:</span></span>

   ```output
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

## <a name="run-the-app"></a><span data-ttu-id="4b65f-161">アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="4b65f-161">Run the app</span></span>

1. <span data-ttu-id="4b65f-162">ターミナルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-162">Run the following command in the terminal:</span></span>

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. <span data-ttu-id="4b65f-163">文字列を入力して <kbd>Enter</kbd> キーを押してプログラムを実行し、<kbd>Enter</kbd> キーを押して終了します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-163">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   <span data-ttu-id="4b65f-164">ターミナルには次の例のような出力があります。</span><span class="sxs-lookup"><span data-stu-id="4b65f-164">The terminal output looks like the following example:</span></span>

   ```output
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   a string that starts with a lowercase letter
   Input: a string that starts with a lowercase letter
   Begins with uppercase? : No
   ```

## <a name="additional-resources"></a><span data-ttu-id="4b65f-165">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="4b65f-165">Additional resources</span></span>

* [<span data-ttu-id="4b65f-166">.NET Core CLI を使用したライブラリの開発</span><span class="sxs-lookup"><span data-stu-id="4b65f-166">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="4b65f-167">[.NET Standard のバージョンとそれらでサポートされているプラットフォーム](../../standard/net-standard.md)。</span><span class="sxs-lookup"><span data-stu-id="4b65f-167">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4b65f-168">次の手順</span><span class="sxs-lookup"><span data-stu-id="4b65f-168">Next steps</span></span>

<span data-ttu-id="4b65f-169">このチュートリアルでは、ソリューションを作成し、ライブラリ プロジェクトを追加し、ライブラリを使用するコンソール アプリ プロジェクトを追加しました。</span><span class="sxs-lookup"><span data-stu-id="4b65f-169">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="4b65f-170">次のチュートリアルでは、ソリューションに単体テスト プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b65f-170">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4b65f-171">Visual Studio Code を使用して .NET Core で .NET Standard ライブラリをテストする</span><span class="sxs-lookup"><span data-stu-id="4b65f-171">Test a .NET Standard library with .NET Core using Visual Studio Code</span></span>](testing-library-with-visual-studio-code.md)
