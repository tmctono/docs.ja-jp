---
title: Visual Studio での WPF アプリケーションを作成します。
ms.date: 03/20/2019
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
ms.openlocfilehash: 9d0abd18b2242ab21e8a915caac1ff9e3216acd0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617274"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="1f66f-102">チュートリアル: 初めての WPF デスクトップ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1f66f-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="1f66f-103">この記事では、ほとんどの WPF アプリケーションに共通する要素を含む Windows Presentation Foundation (WPF) デスクトップ アプリケーションを開発する方法を示します。Extensible Application Markup Language (XAML) マークアップ、分離コード、アプリケーション定義、コントロール、レイアウト、データ バインド、およびスタイル。</span><span class="sxs-lookup"><span data-stu-id="1f66f-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="1f66f-104">アプリケーションを開発するには、Visual Studio を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="1f66f-105">このチュートリアルには、次の手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1f66f-105">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="1f66f-106">XAML を使用して、アプリケーションのユーザー インターフェイス (UI) の外観をデザインします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-106">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="1f66f-107">アプリケーションの動作を構築するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-107">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="1f66f-108">アプリケーションを管理するアプリケーション定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-108">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="1f66f-109">コントロールを追加し、アプリケーションの UI を作成するレイアウトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-109">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="1f66f-110">アプリケーションの UI 全体で一貫した外観のスタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-110">Create styles for a consistent appearance throughout the application's UI.</span></span>

- <span data-ttu-id="1f66f-111">データをデータから UI を設定して、データと UI の同期を維持するには、UI をバインドします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-111">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="1f66f-112">チュートリアルの目的は、スタンドアロンのユーザーを選択したユーザーの経費報告書を表示できる Windows アプリケーションを構築したします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-112">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="1f66f-113">アプリケーションは、ブラウザー スタイルのウィンドウでホストされているいくつかの WPF ページで構成されます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-113">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="1f66f-114">このチュートリアルの構築に使用するサンプル コードについては、Visual basic の両方とC#で[チュートリアル WPF アプリのサンプル コード](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-114">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Walkthrough WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="1f66f-115">間のサンプル コードのコードの言語を切り替えることができますC#および Visual Basic を使用して、 **\< />** この記事の右上隅のドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="1f66f-115">You can toggle the code language of the sample code between C# and Visual Basic by using the **\</>** drop-down on the upper right side of this article.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1f66f-116">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1f66f-116">Prerequisites</span></span>

- <span data-ttu-id="1f66f-117">Visual Studio 2017 またはそれ以降</span><span class="sxs-lookup"><span data-stu-id="1f66f-117">Visual Studio 2017 or later</span></span>

   <span data-ttu-id="1f66f-118">最新バージョンの Visual Studio のインストールの詳細については、次を参照してください。 [Visual Studio のインストール](/visualstudio/install/install-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-118">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span> <span data-ttu-id="1f66f-119">この記事では、Visual Studio 2019 を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-119">This article uses Visual Studio 2019.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="1f66f-120">アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-120">Create the application project</span></span>

<span data-ttu-id="1f66f-121">最初の手順では、アプリケーションの定義を 2 つのページとイメージを含むアプリケーション インフラストラクチャを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="1f66f-122">Visual Basic または Visual C# のという名前で新しい WPF アプリケーション プロジェクトを作成する **`ExpenseIt`** :</span><span class="sxs-lookup"><span data-stu-id="1f66f-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="1f66f-123">Visual Studio を開き、選択**ファイル** > **新規** > **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-123">Open Visual Studio and select **File** > **New** > **Project**.</span></span>

      <span data-ttu-id="1f66f-124">**新しいプロジェクトを作成**ダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-124">The **Create a new project** dialog opens.</span></span>

      ![新しいプロジェクト ダイアログを作成します。](./media/gettingstartedfigure0a.png)

   2. <span data-ttu-id="1f66f-126">**言語**ドロップダウンで、いずれかを選択**C#** または**Visual Basic**します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-126">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>

   3. <span data-ttu-id="1f66f-127">選択、 **WPF アプリ (.NET Framework)** テンプレートと、選択**次**します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-127">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
    
   4. <span data-ttu-id="1f66f-128">選択**新しいプロジェクトを作成**です。</span><span class="sxs-lookup"><span data-stu-id="1f66f-128">Select **Create a new project**.</span></span>

      <span data-ttu-id="1f66f-129">**新しいプロジェクトを構成**ダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-129">The **Configure a new project** dialog opens.</span></span>

      ![新しいプロジェクト ダイアログを構成します。](./media/gettingstartedfigure0c.png)

   5. <span data-ttu-id="1f66f-131">プロジェクト名を入力**`ExpenseIt`** 選び**作成**です。</span><span class="sxs-lookup"><span data-stu-id="1f66f-131">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      <span data-ttu-id="1f66f-132">Visual Studio は、プロジェクトを作成し、という名前の既定アプリケーション ウィンドウのデザイナーが開きます**MainWindow.xaml**します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-132">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="1f66f-133">開いている*Application.xaml* (Visual Basic) または*App.xaml* (c#)。</span><span class="sxs-lookup"><span data-stu-id="1f66f-133">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="1f66f-134">この XAML ファイルでは、WPF アプリケーションとすべてのアプリケーション リソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-134">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="1f66f-135">ここでは、UI を指定するこのファイルを使用するも*MainWindow.xaml*アプリケーションの起動時に自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-135">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="1f66f-136">Visual Basic では、次のように XAML になります。</span><span class="sxs-lookup"><span data-stu-id="1f66f-136">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="1f66f-137">では、次のようなC#:</span><span class="sxs-lookup"><span data-stu-id="1f66f-137">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="1f66f-138">*MainWindow.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-138">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="1f66f-139">この XAML ファイルは、アプリケーションのメイン ウィンドウであるため、ページで作成されたコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-139">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="1f66f-140"><xref:System.Windows.Window>クラスは、タイトル、サイズ、アイコンなど、ウィンドウのプロパティを定義し、閉じるか、非表示などのイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-140">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="1f66f-141"><xref:System.Windows.Navigation.NavigationWindow>.xaml の<xref:System.Windows.Window>要素を、次に示すように変更します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-141">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="1f66f-142">このアプリは、ユーザーの入力に応じてさまざまなコンテンツに移動します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-142">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="1f66f-143">そのため、メイン ウィンドウを<xref:System.Windows.Window>から<xref:System.Windows.Navigation.NavigationWindow>に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f66f-143">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="1f66f-144"><xref:System.Windows.Navigation.NavigationWindow>  は、<xref:System.Windows.Window>のすべてのプロパティを継承しています。</span><span class="sxs-lookup"><span data-stu-id="1f66f-144"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="1f66f-145"><xref:System.Windows.Navigation.NavigationWindow> XAML ファイル内の要素のインスタンスを作成する、<xref:System.Windows.Navigation.NavigationWindow>クラス。</span><span class="sxs-lookup"><span data-stu-id="1f66f-145">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="1f66f-146">詳細については、次を参照してください。[ナビゲーションの概要](../app-development/navigation-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-146">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="1f66f-147">削除、<xref:System.Windows.Controls.Grid>間からの要素、<xref:System.Windows.Navigation.NavigationWindow>タグ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-147">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="1f66f-148">XAML コードでは、次のプロパティを変更、<xref:System.Windows.Navigation.NavigationWindow>要素。</span><span class="sxs-lookup"><span data-stu-id="1f66f-148">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="1f66f-149">設定、<xref:System.Windows.Window.Title%2A>プロパティを"`ExpenseIt`"。</span><span class="sxs-lookup"><span data-stu-id="1f66f-149">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="1f66f-150">設定、<xref:System.Windows.FrameworkElement.Height%2A>プロパティを 350 ピクセル、高さ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-150">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="1f66f-151">設定、<xref:System.Windows.FrameworkElement.Width%2A>プロパティを 500 ピクセルにします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-151">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="1f66f-152">Visual basic の場合、次のように XAML になります。</span><span class="sxs-lookup"><span data-stu-id="1f66f-152">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="1f66f-153">次のようなC#:</span><span class="sxs-lookup"><span data-stu-id="1f66f-153">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="1f66f-154">開いている*MainWindow.xaml.vb*または*MainWindow.xaml.cs*します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-154">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="1f66f-155">このファイルは、分離コード ファイルで宣言されたイベントを処理するコードを含む*MainWindow.xaml*します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-155">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="1f66f-156">このファイルには、XAML で定義されたウィンドウの部分クラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1f66f-156">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="1f66f-157">使用している場合C#、変更、`MainWindow`クラスから派生する<xref:System.Windows.Navigation.NavigationWindow>します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-157">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="1f66f-158">(Visual basic の場合は、これは XAML でウィンドウを変更するときにします。)C#コードが次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1f66f-158">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="1f66f-159">ファイルをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-159">Add files to the application</span></span>

<span data-ttu-id="1f66f-160">このセクションでは、アプリケーションに 2 つのページと 1 つのイメージを追加します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-160">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="1f66f-161">プロジェクトに新しいページを追加し、名前*`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="1f66f-161">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="1f66f-162">**ソリューション エクスプ ローラー**を右クリックし、 **`ExpenseIt`** プロジェクト ノード**追加** > **ページ**します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-162">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="1f66f-163">**新しい項目の追加**ダイアログ ボックスで、**ページ (WPF)** テンプレートは既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="1f66f-163">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="1f66f-164">名前を入力します **`ExpenseItHome`** 、し、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-164">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="1f66f-165">このページは、アプリケーションの起動時に表示される最初のページです。</span><span class="sxs-lookup"><span data-stu-id="1f66f-165">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="1f66f-166">経費報告書を表示するからを選択するユーザーの一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-166">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="1f66f-167">開いている *`ExpenseItHome.xaml`* します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-167">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="1f66f-168">設定、<xref:System.Windows.Controls.Page.Title%2A>に"`ExpenseIt - Home`"。</span><span class="sxs-lookup"><span data-stu-id="1f66f-168">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="1f66f-169">設定、`DesignHeight`と`DesignWidth`要素の値 300 ピクセルにします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-169">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="1f66f-170">XAML は、Visual basic の場合に、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-170">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="1f66f-171">次のようなC#:</span><span class="sxs-lookup"><span data-stu-id="1f66f-171">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="1f66f-172">*MainWindow.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-172">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="1f66f-173">追加、<xref:System.Windows.Navigation.NavigationWindow.Source%2A>プロパティを<xref:System.Windows.Navigation.NavigationWindow>要素に設定および"`ExpenseItHome.xaml`"。</span><span class="sxs-lookup"><span data-stu-id="1f66f-173">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="1f66f-174">これにより設定 *`ExpenseItHome.xaml`* アプリケーションの起動時を開く最初のページになります。</span><span class="sxs-lookup"><span data-stu-id="1f66f-174">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="1f66f-175">Visual Basic での XAML の例:</span><span class="sxs-lookup"><span data-stu-id="1f66f-175">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="1f66f-176">および C# の場合。</span><span class="sxs-lookup"><span data-stu-id="1f66f-176">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="1f66f-177">設定することも、**ソース**プロパティ、 **[その他]** のカテゴリ、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-177">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![プロパティ ウィンドウで、ソース プロパティ](./media/properties-source.png)

1. <span data-ttu-id="1f66f-179">もう 1 つの新しい WPF ページをプロジェクトに追加し、名前*ExpenseReportPage.xaml*:。</span><span class="sxs-lookup"><span data-stu-id="1f66f-179">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="1f66f-180">**ソリューション エクスプ ローラー**を右クリックし、 **`ExpenseIt`** プロジェクト ノード**追加** > **ページ**します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-180">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="1f66f-181">**新しい項目の追加**ダイアログ ボックスで、**ページ (WPF)** テンプレート。</span><span class="sxs-lookup"><span data-stu-id="1f66f-181">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="1f66f-182">名前を入力します**ExpenseReportPage**、し、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-182">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="1f66f-183">このページで選択されているユーザーの経費報告書が表示されます、 **`ExpenseItHome`** ページ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-183">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="1f66f-184">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-184">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="1f66f-185">設定、<xref:System.Windows.Controls.Page.Title%2A>に"`ExpenseIt - View Expense`"。</span><span class="sxs-lookup"><span data-stu-id="1f66f-185">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="1f66f-186">設定、`DesignHeight`と`DesignWidth`要素の値 300 ピクセルにします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-186">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="1f66f-187">*ExpenseReportPage.xaml* Visual Basic では、次のようになりますようになりました。</span><span class="sxs-lookup"><span data-stu-id="1f66f-187">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="1f66f-188">では、次のようなC#:</span><span class="sxs-lookup"><span data-stu-id="1f66f-188">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="1f66f-189">開いている*ExpenseItHome.xaml.vb*と*ExpenseReportPage.xaml.vb*、または*ExpenseItHome.xaml.cs*と*ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="1f66f-189">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="1f66f-190">Visual Studio が自動的に作成、新しいファイルを作成するときにその*コード ビハインド*ファイル。</span><span class="sxs-lookup"><span data-stu-id="1f66f-190">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="1f66f-191">これらの分離コード ファイルでは、ユーザー入力に対応するためのロジックを処理します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-191">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="1f66f-192">コードは、次のようになります**`ExpenseItHome`**:</span><span class="sxs-lookup"><span data-stu-id="1f66f-192">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="1f66f-193">次のような**ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="1f66f-193">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="1f66f-194">という名前のイメージを追加*watermark.png*をプロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-194">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="1f66f-195">独自のイメージを作成、サンプル コードからファイルをコピーまたは入手[ここ](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-195">You can create your own image, copy the file from the sample code, or get it [here](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>

    1. <span data-ttu-id="1f66f-196">プロジェクト ノードを右クリックして**追加** > **既存項目の**、またはキーを押します**Shift**+**Alt**+ **A**します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-196">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="1f66f-197">**既存項目の追加**ダイアログ ボックスで、ファイル フィルターを設定するか、**すべてのファイル**または**イメージ ファイル**を使用し、選択するイメージ ファイルを参照する**追加**.</span><span class="sxs-lookup"><span data-stu-id="1f66f-197">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="1f66f-198">アプリケーションのビルドと実行</span><span class="sxs-lookup"><span data-stu-id="1f66f-198">Build and run the application</span></span>

1. <span data-ttu-id="1f66f-199">ビルド、アプリケーションを実行し、キーを押します**F5**選択または**デバッグの開始**から、**デバッグ**メニュー。</span><span class="sxs-lookup"><span data-stu-id="1f66f-199">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="1f66f-200">次の図は、使用してアプリケーションを<xref:System.Windows.Navigation.NavigationWindow>ボタン。</span><span class="sxs-lookup"><span data-stu-id="1f66f-200">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![ExpenseIt のサンプルのスクリーンショット](./media/gettingstartedfigure1.png)

2. <span data-ttu-id="1f66f-202">Visual Studio に戻るにアプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-202">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="1f66f-203">レイアウトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-203">Create the layout</span></span>

<span data-ttu-id="1f66f-204">レイアウトは、順序付けられた UI 要素を配置する方法を提供し、UI のサイズを変更したときに、それらの要素の位置とサイズも管理します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-204">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="1f66f-205">通常、レイアウトを作成するには、次のいずれかのレイアウト コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-205">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="1f66f-206"><xref:System.Windows.Controls.Canvas> -キャンバス領域に対する相対座標を使用して、子要素を明示的に配置できる領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-206"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="1f66f-207"><xref:System.Windows.Controls.DockPanel> -整列する子要素水平方向または垂直方向に、相互に比較した領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-207"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="1f66f-208"><xref:System.Windows.Controls.Grid> -列と行で構成される柔軟性のあるグリッド領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-208"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="1f66f-209"><xref:System.Windows.Controls.StackPanel> 水平方向または垂直方向に配置する 1 つの行に子要素を整列します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-209"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="1f66f-210"><xref:System.Windows.Controls.VirtualizingStackPanel> -配置し、水平方向または垂直方向に指向である 1 つの行でコンテンツを仮想化します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-210"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="1f66f-211"><xref:System.Windows.Controls.WrapPanel> 順に子要素の位置は左から右、格納ボックスの端にある次の行に改行してコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-211"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="1f66f-212">後続の並べ替えは発生順に上下からまたは右から左の方向プロパティの値に応じて、します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-212">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="1f66f-213">各レイアウト コントロールは、その子要素のレイアウトの特定の種類をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-213">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="1f66f-214">`ExpenseIt` ページのサイズを変更できる、および各ページが他の要素の横の水平および垂直に配置された要素があります。</span><span class="sxs-lookup"><span data-stu-id="1f66f-214">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="1f66f-215">この例で、<xref:System.Windows.Controls.Grid>アプリケーションのレイアウト要素として使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-215">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="1f66f-216">詳細については<xref:System.Windows.Controls.Panel>、要素を参照してください[パネルの概要](../controls/panels-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-216">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="1f66f-217">レイアウトの詳細については、次を参照してください。[レイアウト](../advanced/layout.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-217">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="1f66f-218">このセクションで作成する単一列テーブル 10 ピクセルの余白を 3 行の列と行の定義を追加することによって、<xref:System.Windows.Controls.Grid>で *`ExpenseItHome.xaml`* します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-218">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="1f66f-219">*`ExpenseItHome.xaml`*、設定、<xref:System.Windows.FrameworkElement.Margin%2A>プロパティを<xref:System.Windows.Controls.Grid>「10,0,10,10」は、左、上、右、下の余白に対応する要素。</span><span class="sxs-lookup"><span data-stu-id="1f66f-219">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="1f66f-220">設定することも、**余白**値、**プロパティ**ウィンドウで、**レイアウト**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-220">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![[プロパティ] ウィンドウの余白の値](./media/properties-margin.png)

2. <span data-ttu-id="1f66f-222">間で次の XAML を追加、<xref:System.Windows.Controls.Grid>行と列の定義を作成するタグ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-222">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="1f66f-223"><xref:System.Windows.Controls.RowDefinition.Height%2A> 2 つの行に設定されて<xref:System.Windows.GridLength.Auto%2A>行の内容に基づいて、行のサイズを調整することを意味します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-223">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="1f66f-224">既定の<xref:System.Windows.Controls.RowDefinition.Height%2A>は<xref:System.Windows.GridUnitType.Star>サイズ変更は、行の高さが使用可能な領域の加重比率であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-224">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="1f66f-225">たとえば 2 つの行がある場合、<xref:System.Windows.Controls.RowDefinition.Height%2A>の"\*"、それぞれがある使用可能な領域の半分の高さ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-225">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="1f66f-226"><xref:System.Windows.Controls.Grid>次の XAML が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-226">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="1f66f-227">コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-227">Add controls</span></span>

<span data-ttu-id="1f66f-228">このセクションでは、ホーム ページに、経費報告書を表示する 1 人のユーザーを選択する、人のユーザーの一覧を表示する UI を更新します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-228">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="1f66f-229">コントロールとは、ユーザーがアプリケーションと対話できるようにする UI オブジェクトのことです。</span><span class="sxs-lookup"><span data-stu-id="1f66f-229">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="1f66f-230">詳しくは、「 [コントロール](../controls/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1f66f-230">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="1f66f-231">この UI を作成するには、次の要素を追加します *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="1f66f-231">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="1f66f-232">A <xref:System.Windows.Controls.ListBox> (のメンバーの一覧)。</span><span class="sxs-lookup"><span data-stu-id="1f66f-232">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="1f66f-233">A <xref:System.Windows.Controls.Label> (の一覧のヘッダー)。</span><span class="sxs-lookup"><span data-stu-id="1f66f-233">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="1f66f-234">A <xref:System.Windows.Controls.Button> (をクリックすると、一覧で選択されているユーザーの経費報告書を表示する)。</span><span class="sxs-lookup"><span data-stu-id="1f66f-234">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="1f66f-235">行の各コントロールを配置、<xref:System.Windows.Controls.Grid>を設定して、<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>添付プロパティ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-235">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="1f66f-236">添付プロパティの詳細については、次を参照してください。[添付プロパティの概要](../advanced/attached-properties-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-236">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="1f66f-237"> *`ExpenseItHome.xaml`* を次 XAML どこかの間の追加、<xref:System.Windows.Controls.Grid>タグ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-237">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="1f66f-238">ドラッグしてから、コントロールを作成することも、**ツールボックス**デザイン ウィンドウとでプロパティを設定し、ウィンドウ、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-238">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="1f66f-239">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-239">Build and run the application.</span></span>

    <span data-ttu-id="1f66f-240">次の図は、作成したコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="1f66f-240">The following illustration shows the controls you created:</span></span>

    ![ExpenseIt のサンプルのスクリーンショット](./media/gettingstartedfigure2.png)

3. <span data-ttu-id="1f66f-242">Visual Studio に戻るにアプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-242">Close the application to return to Visual Studio.</span></span>

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="1f66f-243">イメージとタイトルを追加します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-243">Add an image and a title</span></span>

<span data-ttu-id="1f66f-244">このセクションでは、イメージとページ タイトル、ホーム ページの UI を更新します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-244">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="1f66f-245">*`ExpenseItHome.xaml`*、もう 1 つの列を追加、<xref:System.Windows.Controls.Grid.ColumnDefinitions%2A>固定<xref:System.Windows.Controls.ColumnDefinition.Width%2A>230 ピクセルの。</span><span class="sxs-lookup"><span data-stu-id="1f66f-245">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="1f66f-246">別の行を追加、 <xref:System.Windows.Controls.Grid.RowDefinitions%2A>、4 つの行の合計。</span><span class="sxs-lookup"><span data-stu-id="1f66f-246">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="1f66f-247">2 番目の列に設定して、コントロールを移動、<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>を 1 に 3 つのコントロール (枠線、ListBox、およびボタン) の各プロパティ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-247">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="1f66f-248">増分することで、下の行の各コントロールを移動、<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>を 1 つの 3 つのコントロール (枠線、ListBox、およびボタン) の各と Border 要素の値。</span><span class="sxs-lookup"><span data-stu-id="1f66f-248">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="1f66f-249">3 つのコントロールの XAML は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1f66f-249">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="1f66f-250">設定、<xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType>プロパティを*watermark.png* 、次 XAML 任意の場所の間に追加することで、イメージ ファイル、`<Grid>`と`</Grid>`タグ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-250">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="1f66f-251">前に、<xref:System.Windows.Controls.Border>要素を追加、 <xref:System.Windows.Controls.Label> "View Expense Report"の内容。</span><span class="sxs-lookup"><span data-stu-id="1f66f-251">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="1f66f-252">このラベルは、ページのタイトルです。</span><span class="sxs-lookup"><span data-stu-id="1f66f-252">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="1f66f-253">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-253">Build and run the application.</span></span>

<span data-ttu-id="1f66f-254">次の図は、追加したものの結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="1f66f-254">The following illustration shows the results of what you just added:</span></span>

![ExpenseIt のサンプルのスクリーンショット](./media/gettingstartedfigure3.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="1f66f-256">イベントを処理するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-256">Add code to handle events</span></span>

1. <span data-ttu-id="1f66f-257">*`ExpenseItHome.xaml`*、追加、<xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベント ハンドラーを<xref:System.Windows.Controls.Button>要素。</span><span class="sxs-lookup"><span data-stu-id="1f66f-257">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="1f66f-258">詳細については、「[方法 :単純なイベント ハンドラーを作成](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))です。</span><span class="sxs-lookup"><span data-stu-id="1f66f-258">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="1f66f-259">開いている *`ExpenseItHome.xaml.vb`* または *`ExpenseItHome.xaml.cs`* します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-259">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="1f66f-260">次のコードを追加、`ExpenseItHome`ボタンを追加するクラス イベント ハンドラーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-260">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="1f66f-261">イベント ハンドラーが表示されます、 **ExpenseReportPage**ページ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-261">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="1f66f-262">ExpenseReportPage の UI を作成します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-262">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="1f66f-263">*ExpenseReportPage.xaml*で選択されている個人の経費報告書が表示されます、 **`ExpenseItHome`** ページ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-263">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="1f66f-264">このセクションでは、UI を作成します**ExpenseReportPage**します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-264">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="1f66f-265">バック グラウンドを追加し、さまざまな UI 要素の色の塗りつぶしもします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-265">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="1f66f-266">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-266">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="1f66f-267">間で次の XAML を追加、<xref:System.Windows.Controls.Grid>タグ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-267">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="1f66f-268">この UI はのような *`ExpenseItHome.xaml`* でレポート データが表示される点を除いて、<xref:System.Windows.Controls.DataGrid>します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-268">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="1f66f-269">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-269">Build and run the application.</span></span>

4. <span data-ttu-id="1f66f-270">選択、**ビュー**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-270">Select the **View** button.</span></span>

    <span data-ttu-id="1f66f-271">経費明細書ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-271">The expense report page appears.</span></span> <span data-ttu-id="1f66f-272">ナビゲーション ボタンが有効になっていることにも注目してください。</span><span class="sxs-lookup"><span data-stu-id="1f66f-272">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="1f66f-273">次の図は、UI 要素に追加*ExpenseReportPage.xaml*します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-273">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![ExpenseIt のサンプルのスクリーンショット](./media/gettingstartedfigure4.png)

## <a name="style-controls"></a><span data-ttu-id="1f66f-275">スタイルのコントロール</span><span class="sxs-lookup"><span data-stu-id="1f66f-275">Style controls</span></span>

<span data-ttu-id="1f66f-276">さまざまな要素の外観は、多くの場合、UI で同じ種類のすべての要素に対して同じです。</span><span class="sxs-lookup"><span data-stu-id="1f66f-276">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="1f66f-277">UI を使用して[スタイル](../controls/styling-and-templating.md)複数要素の間で外観を再利用可能なことにします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-277">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="1f66f-278">スタイルの再利用性は、XAML の作成と管理を簡略化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-278">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="1f66f-279">このセクションでは、これまでの手順で定義した要素ごとの属性を、スタイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-279">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="1f66f-280">開いている*Application.xaml*または*App.xaml*します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-280">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="1f66f-281">間で次の XAML を追加、<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>タグ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-281">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="1f66f-282">この XAML は、次のスタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-282">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="1f66f-283">`headerTextStyle`:ページ タイトルの書式設定<xref:System.Windows.Controls.Label>します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-283">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="1f66f-284">`labelStyle`:書式設定、<xref:System.Windows.Controls.Label>コントロール。</span><span class="sxs-lookup"><span data-stu-id="1f66f-284">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="1f66f-285">`columnHeaderStyle`:書式設定、<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-285">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="1f66f-286">`listHeaderStyle`:一覧のヘッダーを書式設定する<xref:System.Windows.Controls.Border>コントロール。</span><span class="sxs-lookup"><span data-stu-id="1f66f-286">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="1f66f-287">`listHeaderTextStyle`:一覧のヘッダーを書式設定する<xref:System.Windows.Controls.Label>します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-287">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="1f66f-288">`buttonStyle`:書式設定、<xref:System.Windows.Controls.Button>で`ExpenseItHome.xaml`します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-288">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="1f66f-289">スタイルは、リソースとの子に注目してください、<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>プロパティ要素。</span><span class="sxs-lookup"><span data-stu-id="1f66f-289">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="1f66f-290">ここでは、スタイルはアプリケーション内のすべての要素に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-290">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="1f66f-291">.NET アプリでリソースの使用の例は、次を参照してください。[アプリケーション リソースを使用](../advanced/how-to-use-application-resources.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-291">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="1f66f-292">*`ExpenseItHome.xaml`*、間にあるすべての置換、<xref:System.Windows.Controls.Grid>で次の XAML 要素。</span><span class="sxs-lookup"><span data-stu-id="1f66f-292">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="1f66f-293">各コントロールの外観を定義する <xref:System.Windows.VerticalAlignment> や <xref:System.Windows.Media.FontFamily> などのプロパティは、これらのスタイルを適用することで、削除されて置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-293">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="1f66f-294">たとえば、 `headerTextStyle` "View Expense Report"に適用される<xref:System.Windows.Controls.Label>します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-294">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="1f66f-295">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-295">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="1f66f-296">間にあるすべての置換、<xref:System.Windows.Controls.Grid>で次の XAML 要素。</span><span class="sxs-lookup"><span data-stu-id="1f66f-296">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="1f66f-297">この XAML は、スタイルを追加、<xref:System.Windows.Controls.Label>と<xref:System.Windows.Controls.Border>要素。</span><span class="sxs-lookup"><span data-stu-id="1f66f-297">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="1f66f-298">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-298">Build and run the application.</span></span> <span data-ttu-id="1f66f-299">ウィンドウの外観は、前と同じです。</span><span class="sxs-lookup"><span data-stu-id="1f66f-299">The window appearance is the same as previously.</span></span>

    ![ExpenseIt のサンプルのスクリーンショット](./media/gettingstartedfigure4.png)

7. <span data-ttu-id="1f66f-301">Visual Studio に戻るにアプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-301">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="1f66f-302">データをコントロールにバインドします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-302">Bind data to a control</span></span>

<span data-ttu-id="1f66f-303">このセクションでは、さまざまなコントロールにバインドされている XML データを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-303">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="1f66f-304">*`ExpenseItHome.xaml`*、開始後<xref:System.Windows.Controls.Grid>要素を作成する次の XAML を追加、<xref:System.Windows.Data.XmlDataProvider>各人のデータを格納しています。</span><span class="sxs-lookup"><span data-stu-id="1f66f-304">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="1f66f-305">データとして作成、<xref:System.Windows.Controls.Grid>リソース。</span><span class="sxs-lookup"><span data-stu-id="1f66f-305">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="1f66f-306">ファイルであれば、このデータは通常どおり読み込まれますが、わかりやすくするため、データをインラインで追加します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-306">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="1f66f-307">内で、`<Grid.Resources>`要素では、次の追加`<xref:System.Windows.DataTemplate>`にデータを表示する方法を定義する要素を<xref:System.Windows.Controls.ListBox>後に、`<XmlDataProvider>`要素。</span><span class="sxs-lookup"><span data-stu-id="1f66f-307">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="1f66f-308">データ テンプレートの詳細については、次を参照してください。[データ テンプレートの概要](../data/data-templating-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-308">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="1f66f-309">既存<xref:System.Windows.Controls.ListBox>次の XAML で。</span><span class="sxs-lookup"><span data-stu-id="1f66f-309">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="1f66f-310">この XAML のバインド、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>のプロパティ、<xref:System.Windows.Controls.ListBox>をデータ ソースとしてデータ テンプレートを適用し、 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>。</span><span class="sxs-lookup"><span data-stu-id="1f66f-310">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="1f66f-311">コントロールにデータを接続します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-311">Connect data to controls</span></span>

<span data-ttu-id="1f66f-312">次で選択されている名前を取得するコードを追加します、 **`ExpenseItHome`** ページし、のコンストラクターに渡す**ExpenseReportPage**します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-312">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="1f66f-313">**ExpenseReportPage**コントロールで定義されているは、渡された項目を使用してデータ コンテキストの設定で*ExpenseReportPage.xaml*にバインドします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-313">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="1f66f-314">*ExpenseReportPage.xaml.vb* または *ExpenseReportPage.xaml.cs*を開きます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-314">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="1f66f-315">オブジェクトを取得するコンストラクターを追加して、選択した個人の経費報告書データを渡せるようにします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-315">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="1f66f-316">開いている *`ExpenseItHome.xaml.vb`* または *`ExpenseItHome.xaml.cs`* します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-316">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="1f66f-317">変更、<xref:System.Windows.Controls.Primitives.ButtonBase.Click>選択した個人の経費報告書データを渡す新しいコンス トラクターを呼び出すイベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="1f66f-317">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="1f66f-318">データ テンプレートの形式のデータ</span><span class="sxs-lookup"><span data-stu-id="1f66f-318">Style data with data templates</span></span>

<span data-ttu-id="1f66f-319">このセクションでは、データ テンプレートを使用してデータ バインド リスト内の各項目の UI を更新します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-319">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="1f66f-320">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="1f66f-320">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="1f66f-321">"Name"および"Department"の内容をバインド<xref:System.Windows.Controls.Label>要素を適切なデータ ソースのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="1f66f-321">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="1f66f-322">データ バインディングの詳細については、次を参照してください。[データ バインディングの概要](../data/data-binding-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-322">For more information about data binding, see [Data binding overview](../data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="1f66f-323">開始後に<xref:System.Windows.Controls.Grid>要素、経費報告書データを表示する方法を定義する次のデータ テンプレートを追加します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-323">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="1f66f-324">置換、<xref:System.Windows.Controls.DataGridTextColumn>を持つ要素<xref:System.Windows.Controls.DataGridTemplateColumn>、<xref:System.Windows.Controls.DataGrid>要素とそれらにテンプレートを適用します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-324">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="1f66f-325">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-325">Build and run the application.</span></span>

6. <span data-ttu-id="1f66f-326">ユーザーを選択し、選択、**ビュー**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f66f-326">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="1f66f-327">次の図の両方のページ、`ExpenseIt`アプリケーションをコントロール、レイアウト、スタイル、データ バインディング、およびデータ テンプレートを適用します。</span><span class="sxs-lookup"><span data-stu-id="1f66f-327">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![ExpenseIt のサンプルのスクリーンショット](./media/gettingstartedfigure5.png)

> [!NOTE]
> <span data-ttu-id="1f66f-329">このサンプルでは、WPF の特定の機能について説明し、セキュリティ、ローカリゼーション、およびアクセシビリティなどのすべてのベスト プラクティスに従っていません。</span><span class="sxs-lookup"><span data-stu-id="1f66f-329">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="1f66f-330">WPF と .NET アプリ開発のベスト プラクティスの包括的な対応は、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f66f-330">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="1f66f-331">ユーザー補助</span><span class="sxs-lookup"><span data-stu-id="1f66f-331">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="1f66f-332">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="1f66f-332">Security</span></span>](../security-wpf.md)
>
> - [<span data-ttu-id="1f66f-333">WPF のグローバリゼーションおよびローカリゼーションの概要</span><span class="sxs-lookup"><span data-stu-id="1f66f-333">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="1f66f-334">WPF のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="1f66f-334">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="1f66f-335">次の手順</span><span class="sxs-lookup"><span data-stu-id="1f66f-335">Next steps</span></span>

<span data-ttu-id="1f66f-336">このチュートリアルでは、さまざまな Windows Presentation Foundation (WPF) を使用して UI を作成するための手法について説明しました。</span><span class="sxs-lookup"><span data-stu-id="1f66f-336">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="1f66f-337">これで、データ バインドの .NET アプリのビルド ブロックの基本的な理解が必要です。</span><span class="sxs-lookup"><span data-stu-id="1f66f-337">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="1f66f-338">WPF のアーキテクチャおよびプログラミング モデルの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f66f-338">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="1f66f-339">WPF アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1f66f-339">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="1f66f-340">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="1f66f-340">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="1f66f-341">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="1f66f-341">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="1f66f-342">レイアウト</span><span class="sxs-lookup"><span data-stu-id="1f66f-342">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="1f66f-343">アプリケーションの作成の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f66f-343">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="1f66f-344">アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="1f66f-344">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="1f66f-345">コントロール</span><span class="sxs-lookup"><span data-stu-id="1f66f-345">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="1f66f-346">データバインディングの概要</span><span class="sxs-lookup"><span data-stu-id="1f66f-346">Data binding overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="1f66f-347">グラフィックスとマルチ メディア</span><span class="sxs-lookup"><span data-stu-id="1f66f-347">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="1f66f-348">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="1f66f-348">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="1f66f-349">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f66f-349">See also</span></span>

- [<span data-ttu-id="1f66f-350">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="1f66f-350">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="1f66f-351">データ テンプレートの概要</span><span class="sxs-lookup"><span data-stu-id="1f66f-351">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="1f66f-352">WPF アプリケーションのビルド</span><span class="sxs-lookup"><span data-stu-id="1f66f-352">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="1f66f-353">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="1f66f-353">Styles and templates</span></span>](../controls/styles-and-templates.md)
