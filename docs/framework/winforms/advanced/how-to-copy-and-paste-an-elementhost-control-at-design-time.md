---
title: '方法: デザイン時に ElementHost コントロールをコピーして貼り付ける'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: e8bc4aa4ecd2bff2981b7d4faf1e270337f346e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59346211"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="575c5-102">方法: デザイン時に ElementHost コントロールをコピーして貼り付ける</span><span class="sxs-lookup"><span data-stu-id="575c5-102">How to: Copy and Paste an ElementHost Control at Design Time</span></span>
<span data-ttu-id="575c5-103">この手順では、Windows フォーム上の Windows Presentation Foundation (WPF) コントロールをコピーする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="575c5-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="575c5-104">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="575c5-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="575c5-105">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="575c5-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="575c5-106">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="575c5-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="575c5-107">コピーしてデザイン時に ElementHost コントロールを貼り付ける</span><span class="sxs-lookup"><span data-stu-id="575c5-107">To copy and paste an ElementHost control at design time</span></span>  
  
1. <span data-ttu-id="575c5-108">新しい WPF 追加<xref:System.Windows.Controls.UserControl>を Windows フォーム プロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="575c5-108">Add a new WPF <xref:System.Windows.Controls.UserControl> to your Windows Forms project.</span></span> <span data-ttu-id="575c5-109">コントロール型の既定の名前である `UserControl1.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="575c5-109">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="575c5-110">詳細については、「[チュートリアル:デザイン時に Windows フォームで新しい WPF コンテンツを作成する](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)します。</span><span class="sxs-lookup"><span data-stu-id="575c5-110">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2. <span data-ttu-id="575c5-111">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティの`UserControl1`に`200`します。</span><span class="sxs-lookup"><span data-stu-id="575c5-111">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to `200`.</span></span>  
  
3. <span data-ttu-id="575c5-112"><xref:System.Windows.Controls.Control.Background%2A> プロパティの値を `Blue` に設定します。</span><span class="sxs-lookup"><span data-stu-id="575c5-112">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
4. <span data-ttu-id="575c5-113">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="575c5-113">Build the project.</span></span>  
  
5. <span data-ttu-id="575c5-114">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="575c5-114">Open `Form1` in the Windows Forms Designer.</span></span>  
  
6. <span data-ttu-id="575c5-115">**ツールボックス**のインスタンスをドラッグ`UserControl1`フォーム上にします。</span><span class="sxs-lookup"><span data-stu-id="575c5-115">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="575c5-116">`UserControl1` のインスタンスは、`elementHost1` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="575c5-116">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
7. <span data-ttu-id="575c5-117">`elementHost1` を選択して、CTRL + C キーを押してクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="575c5-117">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
8. <span data-ttu-id="575c5-118">コピーしたコントロールをフォームに貼り付けるには、CTRL + V キーを押します。</span><span class="sxs-lookup"><span data-stu-id="575c5-118">Press CTRL+V to paste the copied control onto the form.</span></span>  
  
     <span data-ttu-id="575c5-119">新しい<xref:System.Windows.Forms.Integration.ElementHost>という名前のコントロール`elementHost2`フォーム上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="575c5-119">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="575c5-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="575c5-120">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="575c5-121">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="575c5-121">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="575c5-122">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="575c5-122">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="575c5-123">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="575c5-123">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
