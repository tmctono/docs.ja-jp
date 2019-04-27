---
title: '方法: TableLayoutPanel コントロールの行と列を拡大する'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: 02db78b07930676235e55e535fb24f6ff618d823
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012972"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="10007-102">方法: TableLayoutPanel コントロールの行と列を拡大する</span><span class="sxs-lookup"><span data-stu-id="10007-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="10007-103">コントロールで、<xref:System.Windows.Forms.TableLayoutPanel>コントロールが隣接する行と列にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="10007-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10007-104">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="10007-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="10007-105">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10007-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="10007-106">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10007-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-span-columns-and-rows"></a><span data-ttu-id="10007-107">列と行にまたがること</span><span class="sxs-lookup"><span data-stu-id="10007-107">To span columns and rows</span></span>  
  
1. <span data-ttu-id="10007-108"><xref:System.Windows.Forms.TableLayoutPanel> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="10007-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2. <span data-ttu-id="10007-109">ドラッグ、<xref:System.Windows.Forms.Button>コントロールから、**ツールボックス**の左上隅のセルに、<xref:System.Windows.Forms.TableLayoutPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="10007-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3. <span data-ttu-id="10007-110">設定、<xref:System.Windows.Forms.Button>コントロールの**ColumnSpan**プロパティを**2**します。</span><span class="sxs-lookup"><span data-stu-id="10007-110">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="10007-111">なお、<xref:System.Windows.Forms.Button>にまたがる最初と 2 番目の列を制御します。</span><span class="sxs-lookup"><span data-stu-id="10007-111">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>  
  
4. <span data-ttu-id="10007-112">設定、<xref:System.Windows.Forms.Button>コントロールの**RowSpan**プロパティを**2**します。</span><span class="sxs-lookup"><span data-stu-id="10007-112">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="10007-113">なお、<xref:System.Windows.Forms.Button>コントロールが最初と 2 番目の行にまたがっています。</span><span class="sxs-lookup"><span data-stu-id="10007-113">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>  
  
5. <span data-ttu-id="10007-114">設定、<xref:System.Windows.Forms.Button>コントロールの**ColumnSpan**プロパティを**1**します。</span><span class="sxs-lookup"><span data-stu-id="10007-114">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="10007-115">なお、<xref:System.Windows.Forms.Button>コントロールは、最初の列に移動し、最初と 2 番目の行にまたがます。</span><span class="sxs-lookup"><span data-stu-id="10007-115">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10007-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="10007-116">See also</span></span>

- [<span data-ttu-id="10007-117">TableLayoutPanel コントロール</span><span class="sxs-lookup"><span data-stu-id="10007-117">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
