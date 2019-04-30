---
title: Windows フォーム DataGridView コントロール内のデータの並べ替え
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 606ffc7bd6136b775adaaaa79cf5042cf1e2dd70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012148"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="9a73b-102">Windows フォーム DataGridView コントロール内のデータの並べ替え</span><span class="sxs-lookup"><span data-stu-id="9a73b-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="9a73b-103">既定では、ユーザーが内のデータを並べ替えることができます、<xref:System.Windows.Forms.DataGridView>コントロールのテキスト ボックスの列見出しをクリックして (またはテキスト ボックスのセルは、.NET Framework 4.7.2 以降でフォーカスがあるときに、f3 キーを押して)。</span><span class="sxs-lookup"><span data-stu-id="9a73b-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="9a73b-104">変更することができます、<xref:System.Windows.Forms.DataGridViewColumn.SortMode>をこれを行う方が良い場合、その他の列の型を並べ替えるにはユーザーを許可する特定の列のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="9a73b-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="9a73b-105">任意の列または複数の列で、データをプログラムで並べ替えるもできます。</span><span class="sxs-lookup"><span data-stu-id="9a73b-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9a73b-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9a73b-106">In this section</span></span>

[<span data-ttu-id="9a73b-107">Windows フォーム DataGridView コントロール内の列の並べ替えモード</span><span class="sxs-lookup"><span data-stu-id="9a73b-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="9a73b-108">コントロール内のデータの並べ替えのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9a73b-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="9a73b-109">方法: Windows フォームの DataGridView コントロール内の列の並べ替えモードを設定します。</span><span class="sxs-lookup"><span data-stu-id="9a73b-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="9a73b-110">ユーザーが既定では並べ替えできない列による並べ替えを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a73b-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="9a73b-111">方法: Windows フォームの DataGridView コントロールでの並べ替えをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="9a73b-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="9a73b-112">プログラムでデータを並べ替える方法とを使用して並べ替え機能をカスタマイズする方法について説明します、<xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType>イベントまたは実装することによって、<xref:System.Collections.IComparer>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="9a73b-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="9a73b-113">参照</span><span class="sxs-lookup"><span data-stu-id="9a73b-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="9a73b-114"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="9a73b-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="9a73b-115">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridView.Sort%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="9a73b-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="9a73b-116">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="9a73b-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="9a73b-117">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridViewColumnSortMode>列挙体。</span><span class="sxs-lookup"><span data-stu-id="9a73b-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a73b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a73b-118">See also</span></span>

- [<span data-ttu-id="9a73b-119">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="9a73b-119">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="9a73b-120">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="9a73b-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
