---
title: DataGridView セル内のコントロールのホスト
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: a64521a15a272ca8140302f39d15e7f17e0c423b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736541"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a><span data-ttu-id="13fe8-102">方法 : Windows フォーム DataGridView Cells でコントロールをホストする</span><span class="sxs-lookup"><span data-stu-id="13fe8-102">How to: Host Controls in Windows Forms DataGridView Cells</span></span>
<span data-ttu-id="13fe8-103"><xref:System.Windows.Forms.DataGridView> コントロールには数種類の列があり、ユーザーはさまざまな方法で値を入力し、編集できます。</span><span class="sxs-lookup"><span data-stu-id="13fe8-103">The <xref:System.Windows.Forms.DataGridView> control provides several column types, enabling your users to enter and edit values in a variety of ways.</span></span> <span data-ttu-id="13fe8-104">ただし、これらの種類の列がデータ入力の要件を満たさない場合は、独自の種類の列を作成して、任意のコントロールをホストするセルを用意できます。</span><span class="sxs-lookup"><span data-stu-id="13fe8-104">If these column types do not meet your data-entry needs, however, you can create your own column types with cells that host controls of your choosing.</span></span> <span data-ttu-id="13fe8-105">これを作成するには、<xref:System.Windows.Forms.DataGridViewColumn> および <xref:System.Windows.Forms.DataGridViewCell> から派生する各クラスを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13fe8-105">To do this, you must define classes that derive from <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewCell>.</span></span> <span data-ttu-id="13fe8-106">また、<xref:System.Windows.Forms.Control> から派生し、<xref:System.Windows.Forms.IDataGridViewEditingControl> インターフェイスを実装するクラスを定義する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="13fe8-106">You must also define a class that derives from <xref:System.Windows.Forms.Control> and implements the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
 <span data-ttu-id="13fe8-107">予定表の列を作成する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="13fe8-107">The following code example shows how to create a calendar column.</span></span> <span data-ttu-id="13fe8-108">この列のセルは、通常のテキスト ボックスのセルに日付を表示しますが、ユーザーがセルを編集するときには <xref:System.Windows.Forms.DateTimePicker> コントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="13fe8-108">The cells of this column display dates in ordinary text box cells, but when the user edits a cell, a <xref:System.Windows.Forms.DateTimePicker> control appears.</span></span> <span data-ttu-id="13fe8-109">テキスト ボックスの表示機能を再度実装しなくてもすむように、`CalendarCell` クラスは、<xref:System.Windows.Forms.DataGridViewCell> クラスを直接継承するのではなく <xref:System.Windows.Forms.DataGridViewTextBoxCell> クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="13fe8-109">In order to avoid having to implement text box display functionality again, the `CalendarCell` class derives from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> class rather than inheriting the <xref:System.Windows.Forms.DataGridViewCell> class directly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13fe8-110"><xref:System.Windows.Forms.DataGridViewCell> や <xref:System.Windows.Forms.DataGridViewColumn> から派生したクラスに新しいプロパティを追加するときは、`Clone` メソッドをオーバーライドし、複製操作時に新しいプロパティをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13fe8-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="13fe8-111">また、基底クラスの `Clone` メソッドを呼び出して、基底クラスのプロパティを新しいセルまたは列にコピーする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="13fe8-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13fe8-112">使用例</span><span class="sxs-lookup"><span data-stu-id="13fe8-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="13fe8-113">コードのコンパイル方法</span><span class="sxs-lookup"><span data-stu-id="13fe8-113">Compiling the Code</span></span>  
 <span data-ttu-id="13fe8-114">この例には、次の項目が必要です。</span><span class="sxs-lookup"><span data-stu-id="13fe8-114">The following example requires:</span></span>  
  
- <span data-ttu-id="13fe8-115">System アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="13fe8-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13fe8-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="13fe8-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>
- <xref:System.Windows.Forms.IDataGridViewEditingControl>
- <xref:System.Windows.Forms.DateTimePicker>
- [<span data-ttu-id="13fe8-117">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="13fe8-117">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="13fe8-118">DataGridView コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="13fe8-118">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="13fe8-119">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="13fe8-119">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
