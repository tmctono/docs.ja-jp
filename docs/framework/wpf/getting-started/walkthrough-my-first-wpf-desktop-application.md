---
title: Visual Studio での WPF アプリケーションを作成します。
ms.date: 10/26/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.custom: vs-dotnet
ms.openlocfilehash: ace9e339a65c14e69e1a672880e392c7e09d36e8
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212379"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="20b68-102">チュートリアル: 初めての WPF デスクトップ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="20b68-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="20b68-103">この記事では、ほとんどの WPF アプリケーションに共通する要素を含む単純な Windows Presentation Foundation (WPF) アプリケーションを開発する方法を示します。Extensible Application Markup Language (XAML) マークアップ、分離コード、アプリケーション定義、コントロール、レイアウト、データ バインド、およびスタイル。</span><span class="sxs-lookup"><span data-stu-id="20b68-103">This article shows you how to develop a simple Windows Presentation Foundation (WPF) application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span>

<span data-ttu-id="20b68-104">このチュートリアルには、次の手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="20b68-104">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="20b68-105">XAML を使用して、アプリケーションのユーザー インターフェイス (UI) の外観をデザインします。</span><span class="sxs-lookup"><span data-stu-id="20b68-105">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="20b68-106">アプリケーションの動作を構築するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="20b68-106">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="20b68-107">アプリケーションを管理するアプリケーション定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="20b68-107">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="20b68-108">コントロールを追加し、アプリケーションの UI を作成するレイアウトを作成します。</span><span class="sxs-lookup"><span data-stu-id="20b68-108">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="20b68-109">アプリケーションの UI 全体で一貫した外観のスタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="20b68-109">Create styles for a consistent appearance throughout an application's UI.</span></span>

- <span data-ttu-id="20b68-110">UI をデータから UI を設定して、データと UI の同期を維持するデータにバインドします。</span><span class="sxs-lookup"><span data-stu-id="20b68-110">Bind the UI to data to both populate the UI from data and keep the data and UI synchronized.</span></span>

<span data-ttu-id="20b68-111">チュートリアルの目的は、スタンドアロンのユーザーを選択したユーザーの経費報告書を表示できる Windows アプリケーションを構築したします。</span><span class="sxs-lookup"><span data-stu-id="20b68-111">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="20b68-112">アプリケーションは、ブラウザー スタイルのウィンドウでホストされているいくつかの WPF ページで構成されます。</span><span class="sxs-lookup"><span data-stu-id="20b68-112">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="20b68-113">このチュートリアルの構築に使用するサンプル コードでは、Visual Basic と c# で使用可能な[Introduction to Building WPF Applications](https://go.microsoft.com/fwlink/?LinkID=160008)します。</span><span class="sxs-lookup"><span data-stu-id="20b68-113">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Introduction to Building WPF Applications](https://go.microsoft.com/fwlink/?LinkID=160008).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="20b68-114">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="20b68-114">Prerequisites</span></span>

- <span data-ttu-id="20b68-115">Visual Studio 2017 またはそれ以降</span><span class="sxs-lookup"><span data-stu-id="20b68-115">Visual Studio 2017 or later</span></span>

   <span data-ttu-id="20b68-116">最新バージョンの Visual Studio のインストールの詳細については、次を参照してください。 [Visual Studio のインストール](/visualstudio/install/install-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="20b68-116">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="20b68-117">アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="20b68-117">Create the application project</span></span>

<span data-ttu-id="20b68-118">最初の手順では、アプリケーションの定義を 2 つのページとイメージを含むアプリケーション インフラストラクチャを作成します。</span><span class="sxs-lookup"><span data-stu-id="20b68-118">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="20b68-119">Visual Basic または Visual c# のという名前で新しい WPF アプリケーション プロジェクトを作成する **`ExpenseIt`** :</span><span class="sxs-lookup"><span data-stu-id="20b68-119">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="20b68-120">Visual Studio を開き、選択**ファイル** > **新規** > **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="20b68-120">Open Visual Studio and select **File** > **New** > **Project**.</span></span>

      <span data-ttu-id="20b68-121">**新しいプロジェクト**ダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="20b68-121">The **New Project** dialog opens.</span></span>

   2. <span data-ttu-id="20b68-122">下、**インストール済み**カテゴリで、いずれかを展開、 **Visual C#** または**Visual Basic**ノードをクリックして**Windows デスクトップ**します。</span><span class="sxs-lookup"><span data-stu-id="20b68-122">Under the **Installed** category, expand either the **Visual C#** or **Visual Basic** node, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="20b68-123">選択、 **WPF アプリ (.NET Framework)** テンプレート。</span><span class="sxs-lookup"><span data-stu-id="20b68-123">Select the **WPF App (.NET Framework)** template.</span></span> <span data-ttu-id="20b68-124">名前を入力します **`ExpenseIt`** 選び**OK**します。</span><span class="sxs-lookup"><span data-stu-id="20b68-124">Enter the name **`ExpenseIt`** and then select **OK**.</span></span>

      ![選択した WPF アプリで新しいプロジェクト ダイアログ ボックス](media/new-project-dialog.png)

      <span data-ttu-id="20b68-126">Visual Studio は、プロジェクトを作成し、という名前の既定アプリケーション ウィンドウのデザイナーが開きます**MainWindow.xaml**します。</span><span class="sxs-lookup"><span data-stu-id="20b68-126">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="20b68-127">このチュートリアルでは、<xref:System.Windows.Controls.DataGrid>以降、.NET Framework 4 で利用可能であるコントロール。</span><span class="sxs-lookup"><span data-stu-id="20b68-127">This walkthrough uses the <xref:System.Windows.Controls.DataGrid> control that is available in the .NET Framework 4 and later.</span></span> <span data-ttu-id="20b68-128">プロジェクトが、.NET Framework 4 を対象とすることを確認以降に。</span><span class="sxs-lookup"><span data-stu-id="20b68-128">Be sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="20b68-129">詳細については、「[方法 :.NET Framework のターゲット バージョンを指定する](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20b68-129">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

2. <span data-ttu-id="20b68-130">開いている*Application.xaml* (Visual Basic) または*App.xaml* (c#)。</span><span class="sxs-lookup"><span data-stu-id="20b68-130">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="20b68-131">この XAML ファイルでは、WPF アプリケーションとすべてのアプリケーション リソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="20b68-131">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="20b68-132">ときに自動的に表示する UI を指定することもこのファイルを使用するアプリケーションを起動します。この場合、 *MainWindow.xaml*します。</span><span class="sxs-lookup"><span data-stu-id="20b68-132">You also use this file to specify the UI that automatically shows when the application starts; in this case, *MainWindow.xaml*.</span></span>

    <span data-ttu-id="20b68-133">このよう Visual Basic では、XAML になります。</span><span class="sxs-lookup"><span data-stu-id="20b68-133">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="20b68-134">C# では、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="20b68-134">Or like this in C#:</span></span>

    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="20b68-135">*MainWindow.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="20b68-135">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="20b68-136">この XAML ファイルは、アプリケーションのメイン ウィンドウであるため、ページで作成されたコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="20b68-136">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="20b68-137"><xref:System.Windows.Window>クラスは、タイトル、サイズ、アイコンなど、ウィンドウのプロパティを定義し、閉じるか、非表示などのイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="20b68-137">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="20b68-138"><xref:System.Windows.Navigation.NavigationWindow>.xaml の<xref:System.Windows.Window>要素を、次に示すように変更します。</span><span class="sxs-lookup"><span data-stu-id="20b68-138">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="20b68-139">このアプリは、ユーザーの入力に応じてさまざまなコンテンツに移動します。</span><span class="sxs-lookup"><span data-stu-id="20b68-139">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="20b68-140">そのため、メイン ウィンドウを<xref:System.Windows.Window>から<xref:System.Windows.Navigation.NavigationWindow>に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20b68-140">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="20b68-141"><xref:System.Windows.Navigation.NavigationWindow>  は、<xref:System.Windows.Window>のすべてのプロパティを継承しています。</span><span class="sxs-lookup"><span data-stu-id="20b68-141"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="20b68-142"><xref:System.Windows.Navigation.NavigationWindow> XAML ファイル内の要素のインスタンスを作成する、<xref:System.Windows.Navigation.NavigationWindow>クラス。</span><span class="sxs-lookup"><span data-stu-id="20b68-142">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="20b68-143">詳細については、次を参照してください。[ナビゲーションの概要](../../../../docs/framework/wpf/app-development/navigation-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="20b68-143">For more information, see [Navigation overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="20b68-144">次のプロパティを変更、<xref:System.Windows.Navigation.NavigationWindow>要素。</span><span class="sxs-lookup"><span data-stu-id="20b68-144">Change the following properties on the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="20b68-145">設定、<xref:System.Windows.Window.Title%2A>プロパティを"`ExpenseIt`"。</span><span class="sxs-lookup"><span data-stu-id="20b68-145">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="20b68-146">設定、<xref:System.Windows.FrameworkElement.Width%2A>プロパティを 500 ピクセルにします。</span><span class="sxs-lookup"><span data-stu-id="20b68-146">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    - <span data-ttu-id="20b68-147">設定、<xref:System.Windows.FrameworkElement.Height%2A>プロパティを 350 ピクセル、高さ。</span><span class="sxs-lookup"><span data-stu-id="20b68-147">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="20b68-148">削除、<xref:System.Windows.Controls.Grid>間の要素、<xref:System.Windows.Navigation.NavigationWindow>タグ。</span><span class="sxs-lookup"><span data-stu-id="20b68-148">Remove the <xref:System.Windows.Controls.Grid> elements between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

    <span data-ttu-id="20b68-149">このよう Visual Basic では、XAML になります。</span><span class="sxs-lookup"><span data-stu-id="20b68-149">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="20b68-150">C# では、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="20b68-150">Or like this in C#:</span></span>

    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

6. <span data-ttu-id="20b68-151">開いている*MainWindow.xaml.vb*または*MainWindow.xaml.cs*します。</span><span class="sxs-lookup"><span data-stu-id="20b68-151">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="20b68-152">このファイルは、分離コード ファイルで宣言されたイベントを処理するコードを含む*MainWindow.xaml*します。</span><span class="sxs-lookup"><span data-stu-id="20b68-152">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="20b68-153">このファイルには、XAML で定義されたウィンドウの部分クラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="20b68-153">This file contains a partial class for the window defined in XAML.</span></span>

7. <span data-ttu-id="20b68-154">C# を使用している場合は、変更、`MainWindow`クラスから派生する<xref:System.Windows.Navigation.NavigationWindow>します。</span><span class="sxs-lookup"><span data-stu-id="20b68-154">If you are using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="20b68-155">(Visual basic の場合は、これは XAML でウィンドウを変更するときにします。)</span><span class="sxs-lookup"><span data-stu-id="20b68-155">(In Visual Basic, this happens automatically when you change the window in XAML.)</span></span>

   <span data-ttu-id="20b68-156">コードについては、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="20b68-156">Your code should look like this:</span></span>

   [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
   [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]

   > [!TIP]
   > <span data-ttu-id="20b68-157">C# と Visual Basic でのサンプル コードのコード言語を切り替えることができます、**言語**この記事の右上隅のドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="20b68-157">You can toggle the code language of the sample code between C# and Visual Basic in the **Language** drop-down on the upper right side of this article.</span></span>

## <a name="add-files-to-the-application"></a><span data-ttu-id="20b68-158">ファイルをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="20b68-158">Add files to the application</span></span>

<span data-ttu-id="20b68-159">このセクションでは、アプリケーションに 2 つのページと 1 つのイメージを追加します。</span><span class="sxs-lookup"><span data-stu-id="20b68-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="20b68-160">新しい WPF ページをプロジェクトに追加し、名前 *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="20b68-160">Add a new WPF page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="20b68-161">**ソリューション エクスプ ローラー**を右クリックし、 **`ExpenseIt`** プロジェクト ノード**追加** > **ページ**します。</span><span class="sxs-lookup"><span data-stu-id="20b68-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="20b68-162">**新しい項目の追加**ダイアログ ボックスで、**ページ (WPF)** テンプレートは既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="20b68-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="20b68-163">名前を入力します **`ExpenseItHome`** 、し、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="20b68-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="20b68-164">このページは、アプリケーションの起動時に表示される最初のページです。</span><span class="sxs-lookup"><span data-stu-id="20b68-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="20b68-165">経費報告書を表示するからを選択するユーザーの一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="20b68-165">It will show a list of people to select from, to show an expense report for.</span></span>

2. <span data-ttu-id="20b68-166">開いている *`ExpenseItHome.xaml`* します。</span><span class="sxs-lookup"><span data-stu-id="20b68-166">Open *`ExpenseItHome.xaml`*.</span></span>

3. <span data-ttu-id="20b68-167">設定、<xref:System.Windows.Controls.Page.Title%2A>に"`ExpenseIt - Home`"。</span><span class="sxs-lookup"><span data-stu-id="20b68-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

    <span data-ttu-id="20b68-168">このよう Visual Basic では、XAML になります。</span><span class="sxs-lookup"><span data-stu-id="20b68-168">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="20b68-169">C# では、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="20b68-169">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

4. <span data-ttu-id="20b68-170">*MainWindow.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="20b68-170">Open *MainWindow.xaml*.</span></span>

5. <span data-ttu-id="20b68-171">設定、<xref:System.Windows.Navigation.NavigationWindow.Source%2A>プロパティを<xref:System.Windows.Navigation.NavigationWindow>に"`ExpenseItHome.xaml`"。</span><span class="sxs-lookup"><span data-stu-id="20b68-171">Set the <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property on the <xref:System.Windows.Navigation.NavigationWindow> to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="20b68-172">これにより設定 *`ExpenseItHome.xaml`* アプリケーションの起動時を開く最初のページになります。</span><span class="sxs-lookup"><span data-stu-id="20b68-172">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> <span data-ttu-id="20b68-173">このよう Visual Basic では、XAML になります。</span><span class="sxs-lookup"><span data-stu-id="20b68-173">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="20b68-174">C# では、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="20b68-174">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="20b68-175">設定することも、**ソース**プロパティ、 **[その他]** のカテゴリ、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="20b68-175">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![プロパティ ウィンドウで、ソース プロパティ](media/properties-source.png)

6. <span data-ttu-id="20b68-177">もう 1 つの新しい WPF ページをプロジェクトに追加し、名前*ExpenseReportPage.xaml*:。</span><span class="sxs-lookup"><span data-stu-id="20b68-177">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="20b68-178">**ソリューション エクスプ ローラー**を右クリックし、 **`ExpenseIt`** プロジェクト ノード**追加** > **ページ**します。</span><span class="sxs-lookup"><span data-stu-id="20b68-178">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="20b68-179">**新しい項目の追加**ダイアログ ボックスで、**ページ (WPF)** テンプレートは既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="20b68-179">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="20b68-180">名前を入力します**ExpenseReportPage**、し、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="20b68-180">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="20b68-181">このページで選択されているユーザーの経費報告書が表示されます、 **`ExpenseItHome`** ページ。</span><span class="sxs-lookup"><span data-stu-id="20b68-181">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

7. <span data-ttu-id="20b68-182">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="20b68-182">Open *ExpenseReportPage.xaml*.</span></span>

8. <span data-ttu-id="20b68-183">設定、<xref:System.Windows.Controls.Page.Title%2A>に"`ExpenseIt - View Expense`"。</span><span class="sxs-lookup"><span data-stu-id="20b68-183">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

    <span data-ttu-id="20b68-184">このよう Visual Basic では、XAML になります。</span><span class="sxs-lookup"><span data-stu-id="20b68-184">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="20b68-185">C# では、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="20b68-185">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

9. <span data-ttu-id="20b68-186">開いている*ExpenseItHome.xaml.vb*と*ExpenseReportPage.xaml.vb*、または*ExpenseItHome.xaml.cs*と*ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="20b68-186">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="20b68-187">Visual Studio が自動的に作成、新しいファイルを作成するときに、*コード ビハインド*ファイル。</span><span class="sxs-lookup"><span data-stu-id="20b68-187">When you create a new Page file, Visual Studio automatically creates a *code-behind* file.</span></span> <span data-ttu-id="20b68-188">これらの分離コード ファイルでは、ユーザー入力に対応するためのロジックを処理します。</span><span class="sxs-lookup"><span data-stu-id="20b68-188">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="20b68-189">コードのようになります **`ExpenseItHome`** :</span><span class="sxs-lookup"><span data-stu-id="20b68-189">Your code should look like this for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="20b68-190">このような**ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="20b68-190">And like this for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

10. <span data-ttu-id="20b68-191">という名前のイメージを追加*watermark.png*をプロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="20b68-191">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="20b68-192">独自のイメージを作成、サンプル コードからファイルをコピーまたは入手[ここ](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/media/watermark.png)します。</span><span class="sxs-lookup"><span data-stu-id="20b68-192">You can create your own image, copy the file from the sample code, or get it [here](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/media/watermark.png).</span></span>

    1. <span data-ttu-id="20b68-193">プロジェクト ノードを右クリックして**追加** > **既存項目の**、またはキーを押します**Shift**+**Alt**+ **A**します。</span><span class="sxs-lookup"><span data-stu-id="20b68-193">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="20b68-194">**既存項目の追加**ダイアログを使用して、選択するイメージ ファイルを見つけます**追加**します。</span><span class="sxs-lookup"><span data-stu-id="20b68-194">In the **Add Existing Item** dialog, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="20b68-195">アプリケーションのビルドと実行</span><span class="sxs-lookup"><span data-stu-id="20b68-195">Build and run the application</span></span>

1. <span data-ttu-id="20b68-196">ビルド、アプリケーションを実行し、キーを押します**F5**選択または**デバッグの開始**から、**デバッグ**メニュー。</span><span class="sxs-lookup"><span data-stu-id="20b68-196">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="20b68-197">次の図は、使用してアプリケーションを<xref:System.Windows.Navigation.NavigationWindow>ボタン。</span><span class="sxs-lookup"><span data-stu-id="20b68-197">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![ExpenseIt のサンプルのスクリーンショット](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png)

2. <span data-ttu-id="20b68-199">Visual Studio に戻るにアプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="20b68-199">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="20b68-200">レイアウトを作成します。</span><span class="sxs-lookup"><span data-stu-id="20b68-200">Create the layout</span></span>

<span data-ttu-id="20b68-201">レイアウトは、順序付けられた UI 要素を配置する方法を提供し、UI のサイズを変更したときに、それらの要素の位置とサイズも管理します。</span><span class="sxs-lookup"><span data-stu-id="20b68-201">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="20b68-202">通常、レイアウトを作成するには、次のいずれかのレイアウト コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="20b68-202">You typically create a layout with one of the following layout controls:</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.VirtualizingStackPanel>
- <xref:System.Windows.Controls.WrapPanel>

<span data-ttu-id="20b68-203">これらの各レイアウト コントロールは、その子要素に対する特別な種類のレイアウトをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="20b68-203">Each of these layout controls supports a special type of layout for its child elements.</span></span> <span data-ttu-id="20b68-204">`ExpenseIt` ページのサイズを変更できる、および各ページが他の要素の横の水平および垂直に配置された要素があります。</span><span class="sxs-lookup"><span data-stu-id="20b68-204">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="20b68-205">その結果、<xref:System.Windows.Controls.Grid>は、アプリケーションの最適なレイアウト要素です。</span><span class="sxs-lookup"><span data-stu-id="20b68-205">Consequently, the <xref:System.Windows.Controls.Grid> is the ideal layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="20b68-206">詳細については<xref:System.Windows.Controls.Panel>、要素を参照してください[パネルの概要](../../../../docs/framework/wpf/controls/panels-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="20b68-206">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span> <span data-ttu-id="20b68-207">レイアウトの詳細については、次を参照してください。[レイアウト](../../../../docs/framework/wpf/advanced/layout.md)します。</span><span class="sxs-lookup"><span data-stu-id="20b68-207">For more information about layout, see [Layout](../../../../docs/framework/wpf/advanced/layout.md).</span></span>

<span data-ttu-id="20b68-208">セクションで、単一列テーブル 3 つの行と 10 ピクセルの余白を追加して作成する列と行の定義を<xref:System.Windows.Controls.Grid>で *`ExpenseItHome.xaml`* します。</span><span class="sxs-lookup"><span data-stu-id="20b68-208">In the section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="20b68-209">開いている *`ExpenseItHome.xaml`* します。</span><span class="sxs-lookup"><span data-stu-id="20b68-209">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="20b68-210">設定、<xref:System.Windows.FrameworkElement.Margin%2A>プロパティを<xref:System.Windows.Controls.Grid>「10,0,10,10」は、左、上、右、下の余白に対応する要素。</span><span class="sxs-lookup"><span data-stu-id="20b68-210">Set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="20b68-211">設定することも、**余白**値、**プロパティ**ウィンドウで、**レイアウト**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="20b68-211">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![[プロパティ] ウィンドウの余白の値](media/properties-margin.png)

3. <span data-ttu-id="20b68-213">間で次の XAML を追加、<xref:System.Windows.Controls.Grid>行と列の定義を作成するタグ。</span><span class="sxs-lookup"><span data-stu-id="20b68-213">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="20b68-214"><xref:System.Windows.Controls.RowDefinition.Height%2A> 2 つの行に設定されて<xref:System.Windows.GridLength.Auto%2A>行の内容に基づいて、行のサイズを調整することを意味します。</span><span class="sxs-lookup"><span data-stu-id="20b68-214">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="20b68-215">既定の<xref:System.Windows.Controls.RowDefinition.Height%2A>は<xref:System.Windows.GridUnitType.Star>サイズ変更は、行の高さが使用可能な領域の加重比率であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="20b68-215">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="20b68-216">たとえば 2 つの行がある場合、<xref:System.Windows.Controls.RowDefinition.Height%2A>の"\*"、それぞれがある使用可能な領域の半分の高さ。</span><span class="sxs-lookup"><span data-stu-id="20b68-216">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="20b68-217"><xref:System.Windows.Controls.Grid> XAML を次のようになります。</span><span class="sxs-lookup"><span data-stu-id="20b68-217">Your <xref:System.Windows.Controls.Grid> should now look like the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="20b68-218">コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="20b68-218">Add controls</span></span>

<span data-ttu-id="20b68-219">このセクションでは、ホーム ページの経費レポートを表示するユーザーが選択できるユーザーの一覧を表示する UI を更新します。</span><span class="sxs-lookup"><span data-stu-id="20b68-219">In this section, you'll update the home page UI to show a list of people that a user can select from to show the expense report for.</span></span> <span data-ttu-id="20b68-220">コントロールとは、ユーザーがアプリケーションと対話できるようにする UI オブジェクトのことです。</span><span class="sxs-lookup"><span data-stu-id="20b68-220">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="20b68-221">詳しくは、「 [コントロール](../../../../docs/framework/wpf/controls/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20b68-221">For more information, see [Controls](../../../../docs/framework/wpf/controls/index.md).</span></span>

<span data-ttu-id="20b68-222">この UI を作成するには、次の要素を追加します *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="20b68-222">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="20b68-223"><xref:System.Windows.Controls.ListBox> (用のユーザーの一覧)。</span><span class="sxs-lookup"><span data-stu-id="20b68-223"><xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="20b68-224"><xref:System.Windows.Controls.Label> (一覧のヘッダーとして)。</span><span class="sxs-lookup"><span data-stu-id="20b68-224"><xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="20b68-225"><xref:System.Windows.Controls.Button> (クリックする一覧で選択されているユーザーの経費報告書を表示する)。</span><span class="sxs-lookup"><span data-stu-id="20b68-225"><xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="20b68-226">行の各コントロールを配置、<xref:System.Windows.Controls.Grid>を設定して、<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>添付プロパティ。</span><span class="sxs-lookup"><span data-stu-id="20b68-226">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="20b68-227">添付プロパティの詳細については、次を参照してください。[添付プロパティの概要](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="20b68-227">For more information about attached properties, see [Attached Properties Overview](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="20b68-228">開いている *`ExpenseItHome.xaml`* します。</span><span class="sxs-lookup"><span data-stu-id="20b68-228">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="20b68-229">追加する、次 XAML どこかの間、<xref:System.Windows.Controls.Grid>タグ。</span><span class="sxs-lookup"><span data-stu-id="20b68-229">Add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="20b68-230">ドラッグしてから、コントロールを作成することも、**ツールボックス**デザイン ウィンドウとでプロパティを設定し、ウィンドウ、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="20b68-230">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

3. <span data-ttu-id="20b68-231">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="20b68-231">Build and run the application.</span></span>

<span data-ttu-id="20b68-232">次の図は、作成したコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="20b68-232">The following illustration shows the controls you just created:</span></span>

![ExpenseIt のサンプルのスクリーンショット](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="20b68-234">イメージとタイトルを追加します。</span><span class="sxs-lookup"><span data-stu-id="20b68-234">Add an image and a title</span></span>

<span data-ttu-id="20b68-235">このセクションでは、イメージとページ タイトル、ホーム ページの UI を更新します。</span><span class="sxs-lookup"><span data-stu-id="20b68-235">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="20b68-236">開いている *`ExpenseItHome.xaml`* します。</span><span class="sxs-lookup"><span data-stu-id="20b68-236">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="20b68-237">もう 1 つの列を追加、<xref:System.Windows.Controls.Grid.ColumnDefinitions%2A>固定<xref:System.Windows.Controls.ColumnDefinition.Width%2A>230 ピクセルの。</span><span class="sxs-lookup"><span data-stu-id="20b68-237">Add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]

3. <span data-ttu-id="20b68-238">別の行を追加、 <xref:System.Windows.Controls.Grid.RowDefinitions%2A>、4 つの行の合計。</span><span class="sxs-lookup"><span data-stu-id="20b68-238">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]

4. <span data-ttu-id="20b68-239">2 番目の列に設定して、コントロールを移動、<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>を 1 に 3 つのコントロール (枠線、ListBox、およびボタン) の各プロパティ。</span><span class="sxs-lookup"><span data-stu-id="20b68-239">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

5. <span data-ttu-id="20b68-240">下の行をインクリメントして各コントロールを移動、<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>を 1 つの値。</span><span class="sxs-lookup"><span data-stu-id="20b68-240">Move each control down a row, by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1.</span></span>

   <span data-ttu-id="20b68-241">3 つのコントロールの XAML は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="20b68-241">The XAML for the three controls now looks like this:</span></span>

    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

6. <span data-ttu-id="20b68-242">設定、<xref:System.Windows.Controls.Panel.Background%2A>の<xref:System.Windows.Controls.Grid>する、 *watermark.png* 、次 XAML どこかの間に追加することで、イメージ ファイル、`<Grid>`と`</Grid>`タグ。</span><span class="sxs-lookup"><span data-stu-id="20b68-242">Set the <xref:System.Windows.Controls.Panel.Background%2A> of the <xref:System.Windows.Controls.Grid> to be the *watermark.png* image file, by adding the following XAML somewhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

7. <span data-ttu-id="20b68-243">前に、<xref:System.Windows.Controls.Border>要素を追加、 <xref:System.Windows.Controls.Label> "View Expense Report"の内容。</span><span class="sxs-lookup"><span data-stu-id="20b68-243">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="20b68-244">これは、ページのタイトルです。</span><span class="sxs-lookup"><span data-stu-id="20b68-244">This is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

8. <span data-ttu-id="20b68-245">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="20b68-245">Build and run the application.</span></span>

<span data-ttu-id="20b68-246">次の図は、追加したものの結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="20b68-246">The following illustration shows the results of what you just added:</span></span>

![ExpenseIt のサンプルのスクリーンショット](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="20b68-248">イベントを処理するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="20b68-248">Add code to handle events</span></span>

1. <span data-ttu-id="20b68-249">開いている *`ExpenseItHome.xaml`* します。</span><span class="sxs-lookup"><span data-stu-id="20b68-249">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="20b68-250">追加、<xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベント ハンドラーを<xref:System.Windows.Controls.Button>要素。</span><span class="sxs-lookup"><span data-stu-id="20b68-250">Add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="20b68-251">詳細については、「[方法 :単純なイベント ハンドラーを作成](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))です。</span><span class="sxs-lookup"><span data-stu-id="20b68-251">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

3. <span data-ttu-id="20b68-252">開いている *`ExpenseItHome.xaml.vb`* または *`ExpenseItHome.xaml.cs`* します。</span><span class="sxs-lookup"><span data-stu-id="20b68-252">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="20b68-253">次のコードを追加、`ExpenseItHome`ボタンを追加するクラス イベント ハンドラーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="20b68-253">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="20b68-254">イベント ハンドラーが表示されます、 **ExpenseReportPage**ページ。</span><span class="sxs-lookup"><span data-stu-id="20b68-254">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="20b68-255">ExpenseReportPage の UI を作成します。</span><span class="sxs-lookup"><span data-stu-id="20b68-255">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="20b68-256">*ExpenseReportPage.xaml*で選択されている個人の経費報告書が表示されます、 **`ExpenseItHome`** ページ。</span><span class="sxs-lookup"><span data-stu-id="20b68-256">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="20b68-257">このセクションでは、UI を作成します**ExpenseReportPage**します。</span><span class="sxs-lookup"><span data-stu-id="20b68-257">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="20b68-258">バック グラウンドを追加し、さまざまな UI 要素の色の塗りつぶしもします。</span><span class="sxs-lookup"><span data-stu-id="20b68-258">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="20b68-259">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="20b68-259">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="20b68-260">間で次の XAML を追加、<xref:System.Windows.Controls.Grid>タグ。</span><span class="sxs-lookup"><span data-stu-id="20b68-260">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="20b68-261">この UI はのような *`ExpenseItHome.xaml`* でレポート データが表示される点を除いて、<xref:System.Windows.Controls.DataGrid>します。</span><span class="sxs-lookup"><span data-stu-id="20b68-261">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="20b68-262">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="20b68-262">Build and run the application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="20b68-263">エラーが発生する場合、<xref:System.Windows.Controls.DataGrid>が見つかりませんでしたかが存在しない、プロジェクトが .NET Framework 4 以降を対象とするかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="20b68-263">If you get an error that the <xref:System.Windows.Controls.DataGrid> was not found or does not exist, make sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="20b68-264">詳細については、「[方法 :.NET Framework のターゲット バージョンを指定する](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20b68-264">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

4. <span data-ttu-id="20b68-265">選択、**ビュー**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="20b68-265">Select the **View** button.</span></span>

    <span data-ttu-id="20b68-266">経費明細書ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20b68-266">The expense report page appears.</span></span> <span data-ttu-id="20b68-267">ナビゲーション ボタンが有効になっていることにも注目してください。</span><span class="sxs-lookup"><span data-stu-id="20b68-267">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="20b68-268">次の図は、UI 要素に追加*ExpenseReportPage.xaml*します。</span><span class="sxs-lookup"><span data-stu-id="20b68-268">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![ExpenseIt のサンプルのスクリーンショット](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png)

## <a name="style-controls"></a><span data-ttu-id="20b68-270">スタイルのコントロール</span><span class="sxs-lookup"><span data-stu-id="20b68-270">Style controls</span></span>

<span data-ttu-id="20b68-271">さまざまな要素の外観は、多くの場合、UI で同じ種類のすべての要素に対して同じです。</span><span class="sxs-lookup"><span data-stu-id="20b68-271">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="20b68-272">UI を使用して[スタイル](../../../../docs/framework/wpf/controls/styling-and-templating.md)複数要素の間で外観を再利用可能なことにします。</span><span class="sxs-lookup"><span data-stu-id="20b68-272">UI uses [styles](../../../../docs/framework/wpf/controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="20b68-273">スタイルの再利用性は、XAML の作成と管理を簡略化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="20b68-273">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="20b68-274">このセクションでは、これまでの手順で定義した要素ごとの属性を、スタイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="20b68-274">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="20b68-275">開いている*Application.xaml*または*App.xaml*します。</span><span class="sxs-lookup"><span data-stu-id="20b68-275">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="20b68-276">間で次の XAML を追加、<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>タグ。</span><span class="sxs-lookup"><span data-stu-id="20b68-276">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="20b68-277">この XAML は、次のスタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="20b68-277">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="20b68-278">`headerTextStyle`:ページ タイトルの書式設定<xref:System.Windows.Controls.Label>します。</span><span class="sxs-lookup"><span data-stu-id="20b68-278">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="20b68-279">`labelStyle`:書式設定、<xref:System.Windows.Controls.Label>コントロール。</span><span class="sxs-lookup"><span data-stu-id="20b68-279">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="20b68-280">`columnHeaderStyle`:書式設定、<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>します。</span><span class="sxs-lookup"><span data-stu-id="20b68-280">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="20b68-281">`listHeaderStyle`:一覧のヘッダーを書式設定する<xref:System.Windows.Controls.Border>コントロール。</span><span class="sxs-lookup"><span data-stu-id="20b68-281">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="20b68-282">`listHeaderTextStyle`:一覧のヘッダーを書式設定する<xref:System.Windows.Controls.Label>します。</span><span class="sxs-lookup"><span data-stu-id="20b68-282">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="20b68-283">`buttonStyle`:書式設定、<xref:System.Windows.Controls.Button>で`ExpenseItHome.xaml`します。</span><span class="sxs-lookup"><span data-stu-id="20b68-283">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="20b68-284">スタイルは、リソースとの子に注目してください、<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>プロパティ要素。</span><span class="sxs-lookup"><span data-stu-id="20b68-284">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="20b68-285">ここでは、スタイルはアプリケーション内のすべての要素に適用されます。</span><span class="sxs-lookup"><span data-stu-id="20b68-285">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="20b68-286">.NET Framework アプリケーションでリソースの使用の例は、次を参照してください。[アプリケーション リソースを使用](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md)します。</span><span class="sxs-lookup"><span data-stu-id="20b68-286">For an example of using resources in a .NET Framework application, see [Use Application Resources](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="20b68-287">開いている *`ExpenseItHome.xaml`* します。</span><span class="sxs-lookup"><span data-stu-id="20b68-287">Open *`ExpenseItHome.xaml`*.</span></span>

4. <span data-ttu-id="20b68-288">間にあるすべての置換、<xref:System.Windows.Controls.Grid>で次の XAML 要素。</span><span class="sxs-lookup"><span data-stu-id="20b68-288">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="20b68-289">各コントロールの外観を定義する <xref:System.Windows.VerticalAlignment> や <xref:System.Windows.Media.FontFamily> などのプロパティは、これらのスタイルを適用することで、削除されて置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="20b68-289">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="20b68-290">たとえば、 `headerTextStyle` "View Expense Report"に適用される<xref:System.Windows.Controls.Label>します。</span><span class="sxs-lookup"><span data-stu-id="20b68-290">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

5. <span data-ttu-id="20b68-291">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="20b68-291">Open *ExpenseReportPage.xaml*.</span></span>

6. <span data-ttu-id="20b68-292">間にあるすべての置換、<xref:System.Windows.Controls.Grid>で次の XAML 要素。</span><span class="sxs-lookup"><span data-stu-id="20b68-292">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="20b68-293">これにより、スタイルが <xref:System.Windows.Controls.Label> と <xref:System.Windows.Controls.Border> の要素に追加されます。</span><span class="sxs-lookup"><span data-stu-id="20b68-293">This adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="20b68-294">データをコントロールにバインドします。</span><span class="sxs-lookup"><span data-stu-id="20b68-294">Bind data to a control</span></span>

<span data-ttu-id="20b68-295">このセクションでは、さまざまなコントロールにバインドされている XML データを作成します。</span><span class="sxs-lookup"><span data-stu-id="20b68-295">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="20b68-296">開いている *`ExpenseItHome.xaml`* します。</span><span class="sxs-lookup"><span data-stu-id="20b68-296">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="20b68-297">開始後に<xref:System.Windows.Controls.Grid>要素を作成する次の XAML を追加、<xref:System.Windows.Data.XmlDataProvider>各人のデータを格納しています。</span><span class="sxs-lookup"><span data-stu-id="20b68-297">After the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    <span data-ttu-id="20b68-298">データとして作成、<xref:System.Windows.Controls.Grid>リソース。</span><span class="sxs-lookup"><span data-stu-id="20b68-298">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="20b68-299">通常、これはファイルとして読み込まれますが、説明を簡単にするため、データをインラインで追加します。</span><span class="sxs-lookup"><span data-stu-id="20b68-299">Normally this would be loaded as a file, but for simplicity the data is added inline.</span></span>

3. <span data-ttu-id="20b68-300">内で、`<Grid.Resources>`要素では、次の追加<xref:System.Windows.DataTemplate>、データを表示する方法を定義する、 <xref:System.Windows.Controls.ListBox>:</span><span class="sxs-lookup"><span data-stu-id="20b68-300">Within the `<Grid.Resources>` element, add the following <xref:System.Windows.DataTemplate>, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>:</span></span>

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    <span data-ttu-id="20b68-301">データ テンプレートの詳細については、次を参照してください。[データ テンプレートの概要](../../../../docs/framework/wpf/data/data-templating-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="20b68-301">For more information about data templates, see [Data templating overview](../../../../docs/framework/wpf/data/data-templating-overview.md).</span></span>

4. <span data-ttu-id="20b68-302">既存<xref:System.Windows.Controls.ListBox>次の XAML で。</span><span class="sxs-lookup"><span data-stu-id="20b68-302">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="20b68-303">この XAML のバインド、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>のプロパティ、<xref:System.Windows.Controls.ListBox>をデータ ソースとしてデータ テンプレートを適用し、 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>。</span><span class="sxs-lookup"><span data-stu-id="20b68-303">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="20b68-304">コントロールにデータを接続します。</span><span class="sxs-lookup"><span data-stu-id="20b68-304">Connect data to controls</span></span>

<span data-ttu-id="20b68-305">次で選択されている名前を取得するコードを追加します、 **`ExpenseItHome`** ページし、のコンス トラクターに渡す**ExpenseReportPage**します。</span><span class="sxs-lookup"><span data-stu-id="20b68-305">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="20b68-306">**ExpenseReportPage**コントロールで定義されているは、渡された項目を使用してデータ コンテキストの設定で*ExpenseReportPage.xaml*にバインドします。</span><span class="sxs-lookup"><span data-stu-id="20b68-306">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="20b68-307">*ExpenseReportPage.xaml.vb* または *ExpenseReportPage.xaml.cs*を開きます。</span><span class="sxs-lookup"><span data-stu-id="20b68-307">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="20b68-308">オブジェクトを取得するコンストラクターを追加して、選択した個人の経費報告書データを渡せるようにします。</span><span class="sxs-lookup"><span data-stu-id="20b68-308">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="20b68-309">開いている *`ExpenseItHome.xaml.vb`* または *`ExpenseItHome.xaml.cs`* します。</span><span class="sxs-lookup"><span data-stu-id="20b68-309">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="20b68-310">変更、<xref:System.Windows.Controls.Primitives.ButtonBase.Click>選択した個人の経費報告書データを渡す新しいコンス トラクターを呼び出すイベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="20b68-310">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="20b68-311">データ テンプレートの形式のデータ</span><span class="sxs-lookup"><span data-stu-id="20b68-311">Style data with data templates</span></span>

<span data-ttu-id="20b68-312">このセクションでは、データ テンプレートを使用してデータ バインド リスト内の各項目の UI を更新します。</span><span class="sxs-lookup"><span data-stu-id="20b68-312">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="20b68-313">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="20b68-313">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="20b68-314">"Name"および"Department"の内容をバインド<xref:System.Windows.Controls.Label>要素を適切なデータ ソースのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="20b68-314">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="20b68-315">データ バインディングの詳細については、次を参照してください。[データ バインディングの概要](../../../../docs/framework/wpf/data/data-binding-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="20b68-315">For more information about data binding, see [Data binding overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="20b68-316">開始後に<xref:System.Windows.Controls.Grid>要素、経費報告書データを表示する方法を定義する次のデータ テンプレートを追加します。</span><span class="sxs-lookup"><span data-stu-id="20b68-316">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="20b68-317">置換、<xref:System.Windows.Controls.DataGridTextColumn>を持つ要素<xref:System.Windows.Controls.DataGridTemplateColumn>、<xref:System.Windows.Controls.DataGrid>要素とそれらにテンプレートを適用します。</span><span class="sxs-lookup"><span data-stu-id="20b68-317">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="20b68-318">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="20b68-318">Build and run the application.</span></span>

6. <span data-ttu-id="20b68-319">ユーザーを選択し、選択、**ビュー**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="20b68-319">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="20b68-320">次の図の両方のページ、`ExpenseIt`アプリケーションをコントロール、レイアウト、スタイル、データ バインディング、およびデータ テンプレートを適用します。</span><span class="sxs-lookup"><span data-stu-id="20b68-320">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![ExpenseIt のサンプルのスクリーンショット](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png)

> [!NOTE]
> <span data-ttu-id="20b68-322">このサンプルでは、WPF の特定の機能について説明し、セキュリティ、ローカリゼーション、およびアクセシビリティなどのすべてのベスト プラクティスに従っていません。</span><span class="sxs-lookup"><span data-stu-id="20b68-322">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="20b68-323">WPF と .NET Framework アプリケーション開発のベスト プラクティスの包括的な対応は、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20b68-323">For comprehensive coverage of WPF and the .NET Framework application development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="20b68-324">ユーザー補助</span><span class="sxs-lookup"><span data-stu-id="20b68-324">Accessibility</span></span>](../../../../docs/framework/ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="20b68-325">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="20b68-325">Security</span></span>](../../../../docs/framework/wpf/security-wpf.md)
>
> - [<span data-ttu-id="20b68-326">WPF のグローバリゼーションとローカライズ</span><span class="sxs-lookup"><span data-stu-id="20b68-326">WPF globalization and localization</span></span>](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="20b68-327">WPF のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="20b68-327">WPF performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="20b68-328">次の手順</span><span class="sxs-lookup"><span data-stu-id="20b68-328">Next steps</span></span>

<span data-ttu-id="20b68-329">このチュートリアルでは、さまざまな Windows Presentation Foundation (WPF) を使用して UI を作成するための手法について説明しました。</span><span class="sxs-lookup"><span data-stu-id="20b68-329">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="20b68-330">これで、データ バインド、.NET Framework アプリケーションのビルド ブロックの基本的な理解が必要です。</span><span class="sxs-lookup"><span data-stu-id="20b68-330">You should now have a basic understanding of the building blocks of a data-bound, .NET Framework application.</span></span> <span data-ttu-id="20b68-331">WPF のアーキテクチャおよびプログラミング モデルの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20b68-331">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="20b68-332">WPF アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="20b68-332">WPF architecture</span></span>](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
- [<span data-ttu-id="20b68-333">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="20b68-333">XAML overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="20b68-334">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="20b68-334">Dependency properties overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [<span data-ttu-id="20b68-335">レイアウト</span><span class="sxs-lookup"><span data-stu-id="20b68-335">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)

<span data-ttu-id="20b68-336">アプリケーションの作成の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20b68-336">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="20b68-337">アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="20b68-337">Application development</span></span>](../../../../docs/framework/wpf/app-development/index.md)
- [<span data-ttu-id="20b68-338">コントロール</span><span class="sxs-lookup"><span data-stu-id="20b68-338">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)
- [<span data-ttu-id="20b68-339">データバインディングの概要</span><span class="sxs-lookup"><span data-stu-id="20b68-339">Data binding overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="20b68-340">グラフィックスとマルチ メディア</span><span class="sxs-lookup"><span data-stu-id="20b68-340">Graphics and multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
- [<span data-ttu-id="20b68-341">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="20b68-341">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="20b68-342">関連項目</span><span class="sxs-lookup"><span data-stu-id="20b68-342">See also</span></span>

- [<span data-ttu-id="20b68-343">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="20b68-343">Panels overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
- [<span data-ttu-id="20b68-344">データ テンプレートの概要</span><span class="sxs-lookup"><span data-stu-id="20b68-344">Data templating overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)
- [<span data-ttu-id="20b68-345">WPF アプリケーションを構築します。</span><span class="sxs-lookup"><span data-stu-id="20b68-345">Build a WPF application</span></span>](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="20b68-346">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="20b68-346">Styles and templates</span></span>](../../../../docs/framework/wpf/controls/styles-and-templates.md)
