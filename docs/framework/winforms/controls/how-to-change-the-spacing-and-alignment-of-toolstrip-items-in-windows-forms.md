---
title: '方法: Windows フォーム内の ToolStrip 項目の間隔と配置を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: c7a874659be8dbaec66b78e1e065bcbec21da3b4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650877"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="bc1fc-102">方法: Windows フォーム内の ToolStrip 項目の間隔と配置を変更する</span><span class="sxs-lookup"><span data-stu-id="bc1fc-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="bc1fc-103"><xref:System.Windows.Forms.ToolStrip>コントロールがサイズ変更の間隔などのレイアウト機能を完全にサポート<xref:System.Windows.Forms.ToolStripItem>で相互に比較した、コントロールの配置を制御、<xref:System.Windows.Forms.ToolStrip>とに関連するコントロールの間の間隔、<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="bc1fc-104">の既定値、<xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>プロパティは`true`、設定しない限り、コントロールは自動的に規模、<xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>プロパティを`false`します。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="bc1fc-105">ToolStripItem を手動で調整するには</span><span class="sxs-lookup"><span data-stu-id="bc1fc-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="bc1fc-106">設定、<xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>プロパティを`false`に関連付けられたコントロール。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="bc1fc-107">設定、<xref:System.Windows.Forms.ToolStripItem.Size%2A>プロパティに関連付けられている希望どおり<xref:System.Windows.Forms.ToolStripItem>します。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="bc1fc-108">ToolStripItem の間隔を設定するには</span><span class="sxs-lookup"><span data-stu-id="bc1fc-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="bc1fc-109">(ピクセル単位) で、目的の値を挿入、<xref:System.Windows.Forms.ToolStripItem.Margin%2A>関連するコントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="bc1fc-110">値、<xref:System.Windows.Forms.ToolStripItem.Margin%2A>プロパティは、この順序で項目と隣接する項目間の間隔を指定します。左、上、右、下。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="bc1fc-111">コマンド バーの右側に ToolStripItem を配置するには</span><span class="sxs-lookup"><span data-stu-id="bc1fc-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="bc1fc-112">設定、<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>プロパティを<xref:System.Windows.Forms.ToolStripItemAlignment.Right>に関連付けられたコントロール。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="bc1fc-113">既定では、<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>に設定されている<xref:System.Windows.Forms.ToolStripItemAlignment.Left>の左側にあるコントロールを配置する、<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="bc1fc-114">コマンド バーの ToolStrip 項目を配置するには</span><span class="sxs-lookup"><span data-stu-id="bc1fc-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
- <span data-ttu-id="bc1fc-115">設定、<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>プロパティの値を<xref:System.Windows.Forms.ToolStripLayoutStyle>します。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bc1fc-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc1fc-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="bc1fc-117">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="bc1fc-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="bc1fc-118">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="bc1fc-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="bc1fc-119">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="bc1fc-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
