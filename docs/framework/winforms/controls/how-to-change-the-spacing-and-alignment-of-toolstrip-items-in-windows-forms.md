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
ms.openlocfilehash: 805fbac5fe33071006f29692d503e5c57eacd765
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746564"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="7bc5d-102">方法 : Windows フォーム内の ToolStrip 項目の間隔と配置を変更する</span><span class="sxs-lookup"><span data-stu-id="7bc5d-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="7bc5d-103"><xref:System.Windows.Forms.ToolStrip> コントロールは、サイズ変更、相互に関連する <xref:System.Windows.Forms.ToolStripItem> コントロールの間隔、<xref:System.Windows.Forms.ToolStrip>上のコントロールの配置、<xref:System.Windows.Forms.ToolStrip>を基準としたコントロールの間隔などのレイアウト機能を完全にサポートします。</span><span class="sxs-lookup"><span data-stu-id="7bc5d-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="7bc5d-104"><xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> プロパティの既定値は `true`ので、<xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> プロパティを `false`に設定しない限り、コントロールは自動的にサイズ変更されます。</span><span class="sxs-lookup"><span data-stu-id="7bc5d-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="7bc5d-105">ToolStripItem のサイズを手動で変更するには</span><span class="sxs-lookup"><span data-stu-id="7bc5d-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="7bc5d-106">関連付けられたコントロールの <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> プロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="7bc5d-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="7bc5d-107">関連する <xref:System.Windows.Forms.ToolStripItem>に対して、<xref:System.Windows.Forms.ToolStripItem.Size%2A> プロパティを必要に応じて設定します。</span><span class="sxs-lookup"><span data-stu-id="7bc5d-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="7bc5d-108">ToolStripItem の間隔を設定するには</span><span class="sxs-lookup"><span data-stu-id="7bc5d-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="7bc5d-109">目的の値をピクセル単位で、関連付けられているコントロールの <xref:System.Windows.Forms.ToolStripItem.Margin%2A> プロパティに挿入します。</span><span class="sxs-lookup"><span data-stu-id="7bc5d-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="7bc5d-110"><xref:System.Windows.Forms.ToolStripItem.Margin%2A> プロパティの値は、項目と隣接する項目の間の間隔を、左、上、右、下の順に指定します。</span><span class="sxs-lookup"><span data-stu-id="7bc5d-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="7bc5d-111">ToolStripItem を ToolStrip の右側に配置するには</span><span class="sxs-lookup"><span data-stu-id="7bc5d-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="7bc5d-112">関連付けられたコントロールの <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> プロパティを <xref:System.Windows.Forms.ToolStripItemAlignment.Right> に設定します。</span><span class="sxs-lookup"><span data-stu-id="7bc5d-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="7bc5d-113">既定では、<xref:System.Windows.Forms.ToolStripItem.Alignment%2A> は <xref:System.Windows.Forms.ToolStripItemAlignment.Left>に設定されます。これにより、コントロールが <xref:System.Windows.Forms.ToolStrip>の左側に配置されます。</span><span class="sxs-lookup"><span data-stu-id="7bc5d-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="7bc5d-114">Toolstrip に ToolStrip 項目を配置するには</span><span class="sxs-lookup"><span data-stu-id="7bc5d-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
- <span data-ttu-id="7bc5d-115"><xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> プロパティに、必要な <xref:System.Windows.Forms.ToolStripLayoutStyle> の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7bc5d-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7bc5d-116">参照</span><span class="sxs-lookup"><span data-stu-id="7bc5d-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="7bc5d-117">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="7bc5d-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="7bc5d-118">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="7bc5d-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="7bc5d-119">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="7bc5d-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
