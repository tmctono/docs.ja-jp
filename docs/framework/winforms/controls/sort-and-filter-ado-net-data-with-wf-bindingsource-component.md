---
title: BindingSource コンポーネントを使用した ADO.NET データの並べ替えとフィルター処理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: cf1da3bb94b26449eb72b0e4930b262236487acc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742969"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="d0b19-102">方法 : Windows フォーム BindingSource コンポーネントで ADO.NET データを並べ替える/フィルター処理する</span><span class="sxs-lookup"><span data-stu-id="d0b19-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="d0b19-103"><xref:System.Windows.Forms.BindingSource.Sort%2A> と <xref:System.Windows.Forms.BindingSource.Filter%2A> のプロパティを使用して、<xref:System.Windows.Forms.BindingSource> コントロールの並べ替えとフィルター処理の機能を公開できます。</span><span class="sxs-lookup"><span data-stu-id="d0b19-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="d0b19-104">基になるデータソースが <xref:System.ComponentModel.IBindingList>であれば、単純な並べ替えを適用できます。また、データソースが <xref:System.ComponentModel.IBindingListView>である場合は、フィルター処理や高度な並べ替えを適用できます。</span><span class="sxs-lookup"><span data-stu-id="d0b19-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="d0b19-105"><xref:System.Windows.Forms.BindingSource.Sort%2A> プロパティには、標準の ADO.NET 構文が必要です。これには、データソース内のデータ列の名前を表す文字列と、リストを昇順と降順のどちらで並べ替えるかを示す `ASC` または `DESC` を指定します。</span><span class="sxs-lookup"><span data-stu-id="d0b19-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard ADO.NET syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="d0b19-106">各列をコンマ区切り記号で区切ることによって、高度な並べ替えまたは複数列の並べ替えを設定できます。</span><span class="sxs-lookup"><span data-stu-id="d0b19-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="d0b19-107"><xref:System.Windows.Forms.BindingSource.Filter%2A> プロパティは、文字列式を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d0b19-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0b19-108">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="d0b19-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="d0b19-109">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="d0b19-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="d0b19-110">詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0b19-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="d0b19-111">BindingSource を使用してデータをフィルター処理するには</span><span class="sxs-lookup"><span data-stu-id="d0b19-111">To filter data with the BindingSource</span></span>  
  
- <span data-ttu-id="d0b19-112"><xref:System.Windows.Forms.BindingSource.Filter%2A> プロパティを目的の式に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0b19-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="d0b19-113">次のコード例では、式は列名の後に列に必要な値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="d0b19-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="d0b19-114">BindingSource を使用してデータを並べ替えるには</span><span class="sxs-lookup"><span data-stu-id="d0b19-114">To sort data with the BindingSource</span></span>  
  
1. <span data-ttu-id="d0b19-115"><xref:System.Windows.Forms.BindingSource.Sort%2A> プロパティに、`ASC` または `DESC` 昇順または降順を示す列名を設定します。</span><span class="sxs-lookup"><span data-stu-id="d0b19-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2. <span data-ttu-id="d0b19-116">複数の列をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="d0b19-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="d0b19-117">例</span><span class="sxs-lookup"><span data-stu-id="d0b19-117">Example</span></span>  
 <span data-ttu-id="d0b19-118">次のコード例では、Northwind サンプルデータベースの Customers テーブルから <xref:System.Windows.Forms.DataGridView> コントロールにデータを読み込み、表示されるデータをフィルター処理して並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="d0b19-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d0b19-119">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d0b19-119">Compiling the Code</span></span>  
 <span data-ttu-id="d0b19-120">この例を実行するには、`BindingSource1` という名前の <xref:System.Windows.Forms.BindingSource> と `dataGridView1`という名前の <xref:System.Windows.Forms.DataGridView> を含むフォームにコードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d0b19-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="d0b19-121">フォームの <xref:System.Windows.Forms.Form.Load> イベントを処理し、load イベントハンドラーメソッドで `InitializeSortedFilteredBindingSource` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d0b19-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0b19-122">参照</span><span class="sxs-lookup"><span data-stu-id="d0b19-122">See also</span></span>

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- <span data-ttu-id="d0b19-123">[方法 : サンプル データベースをインストールする](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d0b19-123">[How to: Install Sample Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span></span>
- [<span data-ttu-id="d0b19-124">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d0b19-124">BindingSource Component</span></span>](bindingsource-component.md)
