---
title: Visual Studio で WPF アプリケーションを作成する
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
ms.openlocfilehash: 4919424339df1f8d2c68465bd9f9af42f344fe37
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70254067"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="3491a-102">チュートリアル: 初めての WPF デスクトップ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3491a-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="3491a-103">この記事では、ほとんどの WPF アプリケーションに共通の要素を含む Windows Presentation Foundation (WPF) デスクトップアプリケーションを開発する方法について説明します。Extensible Application Markup Language (XAML) マークアップ、分離コード、アプリケーション定義、コントロール、レイアウト、データバインディング、およびスタイル。</span><span class="sxs-lookup"><span data-stu-id="3491a-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="3491a-104">アプリケーションを開発するには、Visual Studio を使用します。</span><span class="sxs-lookup"><span data-stu-id="3491a-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="3491a-105">このチュートリアルでは、次の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3491a-105">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="3491a-106">XAML を使用して、アプリケーションのユーザーインターフェイス (UI) の外観をデザインします。</span><span class="sxs-lookup"><span data-stu-id="3491a-106">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="3491a-107">アプリケーションの動作を構築するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="3491a-107">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="3491a-108">アプリケーションを管理するためのアプリケーション定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="3491a-108">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="3491a-109">コントロールを追加し、レイアウトを作成してアプリケーション UI を作成します。</span><span class="sxs-lookup"><span data-stu-id="3491a-109">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="3491a-110">アプリケーションの UI 全体で一貫した外観のスタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3491a-110">Create styles for a consistent appearance throughout the application's UI.</span></span>

- <span data-ttu-id="3491a-111">Ui にデータを設定し、データと UI の同期を保つために、UI をデータにバインドします。</span><span class="sxs-lookup"><span data-stu-id="3491a-111">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="3491a-112">チュートリアルを終了すると、選択したユーザーの経費報告書をユーザーが表示できるスタンドアロン Windows アプリケーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3491a-112">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="3491a-113">アプリケーションは、ブラウザースタイルのウィンドウでホストされるいくつかの WPF ページで構成されています。</span><span class="sxs-lookup"><span data-stu-id="3491a-113">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="3491a-114">このチュートリアルのビルドに使用されるサンプルコードは、Visual Basic とC# [チュートリアルの WPF アプリのサンプルコード](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)の両方で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3491a-114">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Walkthrough WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="3491a-115">この記事の右上隅にあるC# **\<ドロップダウンを使用/>** して、と Visual Basic の間でサンプルコードのコード言語を切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="3491a-115">You can toggle the code language of the sample code between C# and Visual Basic by using the **\</>** drop-down on the upper right side of this article.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3491a-116">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3491a-116">Prerequisites</span></span>

- <span data-ttu-id="3491a-117">Visual Studio 2017 以降 (この記事では Visual Studio 2019 を使用します)</span><span class="sxs-lookup"><span data-stu-id="3491a-117">Visual Studio 2017 or later (this article uses Visual Studio 2019)</span></span>

   <span data-ttu-id="3491a-118">最新バージョンの Visual Studio をインストールする方法の詳細については、「 [Visual studio のインストール](/visualstudio/install/install-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3491a-118">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="3491a-119">アプリケーションプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="3491a-119">Create the application project</span></span>

<span data-ttu-id="3491a-120">最初の手順では、アプリケーションの定義、2つのページ、およびイメージを含むアプリケーションインフラストラクチャを作成します。</span><span class="sxs-lookup"><span data-stu-id="3491a-120">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="3491a-121">Visual Basic または Visual C# のという名前で新しい WPF アプリケーション プロジェクトを作成する **`ExpenseIt`** :</span><span class="sxs-lookup"><span data-stu-id="3491a-121">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="3491a-122">Visual Studio を開き、 **[作業の開始]** メニューの **[新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3491a-122">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="3491a-123">**[新しいプロジェクトの作成]** ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3491a-123">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="3491a-124">**言語** ドロップダウンで、 **C#**  または  **Visual Basic** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3491a-124">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>
      
   3. <span data-ttu-id="3491a-125">**[WPF アプリ (.NET Framework)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3491a-125">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
     
      ![[新しいプロジェクトの作成] ダイアログ](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      <span data-ttu-id="3491a-127">**[新しいプロジェクトの構成]** ダイアログボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="3491a-127">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="3491a-128">プロジェクト名を入力 **`ExpenseIt`** 選び **作成** です。</span><span class="sxs-lookup"><span data-stu-id="3491a-128">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![[新しいプロジェクトの構成] ダイアログ](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="3491a-130">Visual Studio によってプロジェクトが作成され、 **mainwindow.xaml**という名前の既定のアプリケーションウィンドウのデザイナーが開きます。</span><span class="sxs-lookup"><span data-stu-id="3491a-130">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="3491a-131">*アプリケーション .xaml* (Visual Basic) または*app.xaml* (C#) を開きます。</span><span class="sxs-lookup"><span data-stu-id="3491a-131">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="3491a-132">この XAML ファイルは、WPF アプリケーションとすべてのアプリケーションリソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="3491a-132">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="3491a-133">また、このファイルを使用して、アプリケーションの起動時に自動的に表示される UI (この場合は Mainwindow.xaml) を指定し*ます*。</span><span class="sxs-lookup"><span data-stu-id="3491a-133">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="3491a-134">XAML は、Visual Basic では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3491a-134">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="3491a-135">およびでは、次C#のようになります。</span><span class="sxs-lookup"><span data-stu-id="3491a-135">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="3491a-136">*MainWindow.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="3491a-136">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="3491a-137">この XAML ファイルは、アプリケーションのメインウィンドウであり、ページで作成されたコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="3491a-137">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="3491a-138">クラス<xref:System.Windows.Window>は、タイトル、サイズ、アイコンなどのウィンドウのプロパティを定義し、終了や非表示などのイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="3491a-138">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="3491a-139"><xref:System.Windows.Navigation.NavigationWindow>.xaml の<xref:System.Windows.Window>要素を、次に示すように変更します。</span><span class="sxs-lookup"><span data-stu-id="3491a-139">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="3491a-140">このアプリは、ユーザーの入力に応じてさまざまなコンテンツに移動します。</span><span class="sxs-lookup"><span data-stu-id="3491a-140">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="3491a-141">そのため、メイン ウィンドウを<xref:System.Windows.Window>から<xref:System.Windows.Navigation.NavigationWindow>に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3491a-141">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="3491a-142"><xref:System.Windows.Navigation.NavigationWindow>  は、<xref:System.Windows.Window>のすべてのプロパティを継承しています。</span><span class="sxs-lookup"><span data-stu-id="3491a-142"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="3491a-143">XAML ファイルの<xref:System.Windows.Navigation.NavigationWindow> 要素によって、クラスのインスタンスが作成<xref:System.Windows.Navigation.NavigationWindow>されます。</span><span class="sxs-lookup"><span data-stu-id="3491a-143">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="3491a-144">詳細については、「[ナビゲーションの概要](../app-development/navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3491a-144">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="3491a-145">タグ間の<xref:System.Windows.Controls.Grid>要素を削除<xref:System.Windows.Navigation.NavigationWindow>します。</span><span class="sxs-lookup"><span data-stu-id="3491a-145">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="3491a-146"><xref:System.Windows.Navigation.NavigationWindow>要素の XAML コードで、次のプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="3491a-146">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="3491a-147">プロパティを "`ExpenseIt`" に設定します。 <xref:System.Windows.Window.Title%2A></span><span class="sxs-lookup"><span data-stu-id="3491a-147">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="3491a-148"><xref:System.Windows.FrameworkElement.Height%2A>プロパティを350ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="3491a-148">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="3491a-149"><xref:System.Windows.FrameworkElement.Width%2A>プロパティを500ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="3491a-149">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="3491a-150">XAML は、Visual Basic に対して次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3491a-150">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="3491a-151">では、次のC#ようになります。</span><span class="sxs-lookup"><span data-stu-id="3491a-151">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="3491a-152">*Mainwindow.xaml*または*MainWindow.xaml.cs*を開きます。</span><span class="sxs-lookup"><span data-stu-id="3491a-152">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="3491a-153">このファイルは、 *mainwindow.xaml*で宣言されたイベントを処理するコードを含む分離コードファイルです。</span><span class="sxs-lookup"><span data-stu-id="3491a-153">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="3491a-154">このファイルには、XAML で定義されたウィンドウの部分クラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3491a-154">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="3491a-155">を使用してC#いる場合は`MainWindow` 、から<xref:System.Windows.Navigation.NavigationWindow>派生するようにクラスを変更します。</span><span class="sxs-lookup"><span data-stu-id="3491a-155">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="3491a-156">(Visual Basic では、XAML でウィンドウを変更すると、自動的にこの処理が行われます)。コードC#は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3491a-156">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="3491a-157">アプリケーションへのファイルの追加</span><span class="sxs-lookup"><span data-stu-id="3491a-157">Add files to the application</span></span>

<span data-ttu-id="3491a-158">このセクションでは、アプリケーションに 2 つのページと 1 つのイメージを追加します。</span><span class="sxs-lookup"><span data-stu-id="3491a-158">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="3491a-159">プロジェクトに新しいページを追加し、名前 *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="3491a-159">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="3491a-160">**ソリューション エクスプ ローラー**を右クリックし、 **`ExpenseIt`** プロジェクト ノード**追加** > **ページ**します。</span><span class="sxs-lookup"><span data-stu-id="3491a-160">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="3491a-161">**[新しい項目の追加]** ダイアログでは、 **[ページ (WPF)]** テンプレートは既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="3491a-161">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="3491a-162">名前を入力します **`ExpenseItHome`** 、し、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="3491a-162">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="3491a-163">このページは、アプリケーションの起動時に表示される最初のページです。</span><span class="sxs-lookup"><span data-stu-id="3491a-163">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="3491a-164">このレポートには、の経費明細書を表示するために選択する相手の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3491a-164">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="3491a-165">開いている *`ExpenseItHome.xaml`* します。</span><span class="sxs-lookup"><span data-stu-id="3491a-165">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="3491a-166"><xref:System.Windows.Controls.Page.Title%2A>を"`ExpenseIt - Home`" に設定します。</span><span class="sxs-lookup"><span data-stu-id="3491a-166">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="3491a-167">を350ピクセル`DesignWidth`に、を500ピクセルに設定します。 `DesignHeight`</span><span class="sxs-lookup"><span data-stu-id="3491a-167">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="3491a-168">XAML は、Visual Basic に対して次のように表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3491a-168">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="3491a-169">では、次のC#ようになります。</span><span class="sxs-lookup"><span data-stu-id="3491a-169">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="3491a-170">*MainWindow.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="3491a-170">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="3491a-171">要素にプロパティを<xref:System.Windows.Navigation.NavigationWindow.Source%2A>追加し、それを "`ExpenseItHome.xaml`" に設定します。 <xref:System.Windows.Navigation.NavigationWindow></span><span class="sxs-lookup"><span data-stu-id="3491a-171">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="3491a-172">これにより設定 *`ExpenseItHome.xaml`* アプリケーションの起動時を開く最初のページになります。</span><span class="sxs-lookup"><span data-stu-id="3491a-172">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="3491a-173">Visual Basic の XAML の例:</span><span class="sxs-lookup"><span data-stu-id="3491a-173">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="3491a-174">および C# の場合。</span><span class="sxs-lookup"><span data-stu-id="3491a-174">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="3491a-175">また、 **[プロパティ]** ウィンドウの **[その他]** カテゴリで、 **[ソース]** プロパティを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3491a-175">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![プロパティウィンドウのソースプロパティ](./media/properties-source.png)

1. <span data-ttu-id="3491a-177">別の新しい WPF ページをプロジェクトに追加し、次*のように*名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3491a-177">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="3491a-178">**ソリューション エクスプ ローラー**を右クリックし、 **`ExpenseIt`** プロジェクト ノード**追加** > **ページ**します。</span><span class="sxs-lookup"><span data-stu-id="3491a-178">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="3491a-179">**[新しい項目の追加]** ダイアログで、 **[ページ (WPF)]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="3491a-179">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="3491a-180">[名前の指定] をクリック**し、[** **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3491a-180">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="3491a-181">このページで選択されているユーザーの経費報告書が表示されます、 **`ExpenseItHome`** ページ。</span><span class="sxs-lookup"><span data-stu-id="3491a-181">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="3491a-182">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="3491a-182">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="3491a-183"><xref:System.Windows.Controls.Page.Title%2A>を"`ExpenseIt - View Expense`" に設定します。</span><span class="sxs-lookup"><span data-stu-id="3491a-183">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="3491a-184">を350ピクセル`DesignWidth`に、を500ピクセルに設定します。 `DesignHeight`</span><span class="sxs-lookup"><span data-stu-id="3491a-184">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span> 

    <span data-ttu-id="3491a-185">Visual Basic では、この*xaml*は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3491a-185">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="3491a-186">およびでは、次C#のようになります。</span><span class="sxs-lookup"><span data-stu-id="3491a-186">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="3491a-187">*Expenseithome.xaml*を開き、 *ExpenseItHome.xaml.cs* 、または ExpenseReportPage.xaml.cs *、また*はを開きます。</span><span class="sxs-lookup"><span data-stu-id="3491a-187">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="3491a-188">新しいページファイルを作成すると、Visual Studio によってその*分離コード*ファイルが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="3491a-188">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="3491a-189">これらの分離コード ファイルでは、ユーザー入力に対応するためのロジックを処理します。</span><span class="sxs-lookup"><span data-stu-id="3491a-189">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="3491a-190">コードは、次のようになります **`ExpenseItHome`** :</span><span class="sxs-lookup"><span data-stu-id="3491a-190">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="3491a-191">また、次のような**ページ**があります。</span><span class="sxs-lookup"><span data-stu-id="3491a-191">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="3491a-192">*透かし*という名前のイメージをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="3491a-192">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="3491a-193">独自のイメージを作成したり、サンプルコードからファイルをコピーしたり、[ここで](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png)取得したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3491a-193">You can create your own image, copy the file from the sample code, or get it [here](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png).</span></span>

    1. <span data-ttu-id="3491a-194">プロジェクトノードを右クリックし、[**既存項目**の**追加** > ] を選択するか、 **Shift**+**Alt**+**A**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3491a-194">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="3491a-195">**[既存項目の追加]** ダイアログボックスで、すべての **[ファイル]** または **[イメージファイル]** のいずれかにファイルフィルターを設定し、使用するイメージファイルを参照して **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3491a-195">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="3491a-196">アプリケーションのビルドと実行</span><span class="sxs-lookup"><span data-stu-id="3491a-196">Build and run the application</span></span>

1. <span data-ttu-id="3491a-197">アプリケーションをビルドして実行するには、 **F5**キーを押すか、 **[デバッグ]** メニューの **[デバッグの開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3491a-197">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="3491a-198">次の図は、 <xref:System.Windows.Navigation.NavigationWindow>ボタンを使用したアプリケーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="3491a-198">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![アプリケーションをビルドして実行します。](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="3491a-200">アプリケーションを閉じて、Visual Studio に戻ります。</span><span class="sxs-lookup"><span data-stu-id="3491a-200">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="3491a-201">レイアウトを作成する</span><span class="sxs-lookup"><span data-stu-id="3491a-201">Create the layout</span></span>

<span data-ttu-id="3491a-202">レイアウトは、UI 要素を配置するための順序付けされた方法を提供し、UI のサイズが変更されたときの要素のサイズと位置も管理します。</span><span class="sxs-lookup"><span data-stu-id="3491a-202">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="3491a-203">通常、レイアウトを作成するには、次のいずれかのレイアウト コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="3491a-203">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="3491a-204"><xref:System.Windows.Controls.Canvas>-キャンバス領域に対する相対座標を使用して子要素を明示的に配置できる領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="3491a-204"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="3491a-205"><xref:System.Windows.Controls.DockPanel>-子要素を水平方向または垂直方向に整列できる領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="3491a-205"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="3491a-206"><xref:System.Windows.Controls.Grid>-列と行で構成される柔軟性のあるグリッド領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="3491a-206"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="3491a-207"><xref:System.Windows.Controls.StackPanel>-子要素を水平方向または垂直方向の単一行に整列します。</span><span class="sxs-lookup"><span data-stu-id="3491a-207"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="3491a-208"><xref:System.Windows.Controls.VirtualizingStackPanel>-水平方向または垂直方向の単一行でコンテンツを整列し、仮想化します。</span><span class="sxs-lookup"><span data-stu-id="3491a-208"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="3491a-209"><xref:System.Windows.Controls.WrapPanel>-左から右へ順番に子要素を配置し、格納ボックスの端の次の行にコンテンツを分割します。</span><span class="sxs-lookup"><span data-stu-id="3491a-209"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="3491a-210">後続の順序付けは、Orientation プロパティの値に応じて、上から下または右から左に順番に行われます。</span><span class="sxs-lookup"><span data-stu-id="3491a-210">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="3491a-211">これらの各レイアウトコントロールは、その子要素に対して特定の種類のレイアウトをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3491a-211">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="3491a-212">`ExpenseIt`ページのサイズを変更できます。また、各ページには、水平方向および垂直方向に他の要素と共に配置された要素があります。</span><span class="sxs-lookup"><span data-stu-id="3491a-212">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="3491a-213">この例<xref:System.Windows.Controls.Grid>では、アプリケーションのレイアウト要素としてが使用されています。</span><span class="sxs-lookup"><span data-stu-id="3491a-213">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="3491a-214"><xref:System.Windows.Controls.Panel>要素の詳細については、「[パネルの概要](../controls/panels-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3491a-214">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="3491a-215">レイアウトの詳細については、「 [layout](../advanced/layout.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3491a-215">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="3491a-216">このセクションで作成する単一列テーブル 10 ピクセルの余白を 3 行の列と行の定義を追加することによって、<xref:System.Windows.Controls.Grid>で *`ExpenseItHome.xaml`* します。</span><span class="sxs-lookup"><span data-stu-id="3491a-216">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="3491a-217">*`ExpenseItHome.xaml`* 、設定、<xref:System.Windows.FrameworkElement.Margin%2A>プロパティを<xref:System.Windows.Controls.Grid>「10,0,10,10」は、左、上、右、下の余白に対応する要素。</span><span class="sxs-lookup"><span data-stu-id="3491a-217">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="3491a-218">また、 **[プロパティ]** ウィンドウの **[レイアウト]** カテゴリで、**余白**の値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3491a-218">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![プロパティウィンドウの余白の値](./media/properties-margin.png)

2. <span data-ttu-id="3491a-220">次の XAML をタグの<xref:System.Windows.Controls.Grid>間に追加して、行と列の定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="3491a-220">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="3491a-221">2 <xref:System.Windows.Controls.RowDefinition.Height%2A>つの行のはに<xref:System.Windows.GridLength.Auto%2A>設定されます。つまり、行のサイズは、行のコンテンツに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="3491a-221">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="3491a-222">既定値<xref:System.Windows.Controls.RowDefinition.Height%2A>は<xref:System.Windows.GridUnitType.Star>サイズ変更です。これは、行の高さが使用可能な領域の重み付け比率であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3491a-222">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="3491a-223">たとえば、2つの行のそれぞれ<xref:System.Windows.Controls.RowDefinition.Height%2A>に "\*" が含まれている場合、それぞれの行の高さは使用可能な領域の半分になります。</span><span class="sxs-lookup"><span data-stu-id="3491a-223">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="3491a-224">に<xref:System.Windows.Controls.Grid>は、次の XAML が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3491a-224">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="3491a-225">コントロールの追加</span><span class="sxs-lookup"><span data-stu-id="3491a-225">Add controls</span></span>

<span data-ttu-id="3491a-226">このセクションでは、ホームページの UI を更新して、人の一覧を表示します。ここでは、1人のユーザーを選択して経費報告書を表示します。</span><span class="sxs-lookup"><span data-stu-id="3491a-226">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="3491a-227">コントロールとは、ユーザーがアプリケーションと対話できるようにする UI オブジェクトのことです。</span><span class="sxs-lookup"><span data-stu-id="3491a-227">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="3491a-228">詳しくは、「 [コントロール](../controls/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3491a-228">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="3491a-229">この UI を作成するには、次の要素を追加します *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="3491a-229">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="3491a-230"><xref:System.Windows.Controls.ListBox> (People の一覧の場合)。</span><span class="sxs-lookup"><span data-stu-id="3491a-230">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="3491a-231"><xref:System.Windows.Controls.Label> (リストヘッダーの場合)。</span><span class="sxs-lookup"><span data-stu-id="3491a-231">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="3491a-232"><xref:System.Windows.Controls.Button> (クリックすると、一覧で選択されているユーザーの経費明細書が表示されます)。</span><span class="sxs-lookup"><span data-stu-id="3491a-232">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="3491a-233">各コントロールは、 <xref:System.Windows.Controls.Grid> <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>添付プロパティを設定することによって、の行に配置されます。</span><span class="sxs-lookup"><span data-stu-id="3491a-233">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="3491a-234">添付プロパティの詳細については、「[添付プロパティの概要](../advanced/attached-properties-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3491a-234">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="3491a-235">で *`ExpenseItHome.xaml`* 、タグの<xref:System.Windows.Controls.Grid>間に次の XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="3491a-235">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="3491a-236">コントロールは、 **[ツールボックス]** ウィンドウからデザインウィンドウにドラッグして、 **[プロパティ]** ウィンドウでプロパティを設定することによって作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3491a-236">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="3491a-237">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="3491a-237">Build and run the application.</span></span>

    <span data-ttu-id="3491a-238">次の図は、作成したコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="3491a-238">The following illustration shows the controls you created:</span></span>

![名前の一覧を表示している、このサンプルスクリーンショット](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="3491a-240">イメージとタイトルを追加する</span><span class="sxs-lookup"><span data-stu-id="3491a-240">Add an image and a title</span></span>

<span data-ttu-id="3491a-241">このセクションでは、ホームページの UI をイメージとページタイトルで更新します。</span><span class="sxs-lookup"><span data-stu-id="3491a-241">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="3491a-242">で *`ExpenseItHome.xaml`* 、230ピクセルの固定<xref:System.Windows.Controls.ColumnDefinition.Width%2A>の<xref:System.Windows.Controls.Grid.ColumnDefinitions%2A>を使用して、に別の列を追加します。</span><span class="sxs-lookup"><span data-stu-id="3491a-242">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="3491a-243">に<xref:System.Windows.Controls.Grid.RowDefinitions%2A>次の行を追加します。合計4行になります。</span><span class="sxs-lookup"><span data-stu-id="3491a-243">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="3491a-244">コントロールを2番目の列に移動する<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>には、3つのコントロール (Border、ListBox、および Button) のそれぞれで、プロパティを1に設定します。</span><span class="sxs-lookup"><span data-stu-id="3491a-244">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="3491a-245">各コントロールを1行下に移動し<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>ます。そのためには、3つのコントロール (border、ListBox、および Button) と border 要素のそれぞれの値を1ずつインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="3491a-245">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="3491a-246">3つのコントロールの XAML は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3491a-246">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="3491a-247"><xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType>タグ`<Grid>`とタグ`</Grid>`の間に次の XAML を追加して、プロパティを*ウォーターマークの .png*画像ファイルに設定します。</span><span class="sxs-lookup"><span data-stu-id="3491a-247">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="3491a-248">要素の<xref:System.Windows.Controls.Border>前に、「 <xref:System.Windows.Controls.Label>経費報告書の表示」という内容のを追加します。</span><span class="sxs-lookup"><span data-stu-id="3491a-248">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="3491a-249">このラベルはページのタイトルです。</span><span class="sxs-lookup"><span data-stu-id="3491a-249">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="3491a-250">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="3491a-250">Build and run the application.</span></span>

<span data-ttu-id="3491a-251">次の図は、先ほど追加したものの結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="3491a-251">The following illustration shows the results of what you just added:</span></span>

![新しいイメージの背景とページのタイトルを示す、ページのサンプルスクリーンショット](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="3491a-253">イベントを処理するコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3491a-253">Add code to handle events</span></span>

1. <span data-ttu-id="3491a-254">で *`ExpenseItHome.xaml`* <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 、要素<xref:System.Windows.Controls.Button>にイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3491a-254">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="3491a-255">詳細については、「[方法 :単純なイベントハンドラー](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))を作成します。</span><span class="sxs-lookup"><span data-stu-id="3491a-255">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="3491a-256">開いている *`ExpenseItHome.xaml.vb`* または *`ExpenseItHome.xaml.cs`* します。</span><span class="sxs-lookup"><span data-stu-id="3491a-256">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="3491a-257">次のコードを`ExpenseItHome`クラスに追加して、ボタンクリックイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3491a-257">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="3491a-258">イベントハンドラーによって、[処理された**Sereportpage** ] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="3491a-258">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="3491a-259">[印刷] ページの UI を作成する</span><span class="sxs-lookup"><span data-stu-id="3491a-259">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="3491a-260">*ExpenseReportPage.xaml*で選択されている個人の経費報告書が表示されます、 **`ExpenseItHome`** ページ。</span><span class="sxs-lookup"><span data-stu-id="3491a-260">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="3491a-261">このセクションでは、[の使用]**ページ**の UI を作成します。</span><span class="sxs-lookup"><span data-stu-id="3491a-261">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="3491a-262">また、さまざまな UI 要素に背景色と塗りつぶしの色を追加します。</span><span class="sxs-lookup"><span data-stu-id="3491a-262">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="3491a-263">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="3491a-263">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="3491a-264">タグの<xref:System.Windows.Controls.Grid>間に次の XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="3491a-264">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="3491a-265">この UI はのような *`ExpenseItHome.xaml`* でレポート データが表示される点を除いて、<xref:System.Windows.Controls.DataGrid>します。</span><span class="sxs-lookup"><span data-stu-id="3491a-265">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="3491a-266">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="3491a-266">Build and run the application.</span></span>

4. <span data-ttu-id="3491a-267">**[表示]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="3491a-267">Select the **View** button.</span></span>

    <span data-ttu-id="3491a-268">経費明細書ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3491a-268">The expense report page appears.</span></span> <span data-ttu-id="3491a-269">また、[戻る] ナビゲーションボタンが有効になっていることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="3491a-269">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="3491a-270">次の図は、*ページ*に追加された UI 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="3491a-270">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![このページでは、[ページの作成] で作成した UI を示しています。](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="3491a-272">スタイルコントロール</span><span class="sxs-lookup"><span data-stu-id="3491a-272">Style controls</span></span>

<span data-ttu-id="3491a-273">多くの場合、UI で同じ種類のすべての要素に対して、さまざまな要素の外観が同じになります。</span><span class="sxs-lookup"><span data-stu-id="3491a-273">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="3491a-274">UI では、[スタイル](../controls/styling-and-templating.md)を使用して、複数の要素間で外観を再利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3491a-274">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="3491a-275">スタイルの再利用性により、XAML の作成と管理が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="3491a-275">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="3491a-276">このセクションでは、これまでの手順で定義した要素ごとの属性を、スタイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3491a-276">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="3491a-277">*アプリケーション .xaml* *または app.xaml を*開きます。</span><span class="sxs-lookup"><span data-stu-id="3491a-277">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="3491a-278">タグの<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>間に次の XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="3491a-278">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="3491a-279">この XAML は、次のスタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="3491a-279">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="3491a-280">`headerTextStyle`:ページタイトル<xref:System.Windows.Controls.Label>の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="3491a-280">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="3491a-281">`labelStyle`:コントロールの<xref:System.Windows.Controls.Label>書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="3491a-281">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="3491a-282">`columnHeaderStyle`:の書式を<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>設定する場合は。</span><span class="sxs-lookup"><span data-stu-id="3491a-282">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="3491a-283">`listHeaderStyle`:リストヘッダー <xref:System.Windows.Controls.Border>コントロールの書式を設定する場合は。</span><span class="sxs-lookup"><span data-stu-id="3491a-283">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="3491a-284">`listHeaderTextStyle`:リストヘッダー <xref:System.Windows.Controls.Label>の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="3491a-284">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="3491a-285">`buttonStyle`:を<xref:System.Windows.Controls.Button> に`ExpenseItHome.xaml`設定します。</span><span class="sxs-lookup"><span data-stu-id="3491a-285">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="3491a-286">スタイルは、 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>プロパティ要素のリソースと子であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3491a-286">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="3491a-287">ここでは、スタイルはアプリケーション内のすべての要素に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3491a-287">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="3491a-288">.NET アプリでのリソースの使用例については、「[アプリケーションリソースの使用](../advanced/how-to-use-application-resources.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3491a-288">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="3491a-289">で *`ExpenseItHome.xaml`* は<xref:System.Windows.Controls.Grid> 、要素間のすべてを次の XAML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3491a-289">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="3491a-290">各コントロールの外観を定義する <xref:System.Windows.VerticalAlignment> や <xref:System.Windows.Media.FontFamily> などのプロパティは、これらのスタイルを適用することで、削除されて置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="3491a-290">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="3491a-291">たとえば`headerTextStyle` 、は "経費報告書の表示" <xref:System.Windows.Controls.Label>に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3491a-291">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="3491a-292">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="3491a-292">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="3491a-293"><xref:System.Windows.Controls.Grid>要素間のすべてを次の XAML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3491a-293">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="3491a-294">この XAML は<xref:System.Windows.Controls.Label> 、要素と<xref:System.Windows.Controls.Border>要素にスタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="3491a-294">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="3491a-295">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="3491a-295">Build and run the application.</span></span> <span data-ttu-id="3491a-296">ウィンドウの外観は、以前と同じです。</span><span class="sxs-lookup"><span data-stu-id="3491a-296">The window appearance is the same as previously.</span></span>

    ![前回のセクションと同じ外観の、このサンプルスクリーンショット。](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="3491a-298">アプリケーションを閉じて、Visual Studio に戻ります。</span><span class="sxs-lookup"><span data-stu-id="3491a-298">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="3491a-299">コントロールへのデータのバインド</span><span class="sxs-lookup"><span data-stu-id="3491a-299">Bind data to a control</span></span>

<span data-ttu-id="3491a-300">このセクションでは、さまざまなコントロールにバインドされている XML データを作成します。</span><span class="sxs-lookup"><span data-stu-id="3491a-300">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="3491a-301">で *`ExpenseItHome.xaml`* 、開始<xref:System.Windows.Controls.Grid>要素の後に<xref:System.Windows.Data.XmlDataProvider>次の XAML を追加して、各ユーザーのデータを含むを作成します。</span><span class="sxs-lookup"><span data-stu-id="3491a-301">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="3491a-302">データは<xref:System.Windows.Controls.Grid>リソースとして作成されます。</span><span class="sxs-lookup"><span data-stu-id="3491a-302">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="3491a-303">通常、このデータはファイルとして読み込まれますが、わかりやすくするために、データはインラインで追加されます。</span><span class="sxs-lookup"><span data-stu-id="3491a-303">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="3491a-304">要素内に次`<xref:System.Windows.DataTemplate>`の要素を追加します。この要素は、要素の`<XmlDataProvider>`後<xref:System.Windows.Controls.ListBox>に、のデータを表示する方法を定義します。 `<Grid.Resources>`</span><span class="sxs-lookup"><span data-stu-id="3491a-304">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="3491a-305">データテンプレートの詳細については、「データテンプレートの[概要](../data/data-templating-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3491a-305">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="3491a-306">既存<xref:System.Windows.Controls.ListBox>のを次の XAML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3491a-306">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="3491a-307">この XAML は、 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox>のプロパティをデータソースにバインドし、データテンプレート<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>をとして適用します。</span><span class="sxs-lookup"><span data-stu-id="3491a-307">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="3491a-308">コントロールへのデータの接続</span><span class="sxs-lookup"><span data-stu-id="3491a-308">Connect data to controls</span></span>

<span data-ttu-id="3491a-309">次で選択されている名前を取得するコードを追加します、 **`ExpenseItHome`** ページし、のコンストラクターに渡す**ExpenseReportPage**します。</span><span class="sxs-lookup"><span data-stu-id="3491a-309">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="3491a-310">[調整された**Sereportpage** ] は、渡された項目を使用してそのデータコンテキストを設定します。これは、"*ページ*のバインド先" に定義されているコントロールです。</span><span class="sxs-lookup"><span data-stu-id="3491a-310">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="3491a-311">*ExpenseReportPage.xaml.vb* または *ExpenseReportPage.xaml.cs*を開きます。</span><span class="sxs-lookup"><span data-stu-id="3491a-311">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="3491a-312">オブジェクトを取得するコンストラクターを追加して、選択した個人の経費報告書データを渡せるようにします。</span><span class="sxs-lookup"><span data-stu-id="3491a-312">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="3491a-313">開いている *`ExpenseItHome.xaml.vb`* または *`ExpenseItHome.xaml.cs`* します。</span><span class="sxs-lookup"><span data-stu-id="3491a-313">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="3491a-314">選択し<xref:System.Windows.Controls.Primitives.ButtonBase.Click>たユーザーの経費報告書データを渡す新しいコンストラクターを呼び出すように、イベントハンドラーを変更します。</span><span class="sxs-lookup"><span data-stu-id="3491a-314">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="3491a-315">データテンプレートを使用したデータのスタイル</span><span class="sxs-lookup"><span data-stu-id="3491a-315">Style data with data templates</span></span>

<span data-ttu-id="3491a-316">このセクションでは、データテンプレートを使用して、データバインドリストの各項目の UI を更新します。</span><span class="sxs-lookup"><span data-stu-id="3491a-316">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="3491a-317">*ExpenseReportPage.xaml*を開きます。</span><span class="sxs-lookup"><span data-stu-id="3491a-317">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="3491a-318">"Name" 要素と "Department" <xref:System.Windows.Controls.Label>要素の内容を適切なデータソースプロパティにバインドします。</span><span class="sxs-lookup"><span data-stu-id="3491a-318">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="3491a-319">データバインディングの詳細については、「[データバインディングの概要](../data/data-binding-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3491a-319">For more information about data binding, see [Data binding overview](../data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="3491a-320">開い<xref:System.Windows.Controls.Grid>ている要素の後に、経費報告書データの表示方法を定義する次のデータテンプレートを追加します。</span><span class="sxs-lookup"><span data-stu-id="3491a-320">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="3491a-321">要素のをに<xref:System.Windows.Controls.DataGridTemplateColumn> <xref:System.Windows.Controls.DataGrid>置き換え、テンプレートを適用します。 <xref:System.Windows.Controls.DataGridTextColumn></span><span class="sxs-lookup"><span data-stu-id="3491a-321">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="3491a-322">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="3491a-322">Build and run the application.</span></span>

6. <span data-ttu-id="3491a-323">ユーザーを選択し、 **[表示]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="3491a-323">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="3491a-324">次の図は、適用され`ExpenseIt`たコントロール、レイアウト、スタイル、データバインディング、およびデータテンプレートを使用したアプリケーションの両方のページを示しています。</span><span class="sxs-lookup"><span data-stu-id="3491a-324">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![名前の一覧と経費報告書を表示するアプリの両方のページ。](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="3491a-326">このサンプルでは、WPF の特定の機能について説明します。セキュリティ、ローカライズ、アクセシビリティなどのベストプラクティスについては説明しません。</span><span class="sxs-lookup"><span data-stu-id="3491a-326">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="3491a-327">WPF と .NET アプリ開発のベストプラクティスの包括的な説明については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3491a-327">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="3491a-328">ユーザー補助</span><span class="sxs-lookup"><span data-stu-id="3491a-328">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="3491a-329">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="3491a-329">Security</span></span>](../security-wpf.md)
>
> - [<span data-ttu-id="3491a-330">WPF のグローバリゼーションおよびローカリゼーションの概要</span><span class="sxs-lookup"><span data-stu-id="3491a-330">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="3491a-331">WPF のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="3491a-331">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="3491a-332">次の手順</span><span class="sxs-lookup"><span data-stu-id="3491a-332">Next steps</span></span>

<span data-ttu-id="3491a-333">このチュートリアルでは、Windows Presentation Foundation (WPF) を使用して UI を作成するためのいくつかの手法について学習しました。</span><span class="sxs-lookup"><span data-stu-id="3491a-333">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="3491a-334">これで、データバインドされた .NET アプリの構成要素についての基本的な理解ができました。</span><span class="sxs-lookup"><span data-stu-id="3491a-334">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="3491a-335">WPF のアーキテクチャおよびプログラミング モデルの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3491a-335">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="3491a-336">WPF のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="3491a-336">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="3491a-337">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="3491a-337">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="3491a-338">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="3491a-338">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="3491a-339">レイアウト</span><span class="sxs-lookup"><span data-stu-id="3491a-339">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="3491a-340">アプリケーションの作成の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3491a-340">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="3491a-341">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="3491a-341">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="3491a-342">コントロール</span><span class="sxs-lookup"><span data-stu-id="3491a-342">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="3491a-343">データバインディングの概要</span><span class="sxs-lookup"><span data-stu-id="3491a-343">Data binding overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="3491a-344">グラフィックスとマルチメディア</span><span class="sxs-lookup"><span data-stu-id="3491a-344">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="3491a-345">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="3491a-345">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="3491a-346">関連項目</span><span class="sxs-lookup"><span data-stu-id="3491a-346">See also</span></span>

- [<span data-ttu-id="3491a-347">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="3491a-347">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="3491a-348">データテンプレートの概要</span><span class="sxs-lookup"><span data-stu-id="3491a-348">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="3491a-349">WPF アプリケーションのビルド</span><span class="sxs-lookup"><span data-stu-id="3491a-349">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="3491a-350">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="3491a-350">Styles and templates</span></span>](../controls/styles-and-templates.md)
