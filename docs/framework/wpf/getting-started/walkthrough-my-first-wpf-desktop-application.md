---
title: Visual Studio 2019 で初めての WPF アプリを作成する-.NET Framework
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 232605850c65aebd9aafdc9b76c90af42f2c901c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746977"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="46a70-102">チュートリアル: Visual Studio 2019 で初めての WPF アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="46a70-102">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="46a70-103">この記事では、ほとんどの WPF アプリケーションに共通する要素 (Extensible Application Markup Language (XAML) マークアップ、分離コード、アプリケーション定義) を含む Windows Presentation Foundation (WPF) デスクトップアプリケーションを開発する方法について説明します。コントロール、レイアウト、データバインディング、およびスタイル。</span><span class="sxs-lookup"><span data-stu-id="46a70-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="46a70-104">アプリケーションを開発するには、Visual Studio を使用します。</span><span class="sxs-lookup"><span data-stu-id="46a70-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="46a70-105">このチュートリアルでは、以下の内容を学習します。</span><span class="sxs-lookup"><span data-stu-id="46a70-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="46a70-106">WPF プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="46a70-106">Create a WPF project.</span></span>
> - <span data-ttu-id="46a70-107">XAML を使用して、アプリケーションのユーザーインターフェイス (UI) の外観をデザインします。</span><span class="sxs-lookup"><span data-stu-id="46a70-107">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="46a70-108">アプリケーションの動作を構築するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="46a70-108">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="46a70-109">アプリケーションを管理するためのアプリケーション定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="46a70-109">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="46a70-110">コントロールを追加し、レイアウトを作成してアプリケーション UI を作成します。</span><span class="sxs-lookup"><span data-stu-id="46a70-110">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="46a70-111">アプリケーションの UI 全体で一貫した外観のスタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="46a70-111">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="46a70-112">Ui にデータを設定し、データと UI の同期を保つために、UI をデータにバインドします。</span><span class="sxs-lookup"><span data-stu-id="46a70-112">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="46a70-113">チュートリアルを終了すると、選択したユーザーの経費報告書をユーザーが表示できるスタンドアロン Windows アプリケーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="46a70-113">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="46a70-114">アプリケーションは、ブラウザースタイルのウィンドウでホストされるいくつかの WPF ページで構成されています。</span><span class="sxs-lookup"><span data-stu-id="46a70-114">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="46a70-115">このチュートリアルで使用されているサンプルコードは、Visual Basic とC#チュートリアルの[WPF アプリのサンプルコード](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)の両方で使用できます。</span><span class="sxs-lookup"><span data-stu-id="46a70-115">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="46a70-116">このページの上部にある言語セレクターを使用しC#て、と Visual Basic の間でサンプルコードのコード言語を切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="46a70-116">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="46a70-117">前提条件</span><span class="sxs-lookup"><span data-stu-id="46a70-117">Prerequisites</span></span>

- <span data-ttu-id="46a70-118">**.Net デスクトップ開発**ワークロードがインストールされた[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 。</span><span class="sxs-lookup"><span data-stu-id="46a70-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="46a70-119">最新バージョンの Visual Studio をインストールする方法の詳細については、「 [Visual studio のインストール](/visualstudio/install/install-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46a70-119">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="46a70-120">アプリケーションプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="46a70-120">Create the application project</span></span>

<span data-ttu-id="46a70-121">最初の手順では、アプリケーションの定義、2つのページ、およびイメージを含むアプリケーションインフラストラクチャを作成します。</span><span class="sxs-lookup"><span data-stu-id="46a70-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="46a70-122">Visual Basic または Visual C# **`ExpenseIt`** という名前の新しい WPF アプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="46a70-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="46a70-123">Visual Studio を開き、 **[作業の開始]** メニューの **[新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="46a70-123">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="46a70-124">**[新しいプロジェクトの作成]** ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="46a70-124">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="46a70-125">**言語** ドロップダウンで、 **C#**  または  **Visual Basic** を選択します。</span><span class="sxs-lookup"><span data-stu-id="46a70-125">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>
      
   3. <span data-ttu-id="46a70-126">**[WPF アプリ (.NET Framework)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="46a70-126">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
     
      ![[新しいプロジェクトの作成] ダイアログ](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      <span data-ttu-id="46a70-128">**[新しいプロジェクトの構成]** ダイアログボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-128">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="46a70-129">**`ExpenseIt`** プロジェクト名を入力し、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="46a70-129">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![[新しいプロジェクトの構成] ダイアログ](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="46a70-131">Visual Studio によってプロジェクトが作成され、 **mainwindow.xaml**という名前の既定のアプリケーションウィンドウのデザイナーが開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-131">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="46a70-132">*アプリケーション .xaml* (Visual Basic) または*app.xaml* (C#) を開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-132">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="46a70-133">この XAML ファイルは、WPF アプリケーションとすべてのアプリケーションリソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="46a70-133">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="46a70-134">また、このファイルを使用して、アプリケーションの起動時に自動的に表示される UI (この場合は Mainwindow.xaml) を指定し*ます*。</span><span class="sxs-lookup"><span data-stu-id="46a70-134">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="46a70-135">XAML は、Visual Basic では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="46a70-135">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="46a70-136">およびでは、次C#のようになります。</span><span class="sxs-lookup"><span data-stu-id="46a70-136">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="46a70-137">*Mainwindow.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-137">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="46a70-138">この XAML ファイルは、アプリケーションのメインウィンドウであり、ページで作成されたコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="46a70-138">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="46a70-139"><xref:System.Windows.Window> クラスは、ウィンドウのタイトル、サイズ、アイコンなどのプロパティを定義し、終了や非表示などのイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="46a70-139">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="46a70-140">次の XAML に示すように、<xref:System.Windows.Window> 要素を <xref:System.Windows.Navigation.NavigationWindow>に変更します。</span><span class="sxs-lookup"><span data-stu-id="46a70-140">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="46a70-141">このアプリは、ユーザーの入力に応じてさまざまなコンテンツに移動します。</span><span class="sxs-lookup"><span data-stu-id="46a70-141">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="46a70-142">このため、メイン <xref:System.Windows.Window> を <xref:System.Windows.Navigation.NavigationWindow>に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46a70-142">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="46a70-143"><xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Window>のすべてのプロパティを継承します。</span><span class="sxs-lookup"><span data-stu-id="46a70-143"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="46a70-144">XAML ファイルの <xref:System.Windows.Navigation.NavigationWindow> 要素は、<xref:System.Windows.Navigation.NavigationWindow> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="46a70-144">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="46a70-145">詳細については、「[ナビゲーションの概要](../app-development/navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46a70-145">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="46a70-146"><xref:System.Windows.Navigation.NavigationWindow> タグの間から <xref:System.Windows.Controls.Grid> 要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="46a70-146">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="46a70-147"><xref:System.Windows.Navigation.NavigationWindow> 要素の XAML コードで、次のプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="46a70-147">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="46a70-148"><xref:System.Windows.Window.Title%2A> プロパティを "`ExpenseIt`" に設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-148">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="46a70-149"><xref:System.Windows.FrameworkElement.Height%2A> プロパティを350ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-149">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="46a70-150"><xref:System.Windows.FrameworkElement.Width%2A> プロパティを500ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-150">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="46a70-151">XAML は、Visual Basic に対して次のようになります。</span><span class="sxs-lookup"><span data-stu-id="46a70-151">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="46a70-152">では、次のC#ようになります。</span><span class="sxs-lookup"><span data-stu-id="46a70-152">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="46a70-153">*Mainwindow.xaml*または*MainWindow.xaml.cs*を開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-153">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="46a70-154">このファイルは、 *mainwindow.xaml*で宣言されたイベントを処理するコードを含む分離コードファイルです。</span><span class="sxs-lookup"><span data-stu-id="46a70-154">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="46a70-155">このファイルには、XAML で定義されたウィンドウの部分クラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="46a70-155">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="46a70-156">を使用してC#いる場合は、<xref:System.Windows.Navigation.NavigationWindow>から派生するように `MainWindow` クラスを変更します。</span><span class="sxs-lookup"><span data-stu-id="46a70-156">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="46a70-157">(Visual Basic では、XAML でウィンドウを変更すると、自動的にこの処理が行われます)。コードC#は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="46a70-157">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="46a70-158">アプリケーションへのファイルの追加</span><span class="sxs-lookup"><span data-stu-id="46a70-158">Add files to the application</span></span>

<span data-ttu-id="46a70-159">このセクションでは、アプリケーションに 2 つのページと 1 つのイメージを追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="46a70-160">新しいページをプロジェクトに追加し、 *`ExpenseItHome.xaml`* という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-160">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="46a70-161">**ソリューションエクスプローラー**で、[ **`ExpenseIt`** プロジェクト] ノードを右クリックし、[ > **ページ**の**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="46a70-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="46a70-162">**[新しい項目の追加]** ダイアログでは、 **[ページ (WPF)]** テンプレートは既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="46a70-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="46a70-163">**`ExpenseItHome`** 名を入力し、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="46a70-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="46a70-164">このページは、アプリケーションの起動時に表示される最初のページです。</span><span class="sxs-lookup"><span data-stu-id="46a70-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="46a70-165">このレポートには、の経費明細書を表示するために選択する相手の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="46a70-165">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="46a70-166">*`ExpenseItHome.xaml`* を開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-166">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="46a70-167"><xref:System.Windows.Controls.Page.Title%2A> を "`ExpenseIt - Home`" に設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="46a70-168">`DesignHeight` を350ピクセルに設定し、`DesignWidth` を500ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-168">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="46a70-169">XAML は、Visual Basic に対して次のように表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="46a70-169">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="46a70-170">では、次のC#ようになります。</span><span class="sxs-lookup"><span data-stu-id="46a70-170">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="46a70-171">*Mainwindow.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-171">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="46a70-172"><xref:System.Windows.Navigation.NavigationWindow> 要素に <xref:System.Windows.Navigation.NavigationWindow.Source%2A> プロパティを追加し、それを "`ExpenseItHome.xaml`" に設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-172">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="46a70-173">これにより、アプリケーションの起動時に最初に開かれるページに *`ExpenseItHome.xaml`* が設定されます。</span><span class="sxs-lookup"><span data-stu-id="46a70-173">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="46a70-174">Visual Basic の XAML の例:</span><span class="sxs-lookup"><span data-stu-id="46a70-174">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="46a70-175">および C# の場合。</span><span class="sxs-lookup"><span data-stu-id="46a70-175">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="46a70-176">また、 **[プロパティ]** ウィンドウの **[その他]** カテゴリで、 **[ソース]** プロパティを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="46a70-176">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![プロパティウィンドウのソースプロパティ](./media/properties-source.png)

1. <span data-ttu-id="46a70-178">別の新しい WPF ページをプロジェクトに追加し、次*のように*名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-178">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="46a70-179">**ソリューションエクスプローラー**で、[ **`ExpenseIt`** プロジェクト] ノードを右クリックし、[ > **ページ**の**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="46a70-179">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="46a70-180">**[新しい項目の追加]** ダイアログで、 **[ページ (WPF)]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="46a70-180">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="46a70-181">[名前の指定] をクリック**し、[** **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="46a70-181">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="46a70-182">このページには、[ **`ExpenseItHome`** ] ページで選択されたユーザーの経費明細書が表示されます。</span><span class="sxs-lookup"><span data-stu-id="46a70-182">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="46a70-183">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-183">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="46a70-184"><xref:System.Windows.Controls.Page.Title%2A> を "`ExpenseIt - View Expense`" に設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-184">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="46a70-185">`DesignHeight` を350ピクセルに設定し、`DesignWidth` を500ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-185">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span> 

    <span data-ttu-id="46a70-186">Visual Basic では、この*xaml*は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="46a70-186">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="46a70-187">およびでは、次C#のようになります。</span><span class="sxs-lookup"><span data-stu-id="46a70-187">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="46a70-188">*Expenseithome.xaml*を開き、 *ExpenseItHome.xaml.cs* 、または ExpenseReportPage.xaml.cs *、また*はを開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-188">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="46a70-189">新しいページファイルを作成すると、Visual Studio によってその*分離コード*ファイルが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="46a70-189">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="46a70-190">これらの分離コード ファイルでは、ユーザー入力に対応するためのロジックを処理します。</span><span class="sxs-lookup"><span data-stu-id="46a70-190">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="46a70-191">**`ExpenseItHome`** のコードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="46a70-191">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="46a70-192">また、次のような**ページ**があります。</span><span class="sxs-lookup"><span data-stu-id="46a70-192">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="46a70-193">*透かし*という名前のイメージをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-193">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="46a70-194">独自のイメージを作成したり、サンプルコードからファイルをコピーしたり、 [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub リポジトリから取得したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="46a70-194">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="46a70-195">プロジェクトノードを右クリックし、[**既存の項目**の**追加** > ] を選択するか、 **Shift**キーを押し+**Alt**+**A**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="46a70-195">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="46a70-196">**[既存項目の追加]** ダイアログボックスで、すべての **[ファイル]** または **[イメージファイル]** のいずれかにファイルフィルターを設定し、使用するイメージファイルを参照して **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="46a70-196">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="46a70-197">アプリケーションの構築と実行</span><span class="sxs-lookup"><span data-stu-id="46a70-197">Build and run the application</span></span>

1. <span data-ttu-id="46a70-198">アプリケーションをビルドして実行するには、 **F5**キーを押すか、 **[デバッグ]** メニューの **[デバッグの開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46a70-198">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="46a70-199">次の図は、<xref:System.Windows.Navigation.NavigationWindow> ボタンを持つアプリケーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="46a70-199">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![アプリケーションをビルドして実行します。](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="46a70-201">アプリケーションを閉じて、Visual Studio に戻ります。</span><span class="sxs-lookup"><span data-stu-id="46a70-201">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="46a70-202">レイアウトを作成する</span><span class="sxs-lookup"><span data-stu-id="46a70-202">Create the layout</span></span>

<span data-ttu-id="46a70-203">レイアウトは、UI 要素を配置するための順序付けされた方法を提供し、UI のサイズが変更されたときの要素のサイズと位置も管理します。</span><span class="sxs-lookup"><span data-stu-id="46a70-203">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="46a70-204">通常、レイアウトを作成するには、次のいずれかのレイアウト コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="46a70-204">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="46a70-205"><xref:System.Windows.Controls.Canvas>-キャンバス領域に対する相対座標を使用して子要素を明示的に配置できる領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="46a70-205"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="46a70-206"><xref:System.Windows.Controls.DockPanel>-子要素を水平方向または垂直方向に整列できる領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="46a70-206"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="46a70-207"><xref:System.Windows.Controls.Grid>-列と行で構成される柔軟性のあるグリッド領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="46a70-207"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="46a70-208"><xref:System.Windows.Controls.StackPanel>-子要素を水平方向または垂直方向の単一行に整列します。</span><span class="sxs-lookup"><span data-stu-id="46a70-208"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="46a70-209"><xref:System.Windows.Controls.VirtualizingStackPanel>-水平方向または垂直方向の単一行でコンテンツを整列し、仮想化します。</span><span class="sxs-lookup"><span data-stu-id="46a70-209"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="46a70-210">子要素を左から右へ順番に配置し、内容を含んでいるボックスの端にある次の行に分割します。 <xref:System.Windows.Controls.WrapPanel></span><span class="sxs-lookup"><span data-stu-id="46a70-210"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="46a70-211">後続の順序付けは、Orientation プロパティの値に応じて、上から下または右から左に順番に行われます。</span><span class="sxs-lookup"><span data-stu-id="46a70-211">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="46a70-212">これらの各レイアウトコントロールは、その子要素に対して特定の種類のレイアウトをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="46a70-212">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="46a70-213">`ExpenseIt` のページのサイズを変更することができ、各ページには、水平方向および垂直方向に他の要素と共に配置された要素があります。</span><span class="sxs-lookup"><span data-stu-id="46a70-213">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="46a70-214">この例では、<xref:System.Windows.Controls.Grid> はアプリケーションのレイアウト要素として使用されます。</span><span class="sxs-lookup"><span data-stu-id="46a70-214">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="46a70-215"><xref:System.Windows.Controls.Panel> 要素の詳細については、「[パネルの概要](../controls/panels-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46a70-215">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="46a70-216">レイアウトの詳細については、「 [layout](../advanced/layout.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46a70-216">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="46a70-217">このセクションでは、 *`ExpenseItHome.xaml`* の <xref:System.Windows.Controls.Grid> に列と行の定義を追加することによって、3つの行と10ピクセルの余白を含む単一列テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="46a70-217">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="46a70-218">*`ExpenseItHome.xaml`* で、<xref:System.Windows.Controls.Grid> 要素の <xref:System.Windows.FrameworkElement.Margin%2A> プロパティを "10, 0, 10, 10" に設定します。これは、左、上、右、下の余白に対応します。</span><span class="sxs-lookup"><span data-stu-id="46a70-218">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="46a70-219">また、 **[プロパティ]** ウィンドウの **[レイアウト]** カテゴリで、**余白**の値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="46a70-219">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![プロパティウィンドウの余白の値](./media/properties-margin.png)

2. <span data-ttu-id="46a70-221">次の XAML を <xref:System.Windows.Controls.Grid> タグの間に追加して、行と列の定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="46a70-221">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="46a70-222">2つの行の <xref:System.Windows.Controls.RowDefinition.Height%2A> は <xref:System.Windows.GridLength.Auto%2A>に設定されます。つまり、行のサイズは、行の内容に基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="46a70-222">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="46a70-223">既定の <xref:System.Windows.Controls.RowDefinition.Height%2A> は <xref:System.Windows.GridUnitType.Star> サイズ変更です。これは、行の高さが使用可能な領域の加重比率であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="46a70-223">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="46a70-224">たとえば、2つの行のそれぞれに "\*" の <xref:System.Windows.Controls.RowDefinition.Height%2A> がある場合、それぞれの行の高さは使用可能な領域の半分になります。</span><span class="sxs-lookup"><span data-stu-id="46a70-224">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="46a70-225"><xref:System.Windows.Controls.Grid> に次の XAML が含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="46a70-225">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="46a70-226">コントロールの追加</span><span class="sxs-lookup"><span data-stu-id="46a70-226">Add controls</span></span>

<span data-ttu-id="46a70-227">このセクションでは、ホームページの UI を更新して、人の一覧を表示します。ここでは、1人のユーザーを選択して経費報告書を表示します。</span><span class="sxs-lookup"><span data-stu-id="46a70-227">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="46a70-228">コントロールとは、ユーザーがアプリケーションと対話できるようにする UI オブジェクトのことです。</span><span class="sxs-lookup"><span data-stu-id="46a70-228">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="46a70-229">詳しくは、「 [コントロール](../controls/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="46a70-229">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="46a70-230">この UI を作成するには、 *`ExpenseItHome.xaml`* に次の要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-230">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="46a70-231"><xref:System.Windows.Controls.ListBox> (people の一覧)。</span><span class="sxs-lookup"><span data-stu-id="46a70-231">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="46a70-232">(リストヘッダーの) <xref:System.Windows.Controls.Label>。</span><span class="sxs-lookup"><span data-stu-id="46a70-232">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="46a70-233"><xref:System.Windows.Controls.Button> (クリックすると、一覧で選択されているユーザーの経費明細書が表示されます)。</span><span class="sxs-lookup"><span data-stu-id="46a70-233">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="46a70-234">各コントロールは、<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> 添付プロパティを設定することによって、<xref:System.Windows.Controls.Grid> の行に配置されます。</span><span class="sxs-lookup"><span data-stu-id="46a70-234">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="46a70-235">添付プロパティの詳細については、「[添付プロパティの概要](../advanced/attached-properties-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46a70-235">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="46a70-236">*`ExpenseItHome.xaml`* で、<xref:System.Windows.Controls.Grid> タグの間に次の XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-236">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="46a70-237">コントロールは、 **[ツールボックス]** ウィンドウからデザインウィンドウにドラッグして、 **[プロパティ]** ウィンドウでプロパティを設定することによって作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="46a70-237">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="46a70-238">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="46a70-238">Build and run the application.</span></span>

    <span data-ttu-id="46a70-239">次の図は、作成したコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="46a70-239">The following illustration shows the controls you created:</span></span>

![名前の一覧を表示している、このサンプルスクリーンショット](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="46a70-241">イメージとタイトルを追加する</span><span class="sxs-lookup"><span data-stu-id="46a70-241">Add an image and a title</span></span>

<span data-ttu-id="46a70-242">このセクションでは、ホームページの UI をイメージとページタイトルで更新します。</span><span class="sxs-lookup"><span data-stu-id="46a70-242">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="46a70-243">*`ExpenseItHome.xaml`* で <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> に別の列を追加し、230ピクセルの固定 <xref:System.Windows.Controls.ColumnDefinition.Width%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="46a70-243">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="46a70-244"><xref:System.Windows.Controls.Grid.RowDefinitions%2A>に、合計4行の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-244">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="46a70-245">コントロールを2番目の列に移動するには、3つのコントロール (Border、ListBox、および Button) のそれぞれで [<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>] プロパティを1に設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-245">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="46a70-246">各コントロールを1行下に移動します。そのためには、3つのコントロール (Border、ListBox、および Button) と Border 要素のそれぞれに対して、<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> 値を1ずつインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="46a70-246">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="46a70-247">3つのコントロールの XAML は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="46a70-247">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="46a70-248">`<Grid>` タグと `</Grid>` タグの間に次の XAML を追加して、<xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> プロパティを*ウォーターマークの .png*画像ファイルに設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-248">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="46a70-249"><xref:System.Windows.Controls.Border> 要素の前に、「経費報告書の表示」という内容の <xref:System.Windows.Controls.Label> を追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-249">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="46a70-250">このラベルはページのタイトルです。</span><span class="sxs-lookup"><span data-stu-id="46a70-250">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="46a70-251">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="46a70-251">Build and run the application.</span></span>

<span data-ttu-id="46a70-252">次の図は、先ほど追加したものの結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="46a70-252">The following illustration shows the results of what you just added:</span></span>

![新しいイメージの背景とページのタイトルを示す、ページのサンプルスクリーンショット](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="46a70-254">イベントを処理するコードを追加する</span><span class="sxs-lookup"><span data-stu-id="46a70-254">Add code to handle events</span></span>

1. <span data-ttu-id="46a70-255">*`ExpenseItHome.xaml`* で、<xref:System.Windows.Controls.Button> 要素に <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-255">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="46a70-256">詳細については、「[方法: 単純なイベントハンドラーを作成](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46a70-256">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="46a70-257">*`ExpenseItHome.xaml.vb`* または *`ExpenseItHome.xaml.cs`* を開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-257">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="46a70-258">次のコードを `ExpenseItHome` クラスに追加して、ボタンクリックイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-258">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="46a70-259">イベントハンドラーによって、[処理された**Sereportpage** ] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-259">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="46a70-260">[印刷] ページの UI を作成する</span><span class="sxs-lookup"><span data-stu-id="46a70-260">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="46a70-261">[ **`ExpenseItHome`** ] ページで選択されたユーザーの経費明細書*が表示されます。*</span><span class="sxs-lookup"><span data-stu-id="46a70-261">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="46a70-262">このセクションでは、[の使用]**ページ**の UI を作成します。</span><span class="sxs-lookup"><span data-stu-id="46a70-262">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="46a70-263">また、さまざまな UI 要素に背景色と塗りつぶしの色を追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-263">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="46a70-264">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-264">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="46a70-265"><xref:System.Windows.Controls.Grid> タグの間に次の XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-265">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="46a70-266">この UI は *`ExpenseItHome.xaml`* に似ていますが、レポートデータが <xref:System.Windows.Controls.DataGrid>に表示される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="46a70-266">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="46a70-267">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="46a70-267">Build and run the application.</span></span>

4. <span data-ttu-id="46a70-268">**[表示]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="46a70-268">Select the **View** button.</span></span>

    <span data-ttu-id="46a70-269">経費明細書ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="46a70-269">The expense report page appears.</span></span> <span data-ttu-id="46a70-270">また、[戻る] ナビゲーションボタンが有効になっていることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="46a70-270">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="46a70-271">次の図は、*ページ*に追加された UI 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="46a70-271">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![このページでは、[ページの作成] で作成した UI を示しています。](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="46a70-273">スタイルコントロール</span><span class="sxs-lookup"><span data-stu-id="46a70-273">Style controls</span></span>

<span data-ttu-id="46a70-274">多くの場合、UI で同じ種類のすべての要素に対して、さまざまな要素の外観が同じになります。</span><span class="sxs-lookup"><span data-stu-id="46a70-274">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="46a70-275">UI では、[スタイル](../controls/styling-and-templating.md)を使用して、複数の要素間で外観を再利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="46a70-275">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="46a70-276">スタイルの再利用性により、XAML の作成と管理が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="46a70-276">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="46a70-277">このセクションでは、これまでの手順で定義した要素ごとの属性を、スタイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="46a70-277">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="46a70-278">*アプリケーション .xaml* *または app.xaml を*開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-278">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="46a70-279"><xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> タグの間に次の XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-279">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="46a70-280">この XAML は、次のスタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-280">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="46a70-281">`headerTextStyle`: ページ タイトル <xref:System.Windows.Controls.Label>の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-281">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="46a70-282">`labelStyle`: <xref:System.Windows.Controls.Label> コントロールの書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-282">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="46a70-283">`columnHeaderStyle`: <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-283">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="46a70-284">`listHeaderStyle`: リスト ヘッダーの <xref:System.Windows.Controls.Border> コントロールの書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-284">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="46a70-285">`listHeaderTextStyle`: リストヘッダー <xref:System.Windows.Controls.Label>の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-285">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="46a70-286">`buttonStyle`: `ExpenseItHome.xaml`で <xref:System.Windows.Controls.Button> を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="46a70-286">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="46a70-287">スタイルは、<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property 要素のリソースと子であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="46a70-287">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="46a70-288">ここでは、スタイルはアプリケーション内のすべての要素に適用されます。</span><span class="sxs-lookup"><span data-stu-id="46a70-288">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="46a70-289">.NET アプリでのリソースの使用例については、「[アプリケーションリソースの使用](../advanced/how-to-use-application-resources.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46a70-289">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="46a70-290">*`ExpenseItHome.xaml`* で、<xref:System.Windows.Controls.Grid> の要素間のすべてを次の XAML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="46a70-290">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="46a70-291">各コントロールの外観を定義する <xref:System.Windows.VerticalAlignment> や <xref:System.Windows.Media.FontFamily> などのプロパティは、これらのスタイルを適用することで、削除されて置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="46a70-291">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="46a70-292">たとえば、`headerTextStyle` は "経費報告書の表示" <xref:System.Windows.Controls.Label>に適用されます。</span><span class="sxs-lookup"><span data-stu-id="46a70-292">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="46a70-293">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-293">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="46a70-294"><xref:System.Windows.Controls.Grid> の要素間のすべてを次の XAML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="46a70-294">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="46a70-295">この XAML は、<xref:System.Windows.Controls.Label> 要素と <xref:System.Windows.Controls.Border> 要素にスタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-295">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="46a70-296">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="46a70-296">Build and run the application.</span></span> <span data-ttu-id="46a70-297">ウィンドウの外観は、以前と同じです。</span><span class="sxs-lookup"><span data-stu-id="46a70-297">The window appearance is the same as previously.</span></span>

    ![前回のセクションと同じ外観の、このサンプルスクリーンショット。](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="46a70-299">アプリケーションを閉じて、Visual Studio に戻ります。</span><span class="sxs-lookup"><span data-stu-id="46a70-299">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="46a70-300">コントロールへのデータのバインド</span><span class="sxs-lookup"><span data-stu-id="46a70-300">Bind data to a control</span></span>

<span data-ttu-id="46a70-301">このセクションでは、さまざまなコントロールにバインドされている XML データを作成します。</span><span class="sxs-lookup"><span data-stu-id="46a70-301">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="46a70-302">*`ExpenseItHome.xaml`* で、開いている <xref:System.Windows.Controls.Grid> 要素の後に、次の XAML を追加して、各ユーザーのデータを含む <xref:System.Windows.Data.XmlDataProvider> を作成します。</span><span class="sxs-lookup"><span data-stu-id="46a70-302">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="46a70-303">データは <xref:System.Windows.Controls.Grid> リソースとして作成されます。</span><span class="sxs-lookup"><span data-stu-id="46a70-303">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="46a70-304">通常、このデータはファイルとして読み込まれますが、わかりやすくするために、データはインラインで追加されます。</span><span class="sxs-lookup"><span data-stu-id="46a70-304">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="46a70-305">`<Grid.Resources>` 要素内に、次の `<xref:System.Windows.DataTemplate>` 要素を追加します。この要素は、<xref:System.Windows.Controls.ListBox>内のデータを `<XmlDataProvider>` 要素の後に表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="46a70-305">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="46a70-306">データテンプレートの詳細については、「データテンプレートの[概要](../data/data-templating-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46a70-306">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="46a70-307">既存の <xref:System.Windows.Controls.ListBox> を次の XAML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="46a70-307">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="46a70-308">この XAML は、<xref:System.Windows.Controls.ListBox> の <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> プロパティをデータソースにバインドし、データテンプレートを <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>として適用します。</span><span class="sxs-lookup"><span data-stu-id="46a70-308">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="46a70-309">コントロールへのデータの接続</span><span class="sxs-lookup"><span data-stu-id="46a70-309">Connect data to controls</span></span>

<span data-ttu-id="46a70-310">次に、[ **`ExpenseItHome`** ] ページで選択されている名前を取得して、 **[ページの追加] のコンストラクター**に渡すコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-310">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="46a70-311">[調整された**Sereportpage** ] は、渡された項目を使用してそのデータコンテキストを設定します。これは、"*ページ*のバインド先" に定義されているコントロールです。</span><span class="sxs-lookup"><span data-stu-id="46a70-311">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="46a70-312">*ExpenseReportPage.xaml.vb* または *ExpenseReportPage.xaml.cs*を開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-312">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="46a70-313">オブジェクトを取得するコンストラクターを追加して、選択した個人の経費報告書データを渡せるようにします。</span><span class="sxs-lookup"><span data-stu-id="46a70-313">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="46a70-314">*`ExpenseItHome.xaml.vb`* または *`ExpenseItHome.xaml.cs`* を開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-314">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="46a70-315">選択したユーザーの経費報告書データを渡す新しいコンストラクターを呼び出すように、<xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントハンドラーを変更します。</span><span class="sxs-lookup"><span data-stu-id="46a70-315">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="46a70-316">データテンプレートを使用したデータのスタイル</span><span class="sxs-lookup"><span data-stu-id="46a70-316">Style data with data templates</span></span>

<span data-ttu-id="46a70-317">このセクションでは、データテンプレートを使用して、データバインドリストの各項目の UI を更新します。</span><span class="sxs-lookup"><span data-stu-id="46a70-317">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="46a70-318">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="46a70-318">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="46a70-319">"Name" および "Department" <xref:System.Windows.Controls.Label> 要素の内容を適切なデータソースプロパティにバインドします。</span><span class="sxs-lookup"><span data-stu-id="46a70-319">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="46a70-320">データバインディングの詳細については、「[データバインディングの概要](../../../desktop-wpf/data/data-binding-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46a70-320">For more information about data binding, see [Data binding overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="46a70-321">開いている <xref:System.Windows.Controls.Grid> 要素の後に、経費報告書データの表示方法を定義する次のデータテンプレートを追加します。</span><span class="sxs-lookup"><span data-stu-id="46a70-321">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="46a70-322"><xref:System.Windows.Controls.DataGridTextColumn> 要素を <xref:System.Windows.Controls.DataGrid> 要素の下の <xref:System.Windows.Controls.DataGridTemplateColumn> に置き換え、テンプレートを適用します。</span><span class="sxs-lookup"><span data-stu-id="46a70-322">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="46a70-323">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="46a70-323">Build and run the application.</span></span>

6. <span data-ttu-id="46a70-324">ユーザーを選択し、 **[表示]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="46a70-324">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="46a70-325">次の図は、コントロール、レイアウト、スタイル、データバインディング、適用されたデータテンプレートを適用した `ExpenseIt` アプリケーションの両方のページを示しています。</span><span class="sxs-lookup"><span data-stu-id="46a70-325">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![名前の一覧と経費報告書を表示するアプリの両方のページ。](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="46a70-327">このサンプルでは、WPF の特定の機能について説明します。セキュリティ、ローカライズ、アクセシビリティなどのベストプラクティスについては説明しません。</span><span class="sxs-lookup"><span data-stu-id="46a70-327">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="46a70-328">WPF と .NET アプリ開発のベストプラクティスの包括的な説明については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="46a70-328">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="46a70-329">ユーザー補助</span><span class="sxs-lookup"><span data-stu-id="46a70-329">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
> - [<span data-ttu-id="46a70-330">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="46a70-330">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="46a70-331">WPF のグローバリゼーションとローカライズ</span><span class="sxs-lookup"><span data-stu-id="46a70-331">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="46a70-332">WPF のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="46a70-332">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="46a70-333">次のステップ</span><span class="sxs-lookup"><span data-stu-id="46a70-333">Next steps</span></span>

<span data-ttu-id="46a70-334">このチュートリアルでは、Windows Presentation Foundation (WPF) を使用して UI を作成するためのいくつかの手法について学習しました。</span><span class="sxs-lookup"><span data-stu-id="46a70-334">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="46a70-335">これで、データバインドされた .NET アプリの構成要素についての基本的な理解ができました。</span><span class="sxs-lookup"><span data-stu-id="46a70-335">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="46a70-336">WPF のアーキテクチャおよびプログラミング モデルの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="46a70-336">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="46a70-337">WPF のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="46a70-337">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="46a70-338">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="46a70-338">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="46a70-339">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="46a70-339">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="46a70-340">レイアウト</span><span class="sxs-lookup"><span data-stu-id="46a70-340">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="46a70-341">アプリケーションの作成の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="46a70-341">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="46a70-342">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="46a70-342">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="46a70-343">コントロール</span><span class="sxs-lookup"><span data-stu-id="46a70-343">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="46a70-344">データバインディングの概要</span><span class="sxs-lookup"><span data-stu-id="46a70-344">Data binding overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="46a70-345">グラフィックスとマルチメディア</span><span class="sxs-lookup"><span data-stu-id="46a70-345">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="46a70-346">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="46a70-346">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="46a70-347">参照</span><span class="sxs-lookup"><span data-stu-id="46a70-347">See also</span></span>

- [<span data-ttu-id="46a70-348">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="46a70-348">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="46a70-349">データテンプレートの概要</span><span class="sxs-lookup"><span data-stu-id="46a70-349">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="46a70-350">WPF アプリケーションのビルド</span><span class="sxs-lookup"><span data-stu-id="46a70-350">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="46a70-351">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="46a70-351">Styles and templates</span></span>](../controls/styles-and-templates.md)
