---
title: '方法: ToolStrip コントロールにツールヒントを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 3f383b6cccba7825637ea65a0e13280b91b406c9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939734"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="0ddbf-102">方法: ToolStrip コントロールにツールヒントを使用する</span><span class="sxs-lookup"><span data-stu-id="0ddbf-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="0ddbf-103">コントロールの<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>プロパティを<xref:System.Windows.Forms.ToolTip> <xref:System.Windows.Forms.ToolStrip> に`true`設定することによって、必要なコントロールのを表示できます。</span><span class="sxs-lookup"><span data-stu-id="0ddbf-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="0ddbf-104">ツールヒントを表示するには</span><span class="sxs-lookup"><span data-stu-id="0ddbf-104">To display a ToolTip</span></span>  
  
- <span data-ttu-id="0ddbf-105">`true`コントロールの<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>プロパティをに設定します。</span><span class="sxs-lookup"><span data-stu-id="0ddbf-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="0ddbf-106">の<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType>既定値は`true`で、と<xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType>の<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType>既定値は`false`です。</span><span class="sxs-lookup"><span data-stu-id="0ddbf-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="0ddbf-107">ToolStripButton のツールヒントテキストに ToolTipText プロパティを使用するには</span><span class="sxs-lookup"><span data-stu-id="0ddbf-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1. <span data-ttu-id="0ddbf-108">`true`ボタンの<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>プロパティをに設定します。</span><span class="sxs-lookup"><span data-stu-id="0ddbf-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2. <span data-ttu-id="0ddbf-109">`false`ボタンの<xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType>プロパティをに設定します。</span><span class="sxs-lookup"><span data-stu-id="0ddbf-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="0ddbf-110">`true` <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolStripDropDownButton>既定で<xref:System.Windows.Forms.ToolStripSplitButton>は、、、およびに対してプロパティが使用されます。`AutoToolTip`</span><span class="sxs-lookup"><span data-stu-id="0ddbf-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="0ddbf-111">は<xref:System.Windows.Forms.ToolStripButton> 、既定`Text`ではその<xref:System.Windows.Forms.ToolTip>プロパティをテキストに使用します。</span><span class="sxs-lookup"><span data-stu-id="0ddbf-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="0ddbf-112">でカスタムテキストを表示するには、 <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0ddbf-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ddbf-113">をまたは<xref:System.Windows.Forms.ToolStripItemDisplayStyle> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> に<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>設定しても、ボタンにテキストは表示されませんが、ツールヒントは表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ddbf-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ddbf-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ddbf-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="0ddbf-115">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="0ddbf-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
