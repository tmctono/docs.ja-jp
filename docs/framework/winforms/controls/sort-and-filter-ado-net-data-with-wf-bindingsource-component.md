---
title: '方法: Windows フォーム BindingSource コンポーネントで ADO.NET データを並べ替える/フィルター処理する'
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
ms.openlocfilehash: ae331ca9e3fd2aed654659e11434454874eff8fa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960422"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="c7563-102">方法: Windows フォーム BindingSource コンポーネントで ADO.NET データを並べ替える/フィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c7563-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="c7563-103">プロパティ<xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.Sort%2A>とプロパティ<xref:System.Windows.Forms.BindingSource.Filter%2A>を使用して、コントロールの並べ替えとフィルター処理の機能を公開できます。</span><span class="sxs-lookup"><span data-stu-id="c7563-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="c7563-104">基になるデータソースが<xref:System.ComponentModel.IBindingList>である場合は、単純な並べ替えを適用でき<xref:System.ComponentModel.IBindingListView>ます。また、データソースがの場合は、フィルター処理や高度な並べ替えを適用できます。</span><span class="sxs-lookup"><span data-stu-id="c7563-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="c7563-105">プロパティ<xref:System.Windows.Forms.BindingSource.Sort%2A>には、標準の ADO.NET 構文が必要です。これに`ASC`は、データソース内のデータ列の名前`DESC`を表す文字列、またはリストを昇順と降順のどちらで並べ替えるかを示す、またはが必要です。</span><span class="sxs-lookup"><span data-stu-id="c7563-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard ADO.NET syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="c7563-106">各列をコンマ区切り記号で区切ることによって、高度な並べ替えまたは複数列の並べ替えを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c7563-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="c7563-107">プロパティ<xref:System.Windows.Forms.BindingSource.Filter%2A>は、文字列式を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c7563-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7563-108">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="c7563-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="c7563-109">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="c7563-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="c7563-110">詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7563-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="c7563-111">BindingSource を使用してデータをフィルター処理するには</span><span class="sxs-lookup"><span data-stu-id="c7563-111">To filter data with the BindingSource</span></span>  
  
- <span data-ttu-id="c7563-112"><xref:System.Windows.Forms.BindingSource.Filter%2A>プロパティを目的の式に設定します。</span><span class="sxs-lookup"><span data-stu-id="c7563-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="c7563-113">次のコード例では、式は列名の後に列に必要な値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="c7563-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="c7563-114">BindingSource を使用してデータを並べ替えるには</span><span class="sxs-lookup"><span data-stu-id="c7563-114">To sort data with the BindingSource</span></span>  
  
1. <span data-ttu-id="c7563-115">プロパティに、または`DESC`を使用して`ASC`昇順または降順を示す列名を設定します。 <xref:System.Windows.Forms.BindingSource.Sort%2A></span><span class="sxs-lookup"><span data-stu-id="c7563-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2. <span data-ttu-id="c7563-116">複数の列をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="c7563-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="c7563-117">例</span><span class="sxs-lookup"><span data-stu-id="c7563-117">Example</span></span>  
 <span data-ttu-id="c7563-118">次のコード例では、Northwind サンプルデータベースの Customers テーブルから<xref:System.Windows.Forms.DataGridView>コントロールにデータを読み込み、表示されるデータをフィルター処理して並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="c7563-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c7563-119">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="c7563-119">Compiling the Code</span></span>  
 <span data-ttu-id="c7563-120">この例を実行するには、と<xref:System.Windows.Forms.BindingSource>いう名前`BindingSource1`のと<xref:System.Windows.Forms.DataGridView>という`dataGridView1`名前のを含むフォームにコードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c7563-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="c7563-121">フォームの`InitializeSortedFilteredBindingSource`イベントを処理し、load イベントハンドラーメソッドでを呼び出します。 <xref:System.Windows.Forms.Form.Load></span><span class="sxs-lookup"><span data-stu-id="c7563-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7563-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7563-122">See also</span></span>

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- <span data-ttu-id="c7563-123">[方法: サンプルデータベースのインストール](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c7563-123">[How to: Install Sample Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span></span>
- [<span data-ttu-id="c7563-124">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c7563-124">BindingSource Component</span></span>](bindingsource-component.md)
