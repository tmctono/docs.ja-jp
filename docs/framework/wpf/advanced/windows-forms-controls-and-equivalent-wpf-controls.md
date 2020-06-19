---
title: Windows フォーム コントロールおよび同等の WPF コントロール
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
ms.openlocfilehash: 729f893a94688f4a1d8b0a770a3624b27ddfe1c1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794079"
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a><span data-ttu-id="cd6b4-102">Windows フォーム コントロールおよび同等の WPF コントロール</span><span class="sxs-lookup"><span data-stu-id="cd6b4-102">Windows Forms Controls and Equivalent WPF Controls</span></span>
<span data-ttu-id="cd6b4-103">多くの Windows フォーム コントロールには同等の [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コントロールがありますが、一部の Windows フォーム コントロールには [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] に同等のものがありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-103">Many Windows Forms controls have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls, but some Windows Forms controls have no equivalents in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="cd6b4-104">このトピックでは、2 つのテクノロジに用意されているコントロールの種類を比較します。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-104">This topic compares control types provided by the two technologies.</span></span>  
  
 <span data-ttu-id="cd6b4-105">いつでも相互運用を使用して、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ベースのアプリケーションに同等のものがない Windows フォーム コントロールをホストできます。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-105">You can always use interoperation to host Windows Forms controls that do not have equivalents in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
 <span data-ttu-id="cd6b4-106">次の表は、どの Windows フォーム コントロールとコンポーネントに同等の [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コントロール機能があるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-106">The following table shows which Windows Forms controls and components have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control functionality.</span></span>  
  
|<span data-ttu-id="cd6b4-107">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="cd6b4-107">Windows Forms control</span></span>|<span data-ttu-id="cd6b4-108">WPF の同等のコントロール</span><span class="sxs-lookup"><span data-stu-id="cd6b4-108">WPF equivalent control</span></span>|<span data-ttu-id="cd6b4-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="cd6b4-109">Remarks</span></span>|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|<span data-ttu-id="cd6b4-110">同等のコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-110">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<span data-ttu-id="cd6b4-111">コンポジションを使用する <xref:System.Windows.Controls.ListBox>。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-111"><xref:System.Windows.Controls.ListBox> with composition.</span></span>||  
|<xref:System.Windows.Forms.ColorDialog>|<span data-ttu-id="cd6b4-112">同等のコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-112">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<span data-ttu-id="cd6b4-113"><xref:System.Windows.Controls.ComboBox> はオートコンプリートをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-113"><xref:System.Windows.Controls.ComboBox> does not support auto-complete.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<span data-ttu-id="cd6b4-114"><xref:System.Windows.Controls.TextBox> と 2 つの <xref:System.Windows.Controls.Primitives.RepeatButton> コントロール。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-114"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.ErrorProvider>|<span data-ttu-id="cd6b4-115">同等のコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-115">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<span data-ttu-id="cd6b4-116"><xref:System.Windows.Controls.WrapPanel> または <xref:System.Windows.Controls.StackPanel></span><span class="sxs-lookup"><span data-stu-id="cd6b4-116"><xref:System.Windows.Controls.WrapPanel> or <xref:System.Windows.Controls.StackPanel></span></span>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|<span data-ttu-id="cd6b4-117">同等のコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-117">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FontDialog>|<span data-ttu-id="cd6b4-118">同等のコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-118">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<span data-ttu-id="cd6b4-119"><xref:System.Windows.Window> は子ウィンドウをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-119"><xref:System.Windows.Window> does not support child windows.</span></span>|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|<span data-ttu-id="cd6b4-120">同等のコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-120">No equivalent control.</span></span>|<span data-ttu-id="cd6b4-121">F1 ヘルプはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-121">No F1 Help.</span></span> <span data-ttu-id="cd6b4-122">"ポップヒント" ヘルプはツールヒントに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-122">"What's This" Help is replaced by ToolTips.</span></span>|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="cd6b4-123">スクロールは、コンテナー コントロールに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-123">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.ImageList>|<span data-ttu-id="cd6b4-124">同等のコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-124">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|<span data-ttu-id="cd6b4-125">同等のコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-125">No equivalent control.</span></span>|<span data-ttu-id="cd6b4-126"><xref:System.Windows.Documents.Hyperlink> クラスを使用して、フロー コンテンツ内のハイパーリンクをホストできます。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-126">You can use the <xref:System.Windows.Documents.Hyperlink> class to host hyperlinks within flow content.</span></span>|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|<span data-ttu-id="cd6b4-127"><xref:System.Windows.Controls.ListView> コントロールには、読み取り専用の詳細ビューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-127">The <xref:System.Windows.Controls.ListView> control provides a read-only details view.</span></span>|  
|<xref:System.Windows.Forms.MaskedTextBox>|<span data-ttu-id="cd6b4-128">同等のコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-128">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<span data-ttu-id="cd6b4-129"><xref:System.Windows.Controls.Menu> コントロールのスタイル設定を使用すると、<xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> クラスの動作と外観に近づけることができます。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-129"><xref:System.Windows.Controls.Menu> control styling can approximate the behavior and appearance of the <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> class.</span></span>|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|<span data-ttu-id="cd6b4-130">同等のコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-130">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.NumericUpDown>|<span data-ttu-id="cd6b4-131"><xref:System.Windows.Controls.TextBox> と 2 つの <xref:System.Windows.Controls.Primitives.RepeatButton> コントロール。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-131"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|<span data-ttu-id="cd6b4-132"><xref:Microsoft.Win32.OpenFileDialog> クラスは、Win32 コントロールをラップする [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ラッパーです。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-132">The <xref:Microsoft.Win32.OpenFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the Win32 control.</span></span>|  
|<xref:System.Windows.Forms.PageSetupDialog>|<span data-ttu-id="cd6b4-133">同等のコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-133">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|<span data-ttu-id="cd6b4-134">同等のコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-134">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|<span data-ttu-id="cd6b4-135">同等のコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-135">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|<span data-ttu-id="cd6b4-136">同等のコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-136">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|<span data-ttu-id="cd6b4-137"><xref:Microsoft.Win32.SaveFileDialog> クラスは、Win32 コントロールをラップする [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ラッパーです。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-137">The <xref:Microsoft.Win32.SaveFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the Win32 control.</span></span>|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="cd6b4-138">コンポジションを使用する <xref:System.Windows.Controls.ToolBar>。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-138"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="cd6b4-139">コンポジションを使用する <xref:System.Windows.Controls.ToolBar>。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-139"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<span data-ttu-id="cd6b4-140">コンポジションを使用する <xref:System.Windows.Controls.ToolBar>。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-140"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripPanel>|<span data-ttu-id="cd6b4-141">コンポジションを使用する <xref:System.Windows.Controls.ToolBar>。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-141"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="cd6b4-142">スクロールは、コンテナー コントロールに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-142">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.WebBrowser>|<span data-ttu-id="cd6b4-143"><xref:System.Windows.Controls.Frame>、<xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cd6b4-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span></span>|<span data-ttu-id="cd6b4-144"><xref:System.Windows.Controls.Frame> コントロールでは、HTML ページをホストできます。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-144">The <xref:System.Windows.Controls.Frame> control can host HTML pages.</span></span><br /><br /> <span data-ttu-id="cd6b4-145">.NET Framework 3.5 SP1 以降、<xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> コントロールでは HTML ページをホストできます。また、<xref:System.Windows.Controls.Frame> コントロールもサポートします。</span><span class="sxs-lookup"><span data-stu-id="cd6b4-145">Starting in the .NET Framework 3.5 SP1, the <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control can host HTML pages and also backs the <xref:System.Windows.Controls.Frame> control.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd6b4-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd6b4-146">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- <span data-ttu-id="cd6b4-147">[Windows フォーム開発者向け WPF デザイナー](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cd6b4-147">[WPF Designer for Windows Forms Developers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))</span></span>
- [<span data-ttu-id="cd6b4-148">チュートリアル: WPF での Windows フォーム コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="cd6b4-148">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="cd6b4-149">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="cd6b4-149">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="cd6b4-150">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="cd6b4-150">Migration and Interoperability</span></span>](migration-and-interoperability.md)
