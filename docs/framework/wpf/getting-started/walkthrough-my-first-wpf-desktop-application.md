---
title: Visual Studio 2019 で初めての WPF アプリを作成する - .NET フレームワーク
titleSuffix: ''
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: mvc,vs-dotnet
ms.openlocfilehash: 65b6fe31e86380162e90820c2cf118a9d1b96b4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186582"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="448f0-102">チュートリアル: Visual Studio 2019 で最初の WPF アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="448f0-102">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="448f0-103">この記事では、WPF アプリケーションの大部分に共通する要素を含む Windows プレゼンテーション ファンデーション (WPF) デスクトップ アプリケーションを開発する方法を示します。コントロール、レイアウト、データ バインディング、およびスタイル。</span><span class="sxs-lookup"><span data-stu-id="448f0-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="448f0-104">アプリケーションを開発するには、Visual Studio を使用します。</span><span class="sxs-lookup"><span data-stu-id="448f0-104">To develop the application, you'll use Visual Studio.</span></span>

<span data-ttu-id="448f0-105">このチュートリアルでは、以下の内容を学習します。</span><span class="sxs-lookup"><span data-stu-id="448f0-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="448f0-106">WPF プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="448f0-106">Create a WPF project.</span></span>
> - <span data-ttu-id="448f0-107">XAML を使用して、アプリケーションのユーザー インターフェイス (UI) の外観をデザインします。</span><span class="sxs-lookup"><span data-stu-id="448f0-107">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="448f0-108">アプリケーションの動作をビルドするコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="448f0-108">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="448f0-109">アプリケーションを管理するアプリケーション定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="448f0-109">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="448f0-110">コントロールを追加し、レイアウトを作成してアプリケーション UI を構成します。</span><span class="sxs-lookup"><span data-stu-id="448f0-110">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="448f0-111">アプリケーションの UI 全体で一貫した外観を実現するためのスタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="448f0-111">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="448f0-112">データから UI を設定し、データと UI の同期を維持するために、UI をデータにバインドします。</span><span class="sxs-lookup"><span data-stu-id="448f0-112">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="448f0-113">このチュートリアルの最後に、ユーザーが選択したユーザーの経費報告書を表示できるスタンドアロンの Windows アプリケーションを構築します。</span><span class="sxs-lookup"><span data-stu-id="448f0-113">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="448f0-114">アプリケーションは、ブラウザー スタイルのウィンドウでホストされている複数の WPF ページで構成されます。</span><span class="sxs-lookup"><span data-stu-id="448f0-114">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="448f0-115">このチュートリアルで使用するサンプル コードは、[チュートリアル WPF アプリケーションサンプル コード](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)で Visual Basic と C# の両方で使用できます。</span><span class="sxs-lookup"><span data-stu-id="448f0-115">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="448f0-116">このページの上部にある言語セレクタを使用して、サンプル コードのコード言語を C# と Visual Basic の間で切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="448f0-116">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="448f0-117">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="448f0-117">Prerequisites</span></span>

- <span data-ttu-id="448f0-118">**NET デスクトップ開発**ワークロードがインストールされた[Visual Studio 2019。](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)</span><span class="sxs-lookup"><span data-stu-id="448f0-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="448f0-119">最新バージョンの Visual Studio のインストールの詳細については、「 [Visual Studio](/visualstudio/install/install-visual-studio)のインストール 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-119">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="448f0-120">アプリケーション プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="448f0-120">Create the application project</span></span>

<span data-ttu-id="448f0-121">最初の手順では、アプリケーション定義、2 ページ、およびイメージを含むアプリケーション インフラストラクチャを作成します。</span><span class="sxs-lookup"><span data-stu-id="448f0-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="448f0-122">という名前の Visual Basic または Visual C#**`ExpenseIt`** で新しい WPF アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="448f0-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="448f0-123">Visual Studio を開き、[**はじめに**] メニューの [**新しいプロジェクトの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="448f0-123">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="448f0-124">[**新しいプロジェクトの作成**] ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-124">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="448f0-125">[**言語**] ドロップダウンで **、[C#]** または **[Visual Basic]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="448f0-125">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>

   3. <span data-ttu-id="448f0-126">WPF**アプリケーション (.NET Framework)** テンプレートを選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="448f0-126">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span>

      ![[新しいプロジェクトの作成] ダイアログ](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      <span data-ttu-id="448f0-128">[**新しいプロジェクトの構成]** ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-128">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="448f0-129">プロジェクト名**`ExpenseIt`** を入力し、[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="448f0-129">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![新しいプロジェクトダイアログを設定する](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="448f0-131">プロジェクトが作成され、既定のアプリケーション ウィンドウのデザイナー**が開きます**。</span><span class="sxs-lookup"><span data-stu-id="448f0-131">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="448f0-132">*アプリケーション.xaml* (Visual Basic) または*App.xaml* (C#) を開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-132">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="448f0-133">この XAML ファイルは、WPF アプリケーションとすべてのアプリケーション リソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="448f0-133">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="448f0-134">このファイルを使用して、アプリケーションの起動時に自動的に表示される UI (この場合*は MainWindow.xaml)* を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="448f0-134">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="448f0-135">XAML は、Visual Basic で次のようになります。</span><span class="sxs-lookup"><span data-stu-id="448f0-135">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="448f0-136">C# の次のようにします。</span><span class="sxs-lookup"><span data-stu-id="448f0-136">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="448f0-137">*を*開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-137">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="448f0-138">この XAML ファイルは、アプリケーションのメイン ウィンドウであり、ページで作成されたコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="448f0-138">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="448f0-139">クラス<xref:System.Windows.Window>は、ウィンドウのタイトル、サイズ、アイコンなどのプロパティを定義し、閉じる、または非表示などのイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="448f0-139">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="448f0-140">要素を<xref:System.Windows.Window>に変更<xref:System.Windows.Navigation.NavigationWindow>します。</span><span class="sxs-lookup"><span data-stu-id="448f0-140">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="448f0-141">このアプリは、ユーザーの入力に応じて異なるコンテンツに移動します。</span><span class="sxs-lookup"><span data-stu-id="448f0-141">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="448f0-142">これが主なもの<xref:System.Windows.Window>を に変更する必要がある理由<xref:System.Windows.Navigation.NavigationWindow>です。</span><span class="sxs-lookup"><span data-stu-id="448f0-142">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="448f0-143"><xref:System.Windows.Navigation.NavigationWindow>のプロパティをすべて継承<xref:System.Windows.Window>します。</span><span class="sxs-lookup"><span data-stu-id="448f0-143"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="448f0-144">XAML<xref:System.Windows.Navigation.NavigationWindow>ファイル内の要素は、クラスのインスタンス<xref:System.Windows.Navigation.NavigationWindow>を作成します。</span><span class="sxs-lookup"><span data-stu-id="448f0-144">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="448f0-145">詳細については、「ナビゲーションの[概要](../app-development/navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-145">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="448f0-146">タグの<xref:System.Windows.Controls.Grid>間から要素を<xref:System.Windows.Navigation.NavigationWindow>削除します。</span><span class="sxs-lookup"><span data-stu-id="448f0-146">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="448f0-147">要素の XAML コードで次のプロパティ<xref:System.Windows.Navigation.NavigationWindow>を変更します。</span><span class="sxs-lookup"><span data-stu-id="448f0-147">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="448f0-148">プロパティを<xref:System.Windows.Window.Title%2A>"`ExpenseIt`" に設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-148">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="448f0-149">このプロパティ<xref:System.Windows.FrameworkElement.Height%2A>を 350 ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-149">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="448f0-150">プロパティを<xref:System.Windows.FrameworkElement.Width%2A>500 ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-150">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="448f0-151">VISUAL Basic の XAML は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="448f0-151">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="448f0-152">C# の場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="448f0-152">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="448f0-153">*を*開くか *、MainWindow.xaml.cs.*</span><span class="sxs-lookup"><span data-stu-id="448f0-153">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="448f0-154">このファイルは *、MainWindow.xaml*で宣言されたイベントを処理するコードを含む分離コード ファイルです。</span><span class="sxs-lookup"><span data-stu-id="448f0-154">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="448f0-155">このファイルには、XAML で定義されたウィンドウの部分クラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="448f0-155">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="448f0-156">C# を使用している場合は、クラス`MainWindow`をから派生するように<xref:System.Windows.Navigation.NavigationWindow>変更します。</span><span class="sxs-lookup"><span data-stu-id="448f0-156">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="448f0-157">(Visual Basic では、これは XAML でウィンドウを変更すると自動的に発生します)。C# コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="448f0-157">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="448f0-158">アプリケーションにファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="448f0-158">Add files to the application</span></span>

<span data-ttu-id="448f0-159">このセクションでは、アプリケーションに 2 つのページと 1 つのイメージを追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="448f0-160">プロジェクトに新しいページを追加し、名前を*`ExpenseItHome.xaml`* 付けます。</span><span class="sxs-lookup"><span data-stu-id="448f0-160">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="448f0-161">**ソリューション エクスプローラ**で、プロジェクト ノードを**`ExpenseIt`** 右クリックし、[**ページ**の**追加]** > を選択します。</span><span class="sxs-lookup"><span data-stu-id="448f0-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="448f0-162">[**新しい項目の追加]** ダイアログ ボックスで、**ページ (WPF)** テンプレートが既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="448f0-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="448f0-163">名前**`ExpenseItHome`** を入力し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="448f0-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="448f0-164">このページは、アプリケーションの起動時に表示される最初のページです。</span><span class="sxs-lookup"><span data-stu-id="448f0-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="448f0-165">経費精算書を表示するために選択するユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="448f0-165">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="448f0-166">を*`ExpenseItHome.xaml`* 開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-166">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="448f0-167">を<xref:System.Windows.Controls.Page.Title%2A>""`ExpenseIt - Home`に設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="448f0-168">350`DesignHeight`ピクセル、500`DesignWidth`ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-168">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="448f0-169">これで、VISUAL Basic の XAML が次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="448f0-169">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="448f0-170">C# の場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="448f0-170">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="448f0-171">*を*開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-171">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="448f0-172">要素に<xref:System.Windows.Navigation.NavigationWindow.Source%2A>プロパティを<xref:System.Windows.Navigation.NavigationWindow>追加し、それを "`ExpenseItHome.xaml`" に設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-172">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="448f0-173">これは、*`ExpenseItHome.xaml`* アプリケーションの起動時に最初に開かれたページになります。</span><span class="sxs-lookup"><span data-stu-id="448f0-173">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span>

    <span data-ttu-id="448f0-174">Visual Basic の XAML の例:</span><span class="sxs-lookup"><span data-stu-id="448f0-174">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="448f0-175">そしてC#で:</span><span class="sxs-lookup"><span data-stu-id="448f0-175">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="448f0-176">[プロパティ] ウィンドウの **[その他**] カテゴリで **[ソース\*\*\*\*] プロパティ**を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="448f0-176">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![[プロパティ] ウィンドウの [ソース] プロパティ](./media/properties-source.png)

1. <span data-ttu-id="448f0-178">プロジェクトに別の新しい WPF ページを追加し、名前*を付けます。*</span><span class="sxs-lookup"><span data-stu-id="448f0-178">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="448f0-179">**ソリューション エクスプローラ**で、プロジェクト ノードを**`ExpenseIt`** 右クリックし、[**ページ**の**追加]** > を選択します。</span><span class="sxs-lookup"><span data-stu-id="448f0-179">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="448f0-180">[**新しい項目の追加]** ダイアログボックスで、[**ページ (WPF)]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="448f0-180">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="448f0-181">**[経費明細書ページ]** という名前を入力し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="448f0-181">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="448f0-182">このページには、**`ExpenseItHome`** ページで選択したユーザーの経費精算書が表示されます。</span><span class="sxs-lookup"><span data-stu-id="448f0-182">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="448f0-183">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-183">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="448f0-184">を<xref:System.Windows.Controls.Page.Title%2A>""`ExpenseIt - View Expense`に設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-184">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="448f0-185">350`DesignHeight`ピクセル、500`DesignWidth`ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-185">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="448f0-186">*現在*、ビジュアル ベーシックでは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="448f0-186">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="448f0-187">C# の次のようにします。</span><span class="sxs-lookup"><span data-stu-id="448f0-187">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="448f0-188">を開きます*ExpenseReportPage.xaml.cs* *ExpenseReportPage.xaml.vb* *ExpenseItHome.xaml.cs。* *ExpenseItHome.xaml.cs*</span><span class="sxs-lookup"><span data-stu-id="448f0-188">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="448f0-189">新しいページ ファイルを作成すると、Visual Studio によって *、その分離コード*ファイルが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="448f0-189">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="448f0-190">これらの分離コード ファイルでは、ユーザー入力に対応するためのロジックを処理します。</span><span class="sxs-lookup"><span data-stu-id="448f0-190">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="448f0-191">コードは、 の**`ExpenseItHome`** 次のようになります。</span><span class="sxs-lookup"><span data-stu-id="448f0-191">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="448f0-192">そして、**経費報告ページ**の次のように:</span><span class="sxs-lookup"><span data-stu-id="448f0-192">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="448f0-193">プロジェクトに*watermark.png*という名前のイメージを追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-193">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="448f0-194">独自のイメージを作成したり、サンプル コードからファイルをコピーしたり[、Microsoft/WPF-サンプル](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png)GitHub リポジトリから取得したりできます。</span><span class="sxs-lookup"><span data-stu-id="448f0-194">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="448f0-195">プロジェクト ノードを右クリックし、[**既存項目**の**追加** > ] を選択するか **、Shift**+Alt**A**キー**を**+押します。</span><span class="sxs-lookup"><span data-stu-id="448f0-195">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="448f0-196">[**既存項目の追加]** ダイアログで、ファイル フィルタを **[すべてのファイル]** または [**イメージ ファイル]** に設定し、使用するイメージ ファイルを参照して、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="448f0-196">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="448f0-197">アプリケーションの構築と実行</span><span class="sxs-lookup"><span data-stu-id="448f0-197">Build and run the application</span></span>

1. <span data-ttu-id="448f0-198">アプリケーションをビルドして実行するには **、F5**キーを押すか、[**デバッグ**] メニューから **[デバッグの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="448f0-198">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="448f0-199">次の図は、ボタンを持<xref:System.Windows.Navigation.NavigationWindow>つアプリケーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="448f0-199">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![ビルドして実行した後のアプリケーション。](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="448f0-201">アプリケーションを閉じて、Visual Studio に戻ります。</span><span class="sxs-lookup"><span data-stu-id="448f0-201">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="448f0-202">レイアウトを作成する</span><span class="sxs-lookup"><span data-stu-id="448f0-202">Create the layout</span></span>

<span data-ttu-id="448f0-203">レイアウトは、UI 要素を配置するための順序付けされた方法を提供し、UI のサイズと位置を管理します。</span><span class="sxs-lookup"><span data-stu-id="448f0-203">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="448f0-204">通常、レイアウトを作成するには、次のいずれかのレイアウト コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="448f0-204">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="448f0-205"><xref:System.Windows.Controls.Canvas>- キャンバス領域に対する相対座標を使用して子要素を明示的に配置できる領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="448f0-205"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="448f0-206"><xref:System.Windows.Controls.DockPanel>- 子要素を水平方向または垂直方向に配置できる領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="448f0-206"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="448f0-207"><xref:System.Windows.Controls.Grid>- 列と行で構成される柔軟なグリッド領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="448f0-207"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="448f0-208"><xref:System.Windows.Controls.StackPanel>- 子要素を、水平方向または垂直方向に配置できる単一の行に配置します。</span><span class="sxs-lookup"><span data-stu-id="448f0-208"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="448f0-209"><xref:System.Windows.Controls.VirtualizingStackPanel>- 水平方向または垂直方向に配置された単一の行にコンテンツを配置し、仮想化します。</span><span class="sxs-lookup"><span data-stu-id="448f0-209"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="448f0-210"><xref:System.Windows.Controls.WrapPanel>- 子要素を左から右に連続した位置に配置し、内容を含むボックスの端の次の行に分割します。</span><span class="sxs-lookup"><span data-stu-id="448f0-210"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="448f0-211">後続の順序は、Orientation プロパティの値に応じて、上から下へ、または右から左に順番に行われます。</span><span class="sxs-lookup"><span data-stu-id="448f0-211">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="448f0-212">これらのレイアウト コントロールは、子要素に対して特定の種類のレイアウトをサポートします。</span><span class="sxs-lookup"><span data-stu-id="448f0-212">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="448f0-213">`ExpenseIt`ページのサイズを変更することができ、各ページには、他の要素と並んで水平方向および垂直方向に配置された要素があります。</span><span class="sxs-lookup"><span data-stu-id="448f0-213">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="448f0-214">この例では、<xref:System.Windows.Controls.Grid>はアプリケーションのレイアウト要素として使用されます。</span><span class="sxs-lookup"><span data-stu-id="448f0-214">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="448f0-215">要素の詳細<xref:System.Windows.Controls.Panel>については、[パネルの概要 を](../controls/panels-overview.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-215">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="448f0-216">レイアウトの詳細については、「[レイアウト](../advanced/layout.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-216">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="448f0-217">このセクションでは、 に列と行の定義を追加して、3 行 10 ピクセルの余白を持つ単<xref:System.Windows.Controls.Grid>一*`ExpenseItHome.xaml`* 列テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="448f0-217">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="448f0-218">では*`ExpenseItHome.xaml`*、要素の<xref:System.Windows.FrameworkElement.Margin%2A>プロパティを<xref:System.Windows.Controls.Grid>"10,0,10,10"に設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-218">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="448f0-219">[**プロパティ]** ウィンドウの **[レイアウト**] カテゴリで、**余白**の値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="448f0-219">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![[プロパティ] ウィンドウの余白の値](./media/properties-margin.png)

2. <span data-ttu-id="448f0-221">タグの間に次の<xref:System.Windows.Controls.Grid>XAML を追加して、行定義と列定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="448f0-221">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="448f0-222">2<xref:System.Windows.Controls.RowDefinition.Height%2A>つの行の は<xref:System.Windows.GridLength.Auto%2A>に設定され、行の内容に基づいて行のサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="448f0-222">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="448f0-223">デフォルト<xref:System.Windows.Controls.RowDefinition.Height%2A>は<xref:System.Windows.GridUnitType.Star>サイズ変更で、行の高さは使用可能なスペースの加重比率です。</span><span class="sxs-lookup"><span data-stu-id="448f0-223">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="448f0-224">たとえば、2 つの行のそれぞれに<xref:System.Windows.Controls.RowDefinition.Height%2A>"\*" がある場合、それぞれ使用可能なスペースの半分の高さがあります。</span><span class="sxs-lookup"><span data-stu-id="448f0-224">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="448f0-225">次<xref:System.Windows.Controls.Grid>の XAML が含まれるはずです。</span><span class="sxs-lookup"><span data-stu-id="448f0-225">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="448f0-226">コントロールの追加</span><span class="sxs-lookup"><span data-stu-id="448f0-226">Add controls</span></span>

<span data-ttu-id="448f0-227">このセクションでは、ホーム ページの UI を更新して、経費精算書を表示するユーザーを 1 人選択したユーザーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="448f0-227">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="448f0-228">コントロールとは、ユーザーがアプリケーションと対話できるようにする UI オブジェクトのことです。</span><span class="sxs-lookup"><span data-stu-id="448f0-228">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="448f0-229">詳細については、「[コントロール](../controls/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-229">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="448f0-230">この UI を作成するには、次の要素を*`ExpenseItHome.xaml`* に追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-230">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="448f0-231">A <xref:System.Windows.Controls.ListBox> (人のリスト用)。</span><span class="sxs-lookup"><span data-stu-id="448f0-231">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="448f0-232">A <xref:System.Windows.Controls.Label> (リスト ヘッダーの場合)。</span><span class="sxs-lookup"><span data-stu-id="448f0-232">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="448f0-233">A <xref:System.Windows.Controls.Button> (クリックすると、一覧で選択したユーザーの経費精算書を表示します)。</span><span class="sxs-lookup"><span data-stu-id="448f0-233">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="448f0-234">各コントロールは、添付プロパティを設定することにより<xref:System.Windows.Controls.Grid>、 の<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>行に配置されます。</span><span class="sxs-lookup"><span data-stu-id="448f0-234">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="448f0-235">添付プロパティの詳細については、「[添付プロパティの概要](../advanced/attached-properties-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-235">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="448f0-236">で*`ExpenseItHome.xaml`*、タグの間に次の<xref:System.Windows.Controls.Grid>XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-236">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="448f0-237">また、コントロールを作成するには、[**ツールボックス**] ウィンドウからデザイン ウィンドウにコントロールをドラッグし、[**プロパティ]** ウィンドウでプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-237">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="448f0-238">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="448f0-238">Build and run the application.</span></span>

    <span data-ttu-id="448f0-239">次の図は、作成したコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="448f0-239">The following illustration shows the controls you created:</span></span>

![名前の一覧を表示するサンプルのスクリーンショット](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="448f0-241">画像とタイトルを追加する</span><span class="sxs-lookup"><span data-stu-id="448f0-241">Add an image and a title</span></span>

<span data-ttu-id="448f0-242">このセクションでは、ホーム ページの UI を画像とページ タイトルで更新します。</span><span class="sxs-lookup"><span data-stu-id="448f0-242">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="448f0-243">で*`ExpenseItHome.xaml`*、固定<xref:System.Windows.Controls.Grid.ColumnDefinitions%2A><xref:System.Windows.Controls.ColumnDefinition.Width%2A>の 230 ピクセルの別の列をに追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-243">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="448f0-244">に別の行を<xref:System.Windows.Controls.Grid.RowDefinitions%2A>追加し、合計 4 行を指定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-244">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="448f0-245">3 つのコントロール ([境界線]、[リスト<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>ボックス]、および [ボタン]) のそれぞれでプロパティを 1 に設定して、コントロールを 2 番目の列に移動します。</span><span class="sxs-lookup"><span data-stu-id="448f0-245">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="448f0-246">3 つのコントロール ([境界線]、[リスト<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>ボックス]、[ボタン]) と Border 要素の値を 1 ずつ増やして、各コントロールを行の下に移動します。</span><span class="sxs-lookup"><span data-stu-id="448f0-246">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="448f0-247">3 つのコントロールの XAML は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="448f0-247">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="448f0-248">タグと<xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType>タグの間に次の XAML を追加して、プロパティを*watermark.png*イメージ ファイルに`<Grid>``</Grid>`設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-248">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="448f0-249">要素の<xref:System.Windows.Controls.Border>前に、コンテンツ<xref:System.Windows.Controls.Label>「経費報告の表示」 を付けて を追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-249">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="448f0-250">このラベルはページのタイトルです。</span><span class="sxs-lookup"><span data-stu-id="448f0-250">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="448f0-251">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="448f0-251">Build and run the application.</span></span>

<span data-ttu-id="448f0-252">次の図は、追加した結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="448f0-252">The following illustration shows the results of what you just added:</span></span>

![費用新しい画像の背景とページタイトルを示すサンプルスクリーンショット](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="448f0-254">イベントを処理するコードを追加する</span><span class="sxs-lookup"><span data-stu-id="448f0-254">Add code to handle events</span></span>

1. <span data-ttu-id="448f0-255">で*`ExpenseItHome.xaml`*、要素に<xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベント ハンドラーを<xref:System.Windows.Controls.Button>追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-255">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="448f0-256">詳細については、「[方法 : 簡単なイベント ハンドラを作成する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-256">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="448f0-257">または*`ExpenseItHome.xaml.vb`\*\*`ExpenseItHome.xaml.cs`* を開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-257">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="448f0-258">ボタン クリック イベント`ExpenseItHome`ハンドラーを追加するクラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-258">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="448f0-259">イベント ハンドラは **、経費レポート ページを**開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-259">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="448f0-260">経費明細書ページの UI を作成します。</span><span class="sxs-lookup"><span data-stu-id="448f0-260">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="448f0-261">*ページで\*\*\*`ExpenseItHome`*\* 選択した人の経費精算書が表示されます。</span><span class="sxs-lookup"><span data-stu-id="448f0-261">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="448f0-262">ここでは、**経費レポート ページ**の UI を作成します。</span><span class="sxs-lookup"><span data-stu-id="448f0-262">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="448f0-263">また、さまざまな UI 要素に背景色と塗りつぶしの色を追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-263">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="448f0-264">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-264">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="448f0-265">タグの間に次の<xref:System.Windows.Controls.Grid>XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-265">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="448f0-266">この UI は*`ExpenseItHome.xaml`*、 に似ていますが、レポート<xref:System.Windows.Controls.DataGrid>データは に表示されます。</span><span class="sxs-lookup"><span data-stu-id="448f0-266">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="448f0-267">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="448f0-267">Build and run the application.</span></span>

4. <span data-ttu-id="448f0-268">[**表示**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="448f0-268">Select the **View** button.</span></span>

    <span data-ttu-id="448f0-269">経費明細書ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="448f0-269">The expense report page appears.</span></span> <span data-ttu-id="448f0-270">また、戻るナビゲーション ボタンが有効になっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-270">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="448f0-271">次の図は *、ExpenseReportPage.xaml*に追加された UI 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="448f0-271">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![経費経費レポート ページ用に作成した UI を示すサンプル のスクリーンショットです。](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="448f0-273">スタイル コントロール</span><span class="sxs-lookup"><span data-stu-id="448f0-273">Style controls</span></span>

<span data-ttu-id="448f0-274">UI の同じ型のすべての要素で、さまざまな要素の外観が同じであることが多いです。</span><span class="sxs-lookup"><span data-stu-id="448f0-274">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="448f0-275">UI では[、スタイル](../controls/styling-and-templating.md)を使用して、複数の要素にわたって外観を再利用可能にします。</span><span class="sxs-lookup"><span data-stu-id="448f0-275">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="448f0-276">スタイルの再利用性は、XAML の作成と管理を簡略化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="448f0-276">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="448f0-277">このセクションでは、これまでの手順で定義した要素ごとの属性を、スタイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="448f0-277">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="448f0-278">*アプリケーション.xaml*または*App.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-278">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="448f0-279">タグの間に次の<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-279">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="448f0-280">この XAML は、次のスタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-280">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="448f0-281">`headerTextStyle`: ページ タイトル <xref:System.Windows.Controls.Label>の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-281">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="448f0-282">`labelStyle`: <xref:System.Windows.Controls.Label> コントロールの書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-282">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="448f0-283">`columnHeaderStyle`: <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-283">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="448f0-284">`listHeaderStyle`: リスト ヘッダーの <xref:System.Windows.Controls.Border> コントロールの書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="448f0-284">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="448f0-285">`listHeaderTextStyle`: リストヘッダー<xref:System.Windows.Controls.Label>をフォーマットするには.</span><span class="sxs-lookup"><span data-stu-id="448f0-285">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="448f0-286">`buttonStyle`: on `ExpenseItHome.xaml`<xref:System.Windows.Controls.Button>をフォーマットするには.</span><span class="sxs-lookup"><span data-stu-id="448f0-286">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="448f0-287">スタイルは<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>プロパティ要素のリソースと子であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-287">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="448f0-288">ここでは、スタイルはアプリケーション内のすべての要素に適用されます。</span><span class="sxs-lookup"><span data-stu-id="448f0-288">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="448f0-289">NET アプリでリソースを使用する例については、「アプリケーション[リソースの使用](../advanced/how-to-use-application-resources.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-289">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="448f0-290">では*`ExpenseItHome.xaml`*、要素間のすべてのもの<xref:System.Windows.Controls.Grid>を次の XAML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="448f0-290">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="448f0-291">各コントロールの外観を定義する <xref:System.Windows.VerticalAlignment> や <xref:System.Windows.Media.FontFamily> などのプロパティは、これらのスタイルを適用することで、削除されて置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="448f0-291">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="448f0-292">たとえば、`headerTextStyle`は "経費報告の表示"<xref:System.Windows.Controls.Label>に適用されます。</span><span class="sxs-lookup"><span data-stu-id="448f0-292">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="448f0-293">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-293">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="448f0-294">要素間のすべてのもの<xref:System.Windows.Controls.Grid>を次の XAML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="448f0-294">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="448f0-295">この XAML は、 <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.Border>要素にスタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-295">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="448f0-296">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="448f0-296">Build and run the application.</span></span> <span data-ttu-id="448f0-297">ウィンドウの外観は、以前と同じです。</span><span class="sxs-lookup"><span data-stu-id="448f0-297">The window appearance is the same as previously.</span></span>

    ![経費前回のセクションと同じ外観のサンプルスクリーンショットです。](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="448f0-299">アプリケーションを閉じて、Visual Studio に戻ります。</span><span class="sxs-lookup"><span data-stu-id="448f0-299">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="448f0-300">コントロールにデータをバインドする</span><span class="sxs-lookup"><span data-stu-id="448f0-300">Bind data to a control</span></span>

<span data-ttu-id="448f0-301">このセクションでは、さまざまなコントロールにバインドされた XML データを作成します。</span><span class="sxs-lookup"><span data-stu-id="448f0-301">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="448f0-302">で*`ExpenseItHome.xaml`*、開始<xref:System.Windows.Controls.Grid>要素の後に次の XAML を追加<xref:System.Windows.Data.XmlDataProvider>して、各ユーザーのデータを含む を作成します。</span><span class="sxs-lookup"><span data-stu-id="448f0-302">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="448f0-303">データはリソースとして作成されます<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="448f0-303">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="448f0-304">通常、このデータはファイルとしてロードされますが、わかりやすくするため、データはインラインで追加されます。</span><span class="sxs-lookup"><span data-stu-id="448f0-304">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="448f0-305">要素内`<Grid.Resources>`に、要素の後`<xref:System.Windows.DataTemplate>`に<xref:System.Windows.Controls.ListBox>データを表示する方法を定義する次の要素を`<XmlDataProvider>`追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-305">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="448f0-306">データ テンプレートの詳細については、「[データ テンプレートの概要」を](../data/data-templating-overview.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-306">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="448f0-307">既存<xref:System.Windows.Controls.ListBox>の XAML を次の XAML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="448f0-307">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="448f0-308">この XAML は<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>、のプロパティ<xref:System.Windows.Controls.ListBox>をデータ ソースにバインドし、データ テンプレート<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>を として適用します。</span><span class="sxs-lookup"><span data-stu-id="448f0-308">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="448f0-309">コントロールへのデータの接続</span><span class="sxs-lookup"><span data-stu-id="448f0-309">Connect data to controls</span></span>

<span data-ttu-id="448f0-310">次に、**`ExpenseItHome`** ページで選択されている名前を取得し、**それを ExpenseReportPage**のコンストラクタに渡すコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-310">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="448f0-311">**渡**された項目を使用してデータ コンテキストを設定します。 *ExpenseReportPage.xaml*</span><span class="sxs-lookup"><span data-stu-id="448f0-311">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="448f0-312">*ExpenseReportPage.xaml.vb* または *ExpenseReportPage.xaml.cs*を開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-312">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="448f0-313">オブジェクトを取得するコンストラクターを追加して、選択した個人の経費報告書データを渡せるようにします。</span><span class="sxs-lookup"><span data-stu-id="448f0-313">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="448f0-314">または*`ExpenseItHome.xaml.vb`\*\*`ExpenseItHome.xaml.cs`* を開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-314">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="448f0-315">選択した<xref:System.Windows.Controls.Primitives.ButtonBase.Click>ユーザーの経費報告書データを渡す新しいコンストラクターを呼び出すイベント ハンドラーを変更します。</span><span class="sxs-lookup"><span data-stu-id="448f0-315">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="448f0-316">データ テンプレートを使用したスタイル データ</span><span class="sxs-lookup"><span data-stu-id="448f0-316">Style data with data templates</span></span>

<span data-ttu-id="448f0-317">このセクションでは、データ テンプレートを使用して、データ バインド リストの各項目の UI を更新します。</span><span class="sxs-lookup"><span data-stu-id="448f0-317">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="448f0-318">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="448f0-318">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="448f0-319">"Name" 要素と "Department"<xref:System.Windows.Controls.Label>要素の内容を適切なデータ ソース プロパティにバインドします。</span><span class="sxs-lookup"><span data-stu-id="448f0-319">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="448f0-320">データ バインディングの詳細については、「データ バインディングの[概要](../../../desktop-wpf/data/data-binding-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-320">For more information about data binding, see [Data binding overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="448f0-321">開始<xref:System.Windows.Controls.Grid>要素の後に、経費精算書データの表示方法を定義する次のデータ テンプレートを追加します。</span><span class="sxs-lookup"><span data-stu-id="448f0-321">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="448f0-322">要素を<xref:System.Windows.Controls.DataGridTextColumn>要素の<xref:System.Windows.Controls.DataGridTemplateColumn>下<xref:System.Windows.Controls.DataGrid>に置き換え、テンプレートを適用します。</span><span class="sxs-lookup"><span data-stu-id="448f0-322">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="448f0-323">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="448f0-323">Build and run the application.</span></span>

6. <span data-ttu-id="448f0-324">ユーザーを選択し、[**表示**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="448f0-324">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="448f0-325">次の図は、コントロール、レイアウト`ExpenseIt`、スタイル、データ バインディング、およびデータ テンプレートが適用されたアプリケーションの両方のページを示しています。</span><span class="sxs-lookup"><span data-stu-id="448f0-325">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![名前リストと経費報告書を表示するアプリの両方のページ。](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="448f0-327">このサンプルでは、WPF の特定の機能を示し、セキュリティ、ローカライズ、アクセシビリティなどのベスト プラクティスに従うわけではありません。</span><span class="sxs-lookup"><span data-stu-id="448f0-327">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="448f0-328">WPF と .NET アプリ開発のベスト プラクティスの包括的なカバレッジについては、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-328">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="448f0-329">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="448f0-329">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
> - [<span data-ttu-id="448f0-330">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="448f0-330">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="448f0-331">WPF のグローバリゼーションとローカライズ</span><span class="sxs-lookup"><span data-stu-id="448f0-331">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="448f0-332">WPF のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="448f0-332">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="448f0-333">次のステップ</span><span class="sxs-lookup"><span data-stu-id="448f0-333">Next steps</span></span>

<span data-ttu-id="448f0-334">このチュートリアルでは、Windows プレゼンテーション ファンデーション (WPF) を使用して UI を作成するためのいくつかの手法を説明しました。</span><span class="sxs-lookup"><span data-stu-id="448f0-334">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="448f0-335">これで、データ バインド .NET アプリの構成要素の基本を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="448f0-335">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="448f0-336">WPF のアーキテクチャおよびプログラミング モデルの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-336">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="448f0-337">WPF アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="448f0-337">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="448f0-338">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="448f0-338">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="448f0-339">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="448f0-339">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="448f0-340">レイアウト</span><span class="sxs-lookup"><span data-stu-id="448f0-340">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="448f0-341">アプリケーションの作成の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="448f0-341">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="448f0-342">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="448f0-342">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="448f0-343">コントロール</span><span class="sxs-lookup"><span data-stu-id="448f0-343">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="448f0-344">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="448f0-344">Data binding overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="448f0-345">グラフィックスとマルチメディア</span><span class="sxs-lookup"><span data-stu-id="448f0-345">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="448f0-346">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="448f0-346">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="448f0-347">関連項目</span><span class="sxs-lookup"><span data-stu-id="448f0-347">See also</span></span>

- [<span data-ttu-id="448f0-348">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="448f0-348">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="448f0-349">データ テンプレートの概要</span><span class="sxs-lookup"><span data-stu-id="448f0-349">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="448f0-350">WPF アプリケーションをビルドする</span><span class="sxs-lookup"><span data-stu-id="448f0-350">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="448f0-351">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="448f0-351">Styles and templates</span></span>](../controls/styles-and-templates.md)
