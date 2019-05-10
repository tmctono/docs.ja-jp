---
title: '方法: デザイン時に ElementHost コントロールをコピーして貼り付ける'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 0f3367deaaec04744a3f812d7f2d08047d7eb588
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211383"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="dd176-102">方法: デザイン時に ElementHost コントロールをコピーして貼り付ける</span><span class="sxs-lookup"><span data-stu-id="dd176-102">How to: Copy and Paste an ElementHost Control at Design Time</span></span>

<span data-ttu-id="dd176-103">この手順では、Visual Studio で Windows フォーム上の Windows Presentation Foundation (WPF) コントロールをコピーする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dd176-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

## <a name="copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="dd176-104">コピーして、デザイン時に ElementHost コントロールを貼り付ける</span><span class="sxs-lookup"><span data-stu-id="dd176-104">Copy and paste an ElementHost control at design time</span></span>

1. <span data-ttu-id="dd176-105">新しい WPF 追加<xref:System.Windows.Controls.UserControl>を Windows フォーム プロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="dd176-105">Add a new WPF <xref:System.Windows.Controls.UserControl> to your Windows Forms project.</span></span> <span data-ttu-id="dd176-106">コントロール型の既定の名前である `UserControl1.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="dd176-106">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="dd176-107">詳細については、「[チュートリアル:デザイン時に Windows フォームで新しい WPF コンテンツを作成する](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)します。</span><span class="sxs-lookup"><span data-stu-id="dd176-107">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="dd176-108">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティの`UserControl1`に`200`します。</span><span class="sxs-lookup"><span data-stu-id="dd176-108">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to `200`.</span></span>

3. <span data-ttu-id="dd176-109"><xref:System.Windows.Controls.Control.Background%2A> プロパティの値を `Blue` に設定します。</span><span class="sxs-lookup"><span data-stu-id="dd176-109">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>

4. <span data-ttu-id="dd176-110">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="dd176-110">Build the project.</span></span>

5. <span data-ttu-id="dd176-111">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="dd176-111">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="dd176-112">**ツールボックス**のインスタンスをドラッグ`UserControl1`フォーム上にします。</span><span class="sxs-lookup"><span data-stu-id="dd176-112">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="dd176-113">`UserControl1` のインスタンスは、`elementHost1` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="dd176-113">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="dd176-114">`elementHost1` を選択して、CTRL + C キーを押してクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dd176-114">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>

8. <span data-ttu-id="dd176-115">コピーしたコントロールをフォームに貼り付けるには、CTRL + V キーを押します。</span><span class="sxs-lookup"><span data-stu-id="dd176-115">Press CTRL+V to paste the copied control onto the form.</span></span>

   <span data-ttu-id="dd176-116">新しい<xref:System.Windows.Forms.Integration.ElementHost>という名前のコントロール`elementHost2`フォーム上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="dd176-116">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd176-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd176-117">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="dd176-118">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="dd176-118">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="dd176-119">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="dd176-119">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="dd176-120">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="dd176-120">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
