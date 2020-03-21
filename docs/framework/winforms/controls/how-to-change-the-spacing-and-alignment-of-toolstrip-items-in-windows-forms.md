---
title: '方法: ToolStrip 項目の間隔と配置を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182239"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="c5001-102">方法 : Windows フォーム内の ToolStrip 項目の間隔と配置を変更する</span><span class="sxs-lookup"><span data-stu-id="c5001-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="c5001-103">この<xref:System.Windows.Forms.ToolStrip>コントロールは、サイズ変更、相互に相対的なコントロールの<xref:System.Windows.Forms.ToolStripItem>間隔、<xref:System.Windows.Forms.ToolStrip>コントロールの配置、コントロールの間隔などのレイアウト機能を完全にサポートしています<xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="c5001-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="c5001-104">プロパティの既定値は に<xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>設定されている`true`場合、<xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>プロパティのサイズは自動的に`false`変更されます。</span><span class="sxs-lookup"><span data-stu-id="c5001-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="c5001-105">手動でサイズを変更するには</span><span class="sxs-lookup"><span data-stu-id="c5001-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="c5001-106">関連付<xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>けられたコントロール`false`の プロパティを に設定します。</span><span class="sxs-lookup"><span data-stu-id="c5001-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="c5001-107">関連付<xref:System.Windows.Forms.ToolStripItem.Size%2A>けられた<xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="c5001-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="c5001-108">ツールストリップ アイテムの間隔を設定するには</span><span class="sxs-lookup"><span data-stu-id="c5001-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="c5001-109">関連付けられたコントロールのプロパティに、必要な<xref:System.Windows.Forms.ToolStripItem.Margin%2A>値をピクセル単位で挿入します。</span><span class="sxs-lookup"><span data-stu-id="c5001-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="c5001-110"><xref:System.Windows.Forms.ToolStripItem.Margin%2A>このプロパティの値は、アイテムと隣接するアイテムの間隔を、左、上、右、下の順に指定します。</span><span class="sxs-lookup"><span data-stu-id="c5001-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="c5001-111">ツールストリップアイテムをツールストリップの右側に揃えるには</span><span class="sxs-lookup"><span data-stu-id="c5001-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="c5001-112">関連付<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>けられたコントロール<xref:System.Windows.Forms.ToolStripItemAlignment.Right>の プロパティを に設定します。</span><span class="sxs-lookup"><span data-stu-id="c5001-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="c5001-113">既定では、 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> <xref:System.Windows.Forms.ToolStripItemAlignment.Left>は に設定され、コントロールは<xref:System.Windows.Forms.ToolStrip>の左側に揃えます。</span><span class="sxs-lookup"><span data-stu-id="c5001-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="c5001-114">ツールストリップの項目を配置するには</span><span class="sxs-lookup"><span data-stu-id="c5001-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
- <span data-ttu-id="c5001-115">プロパティを<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>目的の<xref:System.Windows.Forms.ToolStripLayoutStyle>値に設定します。</span><span class="sxs-lookup"><span data-stu-id="c5001-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c5001-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5001-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="c5001-117">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="c5001-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="c5001-118">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="c5001-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="c5001-119">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="c5001-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
