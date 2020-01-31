---
title: DataGridView コントロールの行の外観をカスタマイズする
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
ms.openlocfilehash: 099b2104e7a4887aa846c4d65273db2dd4f60559
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744040"
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="f7242-102">方法 : Windows フォームの DataGridView コントロールの行の外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="f7242-102">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f7242-103"><xref:System.Windows.Forms.DataGridView> 行の外観を制御するには、<xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> イベントと <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> イベントの一方、または両方を処理します。</span><span class="sxs-lookup"><span data-stu-id="f7242-103">You can control the appearance of <xref:System.Windows.Forms.DataGridView> rows by handling one or both of the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> and <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> events.</span></span> <span data-ttu-id="f7242-104">これらのイベントは、ユーザーが任意のものだけ描画し、残りは <xref:System.Windows.Forms.DataGridView> コントロールに描画させるようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="f7242-104">These events are designed so that you can paint only what you want to while letting the <xref:System.Windows.Forms.DataGridView> control paint the rest.</span></span> <span data-ttu-id="f7242-105">たとえば、カスタムの背景を描画する場合は、<xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> イベントを処理し、それぞれの前景の内容は個々のセルに描画させるようにします。</span><span class="sxs-lookup"><span data-stu-id="f7242-105">For example, if you want to paint a custom background, you can handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event and let the individual cells paint their own foreground content.</span></span> <span data-ttu-id="f7242-106">または、セルを自動的に描画させ、<xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> イベントのハンドラーでカスタムの前景の内容を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7242-106">Alternately, you can let the cells paint themselves and add custom foreground content in a handler for the <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="f7242-107">さらに、<xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> イベント ハンドラーを使用すれば、セルの描画をすべて無効にし、ユーザー自身ですべてを描画することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7242-107">You can also disable cell painting and paint everything yourself in a <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event handler.</span></span>  
  
 <span data-ttu-id="f7242-108">次のコード例では、選択行にグラデーションの背景を表示し、複数の列にわたるカスタムの前景の内容を提供するために、両方のイベントのハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="f7242-108">The following code example implements handlers for both events in order to provide a gradient selection background and some custom foreground content that spans multiple columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7242-109">使用例</span><span class="sxs-lookup"><span data-stu-id="f7242-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f7242-110">コードのコンパイル方法</span><span class="sxs-lookup"><span data-stu-id="f7242-110">Compiling the Code</span></span>  
 <span data-ttu-id="f7242-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f7242-111">This example requires:</span></span>  
  
- <span data-ttu-id="f7242-112">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="f7242-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7242-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7242-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [<span data-ttu-id="f7242-114">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="f7242-114">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f7242-115">DataGridView コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="f7242-115">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
