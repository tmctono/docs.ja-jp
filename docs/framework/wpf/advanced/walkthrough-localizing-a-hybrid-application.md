---
title: 'チュートリアル: ハイブリッド アプリケーションのローカライズ'
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 86779197004f2a8e84d44aaeff2df2dacb05fb01
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621209"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="64999-102">チュートリアル: ハイブリッド アプリケーションのローカライズ</span><span class="sxs-lookup"><span data-stu-id="64999-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="64999-103">このチュートリアルは、ローカライズする方法を示します[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内の要素を[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-ベースのハイブリッド アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="64999-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-based hybrid application.</span></span>

<span data-ttu-id="64999-104">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="64999-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="64999-105">作成、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]ホスト プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="64999-105">Creating the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] host project.</span></span>

- <span data-ttu-id="64999-106">ローカライズ可能なコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="64999-106">Adding localizable content.</span></span>

- <span data-ttu-id="64999-107">ローカライズを有効にします。</span><span class="sxs-lookup"><span data-stu-id="64999-107">Enabling localization.</span></span>

- <span data-ttu-id="64999-108">リソース識別子を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="64999-108">Assigning resource identifiers.</span></span>

- <span data-ttu-id="64999-109">LocBaml ツールを使用して、サテライト アセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="64999-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="64999-110">このチュートリアルで示すタスクの完全なコード一覧については、次を参照してください。[ハイブリッド アプリケーションのサンプルのローカライズ](https://go.microsoft.com/fwlink/?LinkID=160015)します。</span><span class="sxs-lookup"><span data-stu-id="64999-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="64999-111">完了したら、ローカライズされたハイブリッド アプリケーションを必要があります。</span><span class="sxs-lookup"><span data-stu-id="64999-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="64999-112">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="64999-112">Prerequisites</span></span>

<span data-ttu-id="64999-113">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="64999-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="64999-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="64999-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="64999-115">Windows フォームのホスト プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="64999-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="64999-116">作成するには、まず、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]アプリケーション プロジェクトを追加、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ローカライズがコンテンツを持つ要素。</span><span class="sxs-lookup"><span data-stu-id="64999-116">The first step is to create the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="64999-117">ホスト プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="64999-117">To create the host project</span></span>

1. <span data-ttu-id="64999-118">作成、 **WPF アプリ**という名前のプロジェクト`LocalizingWpfInWf`します。</span><span class="sxs-lookup"><span data-stu-id="64999-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="64999-119">(**ファイル** > **新しい** > **プロジェクト** > **Visual c#** または**Visual Basic**  > **クラシック デスクトップ** > **WPF アプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="64999-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2. <span data-ttu-id="64999-120">追加、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>と呼ばれる要素`SimpleControl`をプロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="64999-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3. <span data-ttu-id="64999-121">使用して、<xref:System.Windows.Forms.Integration.ElementHost>コントロールを配置する、`SimpleControl`フォームの要素。</span><span class="sxs-lookup"><span data-stu-id="64999-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="64999-122">詳細については、「[チュートリアル:Windows フォームでの 3d WPF 複合コントロールをホストしている](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="64999-122">For more information, see [Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="64999-123">ローカライズ可能なコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="64999-123">Adding Localizable Content</span></span>

<span data-ttu-id="64999-124">次に、追加、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロールのラベルし、設定、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]要素のコンテンツをローカライズ可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="64999-124">Next, you will add a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="64999-125">ローカライズ可能なコンテンツを追加するには</span><span class="sxs-lookup"><span data-stu-id="64999-125">To add localizable content</span></span>

1. <span data-ttu-id="64999-126">**ソリューション エクスプ ローラー**、ダブルクリックして**SimpleControl.xaml**で開く、[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="64999-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

2. <span data-ttu-id="64999-127">コンテンツを設定、<xref:System.Windows.Controls.Button>次のコードを使用して制御します。</span><span class="sxs-lookup"><span data-stu-id="64999-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. <span data-ttu-id="64999-128">**ソリューション エクスプ ローラー**、ダブルクリックして**Form1** Windows フォーム デザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="64999-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="64999-129">開く、**ツールボックス** をダブルクリックします**ラベル**ラベル コントロールをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="64999-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="64999-130">
  <xref:System.Windows.Forms.Control.Text%2A> プロパティの値を `"Hello"\` に設定します。</span><span class="sxs-lookup"><span data-stu-id="64999-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5. <span data-ttu-id="64999-131">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="64999-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="64999-132">両方の`SimpleControl`要素と、ラベル コントロールの表示テキスト **「こんにちは」** します。</span><span class="sxs-lookup"><span data-stu-id="64999-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="64999-133">ローカライズを有効にします。</span><span class="sxs-lookup"><span data-stu-id="64999-133">Enabling Localization</span></span>

<span data-ttu-id="64999-134">Windows フォーム デザイナーでは、サテライト アセンブリでのローカライズを有効にするための設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="64999-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="64999-135">ローカライズを有効にするには</span><span class="sxs-lookup"><span data-stu-id="64999-135">To enable localization</span></span>

1. <span data-ttu-id="64999-136">**ソリューション エクスプ ローラー**、ダブルクリックして**Form1.cs** Windows フォーム デザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="64999-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="64999-137">**プロパティ**ウィンドウで、フォームの値を設定する**Localizable**プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="64999-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3. <span data-ttu-id="64999-138">**プロパティ**ウィンドウで、設定の値、**言語**プロパティを**スペイン語 (スペイン)** します。</span><span class="sxs-lookup"><span data-stu-id="64999-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4. <span data-ttu-id="64999-139">Windows フォーム デザイナーでは、ラベル コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="64999-139">In the Windows Forms Designer, select the label control.</span></span>

5. <span data-ttu-id="64999-140">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.Forms.Control.Text%2A>プロパティを`"Hola"`します。</span><span class="sxs-lookup"><span data-stu-id="64999-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="64999-141">Form1.es ES.resx をという名前の新しいリソース ファイルは、プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="64999-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6. <span data-ttu-id="64999-142">**ソリューション エクスプ ローラー**を右クリックして**Form1.cs**クリック**コードの表示**コード エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="64999-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7. <span data-ttu-id="64999-143">次のコードをコピー、`Form1`への呼び出しの前のコンス トラクター`InitializeComponent`します。</span><span class="sxs-lookup"><span data-stu-id="64999-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. <span data-ttu-id="64999-144">**ソリューション エクスプ ローラー**を右クリックして**LocalizingWpfInWf**クリック**プロジェクトのアンロード**します。</span><span class="sxs-lookup"><span data-stu-id="64999-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="64999-145">プロジェクト名のラベルは **(利用不可)** します。</span><span class="sxs-lookup"><span data-stu-id="64999-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="64999-146">右クリックして**LocalizingWpfInWf**、 をクリック**編集 LocalizingWpfInWf.csproj**します。</span><span class="sxs-lookup"><span data-stu-id="64999-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="64999-147">プロジェクト ファイルがコード エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="64999-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="64999-148">最初に、次の行をコピー`PropertyGroup`プロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="64999-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="64999-149">プロジェクト ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="64999-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="64999-150">**ソリューション エクスプ ローラー**を右クリックして**LocalizingWpfInWf**クリック**プロジェクトの再読み込み**します。</span><span class="sxs-lookup"><span data-stu-id="64999-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="64999-151">リソース識別子を割り当てる</span><span class="sxs-lookup"><span data-stu-id="64999-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="64999-152">リソース識別子を使用して、リソース アセンブリに、ローカライズ可能なコンテンツをマップできます。</span><span class="sxs-lookup"><span data-stu-id="64999-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="64999-153">指定するときに MsBuild.exe アプリケーションがリソース識別子に自動的に割り当てられます、`updateuid`オプション。</span><span class="sxs-lookup"><span data-stu-id="64999-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="64999-154">リソースの識別子を割り当てます</span><span class="sxs-lookup"><span data-stu-id="64999-154">To assign resource identifiers</span></span>

1. <span data-ttu-id="64999-155">[スタート] メニューから Visual Studio 用開発者コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="64999-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2. <span data-ttu-id="64999-156">次のコマンドを使用して、ローカライズ可能なコンテンツへのリソースの識別子を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="64999-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. <span data-ttu-id="64999-157">**ソリューション エクスプ ローラー**、ダブルクリックして**SimpleControl.xaml**コード エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="64999-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="64999-158">わかりますが、`msbuild`コマンドが追加、`Uid`属性をすべての要素。</span><span class="sxs-lookup"><span data-stu-id="64999-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="64999-159">これには、リソース識別子の割り当てを通じてローカライズが容易になります。</span><span class="sxs-lookup"><span data-stu-id="64999-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. <span data-ttu-id="64999-160">キーを押して**F6**ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="64999-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="64999-161">LocBaml を使用してサテライト アセンブリを生成するには</span><span class="sxs-lookup"><span data-stu-id="64999-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="64999-162">リソース専用で、ローカライズされたコンテンツが格納されている*サテライト アセンブリ*します。</span><span class="sxs-lookup"><span data-stu-id="64999-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="64999-163">ローカライズされたアセンブリを生成するために、コマンド ライン ツール LocBaml.exe を使用して、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]コンテンツ。</span><span class="sxs-lookup"><span data-stu-id="64999-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="64999-164">サテライト アセンブリを生成するには</span><span class="sxs-lookup"><span data-stu-id="64999-164">To produce a satellite assembly</span></span>

1. <span data-ttu-id="64999-165">LocBaml.exe をプロジェクトの \debug フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="64999-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="64999-166">詳細については、次を参照してください。[アプリケーションをローカライズする](how-to-localize-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="64999-166">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

2. <span data-ttu-id="64999-167">コマンド プロンプト ウィンドウで、次のコマンドを使用して、一時ファイルにリソース文字列を抽出します。</span><span class="sxs-lookup"><span data-stu-id="64999-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. <span data-ttu-id="64999-168">Visual Studio または他のテキスト エディターで temp.csv ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="64999-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="64999-169">文字列に置き換えます`"Hello"`スペイン語に翻訳を`"Hola"`します。</span><span class="sxs-lookup"><span data-stu-id="64999-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4. <span data-ttu-id="64999-170">Temp.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="64999-170">Save the temp.csv file.</span></span>

5. <span data-ttu-id="64999-171">ローカライズされたリソース ファイルを生成するのにには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="64999-171">Use the following command to generate the localized resource file.</span></span>

    ```
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="64999-172">LocalizingWpfInWf.g.es ES.resources ファイルは \debug フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="64999-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6. <span data-ttu-id="64999-173">ローカライズされたサテライト アセンブリをビルドするのにには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="64999-173">Use the following command to build the localized satellite assembly.</span></span>

    ```
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="64999-174">LocalizingWpfInWf.resources.dll ファイルは \debug フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="64999-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7. <span data-ttu-id="64999-175">LocalizingWpfInWf.resources.dll ファイルをプロジェクトの bin\Debug\es ES フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="64999-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="64999-176">既存のファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="64999-176">Replace the existing file.</span></span>

8. <span data-ttu-id="64999-177">プロジェクトの bin \debug フォルダーにある LocalizingWpfInWf.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="64999-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="64999-178">アプリケーションを再構築しないまたはサテライト アセンブリは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="64999-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="64999-179">アプリケーションは、英語の文字列ではなく、ローカライズされた文字列を示しています。</span><span class="sxs-lookup"><span data-stu-id="64999-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="64999-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="64999-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="64999-181">アプリケーションをローカライズする</span><span class="sxs-lookup"><span data-stu-id="64999-181">Localize an Application</span></span>](how-to-localize-an-application.md)
- <span data-ttu-id="64999-182">[チュートリアル: Windows フォームのローカリゼーション](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="64999-182">[Walkthrough: Localizing Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span></span>
- [<span data-ttu-id="64999-183">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="64999-183">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
