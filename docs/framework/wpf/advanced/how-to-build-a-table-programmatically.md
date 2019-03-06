---
title: '方法: プログラムによってテーブルをビルドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
ms.openlocfilehash: 3848032bf527f64ce591eb2cda98028c835d79f7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371933"
---
# <a name="how-to-build-a-table-programmatically"></a><span data-ttu-id="b3df6-102">方法: プログラムによってテーブルをビルドする</span><span class="sxs-lookup"><span data-stu-id="b3df6-102">How to: Build a Table Programmatically</span></span>
<span data-ttu-id="b3df6-103">次の例では、プログラムで作成する方法、<xref:System.Windows.Documents.Table>し、コンテンツを設定します。</span><span class="sxs-lookup"><span data-stu-id="b3df6-103">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="b3df6-104">テーブルの内容は 5 つの行に配分 (によって表される<xref:System.Windows.Documents.TableRow>に含まれるオブジェクトを<xref:System.Windows.Documents.Table.RowGroups%2A>オブジェクト) と 6 つの列 (によって表される<xref:System.Windows.Documents.TableColumn>オブジェクト)。</span><span class="sxs-lookup"><span data-stu-id="b3df6-104">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="b3df6-105">たとえば、タイトル行はテーブル全体のタイトルの設定に使用され、ヘッダー行はテーブル内のデータ列の説明、フッター行は要約情報の格納に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b3df6-105">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="b3df6-106">"タイトル"、"ヘッダー"、"フッター" 行の概念はテーブルに固有のものではなく、単純に異なる特性を持つ行です。</span><span class="sxs-lookup"><span data-stu-id="b3df6-106">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="b3df6-107">テーブルのセルは、テキスト、画像、またはその他のほとんどすべての構成は、実際のコンテンツを含めることが[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]要素。</span><span class="sxs-lookup"><span data-stu-id="b3df6-107">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3df6-108">例</span><span class="sxs-lookup"><span data-stu-id="b3df6-108">Example</span></span>  
 <span data-ttu-id="b3df6-109">最初に、<xref:System.Windows.Documents.FlowDocument>が作成されるホストに、 <xref:System.Windows.Documents.Table>、され、新しい<xref:System.Windows.Documents.Table>が作成され、コンテンツの追加、<xref:System.Windows.Documents.FlowDocument>します。</span><span class="sxs-lookup"><span data-stu-id="b3df6-109">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a><span data-ttu-id="b3df6-110">例</span><span class="sxs-lookup"><span data-stu-id="b3df6-110">Example</span></span>  
 <span data-ttu-id="b3df6-111">次に、6<xref:System.Windows.Documents.TableColumn>オブジェクトが作成され、テーブルの追加<xref:System.Windows.Documents.Table.Columns%2A>コレクション、書式を適用します。</span><span class="sxs-lookup"><span data-stu-id="b3df6-111">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3df6-112">なお、テーブルの<xref:System.Windows.Documents.Table.Columns%2A>コレクションは、標準の 0 から始まるインデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3df6-112">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a><span data-ttu-id="b3df6-113">例</span><span class="sxs-lookup"><span data-stu-id="b3df6-113">Example</span></span>  
 <span data-ttu-id="b3df6-114">次に、タイトル行が作成され、テーブルに追加されます。いくつかの書式設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="b3df6-114">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="b3df6-115">タイトル行には、テーブルの 6 つの列にまたがる 1 つのセルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="b3df6-115">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a><span data-ttu-id="b3df6-116">例</span><span class="sxs-lookup"><span data-stu-id="b3df6-116">Example</span></span>  
 <span data-ttu-id="b3df6-117">次に、ヘッダー行を作成してテーブルに追加し、ヘッダー行のセルを作成してデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="b3df6-117">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a><span data-ttu-id="b3df6-118">例</span><span class="sxs-lookup"><span data-stu-id="b3df6-118">Example</span></span>  
 <span data-ttu-id="b3df6-119">次に、データの行が作成され、テーブルに追加されます。この行のセルが作成され、内容が入力されます。</span><span class="sxs-lookup"><span data-stu-id="b3df6-119">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="b3df6-120">この行の作成はヘッダー行の作成に似ていますが、適用する書式が少し異なります。</span><span class="sxs-lookup"><span data-stu-id="b3df6-120">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a><span data-ttu-id="b3df6-121">例</span><span class="sxs-lookup"><span data-stu-id="b3df6-121">Example</span></span>  
 <span data-ttu-id="b3df6-122">最後に、フッター行が作成され、追加され、書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="b3df6-122">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="b3df6-123">タイトル行と同様に、フッター行にはテーブルの 6 つの列にまたがる 1 つのセルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="b3df6-123">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="b3df6-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3df6-124">See also</span></span>
- [<span data-ttu-id="b3df6-125">テーブルの概要</span><span class="sxs-lookup"><span data-stu-id="b3df6-125">Table Overview</span></span>](table-overview.md)
