---
title: 'チュートリアル: WPF アプリケーション内のアプリケーション データのキャッシュ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: 2609a54ce8ba2076c35567fe5bc1d9961f6fef3f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942060"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="b40f9-102">チュートリアル: WPF アプリケーション内のアプリケーション データのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="b40f9-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="b40f9-103">キャッシュを使用すると、メモリにデータを格納して高速にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="b40f9-104">アプリケーションからそのデータに再アクセスするときに、元のソースからではなく、キャッシュからデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-104">When the data is accessed again, applications can get the data from the cache instead of retrieving it from the original source.</span></span> <span data-ttu-id="b40f9-105">そのため、パフォーマンスとスケーラビリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-105">This can improve performance and scalability.</span></span> <span data-ttu-id="b40f9-106">また、データ ソースが一時的に使用できない場合でも、キャッシュのデータを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="b40f9-107">.NET Framework には、.NET Framework アプリケーションでキャッシュを使用できるようにするクラスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b40f9-107">The .NET Framework provides classes that enable you to use caching in .NET Framework applications.</span></span> <span data-ttu-id="b40f9-108">これらのクラスは、 <xref:System.Runtime.Caching>名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="b40f9-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="b40f9-109">名前<xref:System.Runtime.Caching>空間は .NET Framework 4 で新しく追加されたものです。</span><span class="sxs-lookup"><span data-stu-id="b40f9-109">The <xref:System.Runtime.Caching> namespace is new in the .NET Framework 4.</span></span> <span data-ttu-id="b40f9-110">この名前空間により、すべての .NET Framework アプリケーションでキャッシュを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b40f9-110">This namespace makes caching is available to all .NET Framework applications.</span></span> <span data-ttu-id="b40f9-111">以前のバージョンの .NET Framework では、キャッシュは<xref:System.Web>名前空間でのみ使用できるため、ASP.NET クラスに依存する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="b40f9-111">In previous versions of the .NET Framework, caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="b40f9-112">このチュートリアルでは、 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]アプリケーションの一部として .NET Framework で使用できるキャッシュ機能を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-112">This walkthrough shows you how to use the caching functionality that is available in the .NET Framework as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="b40f9-113">このチュートリアルでは、テキストファイルの内容をキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="b40f9-114">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="b40f9-114">Tasks illustrated in this walkthrough include the following:</span></span>

- <span data-ttu-id="b40f9-115">WPF アプリケーションプロジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="b40f9-115">Creating a WPF application project.</span></span>

- <span data-ttu-id="b40f9-116">.NET Framework 4 への参照を追加しています。</span><span class="sxs-lookup"><span data-stu-id="b40f9-116">Adding a reference to the .NET Framework 4.</span></span>

- <span data-ttu-id="b40f9-117">キャッシュを初期化しています。</span><span class="sxs-lookup"><span data-stu-id="b40f9-117">Initializing a cache.</span></span>

- <span data-ttu-id="b40f9-118">テキストファイルの内容を含むキャッシュエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-118">Adding a cache entry that contains the contents of a text file.</span></span>

- <span data-ttu-id="b40f9-119">キャッシュエントリの削除ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-119">Providing an eviction policy for the cache entry.</span></span>

- <span data-ttu-id="b40f9-120">キャッシュされたファイルのパスを監視し、監視対象の項目に対する変更についてキャッシュインスタンスに通知します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b40f9-121">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b40f9-121">Prerequisites</span></span>
 <span data-ttu-id="b40f9-122">このチュートリアルを完了するための要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b40f9-122">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="b40f9-123">Microsoft Visual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="b40f9-123">Microsoft Visual Studio 2010.</span></span>

- <span data-ttu-id="b40f9-124">少量のテキストを含むテキストファイル。</span><span class="sxs-lookup"><span data-stu-id="b40f9-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="b40f9-125">(テキストファイルの内容はメッセージボックスに表示されます)。このチュートリアルで示すコードは、次のファイルを操作していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b40f9-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="b40f9-126">ただし、このチュートリアルでは、任意のテキストファイルを使用し、コードに小さな変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="b40f9-127">WPF アプリケーションプロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="b40f9-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="b40f9-128">まず、WPF アプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="b40f9-129">WPF アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="b40f9-129">To create a WPF application</span></span>

1. <span data-ttu-id="b40f9-130">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-130">Start Visual Studio.</span></span>

2. <span data-ttu-id="b40f9-131">**[ファイル]** メニューの **[新規作成]** をクリックし、 **[新しいプロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="b40f9-132">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-132">The **New Project** dialog box is displayed.</span></span>

3. <span data-ttu-id="b40f9-133">**[インストールされたテンプレート]** で、使用するプログラミング言語 (**Visual Basic**または**ビジュアルC#** ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4. <span data-ttu-id="b40f9-134">**[新しいプロジェクト]** ダイアログボックスで、 **[WPF アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b40f9-135">**Wpf アプリケーション**テンプレートが表示されない場合は、wpf をサポートする .NET Framework のバージョンをターゲットにしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b40f9-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the .NET Framework that supports WPF.</span></span> <span data-ttu-id="b40f9-136">**新しいプロジェクト** ダイアログボックスで、一覧から .NET Framework 4 を選択します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-136">In the **New Project** dialog box, select .NET Framework 4 from the list.</span></span>

5. <span data-ttu-id="b40f9-137">**[名前]** テキストボックスに、プロジェクトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="b40f9-138">たとえば、「 **WPFCaching**」と入力できます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-138">For example, you can enter **WPFCaching**.</span></span>

6. <span data-ttu-id="b40f9-139">**[ソリューションのディレクトリを作成]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-139">Select the **Create directory for solution** check box.</span></span>

7. <span data-ttu-id="b40f9-140">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-140">Click **OK**.</span></span>

     <span data-ttu-id="b40f9-141">WPF デザイナーが**デザイン**ビューで開き、mainwindow.xaml ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="b40f9-142">Visual Studio によって、 **My プロジェクト**フォルダー、app.xaml ファイル、および mainwindow.xaml ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="b40f9-143">.NET Framework をターゲットにして、キャッシュアセンブリへの参照を追加する</span><span class="sxs-lookup"><span data-stu-id="b40f9-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="b40f9-144">既定では、WPF アプリケーションは[!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]を対象とします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-144">By default, WPF applications target the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span></span> <span data-ttu-id="b40f9-145">WPF アプリケーションで<xref:System.Runtime.Caching>名前空間を使用するには、アプリケーションが .NET Framework 4 (では[!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]なく) を対象とし、名前空間への参照を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b40f9-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the .NET Framework 4 (not the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="b40f9-146">したがって、次の手順では、.NET Framework ターゲットを変更し、 <xref:System.Runtime.Caching>名前空間への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="b40f9-147">.NET Framework ターゲットを変更する手順は、Visual Basic プロジェクトとビジュアルC#プロジェクトで異なります。</span><span class="sxs-lookup"><span data-stu-id="b40f9-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="b40f9-148">Visual Basic でターゲット .NET Framework を変更するには</span><span class="sxs-lookup"><span data-stu-id="b40f9-148">To change the target .NET Framework in Visual Basic</span></span>

1. <span data-ttu-id="b40f9-149">**ソリューションエクスプローラー**で、プロジェクト名を右クリックし、 **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="b40f9-150">アプリケーションの [プロパティ] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-150">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="b40f9-151">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-151">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="b40f9-152">ウィンドウの下部には、をクリックして**詳細コンパイル オプション**.</span><span class="sxs-lookup"><span data-stu-id="b40f9-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="b40f9-153">**[コンパイラの詳細設定**] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4. <span data-ttu-id="b40f9-154">**[ターゲットフレームワーク (すべての構成)]** ボックスの一覧の [.NET Framework 4] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-154">In the **Target framework (all configurations)** list, select .NET Framework 4.</span></span> <span data-ttu-id="b40f9-155">(は選択[!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]しないでください)。</span><span class="sxs-lookup"><span data-stu-id="b40f9-155">(Do not select [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span></span>

5. <span data-ttu-id="b40f9-156">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-156">Click **OK**.</span></span>

     <span data-ttu-id="b40f9-157">**[ターゲット フレームワークの変更]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-157">The **Target Framework Change** dialog box is displayed.</span></span>

6. <span data-ttu-id="b40f9-158">**[ターゲットフレームワークの変更]** ダイアログボックスで、 **[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="b40f9-159">プロジェクトが閉じられ、再び開きます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-159">The project is closed and is then reopened.</span></span>

7. <span data-ttu-id="b40f9-160">次の手順に従って、キャッシュアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-160">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="b40f9-161">**ソリューションエクスプローラー**で、プロジェクトの名前を右クリックし、[参照の**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="b40f9-162">**.Net** タブを選択`System.Runtime.Caching`し、 を選択して、 **OK** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="b40f9-163">ビジュアルC#プロジェクトのターゲット .NET Framework を変更するには</span><span class="sxs-lookup"><span data-stu-id="b40f9-163">To change the target .NET Framework in a Visual C# project</span></span>

1. <span data-ttu-id="b40f9-164">**ソリューションエクスプローラー**で、プロジェクト名を右クリックし、 **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="b40f9-165">アプリケーションの [プロパティ] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-165">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="b40f9-166">**[アプリケーション]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-166">Click the **Application** tab.</span></span>

3. <span data-ttu-id="b40f9-167">**ターゲットフレームワーク** ボックスの一覧で .NET Framework 4 を選択します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-167">In the **Target framework** list, select .NET Framework 4.</span></span> <span data-ttu-id="b40f9-168">( **.NET Framework 4 クライアントプロファイル**を選択しないでください)。</span><span class="sxs-lookup"><span data-stu-id="b40f9-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4. <span data-ttu-id="b40f9-169">次の手順に従って、キャッシュアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-169">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="b40f9-170">**[参照]** フォルダーを右クリックし、 **[参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="b40f9-171">**.Net** タブを選択`System.Runtime.Caching`し、 を選択して、 **OK** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="b40f9-172">WPF ウィンドウへのボタンの追加</span><span class="sxs-lookup"><span data-stu-id="b40f9-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="b40f9-173">次に、ボタンコントロールを追加し、ボタンの`Click`イベントのイベントハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="b40f9-174">その後、ボタンをクリックすると、テキストファイルの内容がキャッシュされて表示されるように、後でコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="b40f9-175">ボタンコントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="b40f9-175">To add a button control</span></span>

1. <span data-ttu-id="b40f9-176">**ソリューションエクスプローラー**で、mainwindow.xaml ファイルをダブルクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2. <span data-ttu-id="b40f9-177">**ツールボックス** **コモン WPF コントロール** 、ドラッグ、 `Button` への制御、 `MainWindow` ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="b40f9-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3. <span data-ttu-id="b40f9-178">**[プロパティ]** ウィンドウで、キャッシュ`Content`を**取得**する`Button`コントロールのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="b40f9-179">キャッシュを初期化してエントリをキャッシュする</span><span class="sxs-lookup"><span data-stu-id="b40f9-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="b40f9-180">次に、次のタスクを実行するためのコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-180">Next, you will add the code to perform the following tasks:</span></span>

- <span data-ttu-id="b40f9-181">キャッシュクラスのインスタンスを作成します。つまり、新しい<xref:System.Runtime.Caching.MemoryCache>オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

- <span data-ttu-id="b40f9-182">キャッシュがオブジェクトを<xref:System.Runtime.Caching.HostFileChangeMonitor>使用してテキストファイルの変更を監視するように指定します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

- <span data-ttu-id="b40f9-183">テキストファイルを読み取り、キャッシュエントリとしてその内容をキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-183">Read the text file and cache its contents as a cache entry.</span></span>

- <span data-ttu-id="b40f9-184">キャッシュされたテキストファイルの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="b40f9-185">キャッシュオブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="b40f9-185">To create the cache object</span></span>

1. <span data-ttu-id="b40f9-186">MainWindow.xaml.cs または Mainwindow.xaml ファイルでイベントハンドラーを作成するために、追加したボタンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2. <span data-ttu-id="b40f9-187">(クラス宣言の前に) ファイルの先頭に、次`Imports`の (Visual Basic) ステートメントまたは`using` (C#) ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. <span data-ttu-id="b40f9-188">イベントハンドラーで、次のコードを追加して、キャッシュオブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="b40f9-189"><xref:System.Runtime.Caching.ObjectCache>クラスは、メモリ内オブジェクトキャッシュを提供する組み込みのクラスです。</span><span class="sxs-lookup"><span data-stu-id="b40f9-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4. <span data-ttu-id="b40f9-190">次のコードを追加して、という名前`filecontents`のキャッシュエントリの内容を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="b40f9-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. <span data-ttu-id="b40f9-191">次のコードを追加して、という名前`filecontents`のキャッシュエントリが存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="b40f9-192">指定したキャッシュエントリが存在しない場合は、テキストファイルを読み取り、キャッシュエントリとしてキャッシュに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b40f9-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6. <span data-ttu-id="b40f9-193">ブロックで、次のコードを追加して、10 <xref:System.Runtime.Caching.CacheItemPolicy>秒後にキャッシュエントリの有効期限が切れることを指定する新しいオブジェクトを作成します。 `if/then`</span><span class="sxs-lookup"><span data-stu-id="b40f9-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="b40f9-194">削除または有効期限の情報が指定されて<xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>いない場合、既定値はになります。これは、キャッシュエントリが絶対時間だけで期限切れにならないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="b40f9-195">代わりに、メモリが不足している場合にのみ、キャッシュエントリの有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="b40f9-196">ベストプラクティスとして、絶対有効期限またはスライド式有効期限を常に明示的に指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-196">As a best practice, you should always explicitly provide either an absolute or a sliding expiration.</span></span>

7. <span data-ttu-id="b40f9-197">`if/then`ブロック内で、前の手順で追加したコードの後に次のコードを追加して、監視するファイルパスのコレクションを作成し、テキストファイルのパスをコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    > <span data-ttu-id="b40f9-198">使用するテキストファイルがでない`c:\cache\cacheText.txt`場合は、使用するテキストファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8. <span data-ttu-id="b40f9-199">前の手順で追加したコードの後に、次のコードを追加して<xref:System.Runtime.Caching.HostFileChangeMonitor> 、キャッシュエントリの変更モニターのコレクションに新しいオブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="b40f9-200">オブジェクト<xref:System.Runtime.Caching.HostFileChangeMonitor>は、テキストファイルのパスを監視し、変更が発生した場合はキャッシュに通知します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="b40f9-201">この例では、ファイルの内容が変更されると、キャッシュエントリの有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="b40f9-202">前の手順で追加したコードの後に、テキストファイルの内容を読み取る次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="b40f9-203">日付と時刻のタイムスタンプが追加されるので、キャッシュエントリの有効期限が切れるタイミングを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="b40f9-204">前の手順で追加したコードの後に、次のコードを追加して、ファイルの内容を<xref:System.Runtime.Caching.CacheItem>インスタンスとしてキャッシュオブジェクトに挿入します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="b40f9-205">前の手順で作成した<xref:System.Runtime.Caching.CacheItemPolicy>オブジェクトをパラメーターとして渡すことによって、キャッシュエントリを削除する方法に関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="b40f9-206">ブロックの`if/then`後に、キャッシュされたファイルの内容をメッセージボックスに表示する次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="b40f9-207">**[ビルド]** メニューの **[WPFCaching のビルド]** をクリックして、プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="b40f9-208">WPF アプリケーションでのキャッシュのテスト</span><span class="sxs-lookup"><span data-stu-id="b40f9-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="b40f9-209">これで、アプリケーションをテストできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b40f9-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="b40f9-210">WPF アプリケーションでキャッシュをテストするには</span><span class="sxs-lookup"><span data-stu-id="b40f9-210">To test caching in the WPF application</span></span>

1. <span data-ttu-id="b40f9-211">Ctrl キーを押しながら F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="b40f9-212">`MainWindow`ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-212">The `MainWindow` window is displayed.</span></span>

2. <span data-ttu-id="b40f9-213">**[キャッシュの取得]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="b40f9-214">テキストファイルからキャッシュされたコンテンツがメッセージボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="b40f9-215">ファイルのタイムスタンプに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b40f9-215">Notice the timestamp on the file.</span></span>

3. <span data-ttu-id="b40f9-216">メッセージボックスを閉じ、 **[キャッシュの取得]** をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-216">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="b40f9-217">タイムスタンプは変更されません。</span><span class="sxs-lookup"><span data-stu-id="b40f9-217">The timestamp is unchanged.</span></span> <span data-ttu-id="b40f9-218">これは、キャッシュされたコンテンツが表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-218">This indicates the cached content is displayed.</span></span>

4. <span data-ttu-id="b40f9-219">10秒以上待ってから、 **[キャッシュの取得]** をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="b40f9-220">今回は、新しいタイムスタンプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="b40f9-221">これは、ポリシーによってキャッシュエントリの有効期限が切れ、キャッシュされた新しいコンテンツが表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5. <span data-ttu-id="b40f9-222">テキストエディターで、作成したテキストファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="b40f9-223">まだ変更を加えないでください。</span><span class="sxs-lookup"><span data-stu-id="b40f9-223">Do not make any changes yet.</span></span>

6. <span data-ttu-id="b40f9-224">メッセージボックスを閉じ、 **[キャッシュの取得]** をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-224">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="b40f9-225">タイムスタンプに再び注目します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-225">Notice the timestamp again.</span></span>

7. <span data-ttu-id="b40f9-226">テキストファイルに変更を加え、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-226">Make a change to the text file and then save the file.</span></span>

8. <span data-ttu-id="b40f9-227">メッセージボックスを閉じ、 **[キャッシュの取得]** をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="b40f9-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="b40f9-228">このメッセージボックスには、テキストファイルから更新されたコンテンツと新しいタイムスタンプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b40f9-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="b40f9-229">これは、絶対タイムアウト期間が経過していないにもかかわらず、ファイルを変更した直後にホストファイルの変更モニターによってキャッシュエントリが削除されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="b40f9-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b40f9-230">ファイルに変更を加える時間を増やすために、削除時間を20秒以上に増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="b40f9-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="b40f9-231">コード例</span><span class="sxs-lookup"><span data-stu-id="b40f9-231">Code Example</span></span>
 <span data-ttu-id="b40f9-232">このチュートリアルを完了すると、作成したプロジェクトのコードは次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="b40f9-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="b40f9-233">関連項目</span><span class="sxs-lookup"><span data-stu-id="b40f9-233">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="b40f9-234">.NET Framework アプリケーションでのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="b40f9-234">Caching in .NET Framework Applications</span></span>](../../performance/caching-in-net-framework-applications.md)
