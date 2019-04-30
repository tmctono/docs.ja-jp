---
title: '方法: Columns プロパティによってテーブルの列を操作する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating table columns
- properties [WPF], Columns [WPF], manipulating table columns
- tables [WPF], manipulating columns
- Columns property [WPF]
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
ms.openlocfilehash: d379d1a98bff614ff9e16cdd340bb69644988743
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051469"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a><span data-ttu-id="23776-102">方法: Columns プロパティによってテーブルの列を操作する</span><span class="sxs-lookup"><span data-stu-id="23776-102">How to: Manipulate a Table's Columns through the Columns Property</span></span>
<span data-ttu-id="23776-103">この例では、によってテーブルの列に対して実行できる一般的な操作の一部を示します、<xref:System.Windows.Documents.Table.Columns%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="23776-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23776-104">例</span><span class="sxs-lookup"><span data-stu-id="23776-104">Example</span></span>  
 <span data-ttu-id="23776-105">次の例は、新しいテーブルを作成しを使用して、<xref:System.Windows.Documents.TableColumnCollection.Add%2A>メソッドに、テーブルの列を追加する<xref:System.Windows.Documents.Table.Columns%2A>コレクション。</span><span class="sxs-lookup"><span data-stu-id="23776-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="23776-106">例</span><span class="sxs-lookup"><span data-stu-id="23776-106">Example</span></span>  
 <span data-ttu-id="23776-107">次の例は、新しい挿入<xref:System.Windows.Documents.TableColumn>します。</span><span class="sxs-lookup"><span data-stu-id="23776-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="23776-108">インデックス位置 0 の場合の表に、新しい最初の列を行うには、新しい列が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="23776-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23776-109"><xref:System.Windows.Documents.TableColumnCollection>コレクションは、標準の 0 から始まるインデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="23776-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="23776-110">例</span><span class="sxs-lookup"><span data-stu-id="23776-110">Example</span></span>  
 <span data-ttu-id="23776-111">次の例では、任意のプロパティ内の列を<xref:System.Windows.Documents.TableColumnCollection>インデックスを使用して、特定の列を参照するコレクション。</span><span class="sxs-lookup"><span data-stu-id="23776-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="23776-112">例</span><span class="sxs-lookup"><span data-stu-id="23776-112">Example</span></span>  
 <span data-ttu-id="23776-113">次の例では、テーブルによって現在ホストされている列の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="23776-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="23776-114">例</span><span class="sxs-lookup"><span data-stu-id="23776-114">Example</span></span>  
 <span data-ttu-id="23776-115">次の例では、参照によって、特定の列を削除します。</span><span class="sxs-lookup"><span data-stu-id="23776-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="23776-116">例</span><span class="sxs-lookup"><span data-stu-id="23776-116">Example</span></span>  
 <span data-ttu-id="23776-117">次の例では、インデックスを使用して、特定の列を削除します。</span><span class="sxs-lookup"><span data-stu-id="23776-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="23776-118">例</span><span class="sxs-lookup"><span data-stu-id="23776-118">Example</span></span>  
 <span data-ttu-id="23776-119">次の例では、テーブルの列のコレクションからすべての列を削除します。</span><span class="sxs-lookup"><span data-stu-id="23776-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="23776-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="23776-120">See also</span></span>

- [<span data-ttu-id="23776-121">テーブルの概要</span><span class="sxs-lookup"><span data-stu-id="23776-121">Table Overview</span></span>](table-overview.md)
- [<span data-ttu-id="23776-122">XAML を使用してテーブルを定義する</span><span class="sxs-lookup"><span data-stu-id="23776-122">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="23776-123">プログラムによってテーブルをビルドする</span><span class="sxs-lookup"><span data-stu-id="23776-123">Build a Table Programmatically</span></span>](how-to-build-a-table-programmatically.md)
- [<span data-ttu-id="23776-124">RowGroups プロパティを介してテーブルの行グループを操作する</span><span class="sxs-lookup"><span data-stu-id="23776-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="23776-125">Blocks プロパティを介して FlowDocument を操作する</span><span class="sxs-lookup"><span data-stu-id="23776-125">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="23776-126">RowGroups プロパティを介してテーブルの行グループを操作する</span><span class="sxs-lookup"><span data-stu-id="23776-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
