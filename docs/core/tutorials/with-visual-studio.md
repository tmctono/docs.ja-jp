---
title: Visual Studio での .NET Core を使用した Hello World アプリケーションの作成
description: Visual Studio を使用して、C# または Visual Basic で最初の .NET Core コンソール アプリケーションを作成する方法について説明します。
author: BillWagner
ms.author: wiwagn
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: ba996e4add1cfe44681154b00a6530b1f3e70b37
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714007"
---
# <a name="tutorial-create-your-first-net-core-console-application-in-visual-studio-2019"></a><span data-ttu-id="4d03f-103">チュートリアル: Visual Studio 2019 で最初の .NET Core コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="4d03f-103">Tutorial: Create your first .NET Core console application in Visual Studio 2019</span></span>

<span data-ttu-id="4d03f-104">この記事では、Visual Studio 2019 で Hello World .NET Core コンソール アプリケーションを作成して実行するためのステップ バイ ステップの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-104">This article provides a step-by-step introduction to create and run a Hello World .NET Core console application in Visual Studio 2019.</span></span> <span data-ttu-id="4d03f-105">Hello World アプリケーションは、従来、初心者に新しいプログラミング言語に紹介するために使用されています。</span><span class="sxs-lookup"><span data-stu-id="4d03f-105">A Hello World application is traditionally used to introduce beginners to a new programming language.</span></span> <span data-ttu-id="4d03f-106">このプログラムは、単に "Hello World!" という語句を</span><span class="sxs-lookup"><span data-stu-id="4d03f-106">This program simply displays the phrase "Hello World!"</span></span> <span data-ttu-id="4d03f-107">画面に出力しました。</span><span class="sxs-lookup"><span data-stu-id="4d03f-107">on the screen.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4d03f-108">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4d03f-108">Prerequisites</span></span>

- <span data-ttu-id="4d03f-109">**.NET Core クロスプラットフォーム開発**ワークロードがインストールされている [Visual Studio 2019 バージョン 16.4 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="4d03f-109">[Visual Studio 2019 version 16.4 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="4d03f-110">このワークロードを選択すると、.NET Core 3.1 SDK が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4d03f-110">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

<span data-ttu-id="4d03f-111">詳細については、記事「[.NET Core SDK をインストールする](../install/sdk.md?pivots=os-windows)」の「[Visual Studio を使用してインストールする](../install/sdk.md?pivots=os-windows#install-with-visual-studio)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d03f-111">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="4d03f-112">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="4d03f-112">Create the app</span></span>

<span data-ttu-id="4d03f-113">次の手順では、単純な Hello World コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-113">The following instructions create a simple Hello World console application:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[<span data-ttu-id="4d03f-114">C#</span><span class="sxs-lookup"><span data-stu-id="4d03f-114">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="4d03f-115">Visual Studio 2019 を開きます。</span><span class="sxs-lookup"><span data-stu-id="4d03f-115">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="4d03f-116">"HelloWorld" という名前の新しい C# .NET Core コンソール アプリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-116">Create a new C# .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="4d03f-117">スタート ウィンドウで、 **[新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-117">On the start window, choose **Create a new project**.</span></span>

      ![Visual Studio の [スタート] ウィンドウで [新しいプロジェクトの作成] ボタンが選択されています](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="4d03f-119">**[新しいプロジェクトの作成]** ページで、検索ボックスに「**コンソール**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-119">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="4d03f-120">次に、言語の一覧から **[C#]** を選択し、続いて、プラットフォームの一覧から **[すべてのプラットフォーム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-120">Next, choose **C#** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="4d03f-121">**[コンソール アプリ (.NET Core)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-121">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![フィルターが選択された状態の [新しいプロジェクトの作成] ウィンドウ](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="4d03f-123">.NET Core テンプレートが表示されない場合は、必要なワークロードがインストールされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4d03f-123">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="4d03f-124">**[お探しの情報が見つかりませんでしたか?]** メッセージで、 **[さらにツールと機能をインストールする]** リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-124">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="4d03f-125">Visual Studio インストーラーが開きます。</span><span class="sxs-lookup"><span data-stu-id="4d03f-125">The Visual Studio Installer opens.</span></span> <span data-ttu-id="4d03f-126">**.NET Core クロスプラットフォーム開発**ワークロードがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4d03f-126">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="4d03f-127">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**HelloWorld**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-127">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="4d03f-128">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-128">Then, choose **Create**.</span></span>

      ![プロジェクト名、場所、およびソリューション名のフィールドを使用して新しいプロジェクト ウィンドウを構成します](./media/with-visual-studio/configure-new-project.png)

   <span data-ttu-id="4d03f-130">.NET Core の C# コンソール アプリケーション テンプレートで、`Program` というクラスが、<xref:System.String> 配列を引数として必要とする単一のメソッド `Main` とともに自動的に定義されます。</span><span class="sxs-lookup"><span data-stu-id="4d03f-130">The C# Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="4d03f-131">`Main` はアプリケーションのエントリ ポイントで、アプリケーションを起動するときに、ランタイムによって自動的に呼び出されるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="4d03f-131">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="4d03f-132">アプリケーションが起動されるときに提供されるコマンドライン引数はすべて *args* 配列にあります。</span><span class="sxs-lookup"><span data-stu-id="4d03f-132">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio と新しい HelloWorld プロジェクト](./media/with-visual-studio/visual-studio-main-window.png)

# <a name="visual-basictabvb"></a>[<span data-ttu-id="4d03f-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d03f-134">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="4d03f-135">Visual Studio 2019 を開きます。</span><span class="sxs-lookup"><span data-stu-id="4d03f-135">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="4d03f-136">"HelloWorld" という名前の新しい Visual Basic .NET Core コンソール アプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-136">Create a new Visual Basic .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="4d03f-137">スタート ウィンドウで、 **[新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-137">On the start window, choose **Create a new project**.</span></span>

      ![Visual Studio の [スタート] ウィンドウで [新しいプロジェクトの作成] ボタンが選択されています](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="4d03f-139">**[新しいプロジェクトの作成]** ページで、検索ボックスに「**コンソール**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-139">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="4d03f-140">次に、言語の一覧から **[Visual Basic]** を選択し、続いて、プラットフォームの一覧から **[すべてのプラットフォーム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-140">Next, choose **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="4d03f-141">**[コンソール アプリ (.NET Core)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-141">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![コンソール アプリ (.NET Framework) 用の Visual Basic テンプレートを選択します。](./media/with-visual-studio/vb/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="4d03f-143">.NET Core テンプレートが表示されない場合は、必要なワークロードがインストールされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4d03f-143">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="4d03f-144">**[お探しの情報が見つかりませんでしたか?]** メッセージで、 **[さらにツールと機能をインストールする]** リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-144">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="4d03f-145">Visual Studio インストーラーが開きます。</span><span class="sxs-lookup"><span data-stu-id="4d03f-145">The Visual Studio Installer opens.</span></span> <span data-ttu-id="4d03f-146">**.NET Core クロスプラットフォーム開発**ワークロードがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4d03f-146">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="4d03f-147">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**HelloWorld**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-147">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="4d03f-148">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-148">Then, choose **Create**.</span></span>

   <span data-ttu-id="4d03f-149">.NET Core のコンソール アプリ テンプレートで、`Program` というクラスが、<xref:System.String> 配列を引数として受け取る単一のメソッド `Main` とともに自動的に定義されます。</span><span class="sxs-lookup"><span data-stu-id="4d03f-149">The console app template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="4d03f-150">`Main` はアプリケーションのエントリ ポイントで、アプリケーションを起動するときに、ランタイムによって自動的に呼び出されるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="4d03f-150">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="4d03f-151">アプリケーションが起動されるときに提供されるコマンド ライン引数はすべて `args` パラメーターにあります。</span><span class="sxs-lookup"><span data-stu-id="4d03f-151">Any command-line arguments supplied when the application is launched are available in the `args` parameter.</span></span>

   ![Visual Studio と新しい HelloWorld プロジェクト](./media/with-visual-studio/vb/visual-studio-main-window.png)

---

   <span data-ttu-id="4d03f-153">このテンプレートでは、シンプルな "Hello World" アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-153">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="4d03f-154"><xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> メソッドを呼び出し、リテラル文字列 "Hello World!" を</span><span class="sxs-lookup"><span data-stu-id="4d03f-154">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="4d03f-155">コンソール ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-155">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="4d03f-156">アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="4d03f-156">Run the app</span></span>

1. <span data-ttu-id="4d03f-157">プログラムを実行するには、ツール バーで **[HelloWorld]** を選択するか、**F5** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-157">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

   ![HelloWorld の実行ボタンが選択された Visual Studio ツールバー](./media/with-visual-studio/run-program.png)

   <span data-ttu-id="4d03f-159">コンソール ウィンドウが開き、"Hello World!" というテキストが</span><span class="sxs-lookup"><span data-stu-id="4d03f-159">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="4d03f-160">画面に出力され、Visual Studio のデバッグ情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d03f-160">printed on the screen and some Visual Studio debug information.</span></span>

   ![Hello World Press any key to continue と表示されているコンソール ウィンドウ](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="4d03f-162">任意のキーを押して、コンソール ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4d03f-162">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="4d03f-163">アプリを拡張する</span><span class="sxs-lookup"><span data-stu-id="4d03f-163">Enhance the app</span></span>

<span data-ttu-id="4d03f-164">アプリケーションを拡張し、ユーザーに名前の入力を求め、日付と時刻と共にそれを表示するようにします。</span><span class="sxs-lookup"><span data-stu-id="4d03f-164">Enhance your application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="4d03f-165">次の手順では、アプリを変更してから再度実行します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-165">The following instructions modify and run the app again:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="4d03f-166">C#</span><span class="sxs-lookup"><span data-stu-id="4d03f-166">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="4d03f-167">`Main` メソッド (現在は `Console.WriteLine` を呼び出す行のみ) の内容を以下のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4d03f-167">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   <span data-ttu-id="4d03f-168">このコードは、"What is your name?" と</span><span class="sxs-lookup"><span data-stu-id="4d03f-168">This code displays "What is your name?"</span></span> <span data-ttu-id="4d03f-169">コンソール ウィンドウに表示して、ユーザーが文字列を入力して Enter キーを押すまで待機します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-169">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="4d03f-170">これは文字列を `name` という変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-170">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="4d03f-171">さらに現在の現地時刻を含む <xref:System.DateTime.Now?displayProperty=nameWithType> プロパティの値を取得して、それを `date` という変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-171">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="4d03f-172">最後に[挿入文字列](../../csharp/language-reference/tokens/interpolated.md)を使用して、これらの値をコンソール ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-172">Finally, it uses an [interpolated string](../../csharp/language-reference/tokens/interpolated.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="4d03f-173">**[ビルド]**  >  **[ソリューションのビルド]** と選択して、プログラムをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="4d03f-173">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="4d03f-174">プログラムを実行するには、ツール バーで **[HelloWorld]** を選択するか、**F5** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-174">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="4d03f-175">プロンプトに対し、名前を入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-175">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![プログラムの出力が変更されたコンソール ウィンドウ](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="4d03f-177">任意のキーを押して、コンソール ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4d03f-177">Press any key to close the console window.</span></span>

# <a name="visual-basictabvb"></a>[<span data-ttu-id="4d03f-178">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d03f-178">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="4d03f-179">`Main` メソッド (現在は `Console.WriteLine` を呼び出す行のみ) の内容を以下のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4d03f-179">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-vb[GettingStarted#1](~/samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   <span data-ttu-id="4d03f-180">このコードは、"What is your name?" と</span><span class="sxs-lookup"><span data-stu-id="4d03f-180">This code displays "What is your name?"</span></span> <span data-ttu-id="4d03f-181">コンソール ウィンドウに表示して、ユーザーが文字列を入力して Enter キーを押すまで待機します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-181">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="4d03f-182">これは文字列を `name` という変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-182">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="4d03f-183">さらに現在の現地時刻を含む <xref:System.DateTime.Now?displayProperty=nameWithType> プロパティの値を取得して、それを `date` という変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-183">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="4d03f-184">最後に[挿入文字列](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)を使用して、これらの値をコンソール ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-184">Finally, it uses an [interpolated string](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="4d03f-185">**[ビルド]**  >  **[ソリューションのビルド]** と選択して、プログラムをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="4d03f-185">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="4d03f-186">プログラムを実行するには、ツール バーで **[HelloWorld]** を選択するか、**F5** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-186">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="4d03f-187">プロンプトに対し、名前を入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4d03f-187">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![プログラムの出力が変更されたコンソール ウィンドウ](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="4d03f-189">任意のキーを押して、コンソール ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4d03f-189">Press any key to close the console window.</span></span>

---

## <a name="next-steps"></a><span data-ttu-id="4d03f-190">次の手順</span><span class="sxs-lookup"><span data-stu-id="4d03f-190">Next steps</span></span>

<span data-ttu-id="4d03f-191">この記事では、最初の .NET Core アプリケーションを作成して実行しました。</span><span class="sxs-lookup"><span data-stu-id="4d03f-191">In this article, you've created and run your first .NET Core application.</span></span> <span data-ttu-id="4d03f-192">次の手順では、このアプリをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="4d03f-192">In the next step, you debug your app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4d03f-193">Visual Studio で .NET Core Hello World アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="4d03f-193">Debug a .NET Core Hello World application in Visual Studio</span></span>](debugging-with-visual-studio.md)
