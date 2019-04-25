---
title: '方法: データベースの行を更新する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
ms.openlocfilehash: e40866c5160d6850b39133050d09026f5ffd6cc5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902942"
---
# <a name="how-to-update-rows-in-the-database"></a><span data-ttu-id="99223-102">方法: データベースの行を更新する</span><span class="sxs-lookup"><span data-stu-id="99223-102">How to: Update Rows in the Database</span></span>
<span data-ttu-id="99223-103">関連付けられているオブジェクトのメンバーの値を変更して、データベース内の行を更新することができます、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601>コレクションとし、データベースへの変更を送信します。</span><span class="sxs-lookup"><span data-stu-id="99223-103">You can update rows in a database by modifying member values of the objects associated with the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="99223-104">適切な SQL に変更を変換`UPDATE`コマンド。</span><span class="sxs-lookup"><span data-stu-id="99223-104">translates your changes into the appropriate SQL `UPDATE` commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99223-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の `Insert`、`Update`、および `Delete` の既定のデータベース操作メソッドはオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="99223-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="99223-106">詳細については、次を参照してください。[のカスタマイズを挿入、更新、および削除を行う](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="99223-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="99223-107">Visual Studio を使用して開発者が使用できる、[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]同じ目的のストアド プロシージャを開発します。</span><span class="sxs-lookup"><span data-stu-id="99223-107">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="99223-108">以下の手順では、有効な <xref:System.Data.Linq.DataContext> で Northwind データベースに接続されるものと想定しています。</span><span class="sxs-lookup"><span data-stu-id="99223-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="99223-109">詳細については、「[方法 :データベースに接続する](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="99223-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-update-a-row-in-the-database"></a><span data-ttu-id="99223-110">データベースの行を更新するには</span><span class="sxs-lookup"><span data-stu-id="99223-110">To update a row in the database</span></span>  
  
1. <span data-ttu-id="99223-111">データベースで更新する行をクエリします。</span><span class="sxs-lookup"><span data-stu-id="99223-111">Query the database for the row to be updated.</span></span>  
  
2. <span data-ttu-id="99223-112">結果として得られた [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] オブジェクトのメンバー値に、必要な変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="99223-112">Make desired changes to member values in the resulting [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object.</span></span>  
  
3. <span data-ttu-id="99223-113">データベースに変更内容を送信します。</span><span class="sxs-lookup"><span data-stu-id="99223-113">Submit the changes to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99223-114">例</span><span class="sxs-lookup"><span data-stu-id="99223-114">Example</span></span>  
 <span data-ttu-id="99223-115">次の例では、データベースの注文 #11000 をクエリし、結果として得られた `ShipName` オブジェクトの `ShipVia` と `Order` の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="99223-115">The following example queries the database for order #11000, and then changes the values of `ShipName` and `ShipVia` in the resulting `Order` object.</span></span> <span data-ttu-id="99223-116">次に、これらのメンバー値の変更内容を、`ShipName` 列と `ShipVia` 列に対する変更としてデータベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="99223-116">Finally, the changes to these member values are submitted to the database as changes in the `ShipName` and `ShipVia` columns.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="99223-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="99223-117">See also</span></span>

- [<span data-ttu-id="99223-118">方法: 変更の競合を管理します。</span><span class="sxs-lookup"><span data-stu-id="99223-118">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="99223-119">方法: 更新、挿入、および削除を実行するストアド プロシージャを割り当てる (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="99223-119">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="99223-120">データの変更と変更の送信</span><span class="sxs-lookup"><span data-stu-id="99223-120">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
