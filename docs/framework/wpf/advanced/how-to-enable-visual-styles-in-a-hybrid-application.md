---
title: '方法 : ハイブリッド アプリケーションで視覚スタイルを有効にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: dd52313e9100f9c6a1141b53ccc5a23a4b54410a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789920"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a><span data-ttu-id="08193-102">方法 : ハイブリッド アプリケーションで視覚スタイルを有効にする</span><span class="sxs-lookup"><span data-stu-id="08193-102">How to: Enable Visual Styles in a Hybrid Application</span></span>
<span data-ttu-id="08193-103">このトピックでは、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ベースのアプリケーションでホストされている Windows フォームコントロールで visual スタイルを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="08193-103">This topic shows how to enable visual styles on a Windows Forms control hosted in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="08193-104">アプリケーションが <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> メソッドを呼び出すと、ほとんどの Windows フォームコントロールで自動的に visual スタイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="08193-104">If your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method, most of your Windows Forms controls will automatically use visual styles.</span></span> <span data-ttu-id="08193-105">詳細については、「[visual スタイルが使用されているコントロールのレンダリング](../../winforms/controls/rendering-controls-with-visual-styles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08193-105">For more information, see [Rendering Controls with Visual Styles](../../winforms/controls/rendering-controls-with-visual-styles.md).</span></span>  
  
 <span data-ttu-id="08193-106">このトピックで説明されているタスクの完全なコード一覧については、「[ハイブリッドアプリケーションでの Visual スタイルの有効化](https://go.microsoft.com/fwlink/?LinkID=159986)」のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="08193-106">For a complete code listing of the tasks illustrated in this topic, see [Enabling Visual Styles in a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=159986).</span></span>  
  
## <a name="enabling-windows-forms-visual-styles"></a><span data-ttu-id="08193-107">Windows フォーム視覚スタイルの有効化</span><span class="sxs-lookup"><span data-stu-id="08193-107">Enabling Windows Forms Visual Styles</span></span>  
  
#### <a name="to-enable-windows-forms-visual-styles"></a><span data-ttu-id="08193-108">Windows フォーム視覚スタイルを有効にするには</span><span class="sxs-lookup"><span data-stu-id="08193-108">To enable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="08193-109">`HostingWfWithVisualStyles`という名前の [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="08193-109">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Application project named `HostingWfWithVisualStyles`.</span></span>  
  
2. <span data-ttu-id="08193-110">ソリューション エクスプローラーで、次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="08193-110">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="08193-111">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="08193-111">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="08193-112">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="08193-112">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="08193-113">ツールボックスで <xref:System.Windows.Controls.Grid> アイコンをダブルクリックして、デザインサーフェイスに <xref:System.Windows.Controls.Grid> 要素を配置します。</span><span class="sxs-lookup"><span data-stu-id="08193-113">In the Toolbox, double-click the <xref:System.Windows.Controls.Grid> icon to place a <xref:System.Windows.Controls.Grid> element on the design surface.</span></span>  
  
4. <span data-ttu-id="08193-114">プロパティウィンドウで、<xref:System.Windows.FrameworkElement.Height%2A> の値と <xref:System.Windows.FrameworkElement.Width%2A> プロパティを**Auto**に設定します。</span><span class="sxs-lookup"><span data-stu-id="08193-114">In the Properties window, set the values of the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties to **Auto**.</span></span>  
  
5. <span data-ttu-id="08193-115">デザインビューまたは XAML ビューで、<xref:System.Windows.Window>を選択します。</span><span class="sxs-lookup"><span data-stu-id="08193-115">In Design view or XAML view, select the <xref:System.Windows.Window>.</span></span>  
  
6. <span data-ttu-id="08193-116">プロパティウィンドウで、 **[イベント]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="08193-116">In the Properties window, click the **Events** tab.</span></span>  
  
7. <span data-ttu-id="08193-117"><xref:System.Windows.FrameworkElement.Loaded> イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="08193-117">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>
  
8. <span data-ttu-id="08193-118">Mainwindow.xaml または MainWindow.xaml.cs で、<xref:System.Windows.FrameworkElement.Loaded> イベントを処理する次のコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="08193-118">In MainWindow.xaml.vb or MainWindow.xaml.cs, insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. <span data-ttu-id="08193-119">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="08193-119">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="08193-120">Windows フォームコントロールは、visual スタイルを使用して描画されます。</span><span class="sxs-lookup"><span data-stu-id="08193-120">The Windows Forms control is painted with visual styles.</span></span>  
  
## <a name="disabling-windows-forms-visual-styles"></a><span data-ttu-id="08193-121">Windows フォーム視覚スタイルの無効化</span><span class="sxs-lookup"><span data-stu-id="08193-121">Disabling Windows Forms Visual Styles</span></span>  
 <span data-ttu-id="08193-122">視覚スタイルを無効にするには、単に <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> メソッドの呼び出しを削除します。</span><span class="sxs-lookup"><span data-stu-id="08193-122">To disable visual styles, simply remove the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
#### <a name="to-disable-windows-forms-visual-styles"></a><span data-ttu-id="08193-123">Windows フォーム視覚スタイルを無効にするには</span><span class="sxs-lookup"><span data-stu-id="08193-123">To disable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="08193-124">コード エディターで MainWindow.xaml.vb または MainWindow.xaml.cs を開きます。</span><span class="sxs-lookup"><span data-stu-id="08193-124">Open MainWindow.xaml.vb or MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2. <span data-ttu-id="08193-125"><xref:System.Windows.Forms.Application.EnableVisualStyles%2A> メソッドへの呼び出しをコメントアウトします。</span><span class="sxs-lookup"><span data-stu-id="08193-125">Comment out the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
3. <span data-ttu-id="08193-126">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="08193-126">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="08193-127">Windows フォームコントロールは、既定のシステムスタイルで描画されます。</span><span class="sxs-lookup"><span data-stu-id="08193-127">The Windows Forms control is painted with the default system style.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08193-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="08193-128">See also</span></span>

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="08193-129">visual スタイルが使用されているコントロールのレンダリング</span><span class="sxs-lookup"><span data-stu-id="08193-129">Rendering Controls with Visual Styles</span></span>](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [<span data-ttu-id="08193-130">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="08193-130">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
