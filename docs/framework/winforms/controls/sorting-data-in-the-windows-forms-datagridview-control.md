---
title: DataGridView コントロールでのデータの並べ替え
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742952"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="88bda-102">Windows フォーム DataGridView コントロールでのデータの並べ替え</span><span class="sxs-lookup"><span data-stu-id="88bda-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="88bda-103">既定では、ユーザーはテキストボックスの列のヘッダーをクリックして <xref:System.Windows.Forms.DataGridView> コントロールのデータを並べ替えることができます (または、テキストボックスのセルが4.7.2 以降 .NET Framework のバージョンにフォーカスされている場合は、F3 キーを押します)。</span><span class="sxs-lookup"><span data-stu-id="88bda-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="88bda-104">特定の列の <xref:System.Windows.Forms.DataGridViewColumn.SortMode> プロパティを変更することで、ユーザーが他の列の種類を基準に並べ替えられるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="88bda-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="88bda-105">また、任意の列または複数の列を使用して、データをプログラムによって並べ替えることもできます。</span><span class="sxs-lookup"><span data-stu-id="88bda-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="88bda-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="88bda-106">In this section</span></span>

[<span data-ttu-id="88bda-107">Windows フォーム DataGridView コントロール内の列の並べ替えモード</span><span class="sxs-lookup"><span data-stu-id="88bda-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="88bda-108">コントロール内のデータを並べ替えるためのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="88bda-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="88bda-109">方法: Windows フォーム DataGridView コントロール内の列の並べ替えモードを設定する</span><span class="sxs-lookup"><span data-stu-id="88bda-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="88bda-110">既定では並べ替えられていない列でユーザーが並べ替えることができるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88bda-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="88bda-111">方法: Windows フォーム DataGridView コントロールの並べ替え機能をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="88bda-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="88bda-112">プログラムによってデータを並べ替える方法と、<xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> イベントを使用するか <xref:System.Collections.IComparer> インターフェイスを実装することによって並べ替えをカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88bda-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="88bda-113">参照先</span><span class="sxs-lookup"><span data-stu-id="88bda-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="88bda-114"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="88bda-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="88bda-115"><xref:System.Windows.Forms.DataGridView.Sort%2A> メソッドのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="88bda-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="88bda-116"><xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> プロパティのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="88bda-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="88bda-117"><xref:System.Windows.Forms.DataGridViewColumnSortMode> 列挙体に関するリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="88bda-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="88bda-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="88bda-118">See also</span></span>

- [<span data-ttu-id="88bda-119">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="88bda-119">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="88bda-120">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="88bda-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
