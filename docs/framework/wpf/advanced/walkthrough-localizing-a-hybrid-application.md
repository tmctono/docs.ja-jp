---
title: 'チュートリアル : ハイブリッド アプリケーションのローカライズ'
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 69aa5ae145ffe378b7a4547e5a33826965bf7894
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111115"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="c2821-102">チュートリアル : ハイブリッド アプリケーションのローカライズ</span><span class="sxs-lookup"><span data-stu-id="c2821-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="c2821-103">このチュートリアルでは、Windows フォーム[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ベースのハイブリッド アプリケーションで要素をローカライズする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c2821-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a Windows Forms-based hybrid application.</span></span>

<span data-ttu-id="c2821-104">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="c2821-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="c2821-105">Windows フォーム ホスト プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2821-105">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="c2821-106">ローカライズ可能なコンテンツを追加しています。</span><span class="sxs-lookup"><span data-stu-id="c2821-106">Adding localizable content.</span></span>

- <span data-ttu-id="c2821-107">ローカライズを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c2821-107">Enabling localization.</span></span>

- <span data-ttu-id="c2821-108">リソース識別子の割り当て。</span><span class="sxs-lookup"><span data-stu-id="c2821-108">Assigning resource identifiers.</span></span>

- <span data-ttu-id="c2821-109">LocBaml ツールを使用して、サテライト アセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="c2821-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="c2821-110">このチュートリアルで説明するタスクの完全なコードリストについては、「ハイブリッド[アプリケーションのサンプルのローカライズ](https://go.microsoft.com/fwlink/?LinkID=160015)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2821-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="c2821-111">完了すると、ローカライズされたハイブリッド アプリケーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c2821-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c2821-112">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c2821-112">Prerequisites</span></span>

<span data-ttu-id="c2821-113">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="c2821-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="c2821-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="c2821-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="c2821-115">Windows フォーム ホスト プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="c2821-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="c2821-116">最初の手順では、Windows フォーム アプリケーション プロジェクトを作成[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]し、ローカライズするコンテンツを含む要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="c2821-116">The first step is to create the Windows Forms application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="c2821-117">ホスト プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="c2821-117">To create the host project</span></span>

1. <span data-ttu-id="c2821-118">という名前の**WPF** `LocalizingWpfInWf`アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2821-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="c2821-119">(**ファイル** > **新しい** > **プロジェクト** > **Visual C#** または Visual **Basic** > クラシック**デスクトップ** > WPF**アプリケーション**)</span><span class="sxs-lookup"><span data-stu-id="c2821-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2. <span data-ttu-id="c2821-120">プロジェクトに[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl>呼び`SimpleControl`出される要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="c2821-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3. <span data-ttu-id="c2821-121">コントロールを<xref:System.Windows.Forms.Integration.ElementHost>使用して、フォーム`SimpleControl`上に要素を配置します。</span><span class="sxs-lookup"><span data-stu-id="c2821-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="c2821-122">詳細については、「[チュートリアル : Windows フォームでの 3D WPF 複合コントロールのホスト](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2821-122">For more information, see [Walkthrough: Hosting a 3D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="c2821-123">ローカライズ可能なコンテンツの追加</span><span class="sxs-lookup"><span data-stu-id="c2821-123">Adding Localizable Content</span></span>

<span data-ttu-id="c2821-124">次に、Windows フォーム のラベル コントロールを追加[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]し、要素の内容をローカライズ可能な文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="c2821-124">Next, you will add a Windows Forms label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="c2821-125">ローカライズ可能なコンテンツを追加するには</span><span class="sxs-lookup"><span data-stu-id="c2821-125">To add localizable content</span></span>

1. <span data-ttu-id="c2821-126">**ソリューション エクスプローラー**で、 **SimpleControl.xaml**をダブルクリックして、WPF デザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="c2821-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the WPF Designer.</span></span>

2. <span data-ttu-id="c2821-127">次のコードを使用<xref:System.Windows.Controls.Button>して、コントロールの内容を設定します。</span><span class="sxs-lookup"><span data-stu-id="c2821-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. <span data-ttu-id="c2821-128">**ソリューション エクスプローラー**で **、[Form1]** をダブルクリックして Windows フォーム デザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="c2821-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="c2821-129">**ツールボックス**を開き、[**ラベル**] をダブルクリックして、フォームにラベル コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="c2821-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="c2821-130"><xref:System.Windows.Forms.Control.Text%2A> プロパティの値を `"Hello"` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c2821-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5. <span data-ttu-id="c2821-131">**F5 キー**を押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="c2821-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="c2821-132">`SimpleControl`要素とラベル コントロールの両方に **"Hello"** というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2821-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="c2821-133">ローカリゼーションの有効化</span><span class="sxs-lookup"><span data-stu-id="c2821-133">Enabling Localization</span></span>

<span data-ttu-id="c2821-134">Windows フォーム デザイナーには、サテライト アセンブリのローカライズを有効にするための設定が用意されています。</span><span class="sxs-lookup"><span data-stu-id="c2821-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="c2821-135">ローカリゼーションを有効にするには</span><span class="sxs-lookup"><span data-stu-id="c2821-135">To enable localization</span></span>

1. <span data-ttu-id="c2821-136">**ソリューション エクスプローラー**で **、Form1.cs**をダブルクリックして、Windows フォーム デザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="c2821-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="c2821-137">[**プロパティ]** ウィンドウで、フォームの **"ローカライズ可能**" プロパティの値を`true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="c2821-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3. <span data-ttu-id="c2821-138">[**プロパティ**] ウィンドウで **、Language**プロパティの値を**スペイン語 (スペイン)** に設定します。</span><span class="sxs-lookup"><span data-stu-id="c2821-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4. <span data-ttu-id="c2821-139">Windows フォーム デザイナーで、ラベル コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="c2821-139">In the Windows Forms Designer, select the label control.</span></span>

5. <span data-ttu-id="c2821-140">[**プロパティ]** ウィンドウで、プロパティの値<xref:System.Windows.Forms.Control.Text%2A>を`"Hola"`に設定します。</span><span class="sxs-lookup"><span data-stu-id="c2821-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="c2821-141">Form1.es-ES.resx という名前の新しいリソース ファイルがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c2821-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6. <span data-ttu-id="c2821-142">**ソリューション エクスプローラー**で **、Form1.cs**を右クリックし、[**コードの表示**] をクリックしてコード エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="c2821-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7. <span data-ttu-id="c2821-143">コンストラクターに次のコードを`Form1`コピーします`InitializeComponent`。</span><span class="sxs-lookup"><span data-stu-id="c2821-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. <span data-ttu-id="c2821-144">**ソリューション エクスプローラー**で **、[LocalizingWpfInWf]** を右クリックし、[**プロジェクトのアンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2821-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="c2821-145">プロジェクト名には、(**利用不可)** というラベルが付いています。</span><span class="sxs-lookup"><span data-stu-id="c2821-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="c2821-146">を右クリックし、[**ローカライズするWpfInWf.csproj**の編集] をクリックします。 **LocalizingWpfInWf**</span><span class="sxs-lookup"><span data-stu-id="c2821-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="c2821-147">プロジェクト ファイルがコード エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="c2821-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="c2821-148">次の行をプロジェクト ファイル`PropertyGroup`の最初の行にコピーします。</span><span class="sxs-lookup"><span data-stu-id="c2821-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="c2821-149">プロジェクト ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="c2821-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="c2821-150">**ソリューション エクスプローラー**で **、[LocalizingWpfInWf]** を右クリックし、[**プロジェクトの再読み込み**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2821-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="c2821-151">リソース識別子の割り当て</span><span class="sxs-lookup"><span data-stu-id="c2821-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="c2821-152">リソース識別子を使用して、ローカライズ可能なコンテンツをリソース アセンブリにマップできます。</span><span class="sxs-lookup"><span data-stu-id="c2821-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="c2821-153">MsBuild.exe アプリケーションは、オプションを指定すると、リソース識別子を`updateuid`自動的に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c2821-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="c2821-154">リソース識別子を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="c2821-154">To assign resource identifiers</span></span>

1. <span data-ttu-id="c2821-155">[スタート] メニューから、Visual Studio の開発者コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="c2821-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2. <span data-ttu-id="c2821-156">次のコマンドを使用して、ローカライズ可能なコンテンツにリソース識別子を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c2821-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. <span data-ttu-id="c2821-157">**ソリューション エクスプローラー**で **、SimpleControl.xaml**をダブルクリックしてコード エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="c2821-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="c2821-158">コマンドがすべての要素に`msbuild`属性を`Uid`追加したことがわかります。</span><span class="sxs-lookup"><span data-stu-id="c2821-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="c2821-159">これにより、リソース識別子の割り当てによってローカリゼーションが容易になります。</span><span class="sxs-lookup"><span data-stu-id="c2821-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. <span data-ttu-id="c2821-160">**F6** キーを押して、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="c2821-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="c2821-161">LocBaml を使用したサテライト アセンブリの生成</span><span class="sxs-lookup"><span data-stu-id="c2821-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="c2821-162">ローカライズされたコンテンツは、 リソース専用サ*テライト アセンブリ*に格納されます。</span><span class="sxs-lookup"><span data-stu-id="c2821-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="c2821-163">コンテンツ用のローカライズされたアセンブリを生成するには、コマンド ライン ツール LocBaml.exe を使用します[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c2821-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="c2821-164">サテライト アセンブリを作成するには</span><span class="sxs-lookup"><span data-stu-id="c2821-164">To produce a satellite assembly</span></span>

1. <span data-ttu-id="c2821-165">LocBaml.exe をプロジェクトの obj\Debug フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c2821-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="c2821-166">詳細については、「[アプリケーションのローカライズ](how-to-localize-an-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2821-166">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

2. <span data-ttu-id="c2821-167">コマンド プロンプト ウィンドウで、次のコマンドを使用して、リソース文字列を一時ファイルに抽出します。</span><span class="sxs-lookup"><span data-stu-id="c2821-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. <span data-ttu-id="c2821-168">Visual Studio または別のテキスト エディターで temp.csv ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c2821-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="c2821-169">文字列`"Hello"`をスペイン語の翻訳に置`"Hola"`き換えます。</span><span class="sxs-lookup"><span data-stu-id="c2821-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4. <span data-ttu-id="c2821-170">temp.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="c2821-170">Save the temp.csv file.</span></span>

5. <span data-ttu-id="c2821-171">ローカライズされたリソース ファイルを生成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2821-171">Use the following command to generate the localized resource file.</span></span>

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="c2821-172">LocalizingWpfInWf.g.es-ES.resources ファイルは obj\Debug フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="c2821-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6. <span data-ttu-id="c2821-173">ローカライズされたサテライト アセンブリをビルドするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2821-173">Use the following command to build the localized satellite assembly.</span></span>

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="c2821-174">ファイルは obj\デバッグ フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="c2821-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7. <span data-ttu-id="c2821-175">プロジェクトの bin\Debug\es-ES フォルダーにローカライズWpfInWf.resources.dll ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="c2821-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="c2821-176">既存のファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c2821-176">Replace the existing file.</span></span>

8. <span data-ttu-id="c2821-177">プロジェクトの bin\Debug フォルダーにあるローカライズWpfInWf.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2821-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="c2821-178">アプリケーションを再構築しないか、サテライト アセンブリが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="c2821-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="c2821-179">アプリケーションは、英語の文字列の代わりにローカライズされた文字列を表示します。</span><span class="sxs-lookup"><span data-stu-id="c2821-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2821-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2821-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="c2821-181">アプリケーションのローカライズ</span><span class="sxs-lookup"><span data-stu-id="c2821-181">Localize an Application</span></span>](how-to-localize-an-application.md)
- <span data-ttu-id="c2821-182">[チュートリアル : Windows フォームのローカリゼーション](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c2821-182">[Walkthrough: Localizing Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span></span>
- [<span data-ttu-id="c2821-183">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="c2821-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
