---
title: Visual Studio 2017 での .NET Core を使用した C# Hello World アプリケーションの構築
description: Visual Studio 2017 で C# を使用した、単純な .NET Core コンソール アプリケーションを構築する方法について説明します。
author: BillWagner
ms.author: wiwagn
ms.date: 09/13/2017
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: cc7d78006998b79fe9d522e71883ce1af817c051
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428564"
---
# <a name="build-a-c-hello-world-application-with-the-net-core-sdk-in-visual-studio-2017"></a><span data-ttu-id="61a1b-103">Visual Studio 2017 で .NET Core を使用して C# Hello World アプリケーションを構築する</span><span class="sxs-lookup"><span data-stu-id="61a1b-103">Build a C# Hello World application with the .NET Core SDK in Visual Studio 2017</span></span>

<span data-ttu-id="61a1b-104">この記事では、Visual Studio 2017 で C# を使用して、簡単な .NET Core コンソール アプリケーションを構築、デバッグ、発行するステップ バイ ステップの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-104">This article provides a step-by-step introduction to building, debugging, and publishing a simple .NET Core console application using C# in Visual Studio 2017.</span></span> <span data-ttu-id="61a1b-105">Visual Studio 2017 は、.NET Core アプリケーション構築用の機能をすべて備えた開発環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-105">Visual Studio 2017 provides a full-featured development environment for building .NET Core applications.</span></span> <span data-ttu-id="61a1b-106">アプリケーションが特定のプラットフォームに依存する場合を除き、.NET Core が対象とする任意のプラットフォームおよび .NET Core がインストールされている任意のシステムで実行可能です。</span><span class="sxs-lookup"><span data-stu-id="61a1b-106">As long as the application doesn't have platform-specific dependencies, the application can run on any platform that .NET Core targets and on any system that has .NET Core installed.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="61a1b-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="61a1b-107">Prerequisites</span></span>

<span data-ttu-id="61a1b-108">[Visual Studio 2017 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)が ".NET Core クロスプラット フォーム開発" ワークロードと共にインストールされている。</span><span class="sxs-lookup"><span data-stu-id="61a1b-108">[Visual Studio 2017 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span> <span data-ttu-id="61a1b-109">.NET Core 2.1 以降のバージョンを使用してアプリを開発することができます。</span><span class="sxs-lookup"><span data-stu-id="61a1b-109">You can develop your app with .NET Core 2.1 or later versions.</span></span>

<span data-ttu-id="61a1b-110">詳細については、[.NET Core の依存関係と要件](../install/sdk.md?tabs=netcore30&pivots=os-windows#install-with-visual-studio)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61a1b-110">For more information, see the [.NET Core dependencies and requirements](../install/sdk.md?tabs=netcore30&pivots=os-windows#install-with-visual-studio)article.</span></span>

## <a name="a-simple-hello-world-application"></a><span data-ttu-id="61a1b-111">シンプルな "Hello World" アプリケーション</span><span class="sxs-lookup"><span data-stu-id="61a1b-111">A simple Hello World application</span></span>

<span data-ttu-id="61a1b-112">まず、シンプルな "Hello World" コンソール アプリケーションを作成してみましょう。</span><span class="sxs-lookup"><span data-stu-id="61a1b-112">Begin by creating a simple "Hello World" console application.</span></span> <span data-ttu-id="61a1b-113">この場合は、以下の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="61a1b-113">Follow these steps:</span></span>

1. <span data-ttu-id="61a1b-114">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-114">Launch Visual Studio.</span></span> <span data-ttu-id="61a1b-115">**[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** をメニュー バーから選択します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-115">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="61a1b-116">**[新しいプロジェクト]** ダイアログで、 **[Visual C#]** ノードを選択し、 **[.NET Core]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-116">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="61a1b-117">次に、 **[コンソール アプリ (.NET Core)]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-117">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="61a1b-118">**[名前]** テキスト ボックスに "HelloWorld" と入力します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-118">In the **Name** text box, type "HelloWorld".</span></span> <span data-ttu-id="61a1b-119">**[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-119">Select the **OK** button.</span></span>

   ![コンソール アプリが選択された状態の [新しいプロジェクト] ダイアログ](./media/with-visual-studio/visual-studio-new-project.png)

1. <span data-ttu-id="61a1b-121">Visual Studio は、テンプレートを使用してプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-121">Visual Studio uses the template to create your project.</span></span> <span data-ttu-id="61a1b-122">.NET Core の C# コンソール アプリケーション テンプレートで、`Program` というクラスが、<xref:System.String> 配列を引数として必要とする単一のメソッド `Main` とともに自動的に定義されます。</span><span class="sxs-lookup"><span data-stu-id="61a1b-122">The C# Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="61a1b-123">`Main` はアプリケーションのエントリ ポイントで、アプリケーションを起動するときに、ランタイムによって自動的に呼び出されるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="61a1b-123">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="61a1b-124">アプリケーションが起動されるときに提供されるコマンドライン引数はすべて *args* 配列にあります。</span><span class="sxs-lookup"><span data-stu-id="61a1b-124">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio と新しい HelloWorld プロジェクト](./media/with-visual-studio/visual-studio-main-window.png)

   <span data-ttu-id="61a1b-126">このテンプレートでは、シンプルな "Hello World" アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-126">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="61a1b-127"><xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> メソッドを呼び出し、リテラル文字列 "Hello World!" を</span><span class="sxs-lookup"><span data-stu-id="61a1b-127">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="61a1b-128">コンソール ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-128">in the console window.</span></span> <span data-ttu-id="61a1b-129">ツールバー上の緑色の矢印の付いた **HelloWorld** ボタンを選択すると、プログラムをデバッグ モードで実行できます。</span><span class="sxs-lookup"><span data-stu-id="61a1b-129">By selecting the **HelloWorld** button with the green arrow on the toolbar, you can run the program in Debug mode.</span></span> <span data-ttu-id="61a1b-130">しかしそのとき、コンソール ウィンドウは非常に短い時間だけ表示され、すぐに閉じられます。</span><span class="sxs-lookup"><span data-stu-id="61a1b-130">If you do, the console window is visible for only a brief time interval before it closes.</span></span> <span data-ttu-id="61a1b-131">これは、`Main` メソッド内の単一のステートメントが実行されるとすぐに `Main` メソッドが終了してアプリケーションが終了するためです。</span><span class="sxs-lookup"><span data-stu-id="61a1b-131">This occurs because the `Main` method terminates and the application ends as soon as the single statement in the `Main` method executes.</span></span>

1. <span data-ttu-id="61a1b-132">コンソール ウィンドウを閉じる前にアプリケーションに一時停止させるには、<xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> メソッドへの呼び出しのすぐ後に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-132">To cause the application to pause before it closes the console window, add the following code immediately after the call to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method:</span></span>

   ```csharp
   Console.Write("Press any key to continue...");
   Console.ReadKey(true);
   ```

   <span data-ttu-id="61a1b-133">このコードは、任意のキーを押すようにユーザーにメッセージを表示し、キーが押されるまでプログラムを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-133">This code prompts the user to press any key and then pauses the program until a key is pressed.</span></span>

1. <span data-ttu-id="61a1b-134">メニュー バーで **[ビルド]**  >  **[ソリューションのビルド]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-134">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="61a1b-135">これにより、プログラムが IL (中間言語) にコンパイルされ、それが JIT (just-in-time) コンパイラによってバイナリ コードに変換されます。</span><span class="sxs-lookup"><span data-stu-id="61a1b-135">This compiles your program into an intermediate language (IL) that's converted into binary code by a just-in-time (JIT) compiler.</span></span>

1. <span data-ttu-id="61a1b-136">ツールバー上の緑色の矢印の付いた **HelloWorld** ボタンを選択して、プログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-136">Run the program by selecting the **HelloWorld** button with the green arrow on the toolbar.</span></span>

   ![Hello World Press any key to continue と表示されているコンソール ウィンドウ](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="61a1b-138">任意のキーを押して、コンソール ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="61a1b-138">Press any key to close the console window.</span></span>

## <a name="enhancing-the-hello-world-application"></a><span data-ttu-id="61a1b-139">Hello World アプリケーションの拡張</span><span class="sxs-lookup"><span data-stu-id="61a1b-139">Enhancing the Hello World application</span></span>

<span data-ttu-id="61a1b-140">アプリケーションを拡張し、ユーザーに名前の入力を求め、日付と時刻と共にそれを表示するようにします。</span><span class="sxs-lookup"><span data-stu-id="61a1b-140">Enhance your application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="61a1b-141">以下のように、プログラムを変更してテストします。</span><span class="sxs-lookup"><span data-stu-id="61a1b-141">To modify and test the program, do the following:</span></span>

1. <span data-ttu-id="61a1b-142">コード ウィンドウで `static void Main(string[] args)` 行のすぐ後に、次の C# コードを、左角かっこと右角かっこで囲んで入力します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-142">Enter the following C# code in the code window immediately after the opening bracket that follows the `static void Main(string[] args)` line and before the first closing curly bracket:</span></span>

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   <span data-ttu-id="61a1b-143">このコードにより、`Main` メソッドのコンテンツが置換されます。</span><span class="sxs-lookup"><span data-stu-id="61a1b-143">This code replaces the contents of the `Main` method.</span></span>

   ![Main メソッドが更新された Visual Studio プログラムの C シャープ ファイル](./media/with-visual-studio/visual-csharp-code-window.png)

   <span data-ttu-id="61a1b-145">このコードは、"What is your name?" と</span><span class="sxs-lookup"><span data-stu-id="61a1b-145">This code displays "What is your name?"</span></span> <span data-ttu-id="61a1b-146">コンソール ウィンドウに表示して、ユーザーが文字列を入力して Enter キーを押すまで待機します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-146">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="61a1b-147">これは文字列を `name` という変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-147">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="61a1b-148">さらに現在の現地時刻を含む <xref:System.DateTime.Now?displayProperty=nameWithType> プロパティの値を取得して、それを `date` という変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-148">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="61a1b-149">最後に[挿入文字列](../../csharp/language-reference/tokens/interpolated.md)を使用して、これらの値をコンソール ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-149">Finally, it uses an [interpolated string](../../csharp/language-reference/tokens/interpolated.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="61a1b-150">**[ビルド]**  >  **[ソリューションのビルド]** と選択して、プログラムをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="61a1b-150">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="61a1b-151">Visual Studio で、ツールバーの緑色の矢印を選択するか、F5 を押すか、メニューで **[デバッグ]**  >  **[デバッグの開始]** メニュー アイテムを選択して、プログラムをデバッグ モードで実行します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-151">Run the program in Debug mode in Visual Studio by selecting the green arrow on the toolbar, pressing F5, or choosing the **Debug** > **Start Debugging** menu item.</span></span> <span data-ttu-id="61a1b-152">プロンプトに対し、名前を入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="61a1b-152">Respond to the prompt by entering a name and pressing the Enter key.</span></span>

   ![プログラムの出力が変更されたコンソール ウィンドウ](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="61a1b-154">任意のキーを押して、コンソール ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="61a1b-154">Press any key to close the console window.</span></span>

<span data-ttu-id="61a1b-155">アプリケーションが作成され、実行されました。</span><span class="sxs-lookup"><span data-stu-id="61a1b-155">You've created and run your application.</span></span> <span data-ttu-id="61a1b-156">本格的なアプリケーションを開発するには、さらにいくつか追加の手順を行い、アプリケーションをリリース可能な状態にします。</span><span class="sxs-lookup"><span data-stu-id="61a1b-156">To develop a professional application, take some additional steps to make your application ready for release:</span></span>

- <span data-ttu-id="61a1b-157">アプリケーションのデバッグについては、[Visual Studio 2017 を使用した .NET Core Hello World アプリケーションのデバッグ](debugging-with-visual-studio.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61a1b-157">For information on debugging your application, see [Debug your .NET Core Hello World application using Visual Studio 2017](debugging-with-visual-studio.md).</span></span>

- <span data-ttu-id="61a1b-158">アプリケーションの再頒布可能バージョンの開発と発行については、「[Publish your .NET Core Hello World application with Visual Studio 2017 (Visual Studio 2017 を使用した .NET Core Hello World アプリケーションの発行)](publishing-with-visual-studio.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61a1b-158">For information on developing and publishing a distributable version of your application, see [Publish your .NET Core Hello World application with Visual Studio 2017](publishing-with-visual-studio.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="61a1b-159">関連記事</span><span class="sxs-lookup"><span data-stu-id="61a1b-159">Related articles</span></span>

<span data-ttu-id="61a1b-160">.NET Core と Visual Studio 2017 では、コンソール アプリケーションの代わりにクラス ライブラリを構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="61a1b-160">Instead of a console application, you can also build a class library with .NET Core and Visual Studio 2017.</span></span> <span data-ttu-id="61a1b-161">ステップ バイ ステップの説明については、「[Visual Studio 2017 の C# および .NET Core を使用したクラス ライブラリの構築](library-with-visual-studio.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61a1b-161">For a step-by-step introduction, see [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md).</span></span>

<span data-ttu-id="61a1b-162">無償ダウンロードできるコード エディターである [Visual Studio Code](https://code.visualstudio.com/) を使用して、Mac、Linux、Windows 上で .NET Core コンソール アプリケーションを開発することもできます。</span><span class="sxs-lookup"><span data-stu-id="61a1b-162">You can also develop a .NET Core console app on Mac, Linux, and Windows by using [Visual Studio Code](https://code.visualstudio.com/), a downloadable code editor.</span></span> <span data-ttu-id="61a1b-163">ステップ バイ ステップのチュートリアルについては、「[Visual Studio Code の概要](with-visual-studio-code.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61a1b-163">For a step-by-step tutorial, see [Getting Started with Visual Studio Code](with-visual-studio-code.md).</span></span>
