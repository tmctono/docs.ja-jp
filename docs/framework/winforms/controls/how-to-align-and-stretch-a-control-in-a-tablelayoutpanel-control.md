---
title: '方法: 配置して、コントロールを TableLayoutPanel コントロールで伸縮'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: 511ed20e63778b70355d1deb12e4256b4d2e9101
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702920"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a><span data-ttu-id="cf922-102">方法: 配置して、コントロールを TableLayoutPanel コントロールで伸縮</span><span class="sxs-lookup"><span data-stu-id="cf922-102">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>
<span data-ttu-id="cf922-103">内のコントロールを拡張して整列することができます、<xref:System.Windows.Forms.TableLayoutPanel>で、<xref:System.Windows.Forms.Control.Anchor%2A>と<xref:System.Windows.Forms.Control.Dock%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="cf922-103">You can align and stretch controls in a <xref:System.Windows.Forms.TableLayoutPanel> with the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf922-104">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf922-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="cf922-105">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf922-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="cf922-106">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf922-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-align-and-stretch-a-control"></a><span data-ttu-id="cf922-107">配置して伸縮を制御する</span><span class="sxs-lookup"><span data-stu-id="cf922-107">To align and stretch a control</span></span>  
  
1.  <span data-ttu-id="cf922-108"><xref:System.Windows.Forms.TableLayoutPanel> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="cf922-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="cf922-109">ドラッグ、<xref:System.Windows.Forms.Button>コントロールから、**ツールボックス**の左上隅のセルに、<xref:System.Windows.Forms.TableLayoutPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="cf922-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="cf922-110"><xref:System.Windows.Forms.Button>コントロールがセルの中央に配置します。</span><span class="sxs-lookup"><span data-stu-id="cf922-110">The <xref:System.Windows.Forms.Button> control is centered in the cell.</span></span>  
  
3.  <span data-ttu-id="cf922-111">値を設定、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Anchor%2A>プロパティを`Left,Right`します。</span><span class="sxs-lookup"><span data-stu-id="cf922-111">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left,Right`.</span></span> <span data-ttu-id="cf922-112"><xref:System.Windows.Forms.Button>端まで拡大に合わせてセルの幅を制御します。</span><span class="sxs-lookup"><span data-stu-id="cf922-112">The <xref:System.Windows.Forms.Button> control stretches to match the width of the cell.</span></span>  
  
4.  <span data-ttu-id="cf922-113">値を設定、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Anchor%2A>プロパティを`Top,Bottom`します。</span><span class="sxs-lookup"><span data-stu-id="cf922-113">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top,Bottom`.</span></span> <span data-ttu-id="cf922-114"><xref:System.Windows.Forms.Button>端まで拡大に合わせてセルの高さを制御します。</span><span class="sxs-lookup"><span data-stu-id="cf922-114">The <xref:System.Windows.Forms.Button> control stretches to match the height of the cell.</span></span>  
  
5.  <span data-ttu-id="cf922-115">値を設定、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Dock%2A>プロパティを<xref:System.Windows.Forms.DockStyle.Fill>します。</span><span class="sxs-lookup"><span data-stu-id="cf922-115">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="cf922-116"><xref:System.Windows.Forms.Button>セル コントロールを拡張します。</span><span class="sxs-lookup"><span data-stu-id="cf922-116">The <xref:System.Windows.Forms.Button> control expands to fill the cell.</span></span>  
  
6.  <span data-ttu-id="cf922-117">値を設定、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Dock%2A>プロパティを<xref:System.Windows.Forms.DockStyle.None>します。</span><span class="sxs-lookup"><span data-stu-id="cf922-117">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.None>.</span></span> <span data-ttu-id="cf922-118"><xref:System.Windows.Forms.Button>コントロールは、元のサイズを返し、セルの左上隅に移動します。</span><span class="sxs-lookup"><span data-stu-id="cf922-118">The <xref:System.Windows.Forms.Button> control returns to its original size and moves to the upper-left corner of the cell.</span></span> <span data-ttu-id="cf922-119">**Windows フォーム デザイナー**設定が、<xref:System.Windows.Forms.Control.Anchor%2A>プロパティを`Top, Left`します。</span><span class="sxs-lookup"><span data-stu-id="cf922-119">The **Windows Forms Designer** has set the <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span>  
  
7.  <span data-ttu-id="cf922-120">値を設定、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Anchor%2A>プロパティを`Bottom,Right`します。</span><span class="sxs-lookup"><span data-stu-id="cf922-120">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Bottom,Right`.</span></span> <span data-ttu-id="cf922-121"><xref:System.Windows.Forms.Button>コントロールがセルの右下隅に移動します。</span><span class="sxs-lookup"><span data-stu-id="cf922-121">The <xref:System.Windows.Forms.Button> control moves to the lower-right corner of the cell.</span></span>  
  
8.  <span data-ttu-id="cf922-122">値を設定、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Anchor%2A>プロパティを<xref:System.Windows.Forms.AnchorStyles.None>します。</span><span class="sxs-lookup"><span data-stu-id="cf922-122">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.None>.</span></span> <span data-ttu-id="cf922-123"><xref:System.Windows.Forms.Button>コントロールがセルの中央に移動します。</span><span class="sxs-lookup"><span data-stu-id="cf922-123">The <xref:System.Windows.Forms.Button> control moves to the center of the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf922-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf922-124">See also</span></span>
- [<span data-ttu-id="cf922-125">TableLayoutPanel コントロール</span><span class="sxs-lookup"><span data-stu-id="cf922-125">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
