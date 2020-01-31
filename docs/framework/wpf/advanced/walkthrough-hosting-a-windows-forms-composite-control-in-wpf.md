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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794228"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a><span data-ttu-id="d2ecb-102">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="d2ecb-102">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="d2ecb-103">は、アプリケーションの作成に適した環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-103">provides a rich environment for creating applications.</span></span> <span data-ttu-id="d2ecb-104">ただし Windows フォームコードに多大な投資をしている場合は、最初から書き換えるのではなく、少なくともそのコードの一部を [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションで再利用する方が効率的な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-104">However, when you have a substantial investment in Windows Forms code, it can be more effective to reuse at least some of that code in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application rather than to rewrite it from scratch.</span></span> <span data-ttu-id="d2ecb-105">最も一般的なシナリオは、既存の Windows フォームコントロールがある場合です。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-105">The most common scenario is when you have existing Windows Forms controls.</span></span> <span data-ttu-id="d2ecb-106">場合によっては、これらのコントロールのソースコードにアクセスできないこともあります。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-106">In some cases, you might not even have access to the source code for these controls.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="d2ecb-107">には、このようなコントロールを [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションでホストするための簡単な手順が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-107">provides a straightforward procedure for hosting such controls in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="d2ecb-108">たとえば、特殊な <xref:System.Windows.Forms.DataGridView> コントロールをホストしているときに、ほとんどのプログラミングで [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-108">For example, you can use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] for most of your programming while hosting your specialized <xref:System.Windows.Forms.DataGridView> controls.</span></span>  
  
 <span data-ttu-id="d2ecb-109">このチュートリアルでは、Windows フォーム複合コントロールをホストし、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションでデータ入力を実行するアプリケーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-109">This walkthrough steps you through an application that hosts a Windows Forms composite control to perform data entry in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="d2ecb-110">複合コントロールは DLL にパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-110">The composite control is packaged in a DLL.</span></span> <span data-ttu-id="d2ecb-111">この一般的な手順は、より複雑なアプリケーションやコントロールに拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-111">This general procedure can be extended to more complex applications and controls.</span></span> <span data-ttu-id="d2ecb-112">このチュートリアルは、 [「チュートリアル: Windows フォームでの WPF 複合コントロールのホスト](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)」と同様の外観と機能を持つように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-112">This walkthrough is designed to be nearly identical in appearance and functionality to [Walkthrough: Hosting a WPF Composite Control in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span></span> <span data-ttu-id="d2ecb-113">主な違いは、ホストする側とされる側が逆であることです。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-113">The primary difference is that the hosting scenario is reversed.</span></span>  
  
 <span data-ttu-id="d2ecb-114">このチュートリアルは、2 つのセクションに分かれています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-114">The walkthrough is divided into two sections.</span></span> <span data-ttu-id="d2ecb-115">最初のセクションでは、Windows フォーム複合コントロールの実装について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-115">The first section briefly describes the implementation of the Windows Forms composite control.</span></span> <span data-ttu-id="d2ecb-116">2番目のセクションでは、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションで複合コントロールをホストする方法、コントロールからイベントを受信する方法、およびコントロールのプロパティの一部にアクセスする方法の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-116">The second section discusses in detail how to host the composite control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, receive events from the control, and access some of the control's properties.</span></span>  
  
 <span data-ttu-id="d2ecb-117">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-117">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="d2ecb-118">Windows フォーム複合コントロールの実装。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-118">Implementing the Windows Forms composite control.</span></span>  
  
- <span data-ttu-id="d2ecb-119">WPF ホストアプリケーションの実装。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-119">Implementing the WPF host application.</span></span>  
  
 <span data-ttu-id="d2ecb-120">このチュートリアルで示すタスクの完全なコード一覧については、「 [WPF での Windows フォーム複合コントロールのホスト](https://go.microsoft.com/fwlink/?LinkID=159999)」のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-120">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a Windows Forms Composite Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159999).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d2ecb-121">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="d2ecb-121">Prerequisites</span></span>  

<span data-ttu-id="d2ecb-122">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="implementing-the-windows-forms-composite-control"></a><span data-ttu-id="d2ecb-123">Windows フォーム複合コントロールの実装</span><span class="sxs-lookup"><span data-stu-id="d2ecb-123">Implementing the Windows Forms Composite Control</span></span>  
 <span data-ttu-id="d2ecb-124">この例で使用される複合コントロール Windows フォームは、単純なデータ入力フォームです。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-124">The Windows Forms composite control used in this example is a simple data-entry form.</span></span> <span data-ttu-id="d2ecb-125">このフォームは、ユーザーの名前とアドレスを受け取り、カスタムイベントを使用してその情報をホストに返します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-125">This form takes the user's name and address and then uses a custom event to return that information to the host.</span></span> <span data-ttu-id="d2ecb-126">次の図はレンダリングされたコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-126">The following illustration shows the rendered control.</span></span>  

 <span data-ttu-id="d2ecb-127">次の図は Windows フォーム複合コントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-127">The following image shows a Windows Forms composite control:</span></span>  

 ![単純な Windows フォームコントロールを示すスクリーンショット。](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a><span data-ttu-id="d2ecb-129">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d2ecb-129">Creating the Project</span></span>  
 <span data-ttu-id="d2ecb-130">プロジェクトを開始するには</span><span class="sxs-lookup"><span data-stu-id="d2ecb-130">To start the project:</span></span>  
  
1. <span data-ttu-id="d2ecb-131">Visual Studio を起動し、 **[新しいプロジェクト]** ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-131">Launch Visual Studio, and open the **New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="d2ecb-132">ウィンドウ カテゴリで、 **Windows フォームコントロールライブラリ** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-132">In the Window category, select the **Windows Forms Control Library** template.</span></span>  
  
3. <span data-ttu-id="d2ecb-133">新しいプロジェクトに `MyControls` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-133">Name the new project `MyControls`.</span></span>  
  
4. <span data-ttu-id="d2ecb-134">[場所] には、`WpfHostingWindowsFormsControl`など、便利な名前の付いたトップレベルフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-134">For the location, specify a conveniently named top-level folder, such as `WpfHostingWindowsFormsControl`.</span></span> <span data-ttu-id="d2ecb-135">このフォルダーには後でホスト アプリケーションも配置します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-135">Later, you will put the host application in this folder.</span></span>  
  
5. <span data-ttu-id="d2ecb-136">**[OK]** をクリックして、プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-136">Click **OK** to create the project.</span></span> <span data-ttu-id="d2ecb-137">既定のプロジェクトには、`UserControl1`という名前のコントロールが1つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-137">The default project contains a single control named `UserControl1`.</span></span>  
  
6. <span data-ttu-id="d2ecb-138">ソリューションエクスプローラーで、`UserControl1` の名前を `MyControl1`に変更します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-138">In Solution Explorer, rename `UserControl1` to `MyControl1`.</span></span>  
  
 <span data-ttu-id="d2ecb-139">プロジェクトは、以下のシステム DLL を参照している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-139">Your project should have references to the following system DLLs.</span></span> <span data-ttu-id="d2ecb-140">これらの Dll のいずれかが既定で含まれていない場合は、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-140">If any of these DLLs are not included by default, add them to the project.</span></span>  
  
- <span data-ttu-id="d2ecb-141">System</span><span class="sxs-lookup"><span data-stu-id="d2ecb-141">System</span></span>  
  
- <span data-ttu-id="d2ecb-142">System.Data</span><span class="sxs-lookup"><span data-stu-id="d2ecb-142">System.Data</span></span>  
  
- <span data-ttu-id="d2ecb-143">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="d2ecb-143">System.Drawing</span></span>  
  
- <span data-ttu-id="d2ecb-144">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="d2ecb-144">System.Windows.Forms</span></span>  
  
- <span data-ttu-id="d2ecb-145">System.Xml</span><span class="sxs-lookup"><span data-stu-id="d2ecb-145">System.Xml</span></span>  
  
### <a name="adding-controls-to-the-form"></a><span data-ttu-id="d2ecb-146">フォームへのコントロールの追加</span><span class="sxs-lookup"><span data-stu-id="d2ecb-146">Adding Controls to the Form</span></span>  
 <span data-ttu-id="d2ecb-147">フォームにコントロールを追加するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-147">To add controls to the form:</span></span>  
  
- <span data-ttu-id="d2ecb-148">デザイナーで `MyControl1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-148">Open `MyControl1` in the designer.</span></span>  
  
 <span data-ttu-id="d2ecb-149">上の図に示すように、5つの <xref:System.Windows.Forms.Label> コントロールとそれに対応する <xref:System.Windows.Forms.TextBox> コントロールを、フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-149">Add five <xref:System.Windows.Forms.Label> controls and their corresponding <xref:System.Windows.Forms.TextBox> controls, sized and arranged as they are in the preceding illustration, on the form.</span></span> <span data-ttu-id="d2ecb-150">この例では、<xref:System.Windows.Forms.TextBox> コントロールにという名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-150">In the example, the <xref:System.Windows.Forms.TextBox> controls are named:</span></span>  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 <span data-ttu-id="d2ecb-151">**[OK]** と **[キャンセル**] というラベルの付いた <xref:System.Windows.Forms.Button> コントロールを2つ追加します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-151">Add two <xref:System.Windows.Forms.Button> controls labeled **OK** and **Cancel**.</span></span> <span data-ttu-id="d2ecb-152">この例では、ボタン名はそれぞれ `btnOK`、`btnCancel`ます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-152">In the example, the button names are `btnOK` and `btnCancel`, respectively.</span></span>  
  
### <a name="implementing-the-supporting-code"></a><span data-ttu-id="d2ecb-153">サポートコードの実装</span><span class="sxs-lookup"><span data-stu-id="d2ecb-153">Implementing the Supporting Code</span></span>  
 <span data-ttu-id="d2ecb-154">コードビューでフォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-154">Open the form in code view.</span></span> <span data-ttu-id="d2ecb-155">コントロールは、カスタム `OnButtonClick` イベントを発生させることによって、収集されたデータをホストに返します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-155">The control returns the collected data to its host by raising the custom `OnButtonClick` event.</span></span> <span data-ttu-id="d2ecb-156">データは、イベント引数オブジェクトに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-156">The data is contained in the event argument object.</span></span> <span data-ttu-id="d2ecb-157">次のコードは、イベントとデリゲート宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-157">The following code shows the event and delegate declaration.</span></span>  
  
 <span data-ttu-id="d2ecb-158">`MyControl1` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-158">Add the following code to the `MyControl1` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 <span data-ttu-id="d2ecb-159">`MyControlEventArgs` クラスには、ホストに返される情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-159">The `MyControlEventArgs` class contains the information to be returned to the host.</span></span>

 <span data-ttu-id="d2ecb-160">次のクラスをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-160">Add the following class to the form.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 <span data-ttu-id="d2ecb-161">ユーザーが **[OK]** または **[キャンセル**] ボタンをクリックすると、<xref:System.Windows.Forms.Control.Click> イベントハンドラーによって、データを含む `MyControlEventArgs` オブジェクトが作成され、`OnButtonClick` イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-161">When the user clicks the **OK** or **Cancel** button, the <xref:System.Windows.Forms.Control.Click> event handlers create a `MyControlEventArgs` object that contains the data and raises the `OnButtonClick` event.</span></span> <span data-ttu-id="d2ecb-162">2つのハンドラーの唯一の違いは、イベント引数の `IsOK` プロパティです。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-162">The only difference between the two handlers is the event argument's `IsOK` property.</span></span> <span data-ttu-id="d2ecb-163">このプロパティを使用すると、ホストはどのボタンがクリックされたかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-163">This property enables the host to determine which button was clicked.</span></span> <span data-ttu-id="d2ecb-164">**[OK** ] ボタンの `true` に設定され、 **[キャンセル**] ボタンの `false` ます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-164">It is set to `true` for the **OK** button, and `false` for the **Cancel** button.</span></span> <span data-ttu-id="d2ecb-165">次のコードは、2つのボタンハンドラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-165">The following code shows the two button handlers.</span></span>

 <span data-ttu-id="d2ecb-166">`MyControl1` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-166">Add the following code to the `MyControl1` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a><span data-ttu-id="d2ecb-167">アセンブリに厳密な名前を付け、アセンブリをビルドする</span><span class="sxs-lookup"><span data-stu-id="d2ecb-167">Giving the Assembly a Strong Name and Building the Assembly</span></span>
 <span data-ttu-id="d2ecb-168">このアセンブリを [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションで参照するには、厳密な名前を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-168">For this assembly to be referenced by a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, it must have a strong name.</span></span> <span data-ttu-id="d2ecb-169">厳密な名前を作成するには、Sn.exe でキーファイルを作成し、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-169">To create a strong name, create a key file with Sn.exe and add it to your project.</span></span>

1. <span data-ttu-id="d2ecb-170">Visual Studio コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-170">Open a Visual Studio command prompt.</span></span> <span data-ttu-id="d2ecb-171">これを行うには、 **[スタート]** メニューをクリックし、すべてのプログラム、Microsoft Visual Studio 2010、Visual Studio Tools、 **[Visual Studio コマンドプロンプト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-171">To do so, click the **Start** menu, and then select **All Programs/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio Command Prompt**.</span></span> <span data-ttu-id="d2ecb-172">これにより、環境変数がカスタマイズされたコンソールウィンドウが起動します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-172">This launches a console window with customized environment variables.</span></span>

2. <span data-ttu-id="d2ecb-173">コマンドプロンプトで、`cd` コマンドを使用してプロジェクトフォルダーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-173">At the command prompt, use the `cd` command to go to your project folder.</span></span>

3. <span data-ttu-id="d2ecb-174">次のコマンドを実行して、Mycontrols.dll という名前のキーファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-174">Generate a key file named MyControls.snk by running the following command.</span></span>

    ```console
    Sn.exe -k MyControls.snk
    ```

4. <span data-ttu-id="d2ecb-175">キーファイルをプロジェクトに含めるには、ソリューションエクスプローラーでプロジェクト名を右クリックし、 **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-175">To include the key file in your project, right-click the project name in Solution Explorer and then click **Properties**.</span></span> <span data-ttu-id="d2ecb-176">プロジェクトデザイナーで、 **[署名]** タブをクリックし、 **[アセンブリの署名]** チェックボックスをオンにして、キーファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-176">In the Project Designer, click the **Signing** tab, select the **Sign the assembly** check box and then browse to your key file.</span></span>

5. <span data-ttu-id="d2ecb-177">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-177">Build the solution.</span></span> <span data-ttu-id="d2ecb-178">ビルドでは、MyControls.dll という名前の DLL が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-178">The build will produce a DLL named MyControls.dll.</span></span>

## <a name="implementing-the-wpf-host-application"></a><span data-ttu-id="d2ecb-179">WPF ホストアプリケーションの実装</span><span class="sxs-lookup"><span data-stu-id="d2ecb-179">Implementing the WPF Host Application</span></span>
 <span data-ttu-id="d2ecb-180">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ホストアプリケーションは、<xref:System.Windows.Forms.Integration.WindowsFormsHost> コントロールを使用して `MyControl1`をホストします。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-180">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] host application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control to host `MyControl1`.</span></span> <span data-ttu-id="d2ecb-181">アプリケーションは、コントロールからデータを受信するために `OnButtonClick` イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-181">The application handles the `OnButtonClick` event to receive the data from the control.</span></span> <span data-ttu-id="d2ecb-182">また、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションからコントロールのプロパティの一部を変更できるようにするオプションボタンのコレクションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-182">It also has a collection of option buttons that enable you to change some of the control's properties from the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="d2ecb-183">完成したアプリケーションを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-183">The following illustration shows the finished application.</span></span>

<span data-ttu-id="d2ecb-184">次の図は、WPF アプリケーションに埋め込まれたコントロールを含む、完全なアプリケーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-184">The following image shows the complete application, including the control embedded in the WPF application:</span></span>

 ![WPF ページに埋め込まれたコントロールを示すスクリーンショット。](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a><span data-ttu-id="d2ecb-186">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d2ecb-186">Creating the Project</span></span>
 <span data-ttu-id="d2ecb-187">プロジェクトを開始するには</span><span class="sxs-lookup"><span data-stu-id="d2ecb-187">To start the project:</span></span>

1. <span data-ttu-id="d2ecb-188">Visual Studio を開き、 **[新しいプロジェクト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-188">Open Visual Studio, and select **New Project**.</span></span>

2. <span data-ttu-id="d2ecb-189">ウィンドウ カテゴリで、 **WPF アプリケーション** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-189">In the Window category, select the **WPF Application** template.</span></span>

3. <span data-ttu-id="d2ecb-190">新しいプロジェクトに `WpfHost` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-190">Name the new project `WpfHost`.</span></span>

4. <span data-ttu-id="d2ecb-191">配置場所として、MyControls の配置先と同じ最上位フォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-191">For the location, specify the same top-level folder that contains the MyControls project.</span></span>

5. <span data-ttu-id="d2ecb-192">**[OK]** をクリックして、プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-192">Click **OK** to create the project.</span></span>

 <span data-ttu-id="d2ecb-193">また、`MyControl1` およびその他のアセンブリを含む DLL への参照を追加する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-193">You also need to add references to the DLL that contains `MyControl1` and other assemblies.</span></span>

1. <span data-ttu-id="d2ecb-194">ソリューションエクスプローラーでプロジェクト名を右クリックし、 **[参照の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-194">Right-click the project name in Solution Explorer and select **Add Reference**.</span></span>

2. <span data-ttu-id="d2ecb-195">**[参照]** タブをクリックし、mycontrols.dll が含まれているフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-195">Click the **Browse** tab, and browse to the folder that contains MyControls.dll.</span></span> <span data-ttu-id="d2ecb-196">このチュートリアルの場合は、MyControls\bin\Debug フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-196">For this walkthrough, this folder is MyControls\bin\Debug.</span></span>

3. <span data-ttu-id="d2ecb-197">Mycontrols.dll を選択し、 **OK** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-197">Select MyControls.dll, and then click **OK**.</span></span>

4. <span data-ttu-id="d2ecb-198">Windowsフォーム統合アセンブリへの参照を追加します。このアセンブリには、Windowsフォーム統合 dll という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-198">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

### <a name="implementing-the-basic-layout"></a><span data-ttu-id="d2ecb-199">基本レイアウトの実装</span><span class="sxs-lookup"><span data-stu-id="d2ecb-199">Implementing the Basic Layout</span></span>
 <span data-ttu-id="d2ecb-200">ホストアプリケーションの [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] は、Mainwindow.xaml に実装されています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-200">The [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] of the host application is implemented in MainWindow.xaml.</span></span> <span data-ttu-id="d2ecb-201">このファイルには、レイアウトを定義し、Windows フォームコントロールをホストする [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] マークアップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-201">This file contains [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup that defines the layout, and hosts the Windows Forms control.</span></span> <span data-ttu-id="d2ecb-202">アプリケーションは、次の3つのリージョンに分割されます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-202">The application is divided into three regions:</span></span>

- <span data-ttu-id="d2ecb-203">**[コントロールのプロパティ]** パネル。このパネルには、ホストされているコントロールのさまざまなプロパティを変更するために使用できるオプションボタンのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-203">The **Control Properties** panel, which contains a collection of option buttons that you can use to modify various properties of the hosted control.</span></span>

- <span data-ttu-id="d2ecb-204">コントロールパネルの**データ**。ホストされるコントロールから返されたデータを表示する <xref:System.Windows.Controls.TextBlock> 要素がいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-204">The **Data from Control** panel, which contains several <xref:System.Windows.Controls.TextBlock> elements that display the data returned from the hosted control.</span></span>

- <span data-ttu-id="d2ecb-205">ホストされるコントロール自体。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-205">The hosted control itself.</span></span>

 <span data-ttu-id="d2ecb-206">基本的なレイアウトを次の XAML に示します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-206">The basic layout is shown in the following XAML.</span></span> <span data-ttu-id="d2ecb-207">`MyControl1` をホストするために必要なマークアップは、この例では省略されていますが、後で説明します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-207">The markup that is needed to host `MyControl1` is omitted from this example, but will be discussed later.</span></span>

 <span data-ttu-id="d2ecb-208">Mainwindow.xaml の XAML を次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-208">Replace the XAML in MainWindow.xaml with the following.</span></span> <span data-ttu-id="d2ecb-209">Visual Basic を使用している場合は、クラスを `x:Class="MainWindow"`に変更します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-209">If you are using Visual Basic, change the class to `x:Class="MainWindow"`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 <span data-ttu-id="d2ecb-210">最初の <xref:System.Windows.Controls.StackPanel> 要素には、ホストされるコントロールのさまざまな既定のプロパティを変更できるようにする、<xref:System.Windows.Controls.RadioButton> コントロールのセットがいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-210">The first <xref:System.Windows.Controls.StackPanel> element contains several sets of <xref:System.Windows.Controls.RadioButton> controls that enable you to modify various default properties of the hosted control.</span></span> <span data-ttu-id="d2ecb-211">その後に、`MyControl1`をホストする <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素が続きます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-211">That is followed by a <xref:System.Windows.Forms.Integration.WindowsFormsHost> element, which hosts `MyControl1`.</span></span> <span data-ttu-id="d2ecb-212">最後の <xref:System.Windows.Controls.StackPanel> 要素には、ホストされるコントロールによって返されるデータを表示するいくつかの <xref:System.Windows.Controls.TextBlock> 要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-212">The final <xref:System.Windows.Controls.StackPanel> element contains several <xref:System.Windows.Controls.TextBlock> elements that display the data that is returned by the hosted control.</span></span> <span data-ttu-id="d2ecb-213">要素の順序、および <xref:System.Windows.Controls.DockPanel.Dock%2A> および <xref:System.Windows.FrameworkElement.Height%2A> の属性の設定によって、ホストされるコントロールがギャップやひずみなしでウィンドウに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-213">The ordering of the elements and the <xref:System.Windows.Controls.DockPanel.Dock%2A> and <xref:System.Windows.FrameworkElement.Height%2A> attribute settings embed the hosted control into the window with no gaps or distortion.</span></span>

#### <a name="hosting-the-control"></a><span data-ttu-id="d2ecb-214">コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="d2ecb-214">Hosting the Control</span></span>
 <span data-ttu-id="d2ecb-215">前の XAML の次の編集されたバージョンは、`MyControl1`をホストするために必要な要素に焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-215">The following edited version of the previous XAML focuses on the elements that are needed to host `MyControl1`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 <span data-ttu-id="d2ecb-216">`xmlns` 名前空間マッピング属性は、ホストされているコントロールを含む `MyControls` 名前空間への参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-216">The `xmlns` namespace mapping attribute creates a reference to the `MyControls` namespace that contains the hosted control.</span></span> <span data-ttu-id="d2ecb-217">このマッピングにより、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] の `MyControl1` を `<mcl:MyControl1>`として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-217">This mapping enables you to represent `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] as `<mcl:MyControl1>`.</span></span>

 <span data-ttu-id="d2ecb-218">XAML の2つの要素は、ホストを処理します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-218">Two elements in the XAML handle the hosting:</span></span>

- <span data-ttu-id="d2ecb-219">`WindowsFormsHost` は、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションで Windows フォームコントロールをホストできるようにする <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素を表します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-219">`WindowsFormsHost` represents the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element that enables you to host a Windows Forms control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

- <span data-ttu-id="d2ecb-220">`MyControl1`を表す `mcl:MyControl1`は、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素の子コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-220">`mcl:MyControl1`, which represents `MyControl1`, is added to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child collection.</span></span> <span data-ttu-id="d2ecb-221">その結果、この Windows フォームコントロールは [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ウィンドウの一部としてレンダリングされ、アプリケーションからコントロールと通信できます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-221">As a result, this Windows Forms control is rendered as part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] window, and you can communicate with the control from the application.</span></span>

### <a name="implementing-the-code-behind-file"></a><span data-ttu-id="d2ecb-222">分離コード ファイルの実装</span><span class="sxs-lookup"><span data-stu-id="d2ecb-222">Implementing the Code-Behind File</span></span>
 <span data-ttu-id="d2ecb-223">分離コードファイル Mainwindow.xaml または MainWindow.xaml.cs には、前のセクションで説明した [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] の機能を実装する手続き型のコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-223">The code-behind file, MainWindow.xaml.vb or MainWindow.xaml.cs, contains the procedural code that implements the functionality of the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] discussed in the preceding section.</span></span> <span data-ttu-id="d2ecb-224">主なタスクは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-224">The primary tasks are:</span></span>

- <span data-ttu-id="d2ecb-225">イベントハンドラーを `MyControl1`の `OnButtonClick` イベントにアタッチしています。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-225">Attaching an event handler to `MyControl1`'s `OnButtonClick` event.</span></span>

- <span data-ttu-id="d2ecb-226">オプションボタンのコレクションの設定方法に基づいて、`MyControl1`のさまざまなプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-226">Modifying various properties of `MyControl1`, based on how the collection of option buttons are set.</span></span>

- <span data-ttu-id="d2ecb-227">コントロールによって収集されたデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-227">Displaying the data collected by the control.</span></span>

#### <a name="initializing-the-application"></a><span data-ttu-id="d2ecb-228">アプリケーションの初期化</span><span class="sxs-lookup"><span data-stu-id="d2ecb-228">Initializing the Application</span></span>
 <span data-ttu-id="d2ecb-229">初期化コードは、ウィンドウの <xref:System.Windows.FrameworkElement.Loaded> イベントのイベントハンドラーに含まれており、コントロールの `OnButtonClick` イベントにイベントハンドラーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-229">The initialization code is contained in an event handler for the window's <xref:System.Windows.FrameworkElement.Loaded> event and attaches an event handler to the control's `OnButtonClick` event.</span></span>

 <span data-ttu-id="d2ecb-230">Mainwindow.xaml または MainWindow.xaml.cs で、次のコードを `MainWindow` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-230">In MainWindow.xaml.vb or MainWindow.xaml.cs, add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 <span data-ttu-id="d2ecb-231">前に説明した [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] は <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素の子要素コレクションに `MyControl1` 追加されているため、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素の <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> をキャストして `MyControl1`への参照を取得できます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-231">Because the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] discussed previously added `MyControl1` to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child element collection, you can cast the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> to get the reference to `MyControl1`.</span></span> <span data-ttu-id="d2ecb-232">その後、その参照を使用して、`OnButtonClick`にイベントハンドラーをアタッチできます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-232">You can then use that reference to attach an event handler to `OnButtonClick`.</span></span>

 <span data-ttu-id="d2ecb-233">コントロール自体への参照を提供するだけでなく、<xref:System.Windows.Forms.Integration.WindowsFormsHost> は、アプリケーションから操作できるコントロールのプロパティをいくつか公開します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-233">In addition to providing a reference to the control itself, <xref:System.Windows.Forms.Integration.WindowsFormsHost> exposes a number of the control's properties, which you can manipulate from the application.</span></span> <span data-ttu-id="d2ecb-234">初期化コードは、これらの値をプライベートグローバル変数に割り当てて、後でアプリケーションで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-234">The initialization code assigns those values to private global variables for later use in the application.</span></span>

 <span data-ttu-id="d2ecb-235">`MyControls` DLL の型に簡単にアクセスできるようにするには、ファイルの先頭に次の `Imports` または `using` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-235">So that you can easily access the types in the `MyControls` DLL, add the following `Imports` or `using` statement to the top of the file.</span></span>

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a><span data-ttu-id="d2ecb-236">OnButtonClick イベントの処理</span><span class="sxs-lookup"><span data-stu-id="d2ecb-236">Handling the OnButtonClick Event</span></span>
 <span data-ttu-id="d2ecb-237">ユーザーがコントロールのボタンのいずれかをクリックすると、`MyControl1` によって `OnButtonClick` イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-237">`MyControl1` raises the `OnButtonClick` event when the user clicks either of the control's buttons.</span></span>

 <span data-ttu-id="d2ecb-238">`MainWindow` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-238">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 <span data-ttu-id="d2ecb-239">テキストボックス内のデータは、`MyControlEventArgs` オブジェクトにパックされます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-239">The data in the text boxes is packed into the `MyControlEventArgs` object.</span></span> <span data-ttu-id="d2ecb-240">ユーザーが **[OK** ] ボタンをクリックすると、イベントハンドラーによってデータが抽出され、`MyControl1`下のパネルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-240">If the user clicks the **OK** button, the event handler extracts the data and displays it in the panel below `MyControl1`.</span></span>

#### <a name="modifying-the-controls-properties"></a><span data-ttu-id="d2ecb-241">コントロールのプロパティの変更</span><span class="sxs-lookup"><span data-stu-id="d2ecb-241">Modifying the Control’s Properties</span></span>
 <span data-ttu-id="d2ecb-242"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は、ホストされているコントロールの既定のプロパティのいくつかを公開します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-242">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element exposes several of the hosted control's default properties.</span></span> <span data-ttu-id="d2ecb-243">その結果、アプリケーションのスタイルに合わせてコントロールの外観を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-243">As a result, you can change the appearance of the control to match the style of your application more closely.</span></span> <span data-ttu-id="d2ecb-244">左側のパネルにあるオプションボタンのセットを使用すると、ユーザーはいくつかの色とフォントのプロパティを変更できます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-244">The sets of option buttons in the left panel enable the user to modify several color and font properties.</span></span> <span data-ttu-id="d2ecb-245">各ボタンのセットには、<xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントのハンドラーがあります。このハンドラーによって、ユーザーのオプションボタンの選択が検出され、コントロールの対応するプロパティが変更されます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-245">Each set of buttons has a handler for the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which detects the user's option button selections and changes the corresponding property on the control.</span></span>

 <span data-ttu-id="d2ecb-246">`MainWindow` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-246">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 <span data-ttu-id="d2ecb-247">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-247">Build and run the application.</span></span> <span data-ttu-id="d2ecb-248">Windows フォーム複合コントロールにテキストを追加し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-248">Add some text in the Windows Forms composite control and then click **OK**.</span></span> <span data-ttu-id="d2ecb-249">そのテキストがラベルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-249">The text appears in the labels.</span></span> <span data-ttu-id="d2ecb-250">さまざまなオプションボタンをクリックして、コントロールの効果を確認します。</span><span class="sxs-lookup"><span data-stu-id="d2ecb-250">Click the different radio buttons to see the effect on the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2ecb-251">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2ecb-251">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="d2ecb-252">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="d2ecb-252">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="d2ecb-253">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="d2ecb-253">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="d2ecb-254">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="d2ecb-254">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
