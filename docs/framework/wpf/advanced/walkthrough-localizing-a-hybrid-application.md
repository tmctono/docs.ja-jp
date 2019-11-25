---
title: 'チュートリアル : ハイブリッド アプリケーションのローカライズ'
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 281afad0c0de856ca67abc74c65aff0e7afc3e01
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976505"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="e9f63-102">チュートリアル : ハイブリッド アプリケーションのローカライズ</span><span class="sxs-lookup"><span data-stu-id="e9f63-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="e9f63-103">このチュートリアルでは、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]ベースのハイブリッドアプリケーションで [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 要素をローカライズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-based hybrid application.</span></span>

<span data-ttu-id="e9f63-104">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="e9f63-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="e9f63-105">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ホストプロジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="e9f63-105">Creating the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] host project.</span></span>

- <span data-ttu-id="e9f63-106">ローカライズ可能なコンテンツの追加</span><span class="sxs-lookup"><span data-stu-id="e9f63-106">Adding localizable content.</span></span>

- <span data-ttu-id="e9f63-107">ローカライズを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e9f63-107">Enabling localization.</span></span>

- <span data-ttu-id="e9f63-108">リソース識別子を割り当てています。</span><span class="sxs-lookup"><span data-stu-id="e9f63-108">Assigning resource identifiers.</span></span>

- <span data-ttu-id="e9f63-109">LocBaml ツールを使用してサテライトアセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="e9f63-110">このチュートリアルで示すタスクの完全なコード一覧については、「[ハイブリッドアプリケーションのローカライズのサンプル](https://go.microsoft.com/fwlink/?LinkID=160015)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9f63-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="e9f63-111">完了すると、ローカライズされたハイブリッドアプリケーションが完成します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e9f63-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="e9f63-112">Prerequisites</span></span>

<span data-ttu-id="e9f63-113">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9f63-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="e9f63-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="e9f63-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="e9f63-115">Windows フォームホストプロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="e9f63-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="e9f63-116">最初の手順として、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] アプリケーションプロジェクトを作成し、ローカライズするコンテンツを含む [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-116">The first step is to create the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="e9f63-117">ホストプロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="e9f63-117">To create the host project</span></span>

1. <span data-ttu-id="e9f63-118">`LocalizingWpfInWf`という名前の**WPF アプリ**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="e9f63-119">(**ファイル** > **新しい** > **プロジェクト** > **Visual C#** または**Visual Basic** > **クラシックデスクトップ** > **WPF アプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="e9f63-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2. <span data-ttu-id="e9f63-120">`SimpleControl` という名前の [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> 要素をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3. <span data-ttu-id="e9f63-121">フォームに `SimpleControl` 要素を配置するには、<xref:System.Windows.Forms.Integration.ElementHost> コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="e9f63-122">詳細については、「[チュートリアル: Windows フォームでの 3-D WPF 複合コントロールのホスト](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9f63-122">For more information, see [Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="e9f63-123">ローカライズ可能なコンテンツの追加</span><span class="sxs-lookup"><span data-stu-id="e9f63-123">Adding Localizable Content</span></span>

<span data-ttu-id="e9f63-124">次に、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] label コントロールを追加し、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 要素のコンテンツをローカライズ可能な文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-124">Next, you will add a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="e9f63-125">ローカライズ可能なコンテンツを追加するには</span><span class="sxs-lookup"><span data-stu-id="e9f63-125">To add localizable content</span></span>

1. <span data-ttu-id="e9f63-126">**ソリューションエクスプローラー**で、 **[simplecontrol .xaml]** をダブルクリックして、WPF デザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the WPF Designer.</span></span>

2. <span data-ttu-id="e9f63-127">次のコードを使用して、<xref:System.Windows.Controls.Button> コントロールの内容を設定します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. <span data-ttu-id="e9f63-128">**ソリューションエクスプローラー**で、 **Form1**をダブルクリックして Windows フォームデザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="e9f63-129">**ツールボックス**を開き、 **[ラベル]** をダブルクリックして、フォームにラベルコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="e9f63-130"><xref:System.Windows.Forms.Control.Text%2A> プロパティの値を `"Hello"` に設定します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5. <span data-ttu-id="e9f63-131">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="e9f63-132">`SimpleControl` 要素と label コントロールの両方に **"Hello"** というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="e9f63-133">ローカライズの有効化</span><span class="sxs-lookup"><span data-stu-id="e9f63-133">Enabling Localization</span></span>

<span data-ttu-id="e9f63-134">Windows フォームデザイナーには、サテライトアセンブリでローカライズを有効にするための設定が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e9f63-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="e9f63-135">ローカライズを有効にするには</span><span class="sxs-lookup"><span data-stu-id="e9f63-135">To enable localization</span></span>

1. <span data-ttu-id="e9f63-136">**ソリューションエクスプローラー**で、 **[Form1.cs]** をダブルクリックして、Windows フォームデザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="e9f63-137">**[プロパティ]** ウィンドウで、フォームの**ローカライズ**可能なプロパティの値を `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3. <span data-ttu-id="e9f63-138">**[プロパティ]** ウィンドウで、 **[言語]** プロパティの値を**スペイン語 (スペイン)** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4. <span data-ttu-id="e9f63-139">Windows フォームデザイナーで、ラベル コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-139">In the Windows Forms Designer, select the label control.</span></span>

5. <span data-ttu-id="e9f63-140">**[プロパティ]** ウィンドウで、[<xref:System.Windows.Forms.Control.Text%2A>] プロパティの値を `"Hola"`に設定します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="e9f63-141">Form1.es という名前の新しいリソースファイルがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6. <span data-ttu-id="e9f63-142">**ソリューションエクスプローラー**で、 **[Form1.cs]** を右クリックし、 **[コードの表示]** をクリックしてコードエディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7. <span data-ttu-id="e9f63-143">`InitializeComponent`への呼び出しの前に、次のコードを `Form1` コンストラクターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e9f63-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. <span data-ttu-id="e9f63-144">**ソリューションエクスプローラー**で、 **[Localizingwpfinwf]** を右クリックし、 **[プロジェクトのアンロード]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9f63-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="e9f63-145">プロジェクト名に " **(利用不可)** " というラベルが付いています。</span><span class="sxs-lookup"><span data-stu-id="e9f63-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="e9f63-146">**[Localizingwpfinwf]** を右クリックし、 **[Edit localizingwpfinwf]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9f63-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="e9f63-147">コードエディターでプロジェクトファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="e9f63-148">次の行をプロジェクトファイルの最初の `PropertyGroup` にコピーします。</span><span class="sxs-lookup"><span data-stu-id="e9f63-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="e9f63-149">プロジェクトファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="e9f63-150">**ソリューションエクスプローラー**で、 **[Localizingwpfinwf]** を右クリックし、 **[プロジェクトの再読み込み]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9f63-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="e9f63-151">リソース識別子の割り当て</span><span class="sxs-lookup"><span data-stu-id="e9f63-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="e9f63-152">リソース識別子を使用して、ローカライズ可能なコンテンツをリソースアセンブリにマップできます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="e9f63-153">`updateuid` オプションを指定すると、Msbuild.exe アプリケーションによってリソース識別子が自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="e9f63-154">リソース識別子を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="e9f63-154">To assign resource identifiers</span></span>

1. <span data-ttu-id="e9f63-155">[スタート] メニューから、Visual Studio の開発者コマンドプロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2. <span data-ttu-id="e9f63-156">次のコマンドを使用して、ローカライズ可能なコンテンツにリソース識別子を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. <span data-ttu-id="e9f63-157">**ソリューションエクスプローラー**で、 **[simplecontrol .xaml]** をダブルクリックしてコードエディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="e9f63-158">`msbuild` コマンドによって、`Uid` 属性がすべての要素に追加されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="e9f63-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="e9f63-159">これにより、リソース識別子の割り当てによってローカライズが容易になります。</span><span class="sxs-lookup"><span data-stu-id="e9f63-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. <span data-ttu-id="e9f63-160">**F6**キーを押してソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e9f63-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="e9f63-161">LocBaml を使用してサテライトアセンブリを生成する</span><span class="sxs-lookup"><span data-stu-id="e9f63-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="e9f63-162">ローカライズされたコンテンツは、リソースのみの*サテライトアセンブリ*に格納されます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="e9f63-163">コマンドラインツールの LocBaml を使用して、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コンテンツ用のローカライズされたアセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="e9f63-164">サテライトアセンブリを生成するには</span><span class="sxs-lookup"><span data-stu-id="e9f63-164">To produce a satellite assembly</span></span>

1. <span data-ttu-id="e9f63-165">LocBaml をプロジェクトの obj\Debug フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e9f63-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="e9f63-166">詳細については、「[アプリケーションをローカライズする](how-to-localize-an-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9f63-166">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

2. <span data-ttu-id="e9f63-167">コマンドプロンプトウィンドウで、次のコマンドを使用して、リソース文字列を一時ファイルに抽出します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. <span data-ttu-id="e9f63-168">Visual Studio または他のテキストエディターを使用して、一時 .csv ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="e9f63-169">文字列 `"Hello"` をスペイン語翻訳、`"Hola"`に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4. <span data-ttu-id="e9f63-170">一時 .csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-170">Save the temp.csv file.</span></span>

5. <span data-ttu-id="e9f63-171">次のコマンドを使用して、ローカライズされたリソースファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-171">Use the following command to generate the localized resource file.</span></span>

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="e9f63-172">LocalizingWpfInWf.g.es ファイルが obj\Debug フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6. <span data-ttu-id="e9f63-173">次のコマンドを使用して、ローカライズされたサテライトアセンブリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e9f63-173">Use the following command to build the localized satellite assembly.</span></span>

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="e9f63-174">Obj\Debug フォルダーに、LocalizingWpfInWf .dll ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7. <span data-ttu-id="e9f63-175">プロジェクトの bin\Debug\es-ES フォルダーに、LocalizingWpfInWf ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e9f63-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="e9f63-176">既存のファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-176">Replace the existing file.</span></span>

8. <span data-ttu-id="e9f63-177">プロジェクトの bin\Debug フォルダーにある LocalizingWpfInWf を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9f63-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="e9f63-178">アプリケーションをリビルドしないでください。または、サテライトアセンブリが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="e9f63-179">アプリケーションでは、英語の文字列ではなく、ローカライズされた文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9f63-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9f63-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9f63-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="e9f63-181">アプリケーションをローカライズする</span><span class="sxs-lookup"><span data-stu-id="e9f63-181">Localize an Application</span></span>](how-to-localize-an-application.md)
- <span data-ttu-id="e9f63-182">[チュートリアル: Windows フォームのローカライズ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e9f63-182">[Walkthrough: Localizing Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span></span>
- [<span data-ttu-id="e9f63-183">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="e9f63-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
