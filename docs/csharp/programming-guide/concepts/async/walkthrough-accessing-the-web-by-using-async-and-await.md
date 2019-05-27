---
title: 'チュートリアル: Async と Await を使用した Web へのアクセス (C#)'
ms.date: 07/20/2015
ms.assetid: c95d8d71-5a98-4bf0-aaf4-45fed2ebbacd
ms.openlocfilehash: 1057bdf02d20b0f685e6bd319929188ffd07c726
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052191"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-c"></a><span data-ttu-id="55fd1-102">チュートリアル: Async と Await を使用した Web へのアクセス (C#)</span><span class="sxs-lookup"><span data-stu-id="55fd1-102">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>

<span data-ttu-id="55fd1-103">async/await 機能を使用することで、非同期プログラムをより簡単かつ直感的に記述できます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-103">You can write asynchronous programs more easily and intuitively by using async/await features.</span></span> <span data-ttu-id="55fd1-104">同期コードに似た非同期コードを記述し、通常の非同期コードが必要とする難しいコールバック関数や継続の処理をコンパイラに任せます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>

<span data-ttu-id="55fd1-105">非同期機能について詳しくは、「[Async および Await を使用した非同期プログラミング (C# および Visual Basic)](../../../../csharp/programming-guide/concepts/async/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55fd1-105">For more information about the Async feature, see [Asynchronous Programming with async and await (C#)](../../../../csharp/programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="55fd1-106">このチュートリアルは、Web サイトの一覧でのバイト数の合計を計算する同期 Windows Presentation Foundation (WPF) アプリケーションから開始します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="55fd1-107">その後、新しい機能を使用して、アプリケーションを非同期ソリューションに変換します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>

<span data-ttu-id="55fd1-108">自分でアプリケーションを作成しない場合は、[非同期サンプル:Web へのアクセスのチュートリアル (C# および Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-108">If you don't want to build the applications yourself, you can download [Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>

> [!NOTE]
> <span data-ttu-id="55fd1-109">この例を実行するには、コンピューターに Visual Studio 2012 以降および .NET Framework 4.5 以降がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="55fd1-109">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="create-a-wpf-application"></a><span data-ttu-id="55fd1-110">WPF アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="55fd1-110">Create a WPF application</span></span>

1. <span data-ttu-id="55fd1-111">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-111">Start Visual Studio.</span></span>

2. <span data-ttu-id="55fd1-112">メニュー バーで、 **[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-112">On the menu bar, choose **File** > **New** > **Project**.</span></span>

     <span data-ttu-id="55fd1-113">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-113">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="55fd1-114">**[インストールされたテンプレート]** ウィンドウで、[Visual C#] をクリックし、プロジェクトの種類の一覧で **[WPF アプリケーション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-114">In the **Installed Templates** pane, choose Visual C#, and then choose **WPF Application** from the list of project types.</span></span>

4. <span data-ttu-id="55fd1-115">**[名前]** ボックスに「`AsyncExampleWPF`」と入力して、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-115">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>

     <span data-ttu-id="55fd1-116">**ソリューション エクスプローラー**に新しいプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-116">The new project appears in **Solution Explorer**.</span></span>

## <a name="design-a-simple-wpf-mainwindow"></a><span data-ttu-id="55fd1-117">単純な WPF MainWindow をデザインする</span><span class="sxs-lookup"><span data-stu-id="55fd1-117">Design a simple WPF MainWindow</span></span>

1. <span data-ttu-id="55fd1-118">Visual Studio コード エディターで、 **[MainWindow.xaml]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-118">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

2. <span data-ttu-id="55fd1-119">**[ツールボックス]** ウィンドウが表示されていない場合は、 **[表示]** メニューを開き、 **[ツールボックス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-119">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>

3. <span data-ttu-id="55fd1-120">**[Button]** コントロールと **[TextBox]** コントロールを **[MainWindow]** ウィンドウに追加します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-120">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>

4. <span data-ttu-id="55fd1-121">**[TextBox]** コントロールを強調表示し、 **[プロパティ]** ウィンドウで次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-121">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="55fd1-122">**[Name]** プロパティを `resultsTextBox` に設定します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-122">Set the **Name** property to `resultsTextBox`.</span></span>

    - <span data-ttu-id="55fd1-123">**[Height]** プロパティを 250 に設定します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-123">Set the **Height** property to 250.</span></span>

    - <span data-ttu-id="55fd1-124">**[Width]** プロパティを 500 に設定します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-124">Set the **Width** property to 500.</span></span>

    - <span data-ttu-id="55fd1-125">**[テキスト]** タブで、Lucida Console や Global Monospace などの等幅フォントを指定します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-125">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>

5. <span data-ttu-id="55fd1-126">**[Button]** コントロールを強調表示し、 **[プロパティ]** ウィンドウで次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-126">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="55fd1-127">**[Name]** プロパティを `startButton` に設定します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-127">Set the **Name** property to `startButton`.</span></span>

    - <span data-ttu-id="55fd1-128">**[Content]** プロパティの値を **[Button]** から **[Start]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-128">Change the value of the **Content** property from **Button** to **Start**.</span></span>

6. <span data-ttu-id="55fd1-129">テキスト ボックスとボタンの位置を調整し、両方が **[MainWindow]** ウィンドウ内に表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-129">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>

     <span data-ttu-id="55fd1-130">WPF XAML デザイナーについて詳しくは、「[XAML デザイナーを使用した UI の作成](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55fd1-130">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>

## <a name="add-a-reference"></a><span data-ttu-id="55fd1-131">参照を追加する</span><span class="sxs-lookup"><span data-stu-id="55fd1-131">Add a reference</span></span>

1. <span data-ttu-id="55fd1-132">**ソリューション エクスプローラー**で、プロジェクトの名前を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-132">In **Solution Explorer**, highlight your project's name.</span></span>

2. <span data-ttu-id="55fd1-133">メニュー バーで、 **[プロジェクト]**  >  **[参照の追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-133">On the menu bar, choose **Project** > **Add Reference**.</span></span>

     <span data-ttu-id="55fd1-134">**[参照マネージャー]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-134">The **Reference Manager** dialog box appears.</span></span>

3. <span data-ttu-id="55fd1-135">ダイアログ ボックスの上部で、プロジェクトのターゲットが .NET Framework 4.5 以上であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-135">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>

4. <span data-ttu-id="55fd1-136">**[アセンブリ]** カテゴリで、 **[フレームワーク]** を選択します (選択されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="55fd1-136">In the **Assemblies** category, choose **Framework** if it isn’t already chosen.</span></span>

5. <span data-ttu-id="55fd1-137">名前の一覧で、 **[System.Net.Http]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-137">In the list of names, select the **System.Net.Http** check box.</span></span>

6. <span data-ttu-id="55fd1-138">**[OK]** をクリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-138">Choose the **OK** button to close the dialog box.</span></span>

## <a name="add-necessary-using-directives"></a><span data-ttu-id="55fd1-139">ディレクティブを使用して必要なものを追加する</span><span class="sxs-lookup"><span data-stu-id="55fd1-139">Add necessary using directives</span></span>

1. <span data-ttu-id="55fd1-140">**ソリューション エクスプローラー**で MainWindow.xaml.cs のショートカット メニューを開き、 **[コードの表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-140">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>

2. <span data-ttu-id="55fd1-141">次の `using` ディレクティブが含まれていない場合は、コード ファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-141">Add the following `using` directives at the top of the code file if they’re not already present.</span></span>

    ```csharp
    using System.Net.Http;
    using System.Net;
    using System.IO;
    ```

## <a name="create-a-synchronous-app"></a><span data-ttu-id="55fd1-142">同期アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="55fd1-142">Create a synchronous app</span></span>

1. <span data-ttu-id="55fd1-143">デザイン ウィンドウの MainWindow.xaml で、 **[Start]** ボタンをダブルクリックして、MainWindow.xaml.cs に `startButton_Click` イベント ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-143">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>

2. <span data-ttu-id="55fd1-144">MainWindow.xaml.cs で、次のコードを `startButton_Click` の本文にコピーします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-144">In MainWindow.xaml.cs, copy the following code into the body of `startButton_Click`:</span></span>

    ```csharp
    resultsTextBox.Clear();
    SumPageSizes();
    resultsTextBox.Text += "\r\nControl returned to startButton_Click.";
    ```

    <span data-ttu-id="55fd1-145">このコードは、`SumPageSizes` アプリケーションを実行するメソッドを呼び出し、`startButton_Click` に制御が戻るとメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-145">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>

3. <span data-ttu-id="55fd1-146">同期ソリューションのコードには、次の 4 つのメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="55fd1-146">The code for the synchronous solution contains the following four methods:</span></span>

    - <span data-ttu-id="55fd1-147">`SumPageSizes` は、`SetUpURLList` から Web ページ URL のリストを取得し、`GetURLContents` と `DisplayResults` を呼び出して各 URL を処理します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-147">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>

    - <span data-ttu-id="55fd1-148">`SetUpURLList` は、Web アドレスのリストを作成して返します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-148">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>

    - <span data-ttu-id="55fd1-149">`GetURLContents` は、各 Web サイトのコンテンツをダウンロードし、バイト配列としてそのコンテンツを返します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-149">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>

    - <span data-ttu-id="55fd1-150">`DisplayResults` は、各 URL のバイト配列内のバイト数を表示します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-150">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>

    <span data-ttu-id="55fd1-151">次の 4 つのメソッドをコピーし、それを MainWindow.xaml.cs の `startButton_Click` イベント ハンドラーの下に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-151">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.cs:</span></span>

    ```csharp
    private void SumPageSizes()
    {
        // Make a list of web addresses.
        List<string> urlList = SetUpURLList();

        var total = 0;
        foreach (var url in urlList)
        {
            // GetURLContents returns the contents of url as a byte array.
            byte[] urlContents = GetURLContents(url);

            DisplayResults(url, urlContents);

            // Update the total.
            total += urlContents.Length;
        }

        // Display the total count for all of the web addresses.
        resultsTextBox.Text += $"\r\n\r\nTotal bytes returned:  {total}\r\n";
    }

    private List<string> SetUpURLList()
    {
        var urls = new List<string>
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
        };
        return urls;
    }

    private byte[] GetURLContents(string url)
    {
        // The downloaded resource ends up in the variable named content.
        var content = new MemoryStream();

        // Initialize an HttpWebRequest for the current URL.
        var webReq = (HttpWebRequest)WebRequest.Create(url);

        // Send the request to the Internet resource and wait for
        // the response.
        // Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.
        using (WebResponse response = webReq.GetResponse())
        {
            // Get the data stream that is associated with the specified URL.
            using (Stream responseStream = response.GetResponseStream())
            {
                // Read the bytes in responseStream and copy them to content.
                responseStream.CopyTo(content);
            }
        }

        // Return the result as a byte array.
        return content.ToArray();
    }

    private void DisplayResults(string url, byte[] content)
    {
        // Display the length of each website. The string format
        // is designed to be used with a monospaced font, such as
        // Lucida Console or Global Monospace.
        var bytes = content.Length;
        // Strip off the "https://".
        var displayURL = url.Replace("https://", "");
        resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
    }
    ```

## <a name="test-the-synchronous-solution"></a><span data-ttu-id="55fd1-152">同期ソリューションをテストする</span><span class="sxs-lookup"><span data-stu-id="55fd1-152">Test the synchronous solution</span></span>

<span data-ttu-id="55fd1-153">**F5** キーを押してプログラムを実行し、 **[スタート]** を複数回クリックします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-153">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

<span data-ttu-id="55fd1-154">次の一覧のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-154">Output that resembles the following list should appear:</span></span>

```text
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

<span data-ttu-id="55fd1-155">カウントの表示には数秒かかる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="55fd1-155">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="55fd1-156">その間、要求されたリソースのダウンロードが完了するまで UI スレッドがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-156">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="55fd1-157">このため、 **[Start]** ボタンのクリック後は、表示ウィンドウの移動、最大化、最小化のほか、閉じることさえできなくなります。</span><span class="sxs-lookup"><span data-stu-id="55fd1-157">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="55fd1-158">バイト カウントの表示が開始するまでは、これらの操作を実行しても失敗します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-158">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="55fd1-159">Web サイトが応答していない場合、どのサイトに問題があるのかを示す情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="55fd1-159">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="55fd1-160">待つのをやめて、プログラムを閉じることさえ難しい状態になります。</span><span class="sxs-lookup"><span data-stu-id="55fd1-160">It is difficult even to stop waiting and close the program.</span></span>

## <a name="convert-geturlcontents-to-an-asynchronous-method"></a><span data-ttu-id="55fd1-161">GetURLContents を非同期メソッドに変換する</span><span class="sxs-lookup"><span data-stu-id="55fd1-161">Convert GetURLContents to an asynchronous method</span></span>

1. <span data-ttu-id="55fd1-162">同期ソリューションを非同期ソリューションに変換する際に、最初に取りかかるのに最適な場所は、`GetURLContents` 内です。その理由は、<xref:System.Net.HttpWebRequest> の <xref:System.Net.HttpWebRequest.GetResponse%2A> メソッドおよび <xref:System.IO.Stream> の <xref:System.IO.Stream.CopyTo%2A> メソッドへの呼び出しで、アプリケーションが Web にアクセスするためです。</span><span class="sxs-lookup"><span data-stu-id="55fd1-162">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest> method <xref:System.Net.HttpWebRequest.GetResponse%2A> and to the <xref:System.IO.Stream> method <xref:System.IO.Stream.CopyTo%2A> are where the application accesses the web.</span></span> <span data-ttu-id="55fd1-163">.NET Framework には両方のメソッドの非同期バージョンが用意されているため、変換は簡単です。</span><span class="sxs-lookup"><span data-stu-id="55fd1-163">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>

     <span data-ttu-id="55fd1-164">`GetURLContents` で使用されているメソッドの詳細については、「<xref:System.Net.WebRequest>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55fd1-164">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55fd1-165">このチュートリアルの手順に従っていると、いくつかのコンパイラ エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-165">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="55fd1-166">これらのエラーは無視することで、チュートリアルを続行できます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-166">You can ignore them and continue with the walkthrough.</span></span>

     <span data-ttu-id="55fd1-167">`GetURLContents` の 3 行目で呼び出されるメソッドを、`GetResponse` から、非同期でタスク ベースの <xref:System.Net.WebRequest.GetResponseAsync%2A> メソッドに変更します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-167">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>

    ```csharp
    using (WebResponse response = webReq.GetResponseAsync())
    ```

2. <span data-ttu-id="55fd1-168">`GetResponseAsync` は、<xref:System.Threading.Tasks.Task%601> を返します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-168">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="55fd1-169">この場合、*タスク戻り変数*の `TResult` の型は <xref:System.Net.WebResponse> です。</span><span class="sxs-lookup"><span data-stu-id="55fd1-169">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="55fd1-170">このタスクは、要求されたデータのダウンロードが完了し、タスクが最後まで実行された後に、実際の `WebResponse` オブジェクトを生成するという約束です。</span><span class="sxs-lookup"><span data-stu-id="55fd1-170">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>

     <span data-ttu-id="55fd1-171">タスクから `WebResponse` 値を取得するには、次のコードに示すように、[await](../../../../csharp/language-reference/keywords/await.md) (C#) 演算子を `GetResponseAsync` への呼び出しに適用します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-171">To retrieve the `WebResponse` value from the task, apply an [await](../../../../csharp/language-reference/keywords/await.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>

    ```csharp
    using (WebResponse response = await webReq.GetResponseAsync())
    ```

     <span data-ttu-id="55fd1-172">`await` 演算子は、現在のメソッド、`GetURLContents` の実行を、待機しているタスクが完了するまで中断します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-172">The `await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="55fd1-173">その間、現在のメソッドの呼び出し元に制御が戻されます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-173">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="55fd1-174">この例では、現在のメソッドが `GetURLContents` で、呼び出し元が `SumPageSizes` です。</span><span class="sxs-lookup"><span data-stu-id="55fd1-174">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="55fd1-175">タスクが完了すると、約束されていた `WebResponse` オブジェクトが完了したタスクの値として生成され、変数 `response` に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-175">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>

     <span data-ttu-id="55fd1-176">上記のステートメントは、動作を明確にするため、次の 2 つのステートメントに分割できます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-176">The previous statement can be separated into the following two statements to clarify what happens.</span></span>

    ```csharp
    //Task<WebResponse> responseTask = webReq.GetResponseAsync();
    //using (WebResponse response = await responseTask)
    ```

     <span data-ttu-id="55fd1-177">`webReq.GetResponseAsync` への呼び出しによって、`Task(Of WebResponse)` または `Task<WebResponse>` が返されます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-177">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="55fd1-178">その後、`WebResponse` 値を取得するため、タスクに await 演算子が適用されます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-178">Then an await operator is applied to the task to retrieve the `WebResponse` value.</span></span>

     <span data-ttu-id="55fd1-179">非同期メソッドにタスクの完了に依存しない処理がある場合、メソッドはこれら 2 つのステートメントの間、つまり非同期メソッドへの呼び出しから、`await` 演算子の適用までの間にその処理を続行することができます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-179">If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the `await` operator is applied.</span></span> <span data-ttu-id="55fd1-180">たとえば、「[方法:async と await を使用して複数の Web 要求を並列実行する (C#)](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)」と「[方法:Task.WhenAll を使用して AsyncWalkthrough を拡張する (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55fd1-180">For examples, see [How to: Make Multiple Web Requests in Parallel by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>

3. <span data-ttu-id="55fd1-181">前の手順で `await` 演算子を追加したため、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-181">Because you added the `await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="55fd1-182">この演算子は、[async](../../../../csharp/language-reference/keywords/async.md) 修飾子でマークされているメソッドでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-182">The operator can be used only in methods that are marked with the [async](../../../../csharp/language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="55fd1-183">`CopyTo` への呼び出しを `CopyToAsync` への呼び出しに置き換える変換手順を繰り返す間は、エラーを無視してください。</span><span class="sxs-lookup"><span data-stu-id="55fd1-183">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>

    - <span data-ttu-id="55fd1-184">呼び出されるメソッドの名前を <xref:System.IO.Stream.CopyToAsync%2A> に変更します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-184">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>

    - <span data-ttu-id="55fd1-185">`CopyTo` または `CopyToAsync` メソッドは、その引数 `content` にバイトをコピーし、意味のある値は返しません。</span><span class="sxs-lookup"><span data-stu-id="55fd1-185">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="55fd1-186">同期バージョンでは、`CopyTo` への呼び出しは値を返さない単純なステートメントです。</span><span class="sxs-lookup"><span data-stu-id="55fd1-186">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="55fd1-187">非同期バージョンでは、`CopyToAsync` は <xref:System.Threading.Tasks.Task> を返します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-187">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="55fd1-188">タスクは "Task(void)" のように機能し、メソッドを待機できるようにします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-188">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="55fd1-189">次のコードに示すように、`Await` または `await` を、`CopyToAsync` への呼び出しに適用します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-189">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>

        ```csharp
        await responseStream.CopyToAsync(content);
        ```

         <span data-ttu-id="55fd1-190">上記のステートメントでは、次の 2 行のコードを省略しています。</span><span class="sxs-lookup"><span data-stu-id="55fd1-190">The previous statement abbreviates the following two lines of code.</span></span>

        ```csharp
        // CopyToAsync returns a Task, not a Task<T>.
        //Task copyTask = responseStream.CopyToAsync(content);

        // When copyTask is completed, content contains a copy of
        // responseStream.
        //await copyTask;
        ```

4. <span data-ttu-id="55fd1-191">`GetURLContents` 内で必要な作業として残っているのは、メソッド シグネチャの調整のみです。</span><span class="sxs-lookup"><span data-stu-id="55fd1-191">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="55fd1-192">`await` 演算子は、[async](../../../../csharp/language-reference/keywords/async.md) 修飾子でマークされているメソッドでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-192">You can use the `await` operator only in methods that are marked with the [async](../../../../csharp/language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="55fd1-193">次のコードに示すように、修飾子を追加し、メソッドを*非同期メソッド*としてマークします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-193">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>

    ```csharp
    private async byte[] GetURLContents(string url)
    ```

5. <span data-ttu-id="55fd1-194">C# での非同期メソッドの戻り値の型は、<xref:System.Threading.Tasks.Task>、<xref:System.Threading.Tasks.Task%601>、または `void` のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-194">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, or `void` in C#.</span></span> <span data-ttu-id="55fd1-195">通常、`void` の戻り値の型は、`void` を必要とする非同期イベント ハンドラーでのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-195">Typically, a return type of `void` is used only in an async event handler, where `void` is required.</span></span> <span data-ttu-id="55fd1-196">それ以外のケースでは、完成したメソッドに、T 型の値を返す [return](../../../../csharp/language-reference/keywords/return.md) ステートメントが含まれる場合は `Task(T)` を使用し、完成したメソッドが意味のある値を返さない場合は `Task` を使用します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-196">In other cases, you use `Task(T)` if the completed method has a [return](../../../../csharp/language-reference/keywords/return.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span> <span data-ttu-id="55fd1-197">戻り値の型 `Task` は、"Task(void)" を意味するものと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-197">You can think of the `Task` return type as meaning "Task(void)."</span></span>

     <span data-ttu-id="55fd1-198">詳しくは、「[非同期の戻り値の型 (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55fd1-198">For more information, see [Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>

     <span data-ttu-id="55fd1-199">メソッド `GetURLContents` には return ステートメントがあり、このステートメントはバイト配列を返します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-199">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="55fd1-200">そのため、非同期バージョンの戻り値の型は Task(T) であり、T はバイト配列です。</span><span class="sxs-lookup"><span data-stu-id="55fd1-200">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="55fd1-201">メソッド シグネチャに、次の変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-201">Make the following changes in the method signature:</span></span>

    - <span data-ttu-id="55fd1-202">戻り値の型を `Task<byte[]>` に変更します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-202">Change the return type to `Task<byte[]>`.</span></span>

    - <span data-ttu-id="55fd1-203">規則により、非同期メソッドは "Async" で終わる名前を持つことになっているため、メソッドの名前を `GetURLContentsAsync` に変更します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-203">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>

     <span data-ttu-id="55fd1-204">これらの変更を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-204">The following code shows these changes.</span></span>

    ```csharp
    private async Task<byte[]> GetURLContentsAsync(string url)
    ```

     <span data-ttu-id="55fd1-205">このいくつかの変更によって、`GetURLContents` の非同期メソッドへの変換が完了しました。</span><span class="sxs-lookup"><span data-stu-id="55fd1-205">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a><span data-ttu-id="55fd1-206">SumPageSizes を非同期メソッドに変換する</span><span class="sxs-lookup"><span data-stu-id="55fd1-206">Convert SumPageSizes to an asynchronous method</span></span>

1. <span data-ttu-id="55fd1-207">`SumPageSizes` に対して、前述した手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-207">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="55fd1-208">まずは、`GetURLContents` への呼び出しを非同期呼び出しに変更します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-208">First, change the call to `GetURLContents` to an asynchronous call.</span></span>

    - <span data-ttu-id="55fd1-209">呼び出されるメソッドの名前を `GetURLContents` から `GetURLContentsAsync` に変更します (まだ変更していない場合)。</span><span class="sxs-lookup"><span data-stu-id="55fd1-209">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>

    - <span data-ttu-id="55fd1-210">バイト配列値を取得するために、`await` を、`GetURLContentsAsync` が返すタスクに適用します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-210">Apply `await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>

     <span data-ttu-id="55fd1-211">これらの変更を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-211">The following code shows these changes.</span></span>

    ```csharp
    byte[] urlContents = await GetURLContentsAsync(url);
    ```

     <span data-ttu-id="55fd1-212">上記の割り当てでは、次の 2 行のコードを省略しています。</span><span class="sxs-lookup"><span data-stu-id="55fd1-212">The previous assignment abbreviates the following two lines of code.</span></span>

    ```csharp
    // GetURLContentsAsync returns a Task<T>. At completion, the task
    // produces a byte array.
    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
    //byte[] urlContents = await getContentsTask;
    ```

2. <span data-ttu-id="55fd1-213">メソッドのシグネチャに、次の変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-213">Make the following changes in the method's signature:</span></span>

    - <span data-ttu-id="55fd1-214">メソッドを `async` 修飾子でマークします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-214">Mark the method with the `async` modifier.</span></span>

    - <span data-ttu-id="55fd1-215">メソッド名に "Async" を追加します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-215">Add "Async" to the method name.</span></span>

    - <span data-ttu-id="55fd1-216">今回、タスク戻り変数の T がない理由は、`SumPageSizesAsync` が T のための値を返さないからです (メソッドに `return` ステートメントがありません)。ただし、メソッドは待機可能になるために `Task` を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="55fd1-216">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="55fd1-217">そのため、メソッドの戻り値の型を `void` から `Task` に変更します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-217">Therefore, change the return type of the method from `void` to `Task`.</span></span>

    <span data-ttu-id="55fd1-218">これらの変更を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-218">The following code shows these changes.</span></span>

    ```csharp
    private async Task SumPageSizesAsync()
    ```

     <span data-ttu-id="55fd1-219">`SumPageSizes` から `SumPageSizesAsync` への変換が完了しました。</span><span class="sxs-lookup"><span data-stu-id="55fd1-219">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>

## <a name="convert-startbuttonclick-to-an-asynchronous-method"></a><span data-ttu-id="55fd1-220">startButton_Click を非同期メソッドに変換する</span><span class="sxs-lookup"><span data-stu-id="55fd1-220">Convert startButton_Click to an asynchronous method</span></span>

1. <span data-ttu-id="55fd1-221">イベント ハンドラーで、呼び出されるメソッドの名前を `SumPageSizes` から `SumPageSizesAsync` に変更します (まだ変更していない場合)。</span><span class="sxs-lookup"><span data-stu-id="55fd1-221">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>

2. <span data-ttu-id="55fd1-222">`SumPageSizesAsync` は非同期メソッドであるため、結果を待機するイベント ハンドラーのコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-222">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>

     <span data-ttu-id="55fd1-223">`SumPageSizesAsync` への呼び出しは、`GetURLContentsAsync` の `CopyToAsync` への呼び出しに似ています。</span><span class="sxs-lookup"><span data-stu-id="55fd1-223">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="55fd1-224">この呼び出しによって、`Task(T)` ではなく `Task` が返されます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-224">The call returns a `Task`, not a `Task(T)`.</span></span>

     <span data-ttu-id="55fd1-225">前述した手順と同様に、1 つまたは 2 つのステートメントを使用して、呼び出しを変換できます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-225">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="55fd1-226">これらの変更を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-226">The following code shows these changes.</span></span>

    ```csharp
    // One-step async call.
    await SumPageSizesAsync();

    // Two-step async call.
    //Task sumTask = SumPageSizesAsync();
    //await sumTask;
    ```

3. <span data-ttu-id="55fd1-227">誤って操作が再入することを避けるために、次のステートメントを `startButton_Click` の先頭に追加して **[Start]** ボタンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-227">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>

    ```csharp
    // Disable the button until the operation is complete.
    startButton.IsEnabled = false;
    ```

     <span data-ttu-id="55fd1-228">イベント ハンドラーの末尾で、ボタンを再び有効にできます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-228">You can reenable the button at the end of the event handler.</span></span>

    ```csharp
    // Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = true;
    ```

     <span data-ttu-id="55fd1-229">再入について詳しくは、「[非同期アプリにおける再入の処理 (C#)](../../../../csharp/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55fd1-229">For more information about reentrancy, see [Handling Reentrancy in Async Apps (C#)](../../../../csharp/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span></span>

4. <span data-ttu-id="55fd1-230">最後に、`async` 修飾子を宣言に追加し、イベント ハンドラーが `SumPagSizesAsync` を待機できるようにします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-230">Finally, add the `async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>

    ```csharp
    private async void startButton_Click(object sender, RoutedEventArgs e)
    ```

     <span data-ttu-id="55fd1-231">通常、イベント ハンドラーの名前は変更されません。</span><span class="sxs-lookup"><span data-stu-id="55fd1-231">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="55fd1-232">戻り値の型が `Task` に変更されていない理由は、イベント ハンドラーが `void` を返す必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="55fd1-232">The return type isn’t changed to `Task` because event handlers must return `void`.</span></span>

     <span data-ttu-id="55fd1-233">同期処理から非同期処理へのプロジェクトの変換が完了しました。</span><span class="sxs-lookup"><span data-stu-id="55fd1-233">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>

## <a name="test-the-asynchronous-solution"></a><span data-ttu-id="55fd1-234">非同期ソリューションをテストする</span><span class="sxs-lookup"><span data-stu-id="55fd1-234">Test the asynchronous solution</span></span>

1. <span data-ttu-id="55fd1-235">**F5** キーを押してプログラムを実行し、 **[スタート]** を複数回クリックします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-235">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

2. <span data-ttu-id="55fd1-236">同期ソリューションの出力に似た出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-236">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="55fd1-237">ただし、次の相違点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="55fd1-237">However, notice the following differences.</span></span>

    - <span data-ttu-id="55fd1-238">処理の完了後に、すべての結果が同時に表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="55fd1-238">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="55fd1-239">たとえば、両方のプログラムの `startButton_Click` には、テキスト ボックスをクリアする行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="55fd1-239">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="55fd1-240">この目的は、実行ごとにテキスト ボックスをクリアすることです。1 つの結果セットが表示された後に、もう一度 **[Start]** ボタンをクリックすると、テキスト ボックスがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-240">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="55fd1-241">同期バージョンでは、2 回目のカウントが表示される直前、ダウンロードが完了して UI スレッドが他の処理を実行できる状態になったときにテキスト ボックスがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-241">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="55fd1-242">非同期バージョンでは、 **[Start]** ボタンをクリックした直後にテキスト ボックスがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-242">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>

    - <span data-ttu-id="55fd1-243">最も重要な点は、ダウンロード中に UI スレッドがブロックされないことです。</span><span class="sxs-lookup"><span data-stu-id="55fd1-243">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="55fd1-244">Web リソースをダウンロード、カウント、および表示している間に、ウィンドウの移動やサイズ変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-244">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="55fd1-245">いずれかの Web サイトの処理が遅い、または応答しない場合、**閉じる**ボタン (右上隅の赤色のフィールドにある [x]) をクリックすることで、操作を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-245">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>

## <a name="replace-method-geturlcontentsasync-with-a-net-framework-method"></a><span data-ttu-id="55fd1-246">GetURLContentsAsync メソッドを .NET Framework メソッドに置き換える</span><span class="sxs-lookup"><span data-stu-id="55fd1-246">Replace method GetURLContentsAsync with a .NET Framework method</span></span>

1. <span data-ttu-id="55fd1-247">.NET Framework 4.5 では、使用できる非同期メソッドが数多く用意されています。</span><span class="sxs-lookup"><span data-stu-id="55fd1-247">The .NET Framework 4.5 provides many async methods that you can use.</span></span> <span data-ttu-id="55fd1-248">その 1 つである、<xref:System.Net.Http.HttpClient> の <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> メソッドは、このチュートリアルに必要な処理だけを実行します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-248">One of them, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, does just what you need for this walkthrough.</span></span> <span data-ttu-id="55fd1-249">これを、前述の手順で作成した `GetURLContentsAsync` メソッドの代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-249">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>

     <span data-ttu-id="55fd1-250">まずは、`SumPageSizesAsync` メソッドに `HttpClient` オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-250">The first step is to create an `HttpClient` object in method `SumPageSizesAsync`.</span></span> <span data-ttu-id="55fd1-251">次の宣言をメソッドの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="55fd1-251">Add the following declaration at the start of the method.</span></span>

    ```csharp
    // Declare an HttpClient object and increase the buffer size. The
    // default buffer size is 65,536.
    HttpClient client =
        new HttpClient() { MaxResponseContentBufferSize = 1000000 };
    ```

2. <span data-ttu-id="55fd1-252">`SumPageSizesAsync,` で、`GetURLContentsAsync` メソッドへの呼び出しを `HttpClient` メソッドへの呼び出しに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-252">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>

    ```csharp
    byte[] urlContents = await client.GetByteArrayAsync(url);
    ```

3. <span data-ttu-id="55fd1-253">記述した `GetURLContentsAsync` メソッドを削除するかコメント アウトします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-253">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>

4. <span data-ttu-id="55fd1-254">**F5** キーを押してプログラムを実行し、 **[スタート]** を複数回クリックします。</span><span class="sxs-lookup"><span data-stu-id="55fd1-254">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

     <span data-ttu-id="55fd1-255">このバージョンのプロジェクトの動作は、「非同期ソリューションをテストするには」の手順で説明している動作と同じですが、さらに少ない手間で作成できます。</span><span class="sxs-lookup"><span data-stu-id="55fd1-255">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>

## <a name="example-code"></a><span data-ttu-id="55fd1-256">コード例</span><span class="sxs-lookup"><span data-stu-id="55fd1-256">Example code</span></span>

<span data-ttu-id="55fd1-257">次のコードには、記述した非同期 `GetURLContentsAsync` メソッドを使用する、同期ソリューションから非同期ソリューションへの変換例のすべてが含まれています。</span><span class="sxs-lookup"><span data-stu-id="55fd1-257">The following code contains the full example of the conversion from a synchronous to an asynchronous solution by using the asynchronous `GetURLContentsAsync` method that you wrote.</span></span> <span data-ttu-id="55fd1-258">この例は、元の同期ソリューションと非常によく似ています。</span><span class="sxs-lookup"><span data-stu-id="55fd1-258">Notice that it strongly resembles the original, synchronous solution.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // Disable the button until the operation is complete.
            startButton.IsEnabled = false;

            resultsTextBox.Clear();

            // One-step async call.
            await SumPageSizesAsync();

            // Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";

            // Reenable the button in case you want to run the operation again.
            startButton.IsEnabled = true;
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            var total = 0;

            foreach (var url in urlList)
            {
                byte[] urlContents = await GetURLContentsAsync(url);

                // The previous line abbreviates the following two assignment statements.

                // GetURLContentsAsync returns a Task<T>. At completion, the task
                // produces a byte array.
                //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
                //byte[] urlContents = await getContentsTask;

                DisplayResults(url, urlContents);

                // Update the total.
                total += urlContents.Length;
            }
            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
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
            };
            return urls;
        }

        private async Task<byte[]> GetURLContentsAsync(string url)
        {
            // The downloaded resource ends up in the variable named content.
            var content = new MemoryStream();

            // Initialize an HttpWebRequest for the current URL.
            var webReq = (HttpWebRequest)WebRequest.Create(url);

            // Send the request to the Internet resource and wait for
            // the response.
            using (WebResponse response = await webReq.GetResponseAsync())

            // The previous statement abbreviates the following two statements.

            //Task<WebResponse> responseTask = webReq.GetResponseAsync();
            //using (WebResponse response = await responseTask)
            {
                // Get the data stream that is associated with the specified url.
                using (Stream responseStream = response.GetResponseStream())
                {
                    // Read the bytes in responseStream and copy them to content.
                    await responseStream.CopyToAsync(content);

                    // The previous statement abbreviates the following two statements.

                    // CopyToAsync returns a Task, not a Task<T>.
                    //Task copyTask = responseStream.CopyToAsync(content);

                    // When copyTask is completed, content contains a copy of
                    // responseStream.
                    //await copyTask;
                }
            }
            // Return the result as a byte array.
            return content.ToArray();
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

<span data-ttu-id="55fd1-259">次のコードには、`HttpClient` の `GetByteArrayAsync` メソッドを使用するソリューション例のすべてが含まれています。</span><span class="sxs-lookup"><span data-stu-id="55fd1-259">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // Disable the button until the operation is complete.
            startButton.IsEnabled = false;

            // One-step async call.
            await SumPageSizesAsync();

            //// Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";

            // Reenable the button in case you want to run the operation again.
            startButton.IsEnabled = true;
        }

        private async Task SumPageSizesAsync()
        {
            // Declare an HttpClient object and increase the buffer size. The
            // default buffer size is 65,536.
            HttpClient client =
                new HttpClient() { MaxResponseContentBufferSize = 1000000 };

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            var total = 0;

            foreach (var url in urlList)
            {
                // GetByteArrayAsync returns a task. At completion, the task
                // produces a byte array.
                byte[] urlContents = await client.GetByteArrayAsync(url);

                // The following two lines can replace the previous assignment statement.
                //Task<byte[]> getContentsTask = client.GetByteArrayAsync(url);
                //byte[] urlContents = await getContentsTask;

                DisplayResults(url, urlContents);

                // Update the total.
                total += urlContents.Length;
            }

            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
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
            };
            return urls;
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="55fd1-260">関連項目</span><span class="sxs-lookup"><span data-stu-id="55fd1-260">See also</span></span>

- [<span data-ttu-id="55fd1-261">Async Sample:Web へのアクセスのチュートリアル (C# および Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55fd1-261">Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)
- [<span data-ttu-id="55fd1-262">async</span><span class="sxs-lookup"><span data-stu-id="55fd1-262">async</span></span>](../../../../csharp/language-reference/keywords/async.md)
- [<span data-ttu-id="55fd1-263">await</span><span class="sxs-lookup"><span data-stu-id="55fd1-263">await</span></span>](../../../../csharp/language-reference/keywords/await.md)
- [<span data-ttu-id="55fd1-264">Async および Await を使用した非同期プログラミング (C#)</span><span class="sxs-lookup"><span data-stu-id="55fd1-264">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)
- [<span data-ttu-id="55fd1-265">非同期の戻り値の型 (C#)</span><span class="sxs-lookup"><span data-stu-id="55fd1-265">Async Return Types (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/async-return-types.md)
- [<span data-ttu-id="55fd1-266">タスク ベースの非同期プログラミング (TAP)</span><span class="sxs-lookup"><span data-stu-id="55fd1-266">Task-based Asynchronous Programming (TAP)</span></span>](https://www.microsoft.com/download/details.aspx?id=19957)
- [<span data-ttu-id="55fd1-267">方法: Task.WhenAll を使用して AsyncWalkthrough を拡張する (C#)</span><span class="sxs-lookup"><span data-stu-id="55fd1-267">How to: Extend the async Walkthrough by Using Task.WhenAll (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
- [<span data-ttu-id="55fd1-268">方法: async と await を使用して複数の Web 要求を並列実行する (C#)</span><span class="sxs-lookup"><span data-stu-id="55fd1-268">How to: Make Multiple Web Requests in Parallel by Using async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
