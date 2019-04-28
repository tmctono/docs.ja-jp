---
title: '方法: ハイブリッド アプリケーションで視覚スタイルを有効にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: 7aa5208a4f378408a01a08a2f4c9dbf2edfa5243
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776143"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a><span data-ttu-id="472ea-102">方法: ハイブリッド アプリケーションで視覚スタイルを有効にする</span><span class="sxs-lookup"><span data-stu-id="472ea-102">How to: Enable Visual Styles in a Hybrid Application</span></span>
<span data-ttu-id="472ea-103">このトピックでは、有効にする方法を示しています。[!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]で視覚スタイルを、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]でホストされているコントロールを[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-ベースのアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="472ea-103">This topic shows how to enable [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] visual styles on a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control hosted in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="472ea-104">アプリケーションを呼び出す場合、<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>メソッドでは、ほとんどの[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]、アプリケーションの実行時に、コントロールに視覚スタイルは使用に自動的に[!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="472ea-104">If your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method, most of your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls will automatically use visual styles when your application is run on [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].</span></span> <span data-ttu-id="472ea-105">詳細については、次を参照してください。 [Visual スタイルを使用しているコントロールのレンダリング](../../winforms/controls/rendering-controls-with-visual-styles.md)します。</span><span class="sxs-lookup"><span data-stu-id="472ea-105">For more information, see [Rendering Controls with Visual Styles](../../winforms/controls/rendering-controls-with-visual-styles.md).</span></span>  
  
 <span data-ttu-id="472ea-106">このトピックで示すタスクの完全なコード一覧については、次を参照してください。[ハイブリッド アプリケーションのサンプルの Visual スタイルを有効にする](https://go.microsoft.com/fwlink/?LinkID=159986)します。</span><span class="sxs-lookup"><span data-stu-id="472ea-106">For a complete code listing of the tasks illustrated in this topic, see [Enabling Visual Styles in a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=159986).</span></span>  
  
## <a name="enabling-windows-forms-visual-styles"></a><span data-ttu-id="472ea-107">Windows フォーム視覚スタイルの有効化</span><span class="sxs-lookup"><span data-stu-id="472ea-107">Enabling Windows Forms Visual Styles</span></span>  
  
#### <a name="to-enable-windows-forms-visual-styles"></a><span data-ttu-id="472ea-108">Windows フォーム視覚スタイルを有効にするには</span><span class="sxs-lookup"><span data-stu-id="472ea-108">To enable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="472ea-109">作成、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]という名前のアプリケーション プロジェクト`HostingWfWithVisualStyles`します。</span><span class="sxs-lookup"><span data-stu-id="472ea-109">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Application project named `HostingWfWithVisualStyles`.</span></span>  
  
2. <span data-ttu-id="472ea-110">ソリューション エクスプローラーで、次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="472ea-110">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="472ea-111">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="472ea-111">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="472ea-112">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="472ea-112">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="472ea-113">ツールボックスでダブルクリックして、<xref:System.Windows.Controls.Grid>を配置するにはアイコン、<xref:System.Windows.Controls.Grid>デザイン サーフェイス上の要素。</span><span class="sxs-lookup"><span data-stu-id="472ea-113">In the Toolbox, double-click the <xref:System.Windows.Controls.Grid> icon to place a <xref:System.Windows.Controls.Grid> element on the design surface.</span></span>  
  
4. <span data-ttu-id="472ea-114">[プロパティ] ウィンドウでの値を設定、<xref:System.Windows.FrameworkElement.Height%2A>と<xref:System.Windows.FrameworkElement.Width%2A>プロパティ**自動**します。</span><span class="sxs-lookup"><span data-stu-id="472ea-114">In the Properties window, set the values of the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties to **Auto**.</span></span>  
  
5. <span data-ttu-id="472ea-115">デザイン ビューまたは XAML ビューで、選択、<xref:System.Windows.Window>します。</span><span class="sxs-lookup"><span data-stu-id="472ea-115">In Design view or XAML view, select the <xref:System.Windows.Window>.</span></span>  
  
6. <span data-ttu-id="472ea-116">[プロパティ] ウィンドウ、**イベント**タブ。</span><span class="sxs-lookup"><span data-stu-id="472ea-116">In the Properties window, click the **Events** tab.</span></span>  
  
7. <span data-ttu-id="472ea-117">ダブルクリックして、<xref:System.Windows.FrameworkElement.Loaded>イベント。</span><span class="sxs-lookup"><span data-stu-id="472ea-117">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>
  
8. <span data-ttu-id="472ea-118">MainWindow.xaml.vb または MainWindow.xaml.cs で、処理するために次のコードを挿入、<xref:System.Windows.FrameworkElement.Loaded>イベント。</span><span class="sxs-lookup"><span data-stu-id="472ea-118">In MainWindow.xaml.vb or MainWindow.xaml.cs, insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. <span data-ttu-id="472ea-119">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="472ea-119">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="472ea-120">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロールが visual スタイルで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="472ea-120">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with visual styles.</span></span>  
  
## <a name="disabling-windows-forms-visual-styles"></a><span data-ttu-id="472ea-121">Windows フォーム視覚スタイルの無効化</span><span class="sxs-lookup"><span data-stu-id="472ea-121">Disabling Windows Forms Visual Styles</span></span>  
 <span data-ttu-id="472ea-122">Visual スタイルを無効にするには、単にへの呼び出しを削除、<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="472ea-122">To disable visual styles, simply remove the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
#### <a name="to-disable-windows-forms-visual-styles"></a><span data-ttu-id="472ea-123">Windows フォーム視覚スタイルを無効にするには</span><span class="sxs-lookup"><span data-stu-id="472ea-123">To disable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="472ea-124">コード エディターで MainWindow.xaml.vb または MainWindow.xaml.cs を開きます。</span><span class="sxs-lookup"><span data-stu-id="472ea-124">Open MainWindow.xaml.vb or MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2. <span data-ttu-id="472ea-125">呼び出しをコメント、<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="472ea-125">Comment out the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
3. <span data-ttu-id="472ea-126">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="472ea-126">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="472ea-127">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロールが既定のシステム スタイルで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="472ea-127">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with the default system style.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="472ea-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="472ea-128">See also</span></span>

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="472ea-129">visual スタイルが使用されているコントロールのレンダリング</span><span class="sxs-lookup"><span data-stu-id="472ea-129">Rendering Controls with Visual Styles</span></span>](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [<span data-ttu-id="472ea-130">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="472ea-130">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
