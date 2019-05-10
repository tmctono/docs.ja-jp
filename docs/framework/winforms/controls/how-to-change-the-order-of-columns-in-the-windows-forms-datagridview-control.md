---
title: '方法: Windows フォーム DataGridView コントロールの列の順序を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], changing order
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], changing column order
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
ms.openlocfilehash: 4b3859579814f4a10f38fd47df6fe933e2722cb2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64643348"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1faa9-102">方法: Windows フォーム DataGridView コントロールの列の順序を変更する</span><span class="sxs-lookup"><span data-stu-id="1faa9-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1faa9-103"><xref:System.Windows.Forms.DataGridView> を使用してデータをデータ ソースから表示する場合、データ ソースのスキーマの列が、表示したい順序で表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="1faa9-103">When you use a <xref:System.Windows.Forms.DataGridView> to display data from a data source, the columns in the data source's schema sometimes do not appear in the order you would like to display them.</span></span> <span data-ttu-id="1faa9-104"><xref:System.Windows.Forms.DataGridViewColumn> クラスの <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> プロパティを使用して、列の表示順序を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1faa9-104">You can change the displayed order of the columns by using the <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> property of the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <span data-ttu-id="1faa9-105">次のコード例は、Northwind サンプル データベース内の Customers テーブルにバインドするときに自動的に生成される列のいくつかを再配置します。</span><span class="sxs-lookup"><span data-stu-id="1faa9-105">The following code example repositions some of the columns automatically generated when binding to the Customers table in the Northwind sample database.</span></span> <span data-ttu-id="1faa9-106">バインドする方法について、<xref:System.Windows.Forms.DataGridView>データベース テーブルにコントロールを参照してください[方法。バインド データを Windows フォーム DataGridView コントロール](how-to-bind-data-to-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="1faa9-106">For more information about how to bind the <xref:System.Windows.Forms.DataGridView> control to a database table, see [How to: Bind Data to the Windows Forms DataGridView Control](how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="1faa9-107">Visual Studio では、このタスクに対するサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1faa9-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="1faa9-108">参照してください[方法。デザイナーを使用して Windows フォーム DataGridView コントロール内の列の順序を変更する](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="1faa9-108">Also see [How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer](change-the-order-of-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1faa9-109">例</span><span class="sxs-lookup"><span data-stu-id="1faa9-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1faa9-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="1faa9-110">Compiling the Code</span></span>  
 <span data-ttu-id="1faa9-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1faa9-111">This example requires:</span></span>  
  
- <span data-ttu-id="1faa9-112">Northwind サンプル データベース内の <xref:System.Windows.Forms.DataGridView> テーブルなど、示されている列の名前を持つテーブルにバインドされた、`customersDataGridView` という名前の `Customers` コントロール。</span><span class="sxs-lookup"><span data-stu-id="1faa9-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView` that is bound to a table with the indicated column names, such as the `Customers` table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="1faa9-113"><xref:System?displayProperty=nameWithType>、<xref:System.Windows.Forms?displayProperty=nameWithType>、<xref:System.Data?displayProperty=nameWithType>、および <xref:System.Xml?displayProperty=nameWithType> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="1faa9-113">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1faa9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1faa9-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1faa9-115">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="1faa9-115">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1faa9-116">方法: Windows フォームの DataGridView コントロールにデータをバインドします。</span><span class="sxs-lookup"><span data-stu-id="1faa9-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
