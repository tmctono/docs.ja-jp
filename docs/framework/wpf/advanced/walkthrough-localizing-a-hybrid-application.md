---
title: 'チュートリアル: ハイブリッド アプリケーションのローカライズ'
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 69aa5ae145ffe378b7a4547e5a33826965bf7894
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111115"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="26976-102">チュートリアル: ハイブリッド アプリケーションのローカライズ</span><span class="sxs-lookup"><span data-stu-id="26976-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="26976-103">このチュートリアルでは、Windows フォーム ベースのハイブリッド アプリケーションで [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の要素をローカライズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="26976-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a Windows Forms-based hybrid application.</span></span>

<span data-ttu-id="26976-104">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="26976-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="26976-105">Windows フォーム ホスト プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="26976-105">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="26976-106">ローカライズ可能なコンテンツの追加。</span><span class="sxs-lookup"><span data-stu-id="26976-106">Adding localizable content.</span></span>

- <span data-ttu-id="26976-107">ローカライズの有効化。</span><span class="sxs-lookup"><span data-stu-id="26976-107">Enabling localization.</span></span>

- <span data-ttu-id="26976-108">リソース識別子の割り当て。</span><span class="sxs-lookup"><span data-stu-id="26976-108">Assigning resource identifiers.</span></span>

- <span data-ttu-id="26976-109">LocBaml ツールを使用したサテライト アセンブリの生成。</span><span class="sxs-lookup"><span data-stu-id="26976-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="26976-110">このチュートリアルで説明するタスクの完全なコード リストについては、[ハイブリッド アプリケーションのローカライズのサンプル](https://go.microsoft.com/fwlink/?LinkID=160015)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26976-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="26976-111">完了すると、ローカライズされたハイブリッド アプリケーションが完成します。</span><span class="sxs-lookup"><span data-stu-id="26976-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="26976-112">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="26976-112">Prerequisites</span></span>

<span data-ttu-id="26976-113">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="26976-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="26976-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="26976-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="26976-115">Windows フォーム ホスト プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="26976-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="26976-116">最初のステップでは、Windows フォーム アプリケーション プロジェクトを作成し、ローカライズするコンテンツが含まれる [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="26976-116">The first step is to create the Windows Forms application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="26976-117">ホスト プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="26976-117">To create the host project</span></span>

1. <span data-ttu-id="26976-118">`LocalizingWpfInWf` という名前の **WPF アプリ** プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="26976-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="26976-119">( **[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]**  >  **[Visual C#]** または **[Visual Basic]**  >  **[クラシック デスクトップ]**  >  **[WPF アプリケーション]** )。</span><span class="sxs-lookup"><span data-stu-id="26976-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2. <span data-ttu-id="26976-120">`SimpleControl` という名前の [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 要素をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="26976-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3. <span data-ttu-id="26976-121"><xref:System.Windows.Forms.Integration.ElementHost> コントロールを使用して、フォームに `SimpleControl` 要素を配置します。</span><span class="sxs-lookup"><span data-stu-id="26976-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="26976-122">詳細については、「[チュートリアル:Windows フォームでの 3D WPF 複合コントロールのホスト](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26976-122">For more information, see [Walkthrough: Hosting a 3D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="26976-123">ローカライズ可能なコンテンツの追加</span><span class="sxs-lookup"><span data-stu-id="26976-123">Adding Localizable Content</span></span>

<span data-ttu-id="26976-124">次に、Windows フォームのラベル コントロールを追加し、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 要素のコンテンツにローカライズ可能な文字列を設定します。</span><span class="sxs-lookup"><span data-stu-id="26976-124">Next, you will add a Windows Forms label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="26976-125">ローカライズ可能なコンテンツを追加するには</span><span class="sxs-lookup"><span data-stu-id="26976-125">To add localizable content</span></span>

1. <span data-ttu-id="26976-126">**ソリューション エクスプローラー**で、**SimpleControl.xaml** をダブルクリックして WPF デザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="26976-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the WPF Designer.</span></span>

2. <span data-ttu-id="26976-127">次のコードを使用して、<xref:System.Windows.Controls.Button> コントロールのコンテンツを設定します。</span><span class="sxs-lookup"><span data-stu-id="26976-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. <span data-ttu-id="26976-128">**ソリューション エクスプローラー**で、**Form1** をダブルクリックして Windows フォーム デザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="26976-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="26976-129">**[ツールボックス]** を開き、 **[Label]** をダブルクリックして、フォームにラベル コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="26976-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="26976-130"><xref:System.Windows.Forms.Control.Text%2A> プロパティの値を `"Hello"` に設定します。</span><span class="sxs-lookup"><span data-stu-id="26976-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5. <span data-ttu-id="26976-131">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="26976-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="26976-132">`SimpleControl` 要素とラベル コントロールの両方に、 **"Hello"** というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="26976-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="26976-133">ローカライズの有効化</span><span class="sxs-lookup"><span data-stu-id="26976-133">Enabling Localization</span></span>

<span data-ttu-id="26976-134">Windows フォーム デザイナーには、サテライト アセンブリでローカライズを有効にするための設定が用意されています。</span><span class="sxs-lookup"><span data-stu-id="26976-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="26976-135">ローカライズを有効にするには</span><span class="sxs-lookup"><span data-stu-id="26976-135">To enable localization</span></span>

1. <span data-ttu-id="26976-136">**ソリューション エクスプローラー**で、**Form1.cs** をダブルクリックして Windows フォーム デザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="26976-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="26976-137">**[プロパティ]** ウィンドウで、フォームの **Localizable** プロパティの値を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="26976-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3. <span data-ttu-id="26976-138">**[プロパティ]** ウィンドウで、 **[Language]** プロパティの値を **[スペイン語 (スペイン)]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="26976-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4. <span data-ttu-id="26976-139">Windows フォーム デザイナーでラベル コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="26976-139">In the Windows Forms Designer, select the label control.</span></span>

5. <span data-ttu-id="26976-140">**[プロパティ]** ウィンドウで、<xref:System.Windows.Forms.Control.Text%2A> プロパティの値を `"Hola"` に設定します。</span><span class="sxs-lookup"><span data-stu-id="26976-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="26976-141">Form1.es-ES.resx という名前の新しいリソース ファイルがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="26976-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6. <span data-ttu-id="26976-142">**ソリューション エクスプローラー**で、**Form1.cs** を右クリックし、 **[コードの表示]** をクリックしてコード エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="26976-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7. <span data-ttu-id="26976-143">`Form1` コンストラクターで `InitializeComponent` を呼び出している場所の前に、次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="26976-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. <span data-ttu-id="26976-144">**ソリューション エクスプローラー**で、**LocalizingWpfInWf** を右クリックして **[プロジェクトのアンロード]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26976-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="26976-145">プロジェクト名に、 **[(使用不可)]** というラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="26976-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="26976-146">**LocalizingWpfInWf** を右クリックして、 **[LocalizingWpfInWf.csproj の編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26976-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="26976-147">コード エディターでプロジェクト ファイルが開かれます。</span><span class="sxs-lookup"><span data-stu-id="26976-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="26976-148">次の行を、プロジェクト ファイルの最初の `PropertyGroup` にコピーします。</span><span class="sxs-lookup"><span data-stu-id="26976-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="26976-149">プロジェクト ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="26976-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="26976-150">**ソリューション エクスプローラー**で、**LocalizingWpfInWf** を右クリックして **[プロジェクトの再読み込み]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26976-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="26976-151">リソース識別子の割り当て</span><span class="sxs-lookup"><span data-stu-id="26976-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="26976-152">リソース識別子を使用して、ローカライズ可能なコンテンツをリソース アセンブリにマップできます。</span><span class="sxs-lookup"><span data-stu-id="26976-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="26976-153">`updateuid` オプションを指定すると、MsBuild.exe アプリケーションによってリソース識別子が自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="26976-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="26976-154">リソース識別子を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="26976-154">To assign resource identifiers</span></span>

1. <span data-ttu-id="26976-155">[スタート] メニューから、開発者コマンド プロンプト for Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="26976-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2. <span data-ttu-id="26976-156">次のコマンドを使用して、ローカライズ可能なコンテンツにリソース識別子を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="26976-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. <span data-ttu-id="26976-157">**ソリューション エクスプローラー**で、**SimpleControl.xaml** をダブルクリックしてコード エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="26976-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="26976-158">`msbuild` コマンドによって、`Uid` 属性がすべての要素に追加されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="26976-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="26976-159">これにより、リソース識別子の割り当てによるローカライズが容易になります。</span><span class="sxs-lookup"><span data-stu-id="26976-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. <span data-ttu-id="26976-160">**F6** キーを押してソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="26976-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="26976-161">LocBaml を使用したサテライト アセンブリの生成</span><span class="sxs-lookup"><span data-stu-id="26976-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="26976-162">ローカライズされたコンテンツは、リソース専用の "*サテライト アセンブリ*" に格納されます。</span><span class="sxs-lookup"><span data-stu-id="26976-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="26976-163">LocBaml.exe コマンドライン ツールを使用して、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コンテンツに対するローカライズされたアセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="26976-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="26976-164">サテライト アセンブリを生成するには</span><span class="sxs-lookup"><span data-stu-id="26976-164">To produce a satellite assembly</span></span>

1. <span data-ttu-id="26976-165">LocBaml.exe をプロジェクトの obj\Debug フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="26976-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="26976-166">詳細については、「[アプリケーションをローカライズする](how-to-localize-an-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26976-166">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

2. <span data-ttu-id="26976-167">コマンド プロンプト ウィンドウで、次のコマンドを使用してリソース文字列を一時ファイルに抽出します。</span><span class="sxs-lookup"><span data-stu-id="26976-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. <span data-ttu-id="26976-168">Visual Studio または他のテキスト エディターを使用して、temp.csv ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="26976-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="26976-169">文字列 `"Hello"` を、スペイン語の翻訳 `"Hola"` に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="26976-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4. <span data-ttu-id="26976-170">temp.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="26976-170">Save the temp.csv file.</span></span>

5. <span data-ttu-id="26976-171">次のコマンドを使用して、ローカライズされたリソース ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="26976-171">Use the following command to generate the localized resource file.</span></span>

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="26976-172">LocalizingWpfInWf.g.es-ES.resources ファイルが obj\Debug フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="26976-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6. <span data-ttu-id="26976-173">次のコマンドを使用して、ローカライズされたサテライト アセンブリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="26976-173">Use the following command to build the localized satellite assembly.</span></span>

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="26976-174">LocalizingWpfInWf.resources.dll ファイルが obj\Debug フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="26976-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7. <span data-ttu-id="26976-175">LocalizingWpfInWf.resources.dll ファイルをプロジェクトの bin\Debug\es-ES フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="26976-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="26976-176">既存のファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="26976-176">Replace the existing file.</span></span>

8. <span data-ttu-id="26976-177">プロジェクトの bin\Debug フォルダーにある LocalizingWpfInWf.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="26976-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="26976-178">アプリケーションをリビルドしないでください。リビルドすると、サテライト アセンブリが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="26976-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="26976-179">アプリケーションで、英語の文字列ではなく、ローカライズされた文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26976-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="26976-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="26976-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="26976-181">アプリケーションをローカライズする</span><span class="sxs-lookup"><span data-stu-id="26976-181">Localize an Application</span></span>](how-to-localize-an-application.md)
- <span data-ttu-id="26976-182">[チュートリアル: Windows フォームのローカリゼーション](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="26976-182">[Walkthrough: Localizing Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span></span>
- [<span data-ttu-id="26976-183">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="26976-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
