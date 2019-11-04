---
title: '方法 : デザイン時に ElementHost コントロールをコピーして貼り付ける'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e89510558274558e560bf810afe746e250ff26a4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459231"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a><span data-ttu-id="9138b-102">方法: エンティティコントロールをコピーして貼り付ける</span><span class="sxs-lookup"><span data-stu-id="9138b-102">How to: Copy and paste an ElementHost control</span></span>

<span data-ttu-id="9138b-103">この手順では、Visual Studio の Windows フォームで Windows Presentation Foundation (WPF) コントロールをコピーする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9138b-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

1. <span data-ttu-id="9138b-104">Visual Studio で、新しい WPF <xref:System.Windows.Controls.UserControl> を Windows フォームプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="9138b-104">In Visual Studio, add a new WPF <xref:System.Windows.Controls.UserControl> to a Windows Forms project.</span></span> <span data-ttu-id="9138b-105">コントロール型の既定の名前である `UserControl1.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="9138b-105">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="9138b-106">詳細については、「[チュートリアル: デザイン時の Windows フォームでの新しい WPF コンテンツの作成](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9138b-106">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="9138b-107">**[プロパティ]** ウィンドウで、`UserControl1` の <xref:System.Windows.FrameworkElement.Width%2A> と <xref:System.Windows.FrameworkElement.Height%2A> のプロパティの値を**200**に設定します。</span><span class="sxs-lookup"><span data-stu-id="9138b-107">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to **200**.</span></span>

3. <span data-ttu-id="9138b-108"><xref:System.Windows.Controls.Control.Background%2A> プロパティの値を**Blue**に設定します。</span><span class="sxs-lookup"><span data-stu-id="9138b-108">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

4. <span data-ttu-id="9138b-109">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="9138b-109">Build the project.</span></span>

5. <span data-ttu-id="9138b-110">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="9138b-110">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="9138b-111">**[ツールボックス]** から `UserControl1` のインスタンスをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="9138b-111">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="9138b-112">`UserControl1` のインスタンスは、`elementHost1` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="9138b-112">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="9138b-113">`elementHost1` 選択した状態で、 **Ctrl**+**C**キーを押してクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9138b-113">With `elementHost1` selected, press **Ctrl**+**C** to copy it to the clipboard.</span></span>

8. <span data-ttu-id="9138b-114">**Ctrl**+**V**キーを押して、コピーしたコントロールをフォームに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9138b-114">Press **Ctrl**+**V** to paste the copied control onto the form.</span></span>

   <span data-ttu-id="9138b-115">`elementHost2` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールがフォーム上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="9138b-115">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="9138b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9138b-116">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="9138b-117">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="9138b-117">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="9138b-118">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="9138b-118">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="9138b-119">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="9138b-119">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
