---
title: DataGridView コントロールのボタン列にあるボタンを無効にする
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
ms.openlocfilehash: 691781a43005d66e13029ab8110eb7f9daacc35f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745947"
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="ad04c-102">方法 : Windows フォーム DataGridView コントロールのボタン列にあるボタンを無効にする</span><span class="sxs-lookup"><span data-stu-id="ad04c-102">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="ad04c-103"><xref:System.Windows.Forms.DataGridView> コントロールには、ボタンのようなユーザー インターフェイス (UI) を持つセルを表示するための <xref:System.Windows.Forms.DataGridViewButtonCell> クラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ad04c-103">The <xref:System.Windows.Forms.DataGridView> control includes the <xref:System.Windows.Forms.DataGridViewButtonCell> class for displaying cells with a user interface (UI) like a button.</span></span> <span data-ttu-id="ad04c-104">ただし、<xref:System.Windows.Forms.DataGridViewButtonCell> はセルによって表示されるボタンの外観を無効にする方法は提供しません。</span><span class="sxs-lookup"><span data-stu-id="ad04c-104">However, <xref:System.Windows.Forms.DataGridViewButtonCell> does not provide a way to disable the appearance of the button displayed by the cell.</span></span>  
  
 <span data-ttu-id="ad04c-105">次のコード例は、<xref:System.Windows.Forms.DataGridViewButtonCell> クラスをカスタマイズして表示可能で無効になっているボタンを表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ad04c-105">The following code example demonstrates how to customize the <xref:System.Windows.Forms.DataGridViewButtonCell> class to display buttons that can appear disabled.</span></span> <span data-ttu-id="ad04c-106">この例は、`DataGridViewDisableButtonCell` から派生した新しいセルの種類 <xref:System.Windows.Forms.DataGridViewButtonCell> を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad04c-106">The example defines a new cell type, `DataGridViewDisableButtonCell`, that derives from <xref:System.Windows.Forms.DataGridViewButtonCell>.</span></span> <span data-ttu-id="ad04c-107">このセルの種類は、`Enabled` に設定して無効になっているボタンをセルに描画する提供できる新しい `false` プロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="ad04c-107">This cell type provides a new `Enabled` property that can be set to `false` to draw a disabled button in the cell.</span></span> <span data-ttu-id="ad04c-108">例は、`DataGridViewDisableButtonColumn` オブジェクトを表示する、新しい列の種類である `DataGridViewDisableButtonCell` も定義します。</span><span class="sxs-lookup"><span data-stu-id="ad04c-108">The example also defines a new column type, `DataGridViewDisableButtonColumn`, that displays `DataGridViewDisableButtonCell` objects.</span></span> <span data-ttu-id="ad04c-109">この新しいセルと列の種類を示すために、親の <xref:System.Windows.Forms.DataGridViewCheckBoxCell> 内の各 <xref:System.Windows.Forms.DataGridView> の現在値が、同じ行にある`Enabled` の `DataGridViewDisableButtonCell` プロパティが `true` と `false` のいずれであるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ad04c-109">To demonstrate this new cell and column type, the current value of each <xref:System.Windows.Forms.DataGridViewCheckBoxCell> in the parent <xref:System.Windows.Forms.DataGridView> determines whether the `Enabled` property of the `DataGridViewDisableButtonCell` in the same row is `true` or `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad04c-110"><xref:System.Windows.Forms.DataGridViewCell> や <xref:System.Windows.Forms.DataGridViewColumn> から派生したクラスに新しいプロパティを追加するときは、`Clone` メソッドをオーバーライドし、複製操作時に新しいプロパティをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad04c-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="ad04c-111">また、基底クラスの `Clone` メソッドを呼び出して、基底クラスのプロパティを新しいセルまたは列にコピーする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="ad04c-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad04c-112">例</span><span class="sxs-lookup"><span data-stu-id="ad04c-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ad04c-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ad04c-113">Compiling the Code</span></span>  
 <span data-ttu-id="ad04c-114">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad04c-114">This example requires:</span></span>  
  
- <span data-ttu-id="ad04c-115">System、System.Drawing、System.Windows.Forms、および System.Windows.Forms.VisualStyles の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="ad04c-115">References to the System, System.Drawing, System.Windows.Forms and System.Windows.Forms.VisualStyles assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad04c-116">参照</span><span class="sxs-lookup"><span data-stu-id="ad04c-116">See also</span></span>

- [<span data-ttu-id="ad04c-117">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="ad04c-117">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="ad04c-118">DataGridView コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="ad04c-118">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="ad04c-119">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="ad04c-119">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
