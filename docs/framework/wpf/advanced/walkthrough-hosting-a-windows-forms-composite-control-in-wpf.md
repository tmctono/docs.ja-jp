---
title: WPF で Windows フォーム複合コントロールをホストする
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: 22eb323d1c1921832630d1d1b30463b4ecb7d1fd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794228"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a><span data-ttu-id="d96b9-102">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="d96b9-102">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="d96b9-103">は、アプリケーションの作成に適した環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-103">provides a rich environment for creating applications.</span></span> <span data-ttu-id="d96b9-104">ただし、Windows フォーム コードに多大な投資をしている場合、コードを最初から書き直すよりも、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションでそのコードの少なくとも一部を再利用する方が効率的な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d96b9-104">However, when you have a substantial investment in Windows Forms code, it can be more effective to reuse at least some of that code in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application rather than to rewrite it from scratch.</span></span> <span data-ttu-id="d96b9-105">最も一般的なシナリオは、既存の Windows フォーム コントロールがある場合です。</span><span class="sxs-lookup"><span data-stu-id="d96b9-105">The most common scenario is when you have existing Windows Forms controls.</span></span> <span data-ttu-id="d96b9-106">場合によっては、これらのコントロールのソース コードにアクセスできないこともあります。</span><span class="sxs-lookup"><span data-stu-id="d96b9-106">In some cases, you might not even have access to the source code for these controls.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="d96b9-107">には、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションでそのようなコントロールをホストするための簡単な手順が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-107">provides a straightforward procedure for hosting such controls in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="d96b9-108">たとえば、特殊な <xref:System.Windows.Forms.DataGridView> コントロールをホストしながら、ほとんどのプログラミングに [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-108">For example, you can use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] for most of your programming while hosting your specialized <xref:System.Windows.Forms.DataGridView> controls.</span></span>  
  
 <span data-ttu-id="d96b9-109">このチュートリアルでは、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーション内で Windows フォーム複合コントロールをホストしてデータ エントリを実行するアプリケーションについて、順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-109">This walkthrough steps you through an application that hosts a Windows Forms composite control to perform data entry in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="d96b9-110">複合コントロールは DLL にパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-110">The composite control is packaged in a DLL.</span></span> <span data-ttu-id="d96b9-111">この一般的な手順は、より複雑なアプリケーションやコントロールに拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-111">This general procedure can be extended to more complex applications and controls.</span></span> <span data-ttu-id="d96b9-112">このチュートリアルは、「[チュートリアル:Windows フォームでの WPF 複合コントロールのホスト](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)」とほぼ同じ外観と機能になるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-112">This walkthrough is designed to be nearly identical in appearance and functionality to [Walkthrough: Hosting a WPF Composite Control in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span></span> <span data-ttu-id="d96b9-113">主な違いは、ホストする側とされる側が逆であることです。</span><span class="sxs-lookup"><span data-stu-id="d96b9-113">The primary difference is that the hosting scenario is reversed.</span></span>  
  
 <span data-ttu-id="d96b9-114">このチュートリアルは、2 つのセクションに分かれています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-114">The walkthrough is divided into two sections.</span></span> <span data-ttu-id="d96b9-115">最初のセクションでは、Windows フォーム複合コントロールの実装について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-115">The first section briefly describes the implementation of the Windows Forms composite control.</span></span> <span data-ttu-id="d96b9-116">2 番目のセクションでは、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションで複合コントロールをホストし、コントロールからイベントを受け取って、コントロールのプロパティの一部にアクセスする方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-116">The second section discusses in detail how to host the composite control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, receive events from the control, and access some of the control's properties.</span></span>  
  
 <span data-ttu-id="d96b9-117">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="d96b9-117">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="d96b9-118">Windows フォーム複合コントロールの実装。</span><span class="sxs-lookup"><span data-stu-id="d96b9-118">Implementing the Windows Forms composite control.</span></span>  
  
- <span data-ttu-id="d96b9-119">WPF ホスト アプリケーションの実装。</span><span class="sxs-lookup"><span data-stu-id="d96b9-119">Implementing the WPF host application.</span></span>  
  
 <span data-ttu-id="d96b9-120">このチュートリアルで示されているタスクの完全なコード一覧については、[WPF での Windows フォーム複合コントロールのホストのサンプル](https://go.microsoft.com/fwlink/?LinkID=159999)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d96b9-120">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a Windows Forms Composite Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159999).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d96b9-121">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d96b9-121">Prerequisites</span></span>  

<span data-ttu-id="d96b9-122">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="d96b9-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="implementing-the-windows-forms-composite-control"></a><span data-ttu-id="d96b9-123">Windows フォーム複合コントロールの実装</span><span class="sxs-lookup"><span data-stu-id="d96b9-123">Implementing the Windows Forms Composite Control</span></span>  
 <span data-ttu-id="d96b9-124">この例で使用されている Windows フォーム複合コントロールは、簡単なデータ入力フォームです。</span><span class="sxs-lookup"><span data-stu-id="d96b9-124">The Windows Forms composite control used in this example is a simple data-entry form.</span></span> <span data-ttu-id="d96b9-125">このフォームでは、ユーザーの名前とアドレスを受け取り、カスタム イベントを使用してその情報をホストに返します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-125">This form takes the user's name and address and then uses a custom event to return that information to the host.</span></span> <span data-ttu-id="d96b9-126">次の図はレンダリングされたコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-126">The following illustration shows the rendered control.</span></span>  

 <span data-ttu-id="d96b9-127">次の図は Windows フォーム複合コントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-127">The following image shows a Windows Forms composite control:</span></span>  

 ![シンプルな Windows フォーム コントロールを示すスクリーンショット。](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a><span data-ttu-id="d96b9-129">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d96b9-129">Creating the Project</span></span>  
 <span data-ttu-id="d96b9-130">プロジェクトを開始するには</span><span class="sxs-lookup"><span data-stu-id="d96b9-130">To start the project:</span></span>  
  
1. <span data-ttu-id="d96b9-131">Visual Studio を起動し、 **[新しいプロジェクト]** ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-131">Launch Visual Studio, and open the **New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="d96b9-132">[ウィンドウ] カテゴリで、 **[Windows フォーム コントロール ライブラリ]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-132">In the Window category, select the **Windows Forms Control Library** template.</span></span>  
  
3. <span data-ttu-id="d96b9-133">新しいプロジェクトに `MyControls` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-133">Name the new project `MyControls`.</span></span>  
  
4. <span data-ttu-id="d96b9-134">配置場所として、`WpfHostingWindowsFormsControl` など、わかりやすい名前を付けた最上位フォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-134">For the location, specify a conveniently named top-level folder, such as `WpfHostingWindowsFormsControl`.</span></span> <span data-ttu-id="d96b9-135">このフォルダーには後でホスト アプリケーションも配置します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-135">Later, you will put the host application in this folder.</span></span>  
  
5. <span data-ttu-id="d96b9-136">**[OK]** をクリックして、プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-136">Click **OK** to create the project.</span></span> <span data-ttu-id="d96b9-137">既定のプロジェクトには、`UserControl1` という名前の 1 つのコントロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-137">The default project contains a single control named `UserControl1`.</span></span>  
  
6. <span data-ttu-id="d96b9-138">ソリューション エクスプローラーで、`UserControl1` を `MyControl1` という名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-138">In Solution Explorer, rename `UserControl1` to `MyControl1`.</span></span>  
  
 <span data-ttu-id="d96b9-139">プロジェクトは、以下のシステム DLL を参照している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96b9-139">Your project should have references to the following system DLLs.</span></span> <span data-ttu-id="d96b9-140">これらの DLL のいずれかが既定で含まれていない場合は、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-140">If any of these DLLs are not included by default, add them to the project.</span></span>  
  
- <span data-ttu-id="d96b9-141">システム</span><span class="sxs-lookup"><span data-stu-id="d96b9-141">System</span></span>  
  
- <span data-ttu-id="d96b9-142">System.Data</span><span class="sxs-lookup"><span data-stu-id="d96b9-142">System.Data</span></span>  
  
- <span data-ttu-id="d96b9-143">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="d96b9-143">System.Drawing</span></span>  
  
- <span data-ttu-id="d96b9-144">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="d96b9-144">System.Windows.Forms</span></span>  
  
- <span data-ttu-id="d96b9-145">System.Xml</span><span class="sxs-lookup"><span data-stu-id="d96b9-145">System.Xml</span></span>  
  
### <a name="adding-controls-to-the-form"></a><span data-ttu-id="d96b9-146">フォームへのコントロールの追加</span><span class="sxs-lookup"><span data-stu-id="d96b9-146">Adding Controls to the Form</span></span>  
 <span data-ttu-id="d96b9-147">フォームにコントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="d96b9-147">To add controls to the form:</span></span>  
  
- <span data-ttu-id="d96b9-148">デザイナーで `MyControl1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-148">Open `MyControl1` in the designer.</span></span>  
  
 <span data-ttu-id="d96b9-149">5 つの <xref:System.Windows.Forms.Label> コントロールとそれに対応する<xref:System.Windows.Forms.TextBox> コントロールを、前の図と同じサイズと配置でフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-149">Add five <xref:System.Windows.Forms.Label> controls and their corresponding <xref:System.Windows.Forms.TextBox> controls, sized and arranged as they are in the preceding illustration, on the form.</span></span> <span data-ttu-id="d96b9-150">この例では、<xref:System.Windows.Forms.TextBox> コントロールに次の名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-150">In the example, the <xref:System.Windows.Forms.TextBox> controls are named:</span></span>  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 <span data-ttu-id="d96b9-151">**[OK]** と **[キャンセル]** というラベルの 2 つの <xref:System.Windows.Forms.Button> コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-151">Add two <xref:System.Windows.Forms.Button> controls labeled **OK** and **Cancel**.</span></span> <span data-ttu-id="d96b9-152">この例では、ボタン名はそれぞれ `btnOK` と `btnCancel` です。</span><span class="sxs-lookup"><span data-stu-id="d96b9-152">In the example, the button names are `btnOK` and `btnCancel`, respectively.</span></span>  
  
### <a name="implementing-the-supporting-code"></a><span data-ttu-id="d96b9-153">サポート コードの実装</span><span class="sxs-lookup"><span data-stu-id="d96b9-153">Implementing the Supporting Code</span></span>  
 <span data-ttu-id="d96b9-154">コード ビューでフォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-154">Open the form in code view.</span></span> <span data-ttu-id="d96b9-155">このコントロールでは、カスタム `OnButtonClick` イベントを発生させることによって収集されたデータをホストに返します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-155">The control returns the collected data to its host by raising the custom `OnButtonClick` event.</span></span> <span data-ttu-id="d96b9-156">データは、イベント引数オブジェクトに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-156">The data is contained in the event argument object.</span></span> <span data-ttu-id="d96b9-157">次のコードは、イベントとデリゲートの宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-157">The following code shows the event and delegate declaration.</span></span>  
  
 <span data-ttu-id="d96b9-158">`MyControl1` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-158">Add the following code to the `MyControl1` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 <span data-ttu-id="d96b9-159">`MyControlEventArgs` クラスには、ホストに返される情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-159">The `MyControlEventArgs` class contains the information to be returned to the host.</span></span>

 <span data-ttu-id="d96b9-160">次のクラスをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-160">Add the following class to the form.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 <span data-ttu-id="d96b9-161">ユーザーが **[OK]** または **[キャンセル]** ボタンをクリックすると、<xref:System.Windows.Forms.Control.Click> イベント ハンドラーによってデータが格納された `MyControlEventArgs` オブジェクトが作成され、`OnButtonClick` イベントを発生します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-161">When the user clicks the **OK** or **Cancel** button, the <xref:System.Windows.Forms.Control.Click> event handlers create a `MyControlEventArgs` object that contains the data and raises the `OnButtonClick` event.</span></span> <span data-ttu-id="d96b9-162">2 つのハンドラーの唯一の違いは、イベント引数の `IsOK` プロパティです。</span><span class="sxs-lookup"><span data-stu-id="d96b9-162">The only difference between the two handlers is the event argument's `IsOK` property.</span></span> <span data-ttu-id="d96b9-163">このプロパティを使用すると、クリックされたボタンをホストで判別できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d96b9-163">This property enables the host to determine which button was clicked.</span></span> <span data-ttu-id="d96b9-164">**[OK]** ボタンの場合は `true`、 **[キャンセル]** ボタンの場合は `false` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-164">It is set to `true` for the **OK** button, and `false` for the **Cancel** button.</span></span> <span data-ttu-id="d96b9-165">次のコードは、2 つのボタン ハンドラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-165">The following code shows the two button handlers.</span></span>

 <span data-ttu-id="d96b9-166">`MyControl1` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-166">Add the following code to the `MyControl1` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a><span data-ttu-id="d96b9-167">アセンブリに厳密な名前を付け、アセンブリをビルドする</span><span class="sxs-lookup"><span data-stu-id="d96b9-167">Giving the Assembly a Strong Name and Building the Assembly</span></span>
 <span data-ttu-id="d96b9-168">このアセンブリを [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションから参照するには、厳密な名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="d96b9-168">For this assembly to be referenced by a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, it must have a strong name.</span></span> <span data-ttu-id="d96b9-169">厳密な名前を作成するには、Sn.exe を使用してキー ファイルを作成し、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-169">To create a strong name, create a key file with Sn.exe and add it to your project.</span></span>

1. <span data-ttu-id="d96b9-170">Visual Studio のコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-170">Open a Visual Studio command prompt.</span></span> <span data-ttu-id="d96b9-171">これを行うには、 **[スタート]** メニューをクリックし、 **[すべてのプログラム]、[Microsoft Visual Studio 2010]、[Visual Studio Tools]、[Visual Studio コマンド プロンプト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-171">To do so, click the **Start** menu, and then select **All Programs/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio Command Prompt**.</span></span> <span data-ttu-id="d96b9-172">これにより、カスタマイズされた環境変数を使用してコンソール ウィンドウが起動します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-172">This launches a console window with customized environment variables.</span></span>

2. <span data-ttu-id="d96b9-173">コマンド プロンプトで、`cd` コマンドを使用してプロジェクト フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-173">At the command prompt, use the `cd` command to go to your project folder.</span></span>

3. <span data-ttu-id="d96b9-174">次のコマンドを実行して、MyControls.snk という名前のキー ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-174">Generate a key file named MyControls.snk by running the following command.</span></span>

    ```console
    Sn.exe -k MyControls.snk
    ```

4. <span data-ttu-id="d96b9-175">プロジェクトにキー ファイルを含めるには、ソリューション エクスプローラーでプロジェクト名を右クリックし、 **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d96b9-175">To include the key file in your project, right-click the project name in Solution Explorer and then click **Properties**.</span></span> <span data-ttu-id="d96b9-176">プロジェクト デザイナーで **[署名]** タブをクリックし、 **[アセンブリに署名する]** チェック ボックスをオンにして、キー ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-176">In the Project Designer, click the **Signing** tab, select the **Sign the assembly** check box and then browse to your key file.</span></span>

5. <span data-ttu-id="d96b9-177">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d96b9-177">Build the solution.</span></span> <span data-ttu-id="d96b9-178">ビルドでは、MyControls.dll という名前の DLL が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-178">The build will produce a DLL named MyControls.dll.</span></span>

## <a name="implementing-the-wpf-host-application"></a><span data-ttu-id="d96b9-179">WPF ホスト アプリケーションの実装</span><span class="sxs-lookup"><span data-stu-id="d96b9-179">Implementing the WPF Host Application</span></span>
 <span data-ttu-id="d96b9-180">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ホスト アプリケーションでは、`MyControl1` をホストするために <xref:System.Windows.Forms.Integration.WindowsFormsHost> コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-180">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] host application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control to host `MyControl1`.</span></span> <span data-ttu-id="d96b9-181">アプリケーションでは `OnButtonClick`イベントを処理して複合コントロールからデータを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d96b9-181">The application handles the `OnButtonClick` event to receive the data from the control.</span></span> <span data-ttu-id="d96b9-182">また、オプション ボタンのコレクションもあります。これらを使うと、コントロールのプロパティの一部を [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションから変更できます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-182">It also has a collection of option buttons that enable you to change some of the control's properties from the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="d96b9-183">完成したアプリケーションを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-183">The following illustration shows the finished application.</span></span>

<span data-ttu-id="d96b9-184">次の図は、WPF アプリケーションに埋め込まれたコントロールを含む完全なアプリケーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-184">The following image shows the complete application, including the control embedded in the WPF application:</span></span>

 ![WPF ページに埋め込まれたコントロールを示すスクリーンショット。](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a><span data-ttu-id="d96b9-186">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d96b9-186">Creating the Project</span></span>
 <span data-ttu-id="d96b9-187">プロジェクトを開始するには</span><span class="sxs-lookup"><span data-stu-id="d96b9-187">To start the project:</span></span>

1. <span data-ttu-id="d96b9-188">Visual Studio を開いて、 **[新しいプロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d96b9-188">Open Visual Studio, and select **New Project**.</span></span>

2. <span data-ttu-id="d96b9-189">[ウィンドウ] カテゴリで、 **[WPF アプリケーション テンプレート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-189">In the Window category, select the **WPF Application** template.</span></span>

3. <span data-ttu-id="d96b9-190">新しいプロジェクトに `WpfHost` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-190">Name the new project `WpfHost`.</span></span>

4. <span data-ttu-id="d96b9-191">配置場所として、MyControls の配置先と同じ最上位フォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-191">For the location, specify the same top-level folder that contains the MyControls project.</span></span>

5. <span data-ttu-id="d96b9-192">**[OK]** をクリックして、プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-192">Click **OK** to create the project.</span></span>

 <span data-ttu-id="d96b9-193">`MyControl1` および他のアセンブリを含む DLL への参照も追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96b9-193">You also need to add references to the DLL that contains `MyControl1` and other assemblies.</span></span>

1. <span data-ttu-id="d96b9-194">ソリューション エクスプローラーで、プロジェクト名を右クリックし、 **[参照の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-194">Right-click the project name in Solution Explorer and select **Add Reference**.</span></span>

2. <span data-ttu-id="d96b9-195">**[参照]** タブをクリックし、MyControls.dll を格納しているフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-195">Click the **Browse** tab, and browse to the folder that contains MyControls.dll.</span></span> <span data-ttu-id="d96b9-196">このチュートリアルの場合は、MyControls\bin\Debug フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="d96b9-196">For this walkthrough, this folder is MyControls\bin\Debug.</span></span>

3. <span data-ttu-id="d96b9-197">MyControls.dll を選択し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d96b9-197">Select MyControls.dll, and then click **OK**.</span></span>

4. <span data-ttu-id="d96b9-198">WindowsFormsIntegration.dll という名前の WindowsFormsIntegration アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-198">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

### <a name="implementing-the-basic-layout"></a><span data-ttu-id="d96b9-199">基本的なレイアウトの実装</span><span class="sxs-lookup"><span data-stu-id="d96b9-199">Implementing the Basic Layout</span></span>
 <span data-ttu-id="d96b9-200">ホスト アプリケーションの [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] は MainWindow.xaml に実装されています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-200">The [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] of the host application is implemented in MainWindow.xaml.</span></span> <span data-ttu-id="d96b9-201">このファイルには、レイアウトを定義し、Windows フォーム コントロールをホストする [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] マークアップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-201">This file contains [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup that defines the layout, and hosts the Windows Forms control.</span></span> <span data-ttu-id="d96b9-202">アプリケーションは 3 つの領域に分かれています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-202">The application is divided into three regions:</span></span>

- <span data-ttu-id="d96b9-203">**[Control Properties]\(コントロールのプロパティ\)** パネル。ホストされているコントロールのさまざまなプロパティを変更するために使用できるオプション ボタンのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-203">The **Control Properties** panel, which contains a collection of option buttons that you can use to modify various properties of the hosted control.</span></span>

- <span data-ttu-id="d96b9-204">**[Data from Control]\(コントロールのデータ\)** パネル。ホストされているコントロールから返されたデータを表示する <xref:System.Windows.Controls.TextBlock> 要素がいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-204">The **Data from Control** panel, which contains several <xref:System.Windows.Controls.TextBlock> elements that display the data returned from the hosted control.</span></span>

- <span data-ttu-id="d96b9-205">ホストされているコントロール自体。</span><span class="sxs-lookup"><span data-stu-id="d96b9-205">The hosted control itself.</span></span>

 <span data-ttu-id="d96b9-206">基本的なレイアウトを次の XAML に示します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-206">The basic layout is shown in the following XAML.</span></span> <span data-ttu-id="d96b9-207">`MyControl1` をホストするために必要なマークアップはこの例では省略されていますが、後で説明します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-207">The markup that is needed to host `MyControl1` is omitted from this example, but will be discussed later.</span></span>

 <span data-ttu-id="d96b9-208">MainWindow.xaml の XAML を次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-208">Replace the XAML in MainWindow.xaml with the following.</span></span> <span data-ttu-id="d96b9-209">Visual Basic を使用している場合は、クラスを `x:Class="MainWindow"` に変更します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-209">If you are using Visual Basic, change the class to `x:Class="MainWindow"`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 <span data-ttu-id="d96b9-210">最初の <xref:System.Windows.Controls.StackPanel> 要素には、ホストされているコントロールのさまざまな既定プロパティを変更できる <xref:System.Windows.Controls.RadioButton> コントロールのセットがいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-210">The first <xref:System.Windows.Controls.StackPanel> element contains several sets of <xref:System.Windows.Controls.RadioButton> controls that enable you to modify various default properties of the hosted control.</span></span> <span data-ttu-id="d96b9-211">その後に `MyControl1` をホストする <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素が続きます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-211">That is followed by a <xref:System.Windows.Forms.Integration.WindowsFormsHost> element, which hosts `MyControl1`.</span></span> <span data-ttu-id="d96b9-212">最後の <xref:System.Windows.Controls.StackPanel> 要素には、ホストされたコントロールから返されるデータを表示するいくつかの <xref:System.Windows.Controls.TextBlock> 要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-212">The final <xref:System.Windows.Controls.StackPanel> element contains several <xref:System.Windows.Controls.TextBlock> elements that display the data that is returned by the hosted control.</span></span> <span data-ttu-id="d96b9-213">要素の順序と、<xref:System.Windows.Controls.DockPanel.Dock%2A> および <xref:System.Windows.FrameworkElement.Height%2A> の属性設定により、ギャップやゆがみを生じることなく、ホストされているコントロールがウィンドウに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-213">The ordering of the elements and the <xref:System.Windows.Controls.DockPanel.Dock%2A> and <xref:System.Windows.FrameworkElement.Height%2A> attribute settings embed the hosted control into the window with no gaps or distortion.</span></span>

#### <a name="hosting-the-control"></a><span data-ttu-id="d96b9-214">コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="d96b9-214">Hosting the Control</span></span>
 <span data-ttu-id="d96b9-215">前述の XAML を編集した以下のバージョンでは、`MyControl1` をホストするために必要な要素に焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-215">The following edited version of the previous XAML focuses on the elements that are needed to host `MyControl1`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 <span data-ttu-id="d96b9-216">`xmlns` 名前空間マッピング属性を使用すると、ホストされているコントロールを含む `MyControls` 名前空間への参照が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-216">The `xmlns` namespace mapping attribute creates a reference to the `MyControls` namespace that contains the hosted control.</span></span> <span data-ttu-id="d96b9-217">このマッピングにより、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] の `MyControl1` を `<mcl:MyControl1>` と表すことができます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-217">This mapping enables you to represent `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] as `<mcl:MyControl1>`.</span></span>

 <span data-ttu-id="d96b9-218">XAML の 2 つの要素によってホスティングを処理します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-218">Two elements in the XAML handle the hosting:</span></span>

- <span data-ttu-id="d96b9-219">`WindowsFormsHost` は、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションで Windows フォーム コントロールをホストできるようにする <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素を表します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-219">`WindowsFormsHost` represents the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element that enables you to host a Windows Forms control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

- <span data-ttu-id="d96b9-220">`MyControl1` を表す `mcl:MyControl1` は、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素の子コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-220">`mcl:MyControl1`, which represents `MyControl1`, is added to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child collection.</span></span> <span data-ttu-id="d96b9-221">その結果、この Windows フォーム コントロールは [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ウィンドウの一部としてレンダリングされ、アプリケーションからそのコントロールと通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d96b9-221">As a result, this Windows Forms control is rendered as part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] window, and you can communicate with the control from the application.</span></span>

### <a name="implementing-the-code-behind-file"></a><span data-ttu-id="d96b9-222">分離コード ファイルの実装</span><span class="sxs-lookup"><span data-stu-id="d96b9-222">Implementing the Code-Behind File</span></span>
 <span data-ttu-id="d96b9-223">分離コード ファイル MainWindow.xaml.vb または MainWindow.xaml.cs には、前のセクションで説明した [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] の機能を実装する手続き型コードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-223">The code-behind file, MainWindow.xaml.vb or MainWindow.xaml.cs, contains the procedural code that implements the functionality of the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] discussed in the preceding section.</span></span> <span data-ttu-id="d96b9-224">主なタスクは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d96b9-224">The primary tasks are:</span></span>

- <span data-ttu-id="d96b9-225">`MyControl1` の `OnButtonClick` イベントへのイベント ハンドラーのアタッチ。</span><span class="sxs-lookup"><span data-stu-id="d96b9-225">Attaching an event handler to `MyControl1`'s `OnButtonClick` event.</span></span>

- <span data-ttu-id="d96b9-226">オプション ボタンのコレクションの設定方法に基づく `MyControl1` のさまざまなプロパティの変更。</span><span class="sxs-lookup"><span data-stu-id="d96b9-226">Modifying various properties of `MyControl1`, based on how the collection of option buttons are set.</span></span>

- <span data-ttu-id="d96b9-227">コントロールによって収集されたデータの表示。</span><span class="sxs-lookup"><span data-stu-id="d96b9-227">Displaying the data collected by the control.</span></span>

#### <a name="initializing-the-application"></a><span data-ttu-id="d96b9-228">アプリケーションの初期化</span><span class="sxs-lookup"><span data-stu-id="d96b9-228">Initializing the Application</span></span>
 <span data-ttu-id="d96b9-229">初期化コードは、ウィンドウの <xref:System.Windows.FrameworkElement.Loaded> イベントのイベント ハンドラーに含まれており、これを使用してコントロールの `OnButtonClick` イベントにイベント ハンドラーをアタッチすることができます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-229">The initialization code is contained in an event handler for the window's <xref:System.Windows.FrameworkElement.Loaded> event and attaches an event handler to the control's `OnButtonClick` event.</span></span>

 <span data-ttu-id="d96b9-230">MainWindow.xaml.vb または MainWindow.xaml.cs で、次のコードを `MainWindow` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-230">In MainWindow.xaml.vb or MainWindow.xaml.cs, add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 <span data-ttu-id="d96b9-231">前述の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] では <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素の子要素コレクションに `MyControl1` が追加されたため、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素の <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> をキャストして`MyControl1` への参照を取得できます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-231">Because the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] discussed previously added `MyControl1` to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child element collection, you can cast the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> to get the reference to `MyControl1`.</span></span> <span data-ttu-id="d96b9-232">これで、その参照を使用してイベント ハンドラーを `OnButtonClick` にアタッチできるようになります。</span><span class="sxs-lookup"><span data-stu-id="d96b9-232">You can then use that reference to attach an event handler to `OnButtonClick`.</span></span>

 <span data-ttu-id="d96b9-233"><xref:System.Windows.Forms.Integration.WindowsFormsHost> では、コントロール自体に参照が提供されるだけでなく、アプリケーションから操作できるいくつかのコントロールのプロパティが公開されています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-233">In addition to providing a reference to the control itself, <xref:System.Windows.Forms.Integration.WindowsFormsHost> exposes a number of the control's properties, which you can manipulate from the application.</span></span> <span data-ttu-id="d96b9-234">初期化コードを使用してこれらの値をプライベート グローバル変数に割り当て、後でアプリケーションで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d96b9-234">The initialization code assigns those values to private global variables for later use in the application.</span></span>

 <span data-ttu-id="d96b9-235">`MyControls` DLL の型に簡単にアクセスできるように、次の `Imports` または `using` ステートメントをファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-235">So that you can easily access the types in the `MyControls` DLL, add the following `Imports` or `using` statement to the top of the file.</span></span>

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a><span data-ttu-id="d96b9-236">OnButtonClick イベントの処理</span><span class="sxs-lookup"><span data-stu-id="d96b9-236">Handling the OnButtonClick Event</span></span>
 <span data-ttu-id="d96b9-237">`MyControl1` を使用すると、ユーザーがコントロールのボタンのいずれかをクリックしたときに `OnButtonClick` イベントを発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-237">`MyControl1` raises the `OnButtonClick` event when the user clicks either of the control's buttons.</span></span>

 <span data-ttu-id="d96b9-238">`MainWindow` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-238">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 <span data-ttu-id="d96b9-239">テキスト ボックスのデータは `MyControlEventArgs` オブジェクトにパックされます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-239">The data in the text boxes is packed into the `MyControlEventArgs` object.</span></span> <span data-ttu-id="d96b9-240">ユーザーが **[OK]** ボタンをクリックすると、イベント ハンドラーによってデータが抽出され、そのデータがパネルの `MyControl1` の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-240">If the user clicks the **OK** button, the event handler extracts the data and displays it in the panel below `MyControl1`.</span></span>

#### <a name="modifying-the-controls-properties"></a><span data-ttu-id="d96b9-241">コントロールのプロパティの変更</span><span class="sxs-lookup"><span data-stu-id="d96b9-241">Modifying the Control’s Properties</span></span>
 <span data-ttu-id="d96b9-242"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素では、ホストされているコントロールの既定プロパティの一部が公開されています。</span><span class="sxs-lookup"><span data-stu-id="d96b9-242">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element exposes several of the hosted control's default properties.</span></span> <span data-ttu-id="d96b9-243">その結果、アプリケーションのスタイルに合わせてコントロールの外観を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-243">As a result, you can change the appearance of the control to match the style of your application more closely.</span></span> <span data-ttu-id="d96b9-244">ユーザーは、左側のパネルにあるオプション ボタン セットを使用して、いくつかの色とフォントのプロパティを変更できます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-244">The sets of option buttons in the left panel enable the user to modify several color and font properties.</span></span> <span data-ttu-id="d96b9-245">各ボタン セットには <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントのハンドラーがあります。これによってユーザーのオプション ボタンの選択が検出され、コントロールの対応するプロパティが変更されます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-245">Each set of buttons has a handler for the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which detects the user's option button selections and changes the corresponding property on the control.</span></span>

 <span data-ttu-id="d96b9-246">`MainWindow` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-246">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 <span data-ttu-id="d96b9-247">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-247">Build and run the application.</span></span> <span data-ttu-id="d96b9-248">Windows フォーム複合コントロールにテキストを追加し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d96b9-248">Add some text in the Windows Forms composite control and then click **OK**.</span></span> <span data-ttu-id="d96b9-249">そのテキストがラベルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d96b9-249">The text appears in the labels.</span></span> <span data-ttu-id="d96b9-250">さまざまなラジオ ボタンをクリックしてコントロールへの影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="d96b9-250">Click the different radio buttons to see the effect on the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d96b9-251">関連項目</span><span class="sxs-lookup"><span data-stu-id="d96b9-251">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="d96b9-252">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="d96b9-252">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="d96b9-253">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="d96b9-253">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="d96b9-254">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="d96b9-254">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
