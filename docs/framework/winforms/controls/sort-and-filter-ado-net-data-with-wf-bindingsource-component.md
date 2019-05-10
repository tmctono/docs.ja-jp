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
ms.openlocfilehash: d05cbdf63483c160603ee44f6b507edc2d13b170
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651941"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="3ab45-102">方法: Windows フォーム BindingSource コンポーネントで ADO.NET データを並べ替える/フィルター処理する</span><span class="sxs-lookup"><span data-stu-id="3ab45-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="3ab45-103">並べ替えとフィルタ リングの機能を公開する<xref:System.Windows.Forms.BindingSource>を介して制御、<xref:System.Windows.Forms.BindingSource.Sort%2A>と<xref:System.Windows.Forms.BindingSource.Filter%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3ab45-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="3ab45-104">基になるデータ ソースの場合は、単純な並べ替えを適用することができます、 <xref:System.ComponentModel.IBindingList>、フィルター処理を適用することができ、高度な並べ替え、データ ソースの場合と、<xref:System.ComponentModel.IBindingListView>します。</span><span class="sxs-lookup"><span data-stu-id="3ab45-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="3ab45-105"><xref:System.Windows.Forms.BindingSource.Sort%2A>プロパティには標準[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]構文: データ ソース内のデータの列の名前を表す文字列が続く`ASC`または`DESC`一覧を昇順または降順で並べ替える必要があるかどうかを示す。</span><span class="sxs-lookup"><span data-stu-id="3ab45-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="3ab45-106">高度な並べ替え、または各列をコンマ区切り記号で区切って複数列の並べ替えを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="3ab45-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="3ab45-107"><xref:System.Windows.Forms.BindingSource.Filter%2A>プロパティは文字列式を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3ab45-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ab45-108">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="3ab45-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="3ab45-109">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="3ab45-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="3ab45-110">詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ab45-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="3ab45-111">BindingSource でデータをフィルター処理</span><span class="sxs-lookup"><span data-stu-id="3ab45-111">To filter data with the BindingSource</span></span>  
  
- <span data-ttu-id="3ab45-112">設定、<xref:System.Windows.Forms.BindingSource.Filter%2A>プロパティを使用する式。</span><span class="sxs-lookup"><span data-stu-id="3ab45-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="3ab45-113">次のコード例では、式は、列名の後に、列の値が。</span><span class="sxs-lookup"><span data-stu-id="3ab45-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="3ab45-114">BindingSource でデータを並べ替える</span><span class="sxs-lookup"><span data-stu-id="3ab45-114">To sort data with the BindingSource</span></span>  
  
1. <span data-ttu-id="3ab45-115">設定、<xref:System.Windows.Forms.BindingSource.Sort%2A>プロパティ後に必要な列名を`ASC`または`DESC`を昇順または降順を示します。</span><span class="sxs-lookup"><span data-stu-id="3ab45-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2. <span data-ttu-id="3ab45-116">複数の列をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="3ab45-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="3ab45-117">例</span><span class="sxs-lookup"><span data-stu-id="3ab45-117">Example</span></span>  
 <span data-ttu-id="3ab45-118">次のコード例に、Northwind サンプル データベースの Customers テーブルからデータを読み込みます、<xref:System.Windows.Forms.DataGridView>を制御する、フィルター処理し、表示されるデータを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="3ab45-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3ab45-119">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="3ab45-119">Compiling the Code</span></span>  
 <span data-ttu-id="3ab45-120">この例を実行するには、フォームが含まれていますにコードを貼り付けます、<xref:System.Windows.Forms.BindingSource>という名前`BindingSource1`と<xref:System.Windows.Forms.DataGridView>という`dataGridView1`します。</span><span class="sxs-lookup"><span data-stu-id="3ab45-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="3ab45-121">処理、<xref:System.Windows.Forms.Form.Load>フォームに対する呼び出しイベント`InitializeSortedFilteredBindingSource`load イベント ハンドラー メソッドにします。</span><span class="sxs-lookup"><span data-stu-id="3ab45-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ab45-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ab45-122">See also</span></span>

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- <span data-ttu-id="3ab45-123">[方法: サンプル データベースをインストールします。](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="3ab45-123">[How to: Install Sample Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span></span>
- [<span data-ttu-id="3ab45-124">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3ab45-124">BindingSource Component</span></span>](bindingsource-component.md)
