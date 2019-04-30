---
title: 'チュートリアル: WPF での Windows フォーム複合コントロールのホスト'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: 90d0e2f3c6ebab070809a4813c87da3539fd14f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032189"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a><span data-ttu-id="1e53c-102">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="1e53c-102">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="1e53c-103">は、アプリケーションの作成に適した環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-103">provides a rich environment for creating applications.</span></span> <span data-ttu-id="1e53c-104">ただしがある場合、かなりの投資[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コードをより効果的か以上で再利用するには、そのコードの一部、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションではなく最初から修正します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-104">However, when you have a substantial investment in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] code, it can be more effective to reuse at least some of that code in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application rather than to rewrite it from scratch.</span></span> <span data-ttu-id="1e53c-105">最も一般的なシナリオでは、既存の Windows フォーム コントロールがある場合です。</span><span class="sxs-lookup"><span data-stu-id="1e53c-105">The most common scenario is when you have existing Windows Forms controls.</span></span> <span data-ttu-id="1e53c-106">場合によってもがありませんこれらのコントロールのソース コードにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1e53c-106">In some cases, you might not even have access to the source code for these controls.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="1e53c-107">このようなコントロールをホストするため、簡単な手順を提供する[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="1e53c-107">provides a straightforward procedure for hosting such controls in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="1e53c-108">たとえば、使用することができます[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]、特殊なをホストしているときに、プログラミングの大部分の<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="1e53c-108">For example, you can use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] for most of your programming while hosting your specialized <xref:System.Windows.Forms.DataGridView> controls.</span></span>  
  
 <span data-ttu-id="1e53c-109">このチュートリアルでのデータ入力を実行する Windows フォーム複合コントロールをホストするアプリケーションを通じて、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="1e53c-109">This walkthrough steps you through an application that hosts a Windows Forms composite control to perform data entry in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="1e53c-110">複合コントロールは DLL にパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="1e53c-110">The composite control is packaged in a DLL.</span></span> <span data-ttu-id="1e53c-111">この一般的な手順は、より複雑なアプリケーションやコントロールに拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-111">This general procedure can be extended to more complex applications and controls.</span></span> <span data-ttu-id="1e53c-112">このチュートリアルの外観と機能をほぼ同じにする目的は[チュートリアル。Windows フォームでの WPF 複合コントロールをホストしている](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-112">This walkthrough is designed to be nearly identical in appearance and functionality to [Walkthrough: Hosting a WPF Composite Control in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span></span> <span data-ttu-id="1e53c-113">主な違いは、ホストする側とされる側が逆であることです。</span><span class="sxs-lookup"><span data-stu-id="1e53c-113">The primary difference is that the hosting scenario is reversed.</span></span>  
  
 <span data-ttu-id="1e53c-114">このチュートリアルは、2 つのセクションに分かれています。</span><span class="sxs-lookup"><span data-stu-id="1e53c-114">The walkthrough is divided into two sections.</span></span> <span data-ttu-id="1e53c-115">最初のセクションでは、Windows フォーム複合コントロールの実装について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-115">The first section briefly describes the implementation of the Windows Forms composite control.</span></span> <span data-ttu-id="1e53c-116">2 番目のセクションで詳細に複合コントロールをホストする方法について説明します、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションでは、コントロールからイベントを受信し、コントロールのプロパティの一部にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1e53c-116">The second section discusses in detail how to host the composite control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, receive events from the control, and access some of the control's properties.</span></span>  
  
 <span data-ttu-id="1e53c-117">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="1e53c-117">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="1e53c-118">Windows フォーム複合コントロールを実装します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-118">Implementing the Windows Forms composite control.</span></span>  
  
- <span data-ttu-id="1e53c-119">WPF ホスト アプリケーションの実装。</span><span class="sxs-lookup"><span data-stu-id="1e53c-119">Implementing the WPF host application.</span></span>  
  
 <span data-ttu-id="1e53c-120">このチュートリアルで示すタスクの完全なコード一覧については、次を参照してください。 [WPF サンプル Windows フォーム複合コントロールをホストしている](https://go.microsoft.com/fwlink/?LinkID=159999)します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-120">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a Windows Forms Composite Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159999).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1e53c-121">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1e53c-121">Prerequisites</span></span>  

<span data-ttu-id="1e53c-122">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="1e53c-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="implementing-the-windows-forms-composite-control"></a><span data-ttu-id="1e53c-123">Windows フォーム複合コントロールを実装します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-123">Implementing the Windows Forms Composite Control</span></span>  
 <span data-ttu-id="1e53c-124">この例で使用される Windows フォーム複合コントロールは、単純なデータ入力フォームです。</span><span class="sxs-lookup"><span data-stu-id="1e53c-124">The Windows Forms composite control used in this example is a simple data-entry form.</span></span> <span data-ttu-id="1e53c-125">このフォームは、ユーザーの名前とアドレスを受け取るし、カスタム イベントを使用してホストにその情報を返します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-125">This form takes the user's name and address and then uses a custom event to return that information to the host.</span></span> <span data-ttu-id="1e53c-126">次の図はレンダリングされたコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="1e53c-126">The following illustration shows the rendered control.</span></span>  

 <span data-ttu-id="1e53c-127">次の図は、Windows フォーム複合コントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="1e53c-127">The following image shows a Windows Forms composite control:</span></span>  

 ![シンプルな Windows フォーム コントロールを示すスクリーン ショット。](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a><span data-ttu-id="1e53c-129">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="1e53c-129">Creating the Project</span></span>  
 <span data-ttu-id="1e53c-130">プロジェクトを開始するには</span><span class="sxs-lookup"><span data-stu-id="1e53c-130">To start the project:</span></span>  
  
1. <span data-ttu-id="1e53c-131">起動[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]を開き、**新しいプロジェクト** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="1e53c-131">Launch [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], and open the **New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="1e53c-132">ウィンドウのカテゴリの選択、 **Windows フォーム コントロール ライブラリ**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="1e53c-132">In the Window category, select the **Windows Forms Control Library** template.</span></span>  
  
3. <span data-ttu-id="1e53c-133">新しいプロジェクトに `MyControls` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-133">Name the new project `MyControls`.</span></span>  
  
4. <span data-ttu-id="1e53c-134">など指定便利な名前付きの最上位フォルダーの場所`WpfHostingWindowsFormsControl`します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-134">For the location, specify a conveniently named top-level folder, such as `WpfHostingWindowsFormsControl`.</span></span> <span data-ttu-id="1e53c-135">このフォルダーには後でホスト アプリケーションも配置します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-135">Later, you will put the host application in this folder.</span></span>  
  
5. <span data-ttu-id="1e53c-136">**[OK]** をクリックして、プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-136">Click **OK** to create the project.</span></span> <span data-ttu-id="1e53c-137">既定のプロジェクトには、という名前の 1 つのコントロールが含まれています。`UserControl1`します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-137">The default project contains a single control named `UserControl1`.</span></span>  
  
6. <span data-ttu-id="1e53c-138">ソリューション エクスプローラで、名前を変更`UserControl1`に`MyControl1`します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-138">In Solution Explorer, rename `UserControl1` to `MyControl1`.</span></span>  
  
 <span data-ttu-id="1e53c-139">プロジェクトは、以下のシステム DLL を参照している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e53c-139">Your project should have references to the following system DLLs.</span></span> <span data-ttu-id="1e53c-140">既定で含まれていないこれらの Dll のいずれかの場合は、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-140">If any of these DLLs are not included by default, add them to the project.</span></span>  
  
- <span data-ttu-id="1e53c-141">システム</span><span class="sxs-lookup"><span data-stu-id="1e53c-141">System</span></span>  
  
- <span data-ttu-id="1e53c-142">System.Data</span><span class="sxs-lookup"><span data-stu-id="1e53c-142">System.Data</span></span>  
  
- <span data-ttu-id="1e53c-143">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="1e53c-143">System.Drawing</span></span>  
  
- <span data-ttu-id="1e53c-144">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="1e53c-144">System.Windows.Forms</span></span>  
  
- <span data-ttu-id="1e53c-145">System.Xml</span><span class="sxs-lookup"><span data-stu-id="1e53c-145">System.Xml</span></span>  
  
### <a name="adding-controls-to-the-form"></a><span data-ttu-id="1e53c-146">フォームへのコントロールの追加</span><span class="sxs-lookup"><span data-stu-id="1e53c-146">Adding Controls to the Form</span></span>  
 <span data-ttu-id="1e53c-147">コントロールをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-147">To add controls to the form:</span></span>  
  
- <span data-ttu-id="1e53c-148">開いている`MyControl1`デザイナー。</span><span class="sxs-lookup"><span data-stu-id="1e53c-148">Open `MyControl1` in the designer.</span></span>  
  
 <span data-ttu-id="1e53c-149">5 つ追加<xref:System.Windows.Forms.Label>コントロールとそれに対応する<xref:System.Windows.Forms.TextBox>コントロール、サイズ、およびフォーム上の図のように配置されます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-149">Add five <xref:System.Windows.Forms.Label> controls and their corresponding <xref:System.Windows.Forms.TextBox> controls, sized and arranged as they are in the preceding illustration, on the form.</span></span> <span data-ttu-id="1e53c-150">例では、<xref:System.Windows.Forms.TextBox>コントロールの名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-150">In the example, the <xref:System.Windows.Forms.TextBox> controls are named:</span></span>  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 <span data-ttu-id="1e53c-151">2 つ追加<xref:System.Windows.Forms.Button>というラベルの付いたコントロール**OK**と**キャンセル**します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-151">Add two <xref:System.Windows.Forms.Button> controls labeled **OK** and **Cancel**.</span></span> <span data-ttu-id="1e53c-152">この例では、ボタン名は`btnOK`と`btnCancel`、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="1e53c-152">In the example, the button names are `btnOK` and `btnCancel`, respectively.</span></span>  
  
### <a name="implementing-the-supporting-code"></a><span data-ttu-id="1e53c-153">サポート コードを実装します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-153">Implementing the Supporting Code</span></span>  
 <span data-ttu-id="1e53c-154">コード ビューで、フォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-154">Open the form in code view.</span></span> <span data-ttu-id="1e53c-155">コントロールがそのホストにカスタムを発生させることによって、収集したデータを返します`OnButtonClick`イベント。</span><span class="sxs-lookup"><span data-stu-id="1e53c-155">The control returns the collected data to its host by raising the custom `OnButtonClick` event.</span></span> <span data-ttu-id="1e53c-156">データは、イベント引数オブジェクトに含まれます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-156">The data is contained in the event argument object.</span></span> <span data-ttu-id="1e53c-157">次のコードでは、イベントとデリゲートの宣言を示します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-157">The following code shows the event and delegate declaration.</span></span>  
  
 <span data-ttu-id="1e53c-158">`MyControl1` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-158">Add the following code to the `MyControl1` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 <span data-ttu-id="1e53c-159">`MyControlEventArgs`クラスには、ホストに返される情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1e53c-159">The `MyControlEventArgs` class contains the information to be returned to the host.</span></span>

 <span data-ttu-id="1e53c-160">フォームに次のクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-160">Add the following class to the form.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 <span data-ttu-id="1e53c-161">ユーザーがクリックすると、 **ok**または**キャンセル** ボタン、<xref:System.Windows.Forms.Control.Click>イベント ハンドラーを作成、`MyControlEventArgs`データを格納しているオブジェクトさせ、`OnButtonClick`イベント。</span><span class="sxs-lookup"><span data-stu-id="1e53c-161">When the user clicks the **OK** or **Cancel** button, the <xref:System.Windows.Forms.Control.Click> event handlers create a `MyControlEventArgs` object that contains the data and raises the `OnButtonClick` event.</span></span> <span data-ttu-id="1e53c-162">2 つのハンドラーの唯一の違いは、イベント引数の`IsOK`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="1e53c-162">The only difference between the two handlers is the event argument's `IsOK` property.</span></span> <span data-ttu-id="1e53c-163">このプロパティは、どのボタンがクリックされたかを判断するホストを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-163">This property enables the host to determine which button was clicked.</span></span> <span data-ttu-id="1e53c-164">設定されている`true`の **[ok]** ボタン、および`false`の**キャンセル**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e53c-164">It is set to `true` for the **OK** button, and `false` for the **Cancel** button.</span></span> <span data-ttu-id="1e53c-165">次のコードは、2 つのボタン ハンドラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="1e53c-165">The following code shows the two button handlers.</span></span>

 <span data-ttu-id="1e53c-166">`MyControl1` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-166">Add the following code to the `MyControl1` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a><span data-ttu-id="1e53c-167">アセンブリに厳密な名前を付けると、アセンブリのビルド</span><span class="sxs-lookup"><span data-stu-id="1e53c-167">Giving the Assembly a Strong Name and Building the Assembly</span></span>
 <span data-ttu-id="1e53c-168">このアセンブリによって参照されるの[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションでは、厳密な名前必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e53c-168">For this assembly to be referenced by a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, it must have a strong name.</span></span> <span data-ttu-id="1e53c-169">厳密な名前を作成するには、Sn.exe でキー ファイルを作成し、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-169">To create a strong name, create a key file with Sn.exe and add it to your project.</span></span>

1. <span data-ttu-id="1e53c-170">[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] のコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-170">Open a [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] command prompt.</span></span> <span data-ttu-id="1e53c-171">これを行うには、クリックして、**開始**] メニューの [クリックして**すべてのプログラムまたは Microsoft Visual Studio 2010 または Visual Studio ツール/visual Studio コマンド プロンプト**。</span><span class="sxs-lookup"><span data-stu-id="1e53c-171">To do so, click the **Start** menu, and then select **All Programs/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio Command Prompt**.</span></span> <span data-ttu-id="1e53c-172">これは、カスタマイズされた環境変数のコンソール ウィンドウを起動します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-172">This launches a console window with customized environment variables.</span></span>

2. <span data-ttu-id="1e53c-173">コマンド プロンプトを使用して、`cd`コマンドをプロジェクト フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-173">At the command prompt, use the `cd` command to go to your project folder.</span></span>

3. <span data-ttu-id="1e53c-174">次のコマンドを実行して MyControls.snk をという名前のキー ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-174">Generate a key file named MyControls.snk by running the following command.</span></span>

    ```
    Sn.exe -k MyControls.snk
    ```

4. <span data-ttu-id="1e53c-175">キー ファイルをプロジェクトに含めるにソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-175">To include the key file in your project, right-click the project name in Solution Explorer and then click **Properties**.</span></span> <span data-ttu-id="1e53c-176">プロジェクト デザイナーで、クリックして、**署名**] タブで、[、**アセンブリに署名**チェック ボックスをオンし、キー ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-176">In the Project Designer, click the **Signing** tab, select the **Sign the assembly** check box and then browse to your key file.</span></span>

5. <span data-ttu-id="1e53c-177">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="1e53c-177">Build the solution.</span></span> <span data-ttu-id="1e53c-178">ビルドでは、MyControls.dll という名前の DLL が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-178">The build will produce a DLL named MyControls.dll.</span></span>

## <a name="implementing-the-wpf-host-application"></a><span data-ttu-id="1e53c-179">WPF ホスト アプリケーションの実装</span><span class="sxs-lookup"><span data-stu-id="1e53c-179">Implementing the WPF Host Application</span></span>
 <span data-ttu-id="1e53c-180">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ホスト アプリケーションで使用する、<xref:System.Windows.Forms.Integration.WindowsFormsHost>コントロールをホストに`MyControl1`します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-180">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] host application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control to host `MyControl1`.</span></span> <span data-ttu-id="1e53c-181">アプリケーションのハンドル、`OnButtonClick`コントロールからデータを受信するイベントです。</span><span class="sxs-lookup"><span data-stu-id="1e53c-181">The application handles the `OnButtonClick` event to receive the data from the control.</span></span> <span data-ttu-id="1e53c-182">コントロールのプロパティの一部を変更するためのオプション ボタンのコレクションがあります、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="1e53c-182">It also has a collection of option buttons that enable you to change some of the control's properties from the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="1e53c-183">次の図は、完成したアプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-183">The following illustration shows the finished application.</span></span>

<span data-ttu-id="1e53c-184">次の図は、WPF アプリケーションに埋め込まれたコントロールを含む、完全なアプリケーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="1e53c-184">The following image shows the complete application, including the control embedded in the WPF application:</span></span>

 ![コントロールを示すスクリーン ショットは、WPF ページに埋め込まれます。](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a><span data-ttu-id="1e53c-186">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="1e53c-186">Creating the Project</span></span>
 <span data-ttu-id="1e53c-187">プロジェクトを開始するには</span><span class="sxs-lookup"><span data-stu-id="1e53c-187">To start the project:</span></span>

1. <span data-ttu-id="1e53c-188">開いている[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]、選択および**新しいプロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-188">Open [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], and select **New Project**.</span></span>

2. <span data-ttu-id="1e53c-189">ウィンドウのカテゴリの選択、 **WPF アプリケーション**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="1e53c-189">In the Window category, select the **WPF Application** template.</span></span>

3. <span data-ttu-id="1e53c-190">新しいプロジェクトに `WpfHost` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-190">Name the new project `WpfHost`.</span></span>

4. <span data-ttu-id="1e53c-191">配置場所として、MyControls の配置先と同じ最上位フォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-191">For the location, specify the same top-level folder that contains the MyControls project.</span></span>

5. <span data-ttu-id="1e53c-192">**[OK]** をクリックして、プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-192">Click **OK** to create the project.</span></span>

 <span data-ttu-id="1e53c-193">含んでいる DLL への参照を追加する必要があります`MyControl1`およびその他のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="1e53c-193">You also need to add references to the DLL that contains `MyControl1` and other assemblies.</span></span>

1. <span data-ttu-id="1e53c-194">ソリューション エクスプ ローラーでプロジェクト名を右クリックして**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-194">Right-click the project name in Solution Explorer and select **Add Reference**.</span></span>

2. <span data-ttu-id="1e53c-195">をクリックして、**参照**タブをクリックし、MyControls.dll を含むフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-195">Click the **Browse** tab, and browse to the folder that contains MyControls.dll.</span></span> <span data-ttu-id="1e53c-196">このチュートリアルの場合は、MyControls\bin\Debug フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="1e53c-196">For this walkthrough, this folder is MyControls\bin\Debug.</span></span>

3. <span data-ttu-id="1e53c-197">MyControls.dll を選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-197">Select MyControls.dll, and then click **OK**.</span></span>

4. <span data-ttu-id="1e53c-198">これは、WindowsFormsIntegration.dll がという名前 WindowsFormsIntegration アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-198">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

### <a name="implementing-the-basic-layout"></a><span data-ttu-id="1e53c-199">基本的なレイアウトを実装します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-199">Implementing the Basic Layout</span></span>
 <span data-ttu-id="1e53c-200">[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] MainWindow.xaml で、ホストのアプリケーションを実装します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-200">The [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] of the host application is implemented in MainWindow.xaml.</span></span> <span data-ttu-id="1e53c-201">このファイルを含む[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]レイアウトを定義し、Windows フォーム コントロールをホストするマークアップ。</span><span class="sxs-lookup"><span data-stu-id="1e53c-201">This file contains [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup that defines the layout, and hosts the Windows Forms control.</span></span> <span data-ttu-id="1e53c-202">アプリケーションは、3 つのリージョンに分かれています。</span><span class="sxs-lookup"><span data-stu-id="1e53c-202">The application is divided into three regions:</span></span>

- <span data-ttu-id="1e53c-203">**コントロール プロパティ**パネルで、ホストされるコントロールのさまざまなプロパティを変更に使用できるオプション ボタンのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1e53c-203">The **Control Properties** panel, which contains a collection of option buttons that you can use to modify various properties of the hosted control.</span></span>

- <span data-ttu-id="1e53c-204">**コントロールからのデータ**パネルで、いくつか含む<xref:System.Windows.Controls.TextBlock>ホストされるコントロールからデータを表示する要素が返されます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-204">The **Data from Control** panel, which contains several <xref:System.Windows.Controls.TextBlock> elements that display the data returned from the hosted control.</span></span>

- <span data-ttu-id="1e53c-205">ホストされるコントロール自体。</span><span class="sxs-lookup"><span data-stu-id="1e53c-205">The hosted control itself.</span></span>

 <span data-ttu-id="1e53c-206">次の XAML は、基本的なレイアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-206">The basic layout is shown in the following XAML.</span></span> <span data-ttu-id="1e53c-207">ために必要なマークアップをホストに`MyControl1`をこの例から省略するは、後ほど説明します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-207">The markup that is needed to host `MyControl1` is omitted from this example, but will be discussed later.</span></span>

 <span data-ttu-id="1e53c-208">MainWindow.xaml で XAML を次のように置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-208">Replace the XAML in MainWindow.xaml with the following.</span></span> <span data-ttu-id="1e53c-209">Visual Basic を使用している場合にクラスを変更`x:Class="MainWindow"`します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-209">If you are using Visual Basic, change the class to `x:Class="MainWindow"`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 <span data-ttu-id="1e53c-210">最初の<xref:System.Windows.Controls.StackPanel>要素には、複数のセットが含まれています。<xref:System.Windows.Controls.RadioButton>ホストされるコントロールのさまざまな既定のプロパティを変更できるようにするコントロール。</span><span class="sxs-lookup"><span data-stu-id="1e53c-210">The first <xref:System.Windows.Controls.StackPanel> element contains several sets of <xref:System.Windows.Controls.RadioButton> controls that enable you to modify various default properties of the hosted control.</span></span> <span data-ttu-id="1e53c-211">これは、後は、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素、どのホスト`MyControl1`します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-211">That is followed by a <xref:System.Windows.Forms.Integration.WindowsFormsHost> element, which hosts `MyControl1`.</span></span> <span data-ttu-id="1e53c-212">最終的な<xref:System.Windows.Controls.StackPanel>要素がいくつか含まれています<xref:System.Windows.Controls.TextBlock>ホストされるコントロールによって返されるデータを表示する要素。</span><span class="sxs-lookup"><span data-stu-id="1e53c-212">The final <xref:System.Windows.Controls.StackPanel> element contains several <xref:System.Windows.Controls.TextBlock> elements that display the data that is returned by the hosted control.</span></span> <span data-ttu-id="1e53c-213">要素の順序と<xref:System.Windows.Controls.DockPanel.Dock%2A>と<xref:System.Windows.FrameworkElement.Height%2A>属性の設定では、ウィンドウにホストされるコントロールを埋め込むギャップやゆがみがないです。</span><span class="sxs-lookup"><span data-stu-id="1e53c-213">The ordering of the elements and the <xref:System.Windows.Controls.DockPanel.Dock%2A> and <xref:System.Windows.FrameworkElement.Height%2A> attribute settings embed the hosted control into the window with no gaps or distortion.</span></span>

#### <a name="hosting-the-control"></a><span data-ttu-id="1e53c-214">コントロールをホストしています。</span><span class="sxs-lookup"><span data-stu-id="1e53c-214">Hosting the Control</span></span>
 <span data-ttu-id="1e53c-215">次の編集したバージョン以前の XAML のために必要な要素について重点的にホスト`MyControl1`します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-215">The following edited version of the previous XAML focuses on the elements that are needed to host `MyControl1`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 <span data-ttu-id="1e53c-216">`xmlns`マッピング属性の名前空間への参照を作成し、`MyControls`ホストされるコントロールを含む名前空間。</span><span class="sxs-lookup"><span data-stu-id="1e53c-216">The `xmlns` namespace mapping attribute creates a reference to the `MyControls` namespace that contains the hosted control.</span></span> <span data-ttu-id="1e53c-217">このマッピングを使用すると、表す`MyControl1`で[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]として`<mcl:MyControl1>`します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-217">This mapping enables you to represent `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] as `<mcl:MyControl1>`.</span></span>

 <span data-ttu-id="1e53c-218">2 つの要素、XAML では、ホスティングを処理します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-218">Two elements in the XAML handle the hosting:</span></span>

- <span data-ttu-id="1e53c-219">`WindowsFormsHost` 表す、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素での Windows フォーム コントロールをホストすることができます、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="1e53c-219">`WindowsFormsHost` represents the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element that enables you to host a Windows Forms control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

- <span data-ttu-id="1e53c-220">`mcl:MyControl1`を表す`MyControl1`、に追加されます、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素の子のコレクション。</span><span class="sxs-lookup"><span data-stu-id="1e53c-220">`mcl:MyControl1`, which represents `MyControl1`, is added to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child collection.</span></span> <span data-ttu-id="1e53c-221">一部としてこの Windows フォーム コントロールを表示する結果として、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ウィンドウ、およびするが、アプリケーションからコントロールと通信できます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-221">As a result, this Windows Forms control is rendered as part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] window, and you can communicate with the control from the application.</span></span>

### <a name="implementing-the-code-behind-file"></a><span data-ttu-id="1e53c-222">分離コード ファイルの実装</span><span class="sxs-lookup"><span data-stu-id="1e53c-222">Implementing the Code-Behind File</span></span>
 <span data-ttu-id="1e53c-223">MainWindow.xaml.vb または MainWindow.xaml.cs で、分離コード ファイルには機能を実装する手続き型コードが含まれています、[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]前のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-223">The code-behind file, MainWindow.xaml.vb or MainWindow.xaml.cs, contains the procedural code that implements the functionality of the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] discussed in the preceding section.</span></span> <span data-ttu-id="1e53c-224">主な作業は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1e53c-224">The primary tasks are:</span></span>

- <span data-ttu-id="1e53c-225">イベント ハンドラーをアタッチする`MyControl1`の`OnButtonClick`イベント。</span><span class="sxs-lookup"><span data-stu-id="1e53c-225">Attaching an event handler to `MyControl1`'s `OnButtonClick` event.</span></span>

- <span data-ttu-id="1e53c-226">さまざまなプロパティを変更する`MyControl1`オプション ボタンのコレクションの設定方法に基づいて、します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-226">Modifying various properties of `MyControl1`, based on how the collection of option buttons are set.</span></span>

- <span data-ttu-id="1e53c-227">コントロールによって収集されたデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-227">Displaying the data collected by the control.</span></span>

#### <a name="initializing-the-application"></a><span data-ttu-id="1e53c-228">アプリケーションの初期化</span><span class="sxs-lookup"><span data-stu-id="1e53c-228">Initializing the Application</span></span>
 <span data-ttu-id="1e53c-229">ウィンドウのイベント ハンドラーの初期化コードが含まれている<xref:System.Windows.FrameworkElement.Loaded>イベントをコントロールのイベント ハンドラーをアタッチおよび`OnButtonClick`イベント。</span><span class="sxs-lookup"><span data-stu-id="1e53c-229">The initialization code is contained in an event handler for the window's <xref:System.Windows.FrameworkElement.Loaded> event and attaches an event handler to the control's `OnButtonClick` event.</span></span>

 <span data-ttu-id="1e53c-230">MainWindow.xaml.vb または MainWindow.xaml.cs で次のコードを追加、`MainWindow`クラス。</span><span class="sxs-lookup"><span data-stu-id="1e53c-230">In MainWindow.xaml.vb or MainWindow.xaml.cs, add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 <span data-ttu-id="1e53c-231">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]以前に追加した説明`MyControl1`を<xref:System.Windows.Forms.Integration.WindowsFormsHost>キャストする要素の子要素のコレクション、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素の<xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A>への参照を取得する`MyControl1`します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-231">Because the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] discussed previously added `MyControl1` to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child element collection, you can cast the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> to get the reference to `MyControl1`.</span></span> <span data-ttu-id="1e53c-232">イベント ハンドラーをアタッチするその参照を使用することができますし`OnButtonClick`します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-232">You can then use that reference to attach an event handler to `OnButtonClick`.</span></span>

 <span data-ttu-id="1e53c-233">コントロール自体への参照を提供するだけでなく<xref:System.Windows.Forms.Integration.WindowsFormsHost>多数のアプリケーションから操作できるコントロールのプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-233">In addition to providing a reference to the control itself, <xref:System.Windows.Forms.Integration.WindowsFormsHost> exposes a number of the control's properties, which you can manipulate from the application.</span></span> <span data-ttu-id="1e53c-234">初期化コードでは、プライベートのグローバル変数を後で、アプリケーションで使用するこれらの値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-234">The initialization code assigns those values to private global variables for later use in the application.</span></span>

 <span data-ttu-id="1e53c-235">内の型を簡単にアクセスできるように、 `MyControls` DLL では、次の追加`Imports`または`using`ファイルの先頭にステートメント。</span><span class="sxs-lookup"><span data-stu-id="1e53c-235">So that you can easily access the types in the `MyControls` DLL, add the following `Imports` or `using` statement to the top of the file.</span></span>

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a><span data-ttu-id="1e53c-236">OnButtonClick のイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-236">Handling the OnButtonClick Event</span></span>
 <span data-ttu-id="1e53c-237">`MyControl1` 発生させる、`OnButtonClick`イベントかのコントロールのボタンをクリックするとします。</span><span class="sxs-lookup"><span data-stu-id="1e53c-237">`MyControl1` raises the `OnButtonClick` event when the user clicks either of the control's buttons.</span></span>

 <span data-ttu-id="1e53c-238">`MainWindow` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-238">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 <span data-ttu-id="1e53c-239">テキスト ボックス内のデータをまとめ、`MyControlEventArgs`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1e53c-239">The data in the text boxes is packed into the `MyControlEventArgs` object.</span></span> <span data-ttu-id="1e53c-240">ユーザーがクリックした場合、 **OK**ボタン、イベント ハンドラーは、データを抽出し、下のパネルに表示します`MyControl1`。</span><span class="sxs-lookup"><span data-stu-id="1e53c-240">If the user clicks the **OK** button, the event handler extracts the data and displays it in the panel below `MyControl1`.</span></span>

#### <a name="modifying-the-controls-properties"></a><span data-ttu-id="1e53c-241">コントロールのプロパティの変更</span><span class="sxs-lookup"><span data-stu-id="1e53c-241">Modifying the Control’s Properties</span></span>
 <span data-ttu-id="1e53c-242"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素がいくつかのホストされるコントロールの既定のプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-242">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element exposes several of the hosted control's default properties.</span></span> <span data-ttu-id="1e53c-243">その結果、アプリケーションのスタイルをより厳密に一致するようにコントロールの外観を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-243">As a result, you can change the appearance of the control to match the style of your application more closely.</span></span> <span data-ttu-id="1e53c-244">左側のパネルのオプション ボタンのセットは、いくつかの色とフォントのプロパティを変更するユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1e53c-244">The sets of option buttons in the left panel enable the user to modify several color and font properties.</span></span> <span data-ttu-id="1e53c-245">ボタンの各セットのハンドラーがある、<xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベントでは、ユーザーのオプション ボタンの選択を検出し、コントロールに対応するプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-245">Each set of buttons has a handler for the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which detects the user's option button selections and changes the corresponding property on the control.</span></span>

 <span data-ttu-id="1e53c-246">`MainWindow` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-246">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 <span data-ttu-id="1e53c-247">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-247">Build and run the application.</span></span> <span data-ttu-id="1e53c-248">Windows フォーム複合コントロールでテキストを追加し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="1e53c-248">Add some text in the Windows Forms composite control and then click **OK**.</span></span> <span data-ttu-id="1e53c-249">そのテキストがラベルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e53c-249">The text appears in the labels.</span></span> <span data-ttu-id="1e53c-250">コントロールに影響を表示するさまざまなオプション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e53c-250">Click the different radio buttons to see the effect on the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e53c-251">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e53c-251">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="1e53c-252">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="1e53c-252">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="1e53c-253">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="1e53c-253">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="1e53c-254">チュートリアル: Windows フォームでの WPF 複合コントロールをホストしています。</span><span class="sxs-lookup"><span data-stu-id="1e53c-254">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
