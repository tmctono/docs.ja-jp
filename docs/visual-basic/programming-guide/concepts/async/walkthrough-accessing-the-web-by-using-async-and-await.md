---
title: 'チュートリアル: Async と Await を使用した Web へのアクセス (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
ms.openlocfilehash: feaa1e298cda852492e020a5fa81845fb887f102
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197028"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a><span data-ttu-id="63087-102">チュートリアル: Async と Await を使用した Web へのアクセス (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63087-102">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>

<span data-ttu-id="63087-103">async/await 機能を使用することで、非同期プログラムをより簡単かつ直感的に記述できます。</span><span class="sxs-lookup"><span data-stu-id="63087-103">You can write asynchronous programs more easily and intuitively by using async/await features.</span></span> <span data-ttu-id="63087-104">同期コードに似た非同期コードを記述し、通常の非同期コードが必要とする難しいコールバック関数や継続の処理をコンパイラに任せます。</span><span class="sxs-lookup"><span data-stu-id="63087-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>

<span data-ttu-id="63087-105">非同期機能の詳細については、「 [async および Await を使用した非同期プログラミング (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63087-105">For more information about the Async feature, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="63087-106">このチュートリアルは、Web サイトの一覧でのバイト数の合計を計算する同期 Windows Presentation Foundation (WPF) アプリケーションから開始します。</span><span class="sxs-lookup"><span data-stu-id="63087-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="63087-107">その後、新しい機能を使用して、アプリケーションを非同期ソリューションに変換します。</span><span class="sxs-lookup"><span data-stu-id="63087-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>

<span data-ttu-id="63087-108">自分でアプリケーションを作成しない場合は、[開発者コード サンプル](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)のページから、"Async Sample: Accessing the Web Walkthrough (C# and Visual Basic) (非同期サンプル: Web へのアクセスのチュートリアル (C# および Visual Basic))" をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="63087-108">If you don't want to build the applications yourself, you can download "Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)" from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>

<span data-ttu-id="63087-109">このチュートリアルでは、次のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="63087-109">In this walkthrough, you complete the following tasks:</span></span>

> [!div class="checklist"]
>
> - [<span data-ttu-id="63087-110">WPF アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="63087-110">Create a WPF application</span></span>](#create-a-wpf-application)
> - [<span data-ttu-id="63087-111">単純な WPF Mainwindow.xaml を設計する</span><span class="sxs-lookup"><span data-stu-id="63087-111">Design a simple WPF MainWindow</span></span>](#design-a-simple-wpf-mainwindow)
> - [<span data-ttu-id="63087-112">参照を追加する</span><span class="sxs-lookup"><span data-stu-id="63087-112">Add a reference</span></span>](#add-a-reference)
> - [<span data-ttu-id="63087-113">必要な Imports ステートメントを追加する</span><span class="sxs-lookup"><span data-stu-id="63087-113">Add necessary Imports statements</span></span>](#add-necessary-imports-statements)
> - [<span data-ttu-id="63087-114">同期アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="63087-114">Create a synchronous application</span></span>](#create-a-synchronous-application)
> - [<span data-ttu-id="63087-115">同期ソリューションをテストする</span><span class="sxs-lookup"><span data-stu-id="63087-115">Test the synchronous solution</span></span>](#test-the-synchronous-solution)
> - [<span data-ttu-id="63087-116">GetURLContents を非同期メソッドに変換する</span><span class="sxs-lookup"><span data-stu-id="63087-116">Convert GetURLContents to an asynchronous method</span></span>](#convert-geturlcontents-to-an-asynchronous-method)
> - [<span data-ttu-id="63087-117">SumPageSizes を非同期メソッドに変換する</span><span class="sxs-lookup"><span data-stu-id="63087-117">Convert SumPageSizes to an asynchronous method</span></span>](#convert-sumpagesizes-to-an-asynchronous-method)
> - [<span data-ttu-id="63087-118">StartButton_Click を非同期メソッドに変換する</span><span class="sxs-lookup"><span data-stu-id="63087-118">Convert startButton_Click to an asynchronous method</span></span>](#convert-startbutton_click-to-an-asynchronous-method)
> - [<span data-ttu-id="63087-119">非同期ソリューションをテストする</span><span class="sxs-lookup"><span data-stu-id="63087-119">Test the asynchronous solution</span></span>](#test-the-asynchronous-solution)
> - [<span data-ttu-id="63087-120">Geturlの Async メソッドを .NET Framework メソッドに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="63087-120">Replace the GetURLContentsAsync method with a .NET Framework method</span></span>](#replace-the-geturlcontentsasync-method-with-a-net-framework-method)

<span data-ttu-id="63087-121">完全な非同期の例については、「[例](#example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63087-121">See the [Example](#example) section for the complete asynchronous example.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="63087-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="63087-122">Prerequisites</span></span>

<span data-ttu-id="63087-123">お使いのコンピューターに、Visual Studio 2012 以降がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="63087-123">Visual Studio 2012 or later must be installed on your computer.</span></span> <span data-ttu-id="63087-124">詳細については、Visual Studio の[ダウンロード](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63087-124">For more information, see the Visual Studio [Downloads](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) page.</span></span>

## <a name="create-a-wpf-application"></a><span data-ttu-id="63087-125">WPF アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="63087-125">Create a WPF application</span></span>

1. <span data-ttu-id="63087-126">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="63087-126">Start Visual Studio.</span></span>

2. <span data-ttu-id="63087-127">メニュー バーで **[ファイル]** 、 **[新規作成]** 、 **[プロジェクト]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="63087-127">On the menu bar, choose **File**, **New**, **Project**.</span></span>

    <span data-ttu-id="63087-128">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63087-128">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="63087-129">**[インストールされたテンプレート]** ペインで、Visual Basic を選択し、プロジェクトの種類の一覧から  **[WPF アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63087-129">In the **Installed Templates** pane, choose Visual Basic, and then choose **WPF Application** from the list of project types.</span></span>

4. <span data-ttu-id="63087-130">**[名前]** ボックスに「`AsyncExampleWPF`」と入力して、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63087-130">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>

    <span data-ttu-id="63087-131">**ソリューション エクスプローラー**に新しいプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63087-131">The new project appears in **Solution Explorer**.</span></span>

## <a name="design-a-simple-wpf-mainwindow"></a><span data-ttu-id="63087-132">単純な WPF MainWindow をデザインする</span><span class="sxs-lookup"><span data-stu-id="63087-132">Design a simple WPF MainWindow</span></span>

1. <span data-ttu-id="63087-133">Visual Studio コード エディターで、 **[MainWindow.xaml]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="63087-133">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

2. <span data-ttu-id="63087-134">**[ツールボックス]** ウィンドウが表示されていない場合は、 **[表示]** メニューを開き、 **[ツールボックス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63087-134">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>

3. <span data-ttu-id="63087-135">**[Button]** コントロールと **[TextBox]** コントロールを **[MainWindow]** ウィンドウに追加します。</span><span class="sxs-lookup"><span data-stu-id="63087-135">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>

4. <span data-ttu-id="63087-136">**[TextBox]** コントロールを強調表示し、 **[プロパティ]** ウィンドウで次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="63087-136">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="63087-137">**[Name]** プロパティを `resultsTextBox` に設定します。</span><span class="sxs-lookup"><span data-stu-id="63087-137">Set the **Name** property to `resultsTextBox`.</span></span>

    - <span data-ttu-id="63087-138">**[Height]** プロパティを 250 に設定します。</span><span class="sxs-lookup"><span data-stu-id="63087-138">Set the **Height** property to 250.</span></span>

    - <span data-ttu-id="63087-139">**[Width]** プロパティを 500 に設定します。</span><span class="sxs-lookup"><span data-stu-id="63087-139">Set the **Width** property to 500.</span></span>

    - <span data-ttu-id="63087-140">**[テキスト]** タブで、Lucida Console や Global Monospace などの等幅フォントを指定します。</span><span class="sxs-lookup"><span data-stu-id="63087-140">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>

5. <span data-ttu-id="63087-141">**[Button]** コントロールを強調表示し、 **[プロパティ]** ウィンドウで次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="63087-141">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="63087-142">**[Name]** プロパティを `startButton` に設定します。</span><span class="sxs-lookup"><span data-stu-id="63087-142">Set the **Name** property to `startButton`.</span></span>

    - <span data-ttu-id="63087-143">**[Content]** プロパティの値を **[Button]** から **[Start]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="63087-143">Change the value of the **Content** property from **Button** to **Start**.</span></span>

6. <span data-ttu-id="63087-144">テキスト ボックスとボタンの位置を調整し、両方が **[MainWindow]** ウィンドウ内に表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="63087-144">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>

    <span data-ttu-id="63087-145">WPF XAML デザイナーについて詳しくは、「[XAML デザイナーを使用した UI の作成](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63087-145">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>

## <a name="add-a-reference"></a><span data-ttu-id="63087-146">参照を追加する</span><span class="sxs-lookup"><span data-stu-id="63087-146">Add a reference</span></span>

1. <span data-ttu-id="63087-147">**ソリューション エクスプローラー**で、プロジェクトの名前を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="63087-147">In **Solution Explorer**, highlight your project's name.</span></span>

2. <span data-ttu-id="63087-148">メニュー バーで、 **[プロジェクト]** 、 **[参照の追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="63087-148">On the menu bar, choose **Project**, **Add Reference**.</span></span>

    <span data-ttu-id="63087-149">**[参照マネージャー]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63087-149">The **Reference Manager** dialog box appears.</span></span>

3. <span data-ttu-id="63087-150">ダイアログ ボックスの上部で、プロジェクトのターゲットが .NET Framework 4.5 以上であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63087-150">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>

4. <span data-ttu-id="63087-151">**[アセンブリ]** で、 **[フレームワーク]** を選択します (選択されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="63087-151">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>

5. <span data-ttu-id="63087-152">名前の一覧で、 **[System.Net.Http]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="63087-152">In the list of names, select the **System.Net.Http** check box.</span></span>

6. <span data-ttu-id="63087-153">**[OK]** をクリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="63087-153">Choose the **OK** button to close the dialog box.</span></span>

## <a name="add-necessary-imports-statements"></a><span data-ttu-id="63087-154">必要な Imports ステートメントを追加する</span><span class="sxs-lookup"><span data-stu-id="63087-154">Add necessary Imports statements</span></span>

1. <span data-ttu-id="63087-155">**ソリューションエクスプローラー**で、mainwindow.xaml のショートカットメニューを開き、 **[コードの表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63087-155">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>

2. <span data-ttu-id="63087-156">次の `Imports` ステートメントをコードファイルの先頭に追加します (まだ存在していない場合)。</span><span class="sxs-lookup"><span data-stu-id="63087-156">Add the following `Imports` statements at the top of the code file if they’re not already present.</span></span>

    ```vb
    Imports System.Net.Http
    Imports System.Net
    Imports System.IO
    ```

## <a name="create-a-synchronous-application"></a><span data-ttu-id="63087-157">同期アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="63087-157">Create a synchronous application</span></span>

1. <span data-ttu-id="63087-158">デザインウィンドウの Mainwindow.xaml で、 **[Start]** ボタンをダブルクリックして、mainwindow.xaml に `startButton_Click` イベントハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="63087-158">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>

2. <span data-ttu-id="63087-159">Mainwindow.xaml で、次のコードを `startButton_Click`の本文にコピーします。</span><span class="sxs-lookup"><span data-stu-id="63087-159">In MainWindow.xaml.vb, copy the following code into the body of `startButton_Click`:</span></span>

    ```vb
    resultsTextBox.Clear()
    SumPageSizes()
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."
    ```

    <span data-ttu-id="63087-160">このコードは、`SumPageSizes` アプリケーションを実行するメソッドを呼び出し、`startButton_Click` に制御が戻るとメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="63087-160">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>

3. <span data-ttu-id="63087-161">同期ソリューションのコードには、次の 4 つのメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="63087-161">The code for the synchronous solution contains the following four methods:</span></span>

    - <span data-ttu-id="63087-162">`SumPageSizes` は、`SetUpURLList` から Web ページ URL のリストを取得し、`GetURLContents` と `DisplayResults` を呼び出して各 URL を処理します。</span><span class="sxs-lookup"><span data-stu-id="63087-162">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>

    - <span data-ttu-id="63087-163">`SetUpURLList` は、Web アドレスのリストを作成して返します。</span><span class="sxs-lookup"><span data-stu-id="63087-163">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>

    - <span data-ttu-id="63087-164">`GetURLContents` は、各 Web サイトのコンテンツをダウンロードし、バイト配列としてそのコンテンツを返します。</span><span class="sxs-lookup"><span data-stu-id="63087-164">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>

    - <span data-ttu-id="63087-165">`DisplayResults` は、各 URL のバイト配列内のバイト数を表示します。</span><span class="sxs-lookup"><span data-stu-id="63087-165">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>

    <span data-ttu-id="63087-166">次の4つのメソッドをコピーし、Mainwindow.xaml の `startButton_Click` イベントハンドラーの下に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="63087-166">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.vb:</span></span>

    ```vb
    Private Sub SumPageSizes()

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            ' GetURLContents returns the contents of url as a byte array.
            Dim urlContents As Byte() = GetURLContents(url)

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "Total bytes returned:  {0}" & vbCrLf, total)
    End Sub

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

    Private Function GetURLContents(url As String) As Byte()

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        ' Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.
        Using response As WebResponse = webReq.GetResponse()
            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                responseStream.CopyTo(content)
            End Using
        End Using

        ' Return the result as a byte array.
        Return content.ToArray()
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
    ```

## <a name="test-the-synchronous-solution"></a><span data-ttu-id="63087-167">同期ソリューションをテストする</span><span class="sxs-lookup"><span data-stu-id="63087-167">Test the synchronous solution</span></span>

1. <span data-ttu-id="63087-168">F5 キーを押してプログラムを実行し、 **[Start]** を複数回クリックします。</span><span class="sxs-lookup"><span data-stu-id="63087-168">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

    <span data-ttu-id="63087-169">次の一覧のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="63087-169">Output that resembles the following list should appear:</span></span>

    ```console
    msdn.microsoft.com/library/windows/apps/br211380.aspx        383832
    msdn.microsoft.com                                            33964
    msdn.microsoft.com/library/hh290136.aspx               225793
    msdn.microsoft.com/library/ee256749.aspx               143577
    msdn.microsoft.com/library/hh290138.aspx               237372
    msdn.microsoft.com/library/hh290140.aspx               128279
    msdn.microsoft.com/library/dd470362.aspx               157649
    msdn.microsoft.com/library/aa578028.aspx               204457
    msdn.microsoft.com/library/ms404677.aspx               176405
    msdn.microsoft.com/library/ff730837.aspx               143474

    Total bytes returned:  1834802

    Control returned to startButton_Click.
    ```

    <span data-ttu-id="63087-170">カウントの表示には数秒かかる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="63087-170">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="63087-171">その間、要求されたリソースのダウンロードが完了するまで UI スレッドがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="63087-171">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="63087-172">このため、 **[Start]** ボタンのクリック後は、表示ウィンドウの移動、最大化、最小化のほか、閉じることさえできなくなります。</span><span class="sxs-lookup"><span data-stu-id="63087-172">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="63087-173">バイト カウントの表示が開始するまでは、これらの操作を実行しても失敗します。</span><span class="sxs-lookup"><span data-stu-id="63087-173">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="63087-174">Web サイトが応答していない場合、どのサイトに問題があるのかを示す情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="63087-174">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="63087-175">待つのをやめて、プログラムを閉じることさえ難しい状態になります。</span><span class="sxs-lookup"><span data-stu-id="63087-175">It is difficult even to stop waiting and close the program.</span></span>

## <a name="convert-geturlcontents-to-an-asynchronous-method"></a><span data-ttu-id="63087-176">GetURLContents を非同期メソッドに変換する</span><span class="sxs-lookup"><span data-stu-id="63087-176">Convert GetURLContents to an asynchronous method</span></span>

1. <span data-ttu-id="63087-177">同期ソリューションを非同期ソリューションに変換する場合、開始するのが最適な場所は `GetURLContents` です。これは、<xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> メソッドと <xref:System.IO.Stream.CopyTo%2A?displayProperty=nameWithType> メソッドの呼び出しがアプリケーションによって web にアクセスするためです。</span><span class="sxs-lookup"><span data-stu-id="63087-177">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> method and to the <xref:System.IO.Stream.CopyTo%2A?displayProperty=nameWithType> method are where the application accesses the web.</span></span> <span data-ttu-id="63087-178">.NET Framework には両方のメソッドの非同期バージョンが用意されているため、変換は簡単です。</span><span class="sxs-lookup"><span data-stu-id="63087-178">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>

    <span data-ttu-id="63087-179">`GetURLContents` で使用されているメソッドの詳細については、「<xref:System.Net.WebRequest>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63087-179">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>

    > [!NOTE]
    > <span data-ttu-id="63087-180">このチュートリアルの手順に従っていると、いくつかのコンパイラ エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63087-180">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="63087-181">これらのエラーは無視することで、チュートリアルを続行できます。</span><span class="sxs-lookup"><span data-stu-id="63087-181">You can ignore them and continue with the walkthrough.</span></span>

    <span data-ttu-id="63087-182">`GetURLContents` の 3 行目で呼び出されるメソッドを、`GetResponse` から、非同期でタスク ベースの <xref:System.Net.WebRequest.GetResponseAsync%2A> メソッドに変更します。</span><span class="sxs-lookup"><span data-stu-id="63087-182">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>

    ```vb
    Using response As WebResponse = webReq.GetResponseAsync()
    ```

2. <span data-ttu-id="63087-183">`GetResponseAsync` は、<xref:System.Threading.Tasks.Task%601> を返します。</span><span class="sxs-lookup"><span data-stu-id="63087-183">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="63087-184">この場合、*タスク戻り変数*の `TResult` の型は <xref:System.Net.WebResponse> です。</span><span class="sxs-lookup"><span data-stu-id="63087-184">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="63087-185">このタスクは、要求されたデータのダウンロードが完了し、タスクが最後まで実行された後に、実際の `WebResponse` オブジェクトを生成するという約束です。</span><span class="sxs-lookup"><span data-stu-id="63087-185">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>

    <span data-ttu-id="63087-186">タスクから `WebResponse` 値を取得するには、次のコードに示すように、`GetResponseAsync`への呼び出しに[Await](../../../../visual-basic/language-reference/operators/await-operator.md)演算子を適用します。</span><span class="sxs-lookup"><span data-stu-id="63087-186">To retrieve the `WebResponse` value from the task, apply an [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>

    ```vb
    Using response As WebResponse = Await webReq.GetResponseAsync()
    ```

    <span data-ttu-id="63087-187">`Await` 演算子は、現在のメソッド、`GetURLContents` の実行を、待機しているタスクが完了するまで中断します。</span><span class="sxs-lookup"><span data-stu-id="63087-187">The `Await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="63087-188">その間、現在のメソッドの呼び出し元に制御が戻されます。</span><span class="sxs-lookup"><span data-stu-id="63087-188">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="63087-189">この例では、現在のメソッドが `GetURLContents` で、呼び出し元が `SumPageSizes` です。</span><span class="sxs-lookup"><span data-stu-id="63087-189">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="63087-190">タスクが完了すると、約束されていた `WebResponse` オブジェクトが完了したタスクの値として生成され、変数 `response` に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="63087-190">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>

    <span data-ttu-id="63087-191">上記のステートメントは、動作を明確にするため、次の 2 つのステートメントに分割できます。</span><span class="sxs-lookup"><span data-stu-id="63087-191">The previous statement can be separated into the following two statements to clarify what happens.</span></span>

    ```vb
    Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
    Using response As WebResponse = Await responseTask
    ```

    <span data-ttu-id="63087-192">`webReq.GetResponseAsync` への呼び出しによって、`Task(Of WebResponse)` または `Task<WebResponse>` が返されます。</span><span class="sxs-lookup"><span data-stu-id="63087-192">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="63087-193">次に、`WebResponse` 値を取得するために、タスクに `Await` 演算子が適用されます。</span><span class="sxs-lookup"><span data-stu-id="63087-193">Then an `Await` operator is applied to the task to retrieve the `WebResponse` value.</span></span>

    <span data-ttu-id="63087-194">非同期メソッドにタスクの完了に依存しない処理がある場合、メソッドはこれら 2 つのステートメントの間、つまり非同期メソッドへの呼び出しから、await 演算子の適用までの間にその処理を続行することができます。</span><span class="sxs-lookup"><span data-stu-id="63087-194">If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the await operator is applied.</span></span> <span data-ttu-id="63087-195">例については、「[方法: async と Await を使用して複数の Web 要求を並列実行する方法 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) 」および「[方法: task.whenall (Visual Basic) を使用して非同期のチュートリアルを拡張する](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63087-195">For examples, see [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>

3. <span data-ttu-id="63087-196">前の手順で `Await` 演算子を追加したため、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="63087-196">Because you added the `Await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="63087-197">演算子は、 [Async](../../../../visual-basic/language-reference/modifiers/async.md)修飾子でマークされているメソッドでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="63087-197">The operator can be used only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="63087-198">`CopyTo` への呼び出しを `CopyToAsync` への呼び出しに置き換える変換手順を繰り返す間は、エラーを無視してください。</span><span class="sxs-lookup"><span data-stu-id="63087-198">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>

    - <span data-ttu-id="63087-199">呼び出されるメソッドの名前を <xref:System.IO.Stream.CopyToAsync%2A> に変更します。</span><span class="sxs-lookup"><span data-stu-id="63087-199">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>

    - <span data-ttu-id="63087-200">`CopyTo` または `CopyToAsync` メソッドは、その引数 `content` にバイトをコピーし、意味のある値は返しません。</span><span class="sxs-lookup"><span data-stu-id="63087-200">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="63087-201">同期バージョンでは、`CopyTo` への呼び出しは値を返さない単純なステートメントです。</span><span class="sxs-lookup"><span data-stu-id="63087-201">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="63087-202">非同期バージョンでは、`CopyToAsync` は <xref:System.Threading.Tasks.Task> を返します。</span><span class="sxs-lookup"><span data-stu-id="63087-202">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="63087-203">タスクは "Task(void)" のように機能し、メソッドを待機できるようにします。</span><span class="sxs-lookup"><span data-stu-id="63087-203">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="63087-204">次のコードに示すように、`Await` または `await` を、`CopyToAsync` への呼び出しに適用します。</span><span class="sxs-lookup"><span data-stu-id="63087-204">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>

        ```vb
        Await responseStream.CopyToAsync(content)
        ```

         <span data-ttu-id="63087-205">上記のステートメントでは、次の 2 行のコードを省略しています。</span><span class="sxs-lookup"><span data-stu-id="63087-205">The previous statement abbreviates the following two lines of code.</span></span>

        ```vb
        ' CopyToAsync returns a Task, not a Task<T>.
        Dim copyTask As Task = responseStream.CopyToAsync(content)

        ' When copyTask is completed, content contains a copy of
        ' responseStream.
        Await copyTask
        ```

4. <span data-ttu-id="63087-206">`GetURLContents` 内で必要な作業として残っているのは、メソッド シグネチャの調整のみです。</span><span class="sxs-lookup"><span data-stu-id="63087-206">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="63087-207">`Await` 演算子は、 [Async](../../../../visual-basic/language-reference/modifiers/async.md)修飾子でマークされているメソッドでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="63087-207">You can use the `Await` operator only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="63087-208">次のコードに示すように、修飾子を追加し、メソッドを*非同期メソッド*としてマークします。</span><span class="sxs-lookup"><span data-stu-id="63087-208">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>

    ```vb
    Private Async Function GetURLContents(url As String) As Byte()
    ```

5. <span data-ttu-id="63087-209">非同期メソッドの戻り値の型には、<xref:System.Threading.Tasks.Task>、<xref:System.Threading.Tasks.Task%601>のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="63087-209">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="63087-210">Visual Basic でのメソッドは、`Task` または `Task(Of T)` を返す `Function` にするか、`Sub` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63087-210">In Visual Basic, the method must be a `Function` that returns a `Task` or a `Task(Of T)`, or the method must be a `Sub`.</span></span> <span data-ttu-id="63087-211">通常、`Sub` メソッドは、`Sub` が必要な非同期イベントハンドラーでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="63087-211">Typically, a `Sub` method  is used only in an async event handler, where `Sub` is required.</span></span> <span data-ttu-id="63087-212">`Task` また、完了したメソッドに T 型の値を返す[Return](../../../../visual-basic/language-reference/statements/return-statement.md)ステートメントがあり、完成したメソッドが意味のある値を返さない場合は、`Task(T)` を使用します。</span><span class="sxs-lookup"><span data-stu-id="63087-212">In other cases, you use `Task(T)` if the completed method has a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span>

    <span data-ttu-id="63087-213">詳細については、「[非同期の戻り値の型 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63087-213">For more information, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

    <span data-ttu-id="63087-214">メソッド `GetURLContents` には return ステートメントがあり、このステートメントはバイト配列を返します。</span><span class="sxs-lookup"><span data-stu-id="63087-214">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="63087-215">そのため、非同期バージョンの戻り値の型は Task(T) であり、T はバイト配列です。</span><span class="sxs-lookup"><span data-stu-id="63087-215">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="63087-216">メソッド シグネチャに、次の変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="63087-216">Make the following changes in the method signature:</span></span>

    - <span data-ttu-id="63087-217">戻り値の型を `Task(Of Byte())` に変更します。</span><span class="sxs-lookup"><span data-stu-id="63087-217">Change the return type to `Task(Of Byte())`.</span></span>

    - <span data-ttu-id="63087-218">規則により、非同期メソッドは "Async" で終わる名前を持つことになっているため、メソッドの名前を `GetURLContentsAsync` に変更します。</span><span class="sxs-lookup"><span data-stu-id="63087-218">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>

    <span data-ttu-id="63087-219">これらの変更を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="63087-219">The following code shows these changes.</span></span>

    ```vb
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())
    ```

    <span data-ttu-id="63087-220">このいくつかの変更によって、`GetURLContents` の非同期メソッドへの変換が完了しました。</span><span class="sxs-lookup"><span data-stu-id="63087-220">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a><span data-ttu-id="63087-221">SumPageSizes を非同期メソッドに変換する</span><span class="sxs-lookup"><span data-stu-id="63087-221">Convert SumPageSizes to an asynchronous method</span></span>

1. <span data-ttu-id="63087-222">`SumPageSizes` に対して、前述した手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="63087-222">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="63087-223">まずは、`GetURLContents` への呼び出しを非同期呼び出しに変更します。</span><span class="sxs-lookup"><span data-stu-id="63087-223">First, change the call to `GetURLContents` to an asynchronous call.</span></span>

    - <span data-ttu-id="63087-224">呼び出されるメソッドの名前を `GetURLContents` から `GetURLContentsAsync` に変更します (まだ変更していない場合)。</span><span class="sxs-lookup"><span data-stu-id="63087-224">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>

    - <span data-ttu-id="63087-225">バイト配列値を取得するために、`Await` を、`GetURLContentsAsync` が返すタスクに適用します。</span><span class="sxs-lookup"><span data-stu-id="63087-225">Apply `Await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>

    <span data-ttu-id="63087-226">これらの変更を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="63087-226">The following code shows these changes.</span></span>

    ```vb
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)
    ```

    <span data-ttu-id="63087-227">上記の割り当てでは、次の 2 行のコードを省略しています。</span><span class="sxs-lookup"><span data-stu-id="63087-227">The previous assignment abbreviates the following two lines of code.</span></span>

    ```vb
    ' GetURLContentsAsync returns a task. At completion, the task
    ' produces a byte array.
    Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
    Dim urlContents As Byte() = Await getContentsTask
    ```

2. <span data-ttu-id="63087-228">メソッドのシグネチャに、次の変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="63087-228">Make the following changes in the method's signature:</span></span>

    - <span data-ttu-id="63087-229">メソッドを `Async` 修飾子でマークします。</span><span class="sxs-lookup"><span data-stu-id="63087-229">Mark the method with the `Async` modifier.</span></span>

    - <span data-ttu-id="63087-230">メソッド名に "Async" を追加します。</span><span class="sxs-lookup"><span data-stu-id="63087-230">Add "Async" to the method name.</span></span>

    - <span data-ttu-id="63087-231">現時点では、タスクの戻り変数 T がありません。これは `SumPageSizesAsync` が T の値を返さないためです (このメソッドには `Return` ステートメントがありません)。ただし、メソッドは、待機可能になる `Task` を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="63087-231">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `Return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="63087-232">そのため、メソッドの種類を `Sub` から `Function`に変更します。</span><span class="sxs-lookup"><span data-stu-id="63087-232">Therefore, change the method type from `Sub` to `Function`.</span></span> <span data-ttu-id="63087-233">関数の戻り値の型は、`Task` です。</span><span class="sxs-lookup"><span data-stu-id="63087-233">The return type of the function is `Task`.</span></span>

    <span data-ttu-id="63087-234">これらの変更を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="63087-234">The following code shows these changes.</span></span>

    ```vb
    Private Async Function SumPageSizesAsync() As Task
    ```

    <span data-ttu-id="63087-235">`SumPageSizes` から `SumPageSizesAsync` への変換が完了しました。</span><span class="sxs-lookup"><span data-stu-id="63087-235">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>

## <a name="convert-startbutton_click-to-an-asynchronous-method"></a><span data-ttu-id="63087-236">startButton_Click を非同期メソッドに変換する</span><span class="sxs-lookup"><span data-stu-id="63087-236">Convert startButton_Click to an asynchronous method</span></span>

1. <span data-ttu-id="63087-237">イベント ハンドラーで、呼び出されるメソッドの名前を `SumPageSizes` から `SumPageSizesAsync` に変更します (まだ変更していない場合)。</span><span class="sxs-lookup"><span data-stu-id="63087-237">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>

2. <span data-ttu-id="63087-238">`SumPageSizesAsync` は非同期メソッドであるため、結果を待機するイベント ハンドラーのコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="63087-238">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>

    <span data-ttu-id="63087-239">`SumPageSizesAsync` への呼び出しは、`GetURLContentsAsync` の `CopyToAsync` への呼び出しに似ています。</span><span class="sxs-lookup"><span data-stu-id="63087-239">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="63087-240">この呼び出しによって、`Task(T)` ではなく `Task` が返されます。</span><span class="sxs-lookup"><span data-stu-id="63087-240">The call returns a `Task`, not a `Task(T)`.</span></span>

    <span data-ttu-id="63087-241">前述した手順と同様に、1 つまたは 2 つのステートメントを使用して、呼び出しを変換できます。</span><span class="sxs-lookup"><span data-stu-id="63087-241">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="63087-242">これらの変更を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="63087-242">The following code shows these changes.</span></span>

    ```vb
    ' One-step async call.
    Await SumPageSizesAsync()

    ' Two-step async call.
    Dim sumTask As Task = SumPageSizesAsync()
    Await sumTask
    ```

3. <span data-ttu-id="63087-243">誤って操作が再入することを避けるために、次のステートメントを `startButton_Click` の先頭に追加して **[Start]** ボタンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="63087-243">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>

    ```vb
    ' Disable the button until the operation is complete.
    startButton.IsEnabled = False
    ```

    <span data-ttu-id="63087-244">イベント ハンドラーの末尾で、ボタンを再び有効にできます。</span><span class="sxs-lookup"><span data-stu-id="63087-244">You can reenable the button at the end of the event handler.</span></span>

    ```vb
    ' Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = True
    ```

    <span data-ttu-id="63087-245">再入の詳細については、「[非同期アプリでの再入の処理 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63087-245">For more information about reentrancy, see [Handling Reentrancy in Async Apps (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span></span>

4. <span data-ttu-id="63087-246">最後に、`Async` 修飾子を宣言に追加し、イベント ハンドラーが `SumPagSizesAsync` を待機できるようにします。</span><span class="sxs-lookup"><span data-stu-id="63087-246">Finally, add the `Async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>

    ```vb
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click
    ```

    <span data-ttu-id="63087-247">通常、イベント ハンドラーの名前は変更されません。</span><span class="sxs-lookup"><span data-stu-id="63087-247">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="63087-248">イベントハンドラーは Visual Basic 内の `Sub` プロシージャである必要があるため、戻り値の型を `Task` に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="63087-248">The return type isn’t changed to `Task` because event handlers must be `Sub` procedures in Visual Basic.</span></span>

    <span data-ttu-id="63087-249">同期処理から非同期処理へのプロジェクトの変換が完了しました。</span><span class="sxs-lookup"><span data-stu-id="63087-249">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>

## <a name="test-the-asynchronous-solution"></a><span data-ttu-id="63087-250">非同期ソリューションをテストする</span><span class="sxs-lookup"><span data-stu-id="63087-250">Test the asynchronous solution</span></span>

1. <span data-ttu-id="63087-251">F5 キーを押してプログラムを実行し、 **[Start]** を複数回クリックします。</span><span class="sxs-lookup"><span data-stu-id="63087-251">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

2. <span data-ttu-id="63087-252">同期ソリューションの出力に似た出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="63087-252">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="63087-253">ただし、次の相違点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="63087-253">However, notice the following differences.</span></span>

    - <span data-ttu-id="63087-254">処理の完了後に、すべての結果が同時に表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="63087-254">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="63087-255">たとえば、両方のプログラムの `startButton_Click` には、テキスト ボックスをクリアする行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="63087-255">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="63087-256">この目的は、実行ごとにテキスト ボックスをクリアすることです。1 つの結果セットが表示された後に、もう一度 **[Start]** ボタンをクリックすると、テキスト ボックスがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="63087-256">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="63087-257">同期バージョンでは、2 回目のカウントが表示される直前、ダウンロードが完了して UI スレッドが他の処理を実行できる状態になったときにテキスト ボックスがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="63087-257">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="63087-258">非同期バージョンでは、 **[Start]** ボタンをクリックした直後にテキスト ボックスがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="63087-258">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>

    - <span data-ttu-id="63087-259">最も重要な点は、ダウンロード中に UI スレッドがブロックされないことです。</span><span class="sxs-lookup"><span data-stu-id="63087-259">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="63087-260">Web リソースをダウンロード、カウント、および表示している間に、ウィンドウの移動やサイズ変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="63087-260">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="63087-261">いずれかの Web サイトの処理が遅い、または応答しない場合、**閉じる**ボタン (右上隅の赤色のフィールドにある [x]) をクリックすることで、操作を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="63087-261">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>

## <a name="replace-the-geturlcontentsasync-method-with-a-net-framework-method"></a><span data-ttu-id="63087-262">Geturlの Async メソッドを .NET Framework メソッドに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="63087-262">Replace the GetURLContentsAsync method with a .NET Framework method</span></span>

1. <span data-ttu-id="63087-263">.NET Framework には、使用できる非同期メソッドが数多く用意されています。</span><span class="sxs-lookup"><span data-stu-id="63087-263">The .NET Framework provides many async methods that you can use.</span></span> <span data-ttu-id="63087-264">そのうちの1つは、このチュートリアルで必要なのは、<xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29?displayProperty=nameWithType> メソッドです。</span><span class="sxs-lookup"><span data-stu-id="63087-264">One of them, the <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29?displayProperty=nameWithType> method, does just what you need for this walkthrough.</span></span> <span data-ttu-id="63087-265">これを、前述の手順で作成した `GetURLContentsAsync` メソッドの代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="63087-265">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>

    <span data-ttu-id="63087-266">最初の手順では、`SumPageSizesAsync` メソッドに <xref:System.Net.Http.HttpClient> オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="63087-266">The first step is to create an <xref:System.Net.Http.HttpClient> object in the `SumPageSizesAsync` method.</span></span> <span data-ttu-id="63087-267">次の宣言をメソッドの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="63087-267">Add the following declaration at the start of the method.</span></span>

    ```vb
    ' Declare an HttpClient object and increase the buffer size. The
    ' default buffer size is 65,536.
    Dim client As HttpClient =
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}
    ```

2. <span data-ttu-id="63087-268">`SumPageSizesAsync,` で、`GetURLContentsAsync` メソッドへの呼び出しを `HttpClient` メソッドへの呼び出しに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="63087-268">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>

    ```vb
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
    ```

3. <span data-ttu-id="63087-269">記述した `GetURLContentsAsync` メソッドを削除するかコメント アウトします。</span><span class="sxs-lookup"><span data-stu-id="63087-269">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>

4. <span data-ttu-id="63087-270">F5 キーを押してプログラムを実行し、 **[Start]** を複数回クリックします。</span><span class="sxs-lookup"><span data-stu-id="63087-270">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

    <span data-ttu-id="63087-271">このバージョンのプロジェクトの動作は、「非同期ソリューションをテストするには」の手順で説明している動作と同じですが、さらに少ない手間で作成できます。</span><span class="sxs-lookup"><span data-stu-id="63087-271">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>

## <a name="example"></a><span data-ttu-id="63087-272">例</span><span class="sxs-lookup"><span data-stu-id="63087-272">Example</span></span>

<span data-ttu-id="63087-273">非同期 `GetURLContentsAsync` メソッドを使用する変換された非同期ソリューションの完全な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="63087-273">The following is the full example of the converted asynchronous solution that uses the asynchronous `GetURLContentsAsync` method.</span></span> <span data-ttu-id="63087-274">この例は、元の同期ソリューションと非常によく似ています。</span><span class="sxs-lookup"><span data-stu-id="63087-274">Notice that it strongly resembles the original, synchronous solution.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        ' Disable the button until the operation is complete.
        startButton.IsEnabled = False

        resultsTextBox.Clear()

        '' One-step async call.
        Await SumPageSizesAsync()

        ' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."

        ' Reenable the button in case you want to run the operation again.
        startButton.IsEnabled = True
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            Dim urlContents As Byte() = Await GetURLContentsAsync(url)

            ' The previous line abbreviates the following two assignment statements.

            '//<snippet21>
            ' GetURLContentsAsync returns a task. At completion, the task
            ' produces a byte array.
            'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
            'Dim urlContents As Byte() = Await getContentsTask

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        Using response As WebResponse = Await webReq.GetResponseAsync()

            ' The previous statement abbreviates the following two statements.

            'Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
            'Using response As WebResponse = Await responseTask

            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                Await responseStream.CopyToAsync(content)

                ' The previous statement abbreviates the following two statements.

                ' CopyToAsync returns a Task, not a Task<T>.
                'Dim copyTask As Task = responseStream.CopyToAsync(content)

                ' When copyTask is completed, content contains a copy of
                ' responseStream.
                'Await copyTask
            End Using
        End Using

        ' Return the result as a byte array.
        Return content.ToArray()
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

<span data-ttu-id="63087-275">次のコードには、`HttpClient` の `GetByteArrayAsync` メソッドを使用するソリューション例のすべてが含まれています。</span><span class="sxs-lookup"><span data-stu-id="63087-275">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        ' Disable the button until the operation is complete.
        startButton.IsEnabled = False

        ' One-step async call.
        Await SumPageSizesAsync()

        ' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."

        ' Reenable the button in case you want to run the operation again.
        startButton.IsEnabled = True
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Declare an HttpClient object and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            ' GetByteArrayAsync returns a task. At completion, the task
            ' produces a byte array.
            Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

            ' The following two lines can replace the previous assignment statement.
            'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
            'Dim urlContents As Byte() = Await getContentsTask

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

## <a name="see-also"></a><span data-ttu-id="63087-276">関連項目</span><span class="sxs-lookup"><span data-stu-id="63087-276">See also</span></span>

- [<span data-ttu-id="63087-277">非同期サンプル: Web へのアクセスのチュートリアル (C# および Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63087-277">Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)
- [<span data-ttu-id="63087-278">Await 演算子</span><span class="sxs-lookup"><span data-stu-id="63087-278">Await Operator</span></span>](../../../../visual-basic/language-reference/operators/await-operator.md)
- [<span data-ttu-id="63087-279">Async</span><span class="sxs-lookup"><span data-stu-id="63087-279">Async</span></span>](../../../../visual-basic/language-reference/modifiers/async.md)
- [<span data-ttu-id="63087-280">Async および Await を使用した非同期プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63087-280">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
- [<span data-ttu-id="63087-281">非同期の戻り値の型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63087-281">Async Return Types (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)
- [<span data-ttu-id="63087-282">タスク ベースの非同期プログラミング (TAP)</span><span class="sxs-lookup"><span data-stu-id="63087-282">Task-based Asynchronous Programming (TAP)</span></span>](https://go.microsoft.com/fwlink/?LinkId=204847)
- [<span data-ttu-id="63087-283">方法: Task.WhenAll を使用して AsyncWalkthrough を拡張する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63087-283">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
- [<span data-ttu-id="63087-284">方法: Async と Await を使用して複数の Web 要求を並列実行する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63087-284">How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
