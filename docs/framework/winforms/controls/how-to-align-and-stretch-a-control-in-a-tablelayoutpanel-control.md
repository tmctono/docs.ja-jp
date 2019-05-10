---
title: '方法: TableLayoutPanel コントロール内でコントロールを配置して伸縮する'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: fd32593bcad9e3f3ef93edee8aa2659d423f9feb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210363"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a><span data-ttu-id="8bc7f-102">方法: TableLayoutPanel コントロール内でコントロールを配置して伸縮する</span><span class="sxs-lookup"><span data-stu-id="8bc7f-102">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>

<span data-ttu-id="8bc7f-103">内のコントロールを拡張して整列することができます、<xref:System.Windows.Forms.TableLayoutPanel>で、<xref:System.Windows.Forms.Control.Anchor%2A>と<xref:System.Windows.Forms.Control.Dock%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-103">You can align and stretch controls in a <xref:System.Windows.Forms.TableLayoutPanel> with the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties.</span></span>

## <a name="align-and-stretch-a-control"></a><span data-ttu-id="8bc7f-104">配置して伸縮コントロール</span><span class="sxs-lookup"><span data-stu-id="8bc7f-104">Align and stretch a control</span></span>

1. <span data-ttu-id="8bc7f-105">Visual Studio で、ドラッグ、<xref:System.Windows.Forms.TableLayoutPanel>コントロールから、**ツールボックス**フォームにします。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-105">In Visual Studio, drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="8bc7f-106">ドラッグ、<xref:System.Windows.Forms.Button>コントロールから、**ツールボックス**の左上隅のセルに、<xref:System.Windows.Forms.TableLayoutPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-106">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="8bc7f-107"><xref:System.Windows.Forms.Button>コントロールがセルの中央に配置します。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-107">The <xref:System.Windows.Forms.Button> control is centered in the cell.</span></span>

3. <span data-ttu-id="8bc7f-108">値を設定、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Anchor%2A>プロパティを`Left,Right`します。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-108">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left,Right`.</span></span> <span data-ttu-id="8bc7f-109"><xref:System.Windows.Forms.Button>端まで拡大に合わせてセルの幅を制御します。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-109">The <xref:System.Windows.Forms.Button> control stretches to match the width of the cell.</span></span>

4. <span data-ttu-id="8bc7f-110">値を設定、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Anchor%2A>プロパティを`Top,Bottom`します。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-110">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top,Bottom`.</span></span> <span data-ttu-id="8bc7f-111"><xref:System.Windows.Forms.Button>端まで拡大に合わせてセルの高さを制御します。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-111">The <xref:System.Windows.Forms.Button> control stretches to match the height of the cell.</span></span>

5. <span data-ttu-id="8bc7f-112">値を設定、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Dock%2A>プロパティを<xref:System.Windows.Forms.DockStyle.Fill>します。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-112">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="8bc7f-113"><xref:System.Windows.Forms.Button>セル コントロールを拡張します。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-113">The <xref:System.Windows.Forms.Button> control expands to fill the cell.</span></span>

6. <span data-ttu-id="8bc7f-114">値を設定、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Dock%2A>プロパティを<xref:System.Windows.Forms.DockStyle.None>します。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-114">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.None>.</span></span> <span data-ttu-id="8bc7f-115"><xref:System.Windows.Forms.Button>コントロールは、元のサイズを返し、セルの左上隅に移動します。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-115">The <xref:System.Windows.Forms.Button> control returns to its original size and moves to the upper-left corner of the cell.</span></span> <span data-ttu-id="8bc7f-116">**Windows フォーム デザイナー**設定が、<xref:System.Windows.Forms.Control.Anchor%2A>プロパティを`Top, Left`します。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-116">The **Windows Forms Designer** has set the <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span>

7. <span data-ttu-id="8bc7f-117">値を設定、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Anchor%2A>プロパティを`Bottom,Right`します。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-117">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Bottom,Right`.</span></span> <span data-ttu-id="8bc7f-118"><xref:System.Windows.Forms.Button>コントロールがセルの右下隅に移動します。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-118">The <xref:System.Windows.Forms.Button> control moves to the lower-right corner of the cell.</span></span>

8. <span data-ttu-id="8bc7f-119">値を設定、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Anchor%2A>プロパティを<xref:System.Windows.Forms.AnchorStyles.None>します。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-119">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.None>.</span></span> <span data-ttu-id="8bc7f-120"><xref:System.Windows.Forms.Button>コントロールがセルの中央に移動します。</span><span class="sxs-lookup"><span data-stu-id="8bc7f-120">The <xref:System.Windows.Forms.Button> control moves to the center of the cell.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bc7f-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bc7f-121">See also</span></span>

- [<span data-ttu-id="8bc7f-122">TableLayoutPanel コントロール</span><span class="sxs-lookup"><span data-stu-id="8bc7f-122">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
