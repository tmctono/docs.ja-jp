---
title: Visual Studio 2017 における Visual Basic の .NET Core Hello World アプリケーション
description: Visual Studio 2017 で Visual Basic を使用した、単純な .NET Core コンソール アプリケーションを構築する方法について説明します。
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
dev_langs:
- vb
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: b4f3cc055f73332db1348ef35174beab614df147
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71039615"
---
# <a name="build-a-visual-basic-hello-world-application-with-the-net-core-sdk-in-visual-studio-2017"></a><span data-ttu-id="ac61c-103">Visual Studio 2017 で .NET Core を使用して Visual Basic Hello World アプリケーションを構築する</span><span class="sxs-lookup"><span data-stu-id="ac61c-103">Build a Visual Basic Hello World application with the .NET Core SDK in Visual Studio 2017</span></span>

<span data-ttu-id="ac61c-104">このトピックでは、Visual Studio 2017 で Visual Basic を使用して、簡単な .NET Core コンソール アプリケーションを構築、デバッグ、発行するステップ バイ ステップの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-104">This topic provides a step-by-step introduction to building, debugging, and publishing a simple .NET Core console application using Visual Basic in Visual Studio 2017.</span></span> <span data-ttu-id="ac61c-105">Visual Studio 2017 は、.NET Core アプリケーション構築用の機能をすべて備えた開発環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-105">Visual Studio 2017 provides a full-featured development environment for building .NET Core applications.</span></span> <span data-ttu-id="ac61c-106">アプリケーションが特定のプラットフォームに依存する場合を除き、.NET Core が対象とする任意のプラットフォームおよび .NET Core がインストールされている任意のシステムで実行可能です。</span><span class="sxs-lookup"><span data-stu-id="ac61c-106">As long as the application doesn't have platform-specific dependencies, the application can run on any platform that .NET Core targets and on any system that has .NET Core installed.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ac61c-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ac61c-107">Prerequisites</span></span>

<span data-ttu-id="ac61c-108">[Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) が ".NET Core クロスプラット フォーム開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="ac61c-108">[Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) with the ".NET Core cross-platform development" workload installed.</span></span> <span data-ttu-id="ac61c-109">.NET Core 2.1 以降のバージョンを使用してアプリを開発することができます。</span><span class="sxs-lookup"><span data-stu-id="ac61c-109">You can develop your app with .NET Core 2.1 or later versions.</span></span>

<span data-ttu-id="ac61c-110">詳細については、「[Windows における .NET Core の前提条件](../windows-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac61c-110">For more information, see [Prerequisites for .NET Core on Windows](../windows-prerequisites.md).</span></span>

## <a name="a-simple-hello-world-application"></a><span data-ttu-id="ac61c-111">シンプルな "Hello World" アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ac61c-111">A simple Hello World application</span></span>

<span data-ttu-id="ac61c-112">まず、シンプルな "Hello World" コンソール アプリケーションを作成してみましょう。</span><span class="sxs-lookup"><span data-stu-id="ac61c-112">Begin by creating a simple "Hello World" console application.</span></span> <span data-ttu-id="ac61c-113">この場合は、以下の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="ac61c-113">Follow these steps:</span></span>

1. <span data-ttu-id="ac61c-114">Visual Studio 2017 を起動します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-114">Launch Visual Studio 2017.</span></span> <span data-ttu-id="ac61c-115">**[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** をメニュー バーから選択します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-115">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="ac61c-116">[*新しいプロジェクト*\*] ダイアログで、 **[Visual Basic]** ノードを選択し、 **[.NET Core]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-116">In the *New Project*\* dialog, select the **Visual Basic** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="ac61c-117">次に、 **[コンソール アプリ (.NET Core)]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-117">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="ac61c-118">**[名前]** テキスト ボックスに "HelloWorld" と入力します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-118">In the **Name** text box, type "HelloWorld".</span></span> <span data-ttu-id="ac61c-119">**[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-119">Select the **OK** button.</span></span>

   ![コンソール アプリが選択された状態の [新しいプロジェクト] ダイアログ](./media/vb-with-visual-studio/visual-studio-new-project.png)

1. <span data-ttu-id="ac61c-121">Visual Studio は、テンプレートを使用してプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-121">Visual Studio uses the template to create your project.</span></span> <span data-ttu-id="ac61c-122">.NET Core の Visual Basic コンソール アプリケーション テンプレートで、`Program` というクラスが、<xref:System.String> 配列を引数として必要とする単一のメソッド `Main` とともに自動的に定義されます。</span><span class="sxs-lookup"><span data-stu-id="ac61c-122">The Visual Basic Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="ac61c-123">`Main` はアプリケーションのエントリ ポイントで、アプリケーションを起動するときに、ランタイムによって自動的に呼び出されるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="ac61c-123">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="ac61c-124">アプリケーションが起動されるときに提供されるコマンドライン引数はすべて *args* 配列にあります。</span><span class="sxs-lookup"><span data-stu-id="ac61c-124">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio と新しい HelloWorld プロジェクト](./media/vb-with-visual-studio/visual-studio-main-window.png)

   <span data-ttu-id="ac61c-126">このテンプレートでは、シンプルな "Hello World" アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-126">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="ac61c-127"><xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> メソッドを呼び出し、リテラル文字列 "Hello World!" を</span><span class="sxs-lookup"><span data-stu-id="ac61c-127">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="ac61c-128">コンソール ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-128">in the console window.</span></span> <span data-ttu-id="ac61c-129">ツールバー上の緑色の矢印の付いた **HelloWorld** ボタンを選択すると、プログラムをデバッグ モードで実行できます。</span><span class="sxs-lookup"><span data-stu-id="ac61c-129">By selecting the **HelloWorld** button with the green arrow on the toolbar, you can run the program in Debug mode.</span></span> <span data-ttu-id="ac61c-130">しかしそのとき、コンソール ウィンドウは非常に短い時間だけ表示され、すぐに閉じられます。</span><span class="sxs-lookup"><span data-stu-id="ac61c-130">If you do, the console window is visible for only a brief time interval before it closes.</span></span> <span data-ttu-id="ac61c-131">これは、`Main` メソッド内の単一のステートメントが実行されるとすぐに `Main` メソッドが終了してアプリケーションが終了するためです。</span><span class="sxs-lookup"><span data-stu-id="ac61c-131">This occurs because the `Main` method terminates and the application ends as soon as the single statement in the `Main` method executes.</span></span>

1. <span data-ttu-id="ac61c-132">コンソール ウィンドウを閉じる前にアプリケーションに一時停止させるには、<xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> メソッドへの呼び出しのすぐ後に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-132">To cause the application to pause before it closes the console window, add the following code immediately after the call to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method:</span></span>

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```

   <span data-ttu-id="ac61c-133">このコードは、任意のキーを押すようにユーザーにメッセージを表示し、キーが押されるまでプログラムを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-133">This code prompts the user to press any key and then pauses the program until a key is pressed.</span></span>

1. <span data-ttu-id="ac61c-134">メニュー バーで **[ビルド]**  >  **[ソリューションのビルド]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-134">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="ac61c-135">これにより、プログラムが IL (中間言語) にコンパイルされ、それが JIT (just-in-time) コンパイラによってバイナリ コードに変換されます。</span><span class="sxs-lookup"><span data-stu-id="ac61c-135">This compiles your program into an intermediate language (IL) that's converted into binary code by a just-in-time (JIT) compiler.</span></span>

1. <span data-ttu-id="ac61c-136">ツールバー上の緑色の矢印の付いた **HelloWorld** ボタンを選択して、プログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-136">Run the program by selecting the **HelloWorld** button with the green arrow on the toolbar.</span></span>

   ![Hello World Press any key to continue と表示されているコンソール ウィンドウ](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="ac61c-138">任意のキーを押して、コンソール ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ac61c-138">Press any key to close the console window.</span></span>

## <a name="enhancing-the-hello-world-application"></a><span data-ttu-id="ac61c-139">Hello World アプリケーションの拡張</span><span class="sxs-lookup"><span data-stu-id="ac61c-139">Enhancing the Hello World application</span></span>

<span data-ttu-id="ac61c-140">アプリケーションを拡張し、ユーザーに名前の入力を求め、日付と時刻と共にそれを表示するようにします。</span><span class="sxs-lookup"><span data-stu-id="ac61c-140">Enhance your application to prompt the user for his or her name and to display it along with the date and time.</span></span> <span data-ttu-id="ac61c-141">以下のように、プログラムを変更してテストします。</span><span class="sxs-lookup"><span data-stu-id="ac61c-141">To modify and test the program, do the following:</span></span>

1. <span data-ttu-id="ac61c-142">コード ウィンドウで `Sub Main(args As String())` 行のすぐ後に、次の Visual Basic コードを、先頭に角かっこを付け最後に閉じかっこを付けて入力します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-142">Enter the following Visual Basic code in the code window immediately after the opening bracket that follows the `Sub Main(args As String())` line and before the first closing bracket:</span></span>

   [!code-vb[GettingStarted#1](../../../samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   <span data-ttu-id="ac61c-143">このコードにより、`Main` メソッドのコンテンツが置換されます。</span><span class="sxs-lookup"><span data-stu-id="ac61c-143">This code replaces the contents of the `Main` method.</span></span>

   ![Main メソッドが更新された Visual Studio プログラム ファイル](./media/vb-with-visual-studio/visual-basic-code-window.png)

   <span data-ttu-id="ac61c-145">このコードは、"What is your name?" と</span><span class="sxs-lookup"><span data-stu-id="ac61c-145">This code displays "What is your name?"</span></span> <span data-ttu-id="ac61c-146">コンソール ウィンドウに表示して、ユーザーが文字列を入力して Enter キーを押すまで待機します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-146">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="ac61c-147">これは文字列を `name` という変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-147">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="ac61c-148">さらに現在の現地時刻を含む <xref:System.DateTime.Now?displayProperty=nameWithType> プロパティの値を取得して、それを `currentDate` という変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-148">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `currentDate`.</span></span> <span data-ttu-id="ac61c-149">最後に[挿入文字列](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)を使用して、これらの値をコンソール ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-149">Finally, it uses an [interpolated string](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="ac61c-150">**[ビルド]**  >  **[ソリューションのビルド]** と選択して、プログラムをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="ac61c-150">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="ac61c-151">Visual Studio で、ツールバーの緑色の矢印を選択するか、F5 を押すか、メニューで **[デバッグ]**  >  **[デバッグの開始]** メニュー アイテムを選択して、プログラムをデバッグ モードで実行します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-151">Run the program in Debug mode in Visual Studio by selecting the green arrow on the toolbar, pressing F5, or choosing the **Debug** > **Start Debugging** menu item.</span></span> <span data-ttu-id="ac61c-152">プロンプトに対し、名前を入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ac61c-152">Respond to the prompt by entering a name and pressing the Enter key.</span></span>

   ![プログラムの出力が変更されたコンソール ウィンドウ](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="ac61c-154">任意のキーを押して、コンソール ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ac61c-154">Press any key to close the console window.</span></span>

<span data-ttu-id="ac61c-155">アプリケーションが作成され、実行されました。</span><span class="sxs-lookup"><span data-stu-id="ac61c-155">You've created and run your application.</span></span> <span data-ttu-id="ac61c-156">本格的なアプリケーションを開発するには、さらにいくつか追加の手順を行い、アプリケーションをリリース可能な状態にします。</span><span class="sxs-lookup"><span data-stu-id="ac61c-156">To develop a professional application, take some additional steps to make your application ready for release:</span></span>

- <span data-ttu-id="ac61c-157">アプリケーションをデバッグする場合は、[Visual Studio 2017 を使用した .NET Core Hello World アプリケーションのデバッグ](debugging-with-visual-studio.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac61c-157">To debug your application, see [Debug your .NET Core Hello World application using Visual Studio 2017](debugging-with-visual-studio.md).</span></span>

- <span data-ttu-id="ac61c-158">アプリケーションの再頒布可能バージョンの開発と発行については、[Visual Studio 2017 を使用した .NET Core Hello World アプリケーションの発行](publishing-with-visual-studio.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac61c-158">To publish a distributable version of your application, see [Publish your .NET Core Hello World application with Visual Studio 2017](publishing-with-visual-studio.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ac61c-159">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ac61c-159">Related topics</span></span>

<span data-ttu-id="ac61c-160">Visual Basic、.NET Core、および Visual Studio 2017 では、コンソール アプリケーションの代わりに .NET Standard クラス ライブラリを構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac61c-160">Instead of a console application, you can also build a .NET Standard class library with Visual Basic, .NET Core, and Visual Studio 2017.</span></span> <span data-ttu-id="ac61c-161">段階を追った手順については、「[Visual Studio 2017 で Visual Basic と .NET Core を使用して .NET Standard ライブラリを構築する](vb-library-with-visual-studio.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac61c-161">For a step-by-step introduction, see [Build a .NET Standard library with Visual Basic and .NET Core SDK in Visual Studio 2017](vb-library-with-visual-studio.md).</span></span>
