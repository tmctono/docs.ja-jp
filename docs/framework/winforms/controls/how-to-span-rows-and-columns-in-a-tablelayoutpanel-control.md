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
ms.openlocfilehash: a215b2b4e05bab5c81d2779d4b67d5b9d57b6ba5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039695"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="109eb-102">方法: TableLayoutPanel コントロールの行と列を拡大する</span><span class="sxs-lookup"><span data-stu-id="109eb-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="109eb-103"><xref:System.Windows.Forms.TableLayoutPanel>コントロール内のコントロールは、隣接する行と列にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="109eb-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>

## <a name="to-span-columns-and-rows"></a><span data-ttu-id="109eb-104">列と行をスパンするには</span><span class="sxs-lookup"><span data-stu-id="109eb-104">To span columns and rows</span></span>

1. <span data-ttu-id="109eb-105"><xref:System.Windows.Forms.TableLayoutPanel> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="109eb-105">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="109eb-106">[ <xref:System.Windows.Forms.Button> **ツールボックス**] からコントロールをドラッグして、 <xref:System.Windows.Forms.TableLayoutPanel>コントロールの左上のセルに移動します。</span><span class="sxs-lookup"><span data-stu-id="109eb-106">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="109eb-107">コントロールの**columnspan**プロパティを2に設定します。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="109eb-107">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="109eb-108">コントロールが<xref:System.Windows.Forms.Button> 1 番目と2番目の列にまたがっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="109eb-108">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>

4. <span data-ttu-id="109eb-109">コントロールの RowSpan プロパティを**2**に設定します。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="109eb-109">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="109eb-110">コントロールが<xref:System.Windows.Forms.Button> 1 行目と2番目の行にまたがっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="109eb-110">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>

5. <span data-ttu-id="109eb-111">コントロールの**columnspan**プロパティを1に設定します。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="109eb-111">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="109eb-112">コントロールが<xref:System.Windows.Forms.Button>最初の列に移動し、最初の行と2番目の行にまたがっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="109eb-112">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>

## <a name="see-also"></a><span data-ttu-id="109eb-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="109eb-113">See also</span></span>

- [<span data-ttu-id="109eb-114">TableLayoutPanel コントロール</span><span class="sxs-lookup"><span data-stu-id="109eb-114">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
