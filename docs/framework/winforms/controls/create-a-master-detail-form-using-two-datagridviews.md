---
title: 2つの DataGridView コントロールを使用してマスター/詳細フォームを作成する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
ms.openlocfilehash: d317f4e592790c9b48b539b1601814569e14529f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737324"
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="f8ef9-102">方法 : Windows フォームの 2 つの DataGridView コントロールを使用してマスター/詳細形式のフォームを作成する</span><span class="sxs-lookup"><span data-stu-id="f8ef9-102">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="f8ef9-103">次のコード例では、2 つの <xref:System.Windows.Forms.DataGridView> コンポーネントにバインドされた 2 つの <xref:System.Windows.Forms.BindingSource> コントロールを使用してマスター/詳細フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="f8ef9-103">The following code example creates a master/detail form using two <xref:System.Windows.Forms.DataGridView> controls bound to two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="f8ef9-104">データ ソースが、Northwind SQL Server のサンプル データベース、および <xref:System.Data.DataSet> 列により 2 つに関連する `Customers` からの `Orders` テーブルと <xref:System.Data.DataRelation> テーブルを含む `CustomerID` です。</span><span class="sxs-lookup"><span data-stu-id="f8ef9-104">The data source is a <xref:System.Data.DataSet> that contains the `Customers` and `Orders` tables from the Northwind SQL Server sample database along with a <xref:System.Data.DataRelation> that relates the two through the `CustomerID` column.</span></span>  
  
 <span data-ttu-id="f8ef9-105">1 つの <xref:System.Windows.Forms.BindingSource> はデータセットの親 `Customers` テーブルにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="f8ef9-105">One <xref:System.Windows.Forms.BindingSource> is bound to the parent `Customers` table in the data set.</span></span> <span data-ttu-id="f8ef9-106">このデータは、マスタ <xref:System.Windows.Forms.DataGridView> コントロールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8ef9-106">This data is displayed in the master <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f8ef9-107">もう一方の <xref:System.Windows.Forms.BindingSource> は、最初のデータ コネクタにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="f8ef9-107">The other <xref:System.Windows.Forms.BindingSource> is bound to the first data connector.</span></span> <span data-ttu-id="f8ef9-108">2 つ目の <xref:System.Windows.Forms.BindingSource.DataMember%2A> の <xref:System.Windows.Forms.BindingSource> プロパティは、<xref:System.Data.DataRelation> の名前に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f8ef9-108">The <xref:System.Windows.Forms.BindingSource.DataMember%2A> property of the second <xref:System.Windows.Forms.BindingSource> is set to the <xref:System.Data.DataRelation> name.</span></span> <span data-ttu-id="f8ef9-109">これにより、関連付けられている詳細の <xref:System.Windows.Forms.DataGridView> コントロールが、マスター `Orders` コントロールの現在の行に対応する子の <xref:System.Windows.Forms.DataGridView> テーブルの行を表示します。</span><span class="sxs-lookup"><span data-stu-id="f8ef9-109">This causes the associated detail <xref:System.Windows.Forms.DataGridView> control to display the rows of the child `Orders` table that correspond to the current row in the master <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="f8ef9-110">このコード例の詳細については、「[チュートリアル: 2 つの Windows フォーム DataGridView コントロールを使用してマスター/詳細フォームを作成](creating-a-master-detail-form-using-two-datagridviews.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8ef9-110">For a complete explanation of this code example, see [Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls](creating-a-master-detail-form-using-two-datagridviews.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8ef9-111">例</span><span class="sxs-lookup"><span data-stu-id="f8ef9-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8ef9-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f8ef9-112">Compiling the Code</span></span>  
 <span data-ttu-id="f8ef9-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f8ef9-113">This example requires:</span></span>  
  
 <span data-ttu-id="f8ef9-114">System、System.Data、System.Windows.Forms、および System.XML の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="f8ef9-114">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f8ef9-115">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="f8ef9-115">.NET Framework Security</span></span>  
 <span data-ttu-id="f8ef9-116">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="f8ef9-116">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="f8ef9-117">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="f8ef9-117">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="f8ef9-118">詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8ef9-118">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ef9-119">参照</span><span class="sxs-lookup"><span data-stu-id="f8ef9-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="f8ef9-120">チュートリアル: Windows フォームの 2 つの DataGridView コントロールを使用したマスター/詳細形式のフォームの作成</span><span class="sxs-lookup"><span data-stu-id="f8ef9-120">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)
- [<span data-ttu-id="f8ef9-121">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="f8ef9-121">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f8ef9-122">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="f8ef9-122">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
