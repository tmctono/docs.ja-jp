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
ms.openlocfilehash: 1d00c222dabf446c7c102307c3b904d3f1ff4bca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007280"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="1ecf4-102">チュートリアル: WPF アプリケーション内のアプリケーション データのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="1ecf4-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="1ecf4-103">キャッシュを使用すると、メモリにデータを格納して高速にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="1ecf4-104">アプリケーションからそのデータに再アクセスするときに、元のソースからではなく、キャッシュからデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-104">When the data is accessed again, applications can get the data from the cache instead of retrieving it from the original source.</span></span> <span data-ttu-id="1ecf4-105">そのため、パフォーマンスとスケーラビリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-105">This can improve performance and scalability.</span></span> <span data-ttu-id="1ecf4-106">また、データ ソースが一時的に使用できない場合でも、キャッシュのデータを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="1ecf4-107">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]でキャッシュを使用するためのクラスを提供します[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides classes that enable you to use caching in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="1ecf4-108">これらのクラスにある、<xref:System.Runtime.Caching>名前空間。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
>  <span data-ttu-id="1ecf4-109"><xref:System.Runtime.Caching>名前空間はの新機能、[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-109">The <xref:System.Runtime.Caching> namespace is new in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="1ecf4-110">この名前空間は、すべてに使用可能なキャッシュは[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-110">This namespace makes caching is available to all [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="1ecf4-111">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] の以前のバージョンでは、キャッシュは <xref:System.Web> 名前空間でのみ使用可能だったため、ASP.NET クラスへの依存が必要でした。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-111">In previous versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="1ecf4-112">このチュートリアルで使用できるキャッシュ機能を使用する方法、[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]の一部として、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-112">This walkthrough shows you how to use the caching functionality that is available in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="1ecf4-113">チュートリアルでは、テキスト ファイルの内容をキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="1ecf4-114">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-114">Tasks illustrated in this walkthrough include the following:</span></span>

- <span data-ttu-id="1ecf4-115">WPF アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-115">Creating a WPF application project.</span></span>

- <span data-ttu-id="1ecf4-116">参照を追加、[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-116">Adding a reference to the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>

- <span data-ttu-id="1ecf4-117">キャッシュを初期化しています。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-117">Initializing a cache.</span></span>

- <span data-ttu-id="1ecf4-118">テキスト ファイルの内容を格納するキャッシュ エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-118">Adding a cache entry that contains the contents of a text file.</span></span>

- <span data-ttu-id="1ecf4-119">キャッシュ エントリの削除ポリシーを提供します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-119">Providing an eviction policy for the cache entry.</span></span>

- <span data-ttu-id="1ecf4-120">キャッシュされたファイルのパスの監視と通知する、キャッシュ インスタンスは、監視対象の項目に変更します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1ecf4-121">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1ecf4-121">Prerequisites</span></span>
 <span data-ttu-id="1ecf4-122">このチュートリアルを完了するための要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-122">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="1ecf4-123">Microsoft Visual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-123">Microsoft Visual Studio 2010.</span></span>

- <span data-ttu-id="1ecf4-124">少量のテキストを含むテキスト ファイル。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="1ecf4-125">(テキスト ファイルの内容は、メッセージ ボックスに表示されます)。このチュートリアルで示すコードでは、次のファイルを使用していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="1ecf4-126">ただし、テキスト ファイルを使用し、このチュートリアルのコードに小さな変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="1ecf4-127">WPF アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="1ecf4-128">WPF アプリケーション プロジェクトの作成から始めます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="1ecf4-129">WPF アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="1ecf4-129">To create a WPF application</span></span>

1. <span data-ttu-id="1ecf4-130">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-130">Start Visual Studio.</span></span>

2. <span data-ttu-id="1ecf4-131">**ファイル** メニューのをクリックして**新規**、 をクリックし、**新しいプロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="1ecf4-132">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-132">The **New Project** dialog box is displayed.</span></span>

3. <span data-ttu-id="1ecf4-133">**インストールされたテンプレート**、使用するプログラミング言語を選択します (**Visual Basic**または**Visual c#**)。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4. <span data-ttu-id="1ecf4-134">**新しいプロジェクト**ダイアログ ボックスで、 **WPF アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="1ecf4-135">表示されない場合、 **WPF アプリケーション**テンプレートのバージョンをターゲットにするかどうかを確認、 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] WPF をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] that supports WPF.</span></span> <span data-ttu-id="1ecf4-136">**新しいプロジェクト**ダイアログ ボックスで、[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]一覧から。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-136">In the **New Project** dialog box, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] from the list.</span></span>

5. <span data-ttu-id="1ecf4-137">**名前**テキスト ボックスに、プロジェクトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="1ecf4-138">たとえば、入力**WPFCaching**します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-138">For example, you can enter **WPFCaching**.</span></span>

6. <span data-ttu-id="1ecf4-139">**[ソリューションのディレクトリを作成]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-139">Select the **Create directory for solution** check box.</span></span>

7. <span data-ttu-id="1ecf4-140">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-140">Click **OK**.</span></span>

     <span data-ttu-id="1ecf4-141">WPF デザイナーで開きます**デザイン**を表示し、MainWindow.xaml ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="1ecf4-142">Visual Studio によって作成、 **My Project**フォルダーや、Application.xaml ファイル MainWindow.xaml ファイル。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="1ecf4-143">.NET Framework を対象として、キャッシュのアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="1ecf4-144">既定では、WPF アプリケーションのターゲットによって、[!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-144">By default, WPF applications target the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span></span> <span data-ttu-id="1ecf4-145">使用する、 <xref:System.Runtime.Caching> WPF アプリケーションで名前空間は、アプリケーションを対象にする、 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (いない、 [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) 名前空間への参照を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (not the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="1ecf4-146">したがって、次の手順が、.NET Framework のターゲットを変更しへの参照を追加するは、<xref:System.Runtime.Caching>名前空間。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
>  <span data-ttu-id="1ecf4-147">.NET Framework のターゲットを変更する手順は、Visual Basic プロジェクトおよび Visual c# プロジェクトでは異なります。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="1ecf4-148">Visual Basic での .NET Framework のターゲットを変更するには</span><span class="sxs-lookup"><span data-stu-id="1ecf4-148">To change the target .NET Framework in Visual Basic</span></span>

1. <span data-ttu-id="1ecf4-149">**ソリューション エクスプ ローラー**プロジェクト名を右クリックし、クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="1ecf4-150">アプリケーションのプロパティ ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-150">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="1ecf4-151">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-151">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="1ecf4-152">ウィンドウの下部には、をクリックして**詳細コンパイル オプション**.</span><span class="sxs-lookup"><span data-stu-id="1ecf4-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="1ecf4-153">**コンパイラの詳細設定** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4. <span data-ttu-id="1ecf4-154">**ターゲット フレームワーク (すべての構成)** 一覧で、[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-154">In the **Target framework (all configurations)** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="1ecf4-155">(選択しないでください[!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-155">(Do not select [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span></span>

5. <span data-ttu-id="1ecf4-156">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-156">Click **OK**.</span></span>

     <span data-ttu-id="1ecf4-157">**[ターゲット フレームワークの変更]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-157">The **Target Framework Change** dialog box is displayed.</span></span>

6. <span data-ttu-id="1ecf4-158">**ターゲット フレームワークの変更**ダイアログ ボックスで、をクリックして**はい**します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="1ecf4-159">プロジェクトは閉じられ、再度は。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-159">The project is closed and is then reopened.</span></span>

7. <span data-ttu-id="1ecf4-160">次の手順では、キャッシュのアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-160">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="1ecf4-161">**ソリューション エクスプ ローラー**プロジェクトの名前を右クリックし、クリックして**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="1ecf4-162">選択、 **.NET** ] タブで [ `System.Runtime.Caching`、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="1ecf4-163">Visual c# プロジェクトで .NET Framework ターゲットを変更するには</span><span class="sxs-lookup"><span data-stu-id="1ecf4-163">To change the target .NET Framework in a Visual C# project</span></span>

1. <span data-ttu-id="1ecf4-164">**ソリューション エクスプ ローラー**プロジェクト名を右クリックし、クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="1ecf4-165">アプリケーションのプロパティ ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-165">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="1ecf4-166">**[アプリケーション]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-166">Click the **Application** tab.</span></span>

3. <span data-ttu-id="1ecf4-167">**ターゲット フレームワーク**一覧で、[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-167">In the **Target framework** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="1ecf4-168">(選択しないでください **.NET Framework 4 Client Profile**)。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4. <span data-ttu-id="1ecf4-169">次の手順では、キャッシュのアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-169">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="1ecf4-170">右クリックし、**参照**フォルダーをクリック**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="1ecf4-171">選択、 **.NET** ] タブで [ `System.Runtime.Caching`、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="1ecf4-172">WPF ウィンドウにボタンの追加</span><span class="sxs-lookup"><span data-stu-id="1ecf4-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="1ecf4-173">次に、ボタン コントロールを追加し、ボタンのイベント ハンドラーを作成`Click`イベント。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="1ecf4-174">後で、テキスト ファイルの内容がキャッシュされ、表示されるボタンをクリックすると、コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="1ecf4-175">ボタン コントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="1ecf4-175">To add a button control</span></span>

1. <span data-ttu-id="1ecf4-176">**ソリューション エクスプ ローラー**、開く MainWindow.xaml ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2. <span data-ttu-id="1ecf4-177">**ツールボックス** **コモン WPF コントロール** 、ドラッグ、 `Button` への制御、 `MainWindow` ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3. <span data-ttu-id="1ecf4-178">**プロパティ**ウィンドウで、設定、`Content`のプロパティ、`Button`に制御を**取得キャッシュ**します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="1ecf4-179">キャッシュの初期化とエントリをキャッシュ</span><span class="sxs-lookup"><span data-stu-id="1ecf4-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="1ecf4-180">次に、次のタスクを実行するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-180">Next, you will add the code to perform the following tasks:</span></span>

- <span data-ttu-id="1ecf4-181">キャッシュ クラスのインスタンスを作成-これは、インスタンス化する新しい<xref:System.Runtime.Caching.MemoryCache>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

- <span data-ttu-id="1ecf4-182">キャッシュが使用するように指定、<xref:System.Runtime.Caching.HostFileChangeMonitor>のテキスト ファイルの変更を監視するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

- <span data-ttu-id="1ecf4-183">テキスト ファイルを読み取るし、キャッシュ エントリとしてその内容をキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-183">Read the text file and cache its contents as a cache entry.</span></span>

- <span data-ttu-id="1ecf4-184">キャッシュされたテキスト ファイルの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="1ecf4-185">キャッシュ オブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="1ecf4-185">To create the cache object</span></span>

1. <span data-ttu-id="1ecf4-186">MainWindow.xaml.cs または MainWindow.Xaml.vb ファイルで、イベント ハンドラーを作成するために追加したボタンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2. <span data-ttu-id="1ecf4-187">次のコードを追加 (クラス宣言) の前に、ファイルの上部にある`Imports`(Visual Basic) または`using`ステートメント (c#)。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. <span data-ttu-id="1ecf4-188">イベント ハンドラーでは、キャッシュ オブジェクトをインスタンス化する次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="1ecf4-189"><xref:System.Runtime.Caching.ObjectCache>クラスは、メモリ内オブジェクト キャッシュを提供する組み込みのクラスです。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4. <span data-ttu-id="1ecf4-190">という名前のキャッシュ エントリの内容を読み取るには、次のコードを追加`filecontents`:</span><span class="sxs-lookup"><span data-stu-id="1ecf4-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. <span data-ttu-id="1ecf4-191">キャッシュ エントリが名前付きかどうかを確認するには、次のコードを追加`filecontents`存在します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="1ecf4-192">指定したキャッシュ エントリが存在しない場合は、テキスト ファイルの読み取りし、キャッシュのエントリとしてキャッシュに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6. <span data-ttu-id="1ecf4-193">`if/then`ブロック、新たに作成する次のコードを追加<xref:System.Runtime.Caching.CacheItemPolicy>キャッシュ エントリが 10 秒後に有効期限が切れるを指定するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="1ecf4-194">削除または有効期限の情報が指定されていない場合、既定値は<xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>、絶対時間にのみに基づいて切れないので、キャッシュ エントリ。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="1ecf4-195">代わりに、キャッシュ エントリは、メモリ負荷がある場合にのみ有効期限します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="1ecf4-196">ベスト プラクティスとして、絶対またはスライド式有効期限のいずれかを常に明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-196">As a best practice, you should always explicitly provide either an absolute or a sliding expiration.</span></span>

7. <span data-ttu-id="1ecf4-197">内で、`if/then`をブロックし、前の手順で追加したコードの後を監視して、コレクションにテキスト ファイルのパスを追加するファイルのパスのコレクションを作成するには、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    >  <span data-ttu-id="1ecf4-198">使用するテキスト ファイルがない`c:\cache\cacheText.txt`、テキスト ファイルが使用する場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8. <span data-ttu-id="1ecf4-199">新しいを追加するには、次のコードを追加する前の手順で追加したコードを次<xref:System.Runtime.Caching.HostFileChangeMonitor>キャッシュ エントリの変更のコレクションにオブジェクトを監視します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="1ecf4-200"><xref:System.Runtime.Caching.HostFileChangeMonitor>オブジェクトは、テキスト ファイルのパスを監視し、変更が発生した場合、キャッシュに通知します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="1ecf4-201">この例で、ファイルの内容が変更された場合、キャッシュ エントリの有効期限します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="1ecf4-202">前の手順で追加したコードの後に、テキスト ファイルの内容を読み取るには、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="1ecf4-203">キャッシュ エントリの有効期限が切れるときに表示できるように、日付と時刻のタイムスタンプが追加されます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="1ecf4-204">としてキャッシュ オブジェクトに、ファイルの内容を挿入する次のコードを追加する前の手順で追加したコードの後、<xref:System.Runtime.Caching.CacheItem>インスタンス。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="1ecf4-205">渡すことによって、キャッシュ エントリを削除する方法に関する情報を指定する、<xref:System.Runtime.Caching.CacheItemPolicy>をパラメーターとして、先ほど作成したオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="1ecf4-206">後に、`if/then`ブロック、メッセージ ボックスに、キャッシュされたファイルの内容を表示する次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="1ecf4-207">**ビルド** メニューのをクリックして**ビルド WPFCaching**プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="1ecf4-208">WPF アプリケーションでのキャッシュのテスト</span><span class="sxs-lookup"><span data-stu-id="1ecf4-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="1ecf4-209">アプリケーションをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="1ecf4-210">WPF アプリケーションでキャッシュをテストするには</span><span class="sxs-lookup"><span data-stu-id="1ecf4-210">To test caching in the WPF application</span></span>

1. <span data-ttu-id="1ecf4-211">Ctrl キーを押しながら F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="1ecf4-212">`MainWindow`ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-212">The `MainWindow` window is displayed.</span></span>

2. <span data-ttu-id="1ecf4-213">クリックして**キャッシュを取得する**します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="1ecf4-214">テキスト ファイルからキャッシュされたコンテンツは、メッセージ ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="1ecf4-215">ファイルのタイムスタンプに注目してください。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-215">Notice the timestamp on the file.</span></span>

3. <span data-ttu-id="1ecf4-216">メッセージ ボックスを閉じ、クリックして**取得キャッシュ**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-216">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="1ecf4-217">タイムスタンプは変更されません。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-217">The timestamp is unchanged.</span></span> <span data-ttu-id="1ecf4-218">これは、キャッシュされたコンテンツの表示を示します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-218">This indicates the cached content is displayed.</span></span>

4. <span data-ttu-id="1ecf4-219">クリックして、10 秒以上待機**取得キャッシュ**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="1ecf4-220">この時間に、新しいタイムスタンプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="1ecf4-221">これは、ポリシーが有効期限が切れるキャッシュ エントリを使用し、新しいキャッシュされたコンテンツが表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5. <span data-ttu-id="1ecf4-222">テキスト エディターで作成したテキスト ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="1ecf4-223">すべての変更をまだしないでください。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-223">Do not make any changes yet.</span></span>

6. <span data-ttu-id="1ecf4-224">メッセージ ボックスを閉じ、クリックして**取得キャッシュ**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-224">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="1ecf4-225">もう一度、タイムスタンプに注目してください。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-225">Notice the timestamp again.</span></span>

7. <span data-ttu-id="1ecf4-226">テキスト ファイルに変更を加えるし、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-226">Make a change to the text file and then save the file.</span></span>

8. <span data-ttu-id="1ecf4-227">メッセージ ボックスを閉じ、クリックして**取得キャッシュ**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="1ecf4-228">このメッセージ ボックスには、テキスト ファイルと新しいタイムスタンプから更新されたコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="1ecf4-229">これは、ホスト ファイルの変更モニター削除されるキャッシュ エントリ、ファイルを変更したときにすぐに、絶対のタイムアウト期間の有効期限が切れていない場合でもを示します。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="1ecf4-230">ファイルを変更するための時間を 20 秒以上削除時間を増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="1ecf4-231">コード例</span><span class="sxs-lookup"><span data-stu-id="1ecf4-231">Code Example</span></span>
 <span data-ttu-id="1ecf4-232">このチュートリアルを完了すると後に、作成したプロジェクトのコードが次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="1ecf4-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="1ecf4-233">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ecf4-233">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="1ecf4-234">.NET Framework アプリケーションでのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="1ecf4-234">Caching in .NET Framework Applications</span></span>](../../performance/caching-in-net-framework-applications.md)
