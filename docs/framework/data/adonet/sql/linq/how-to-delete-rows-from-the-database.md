---
title: '方法: 行をデータベースから削除する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
ms.openlocfilehash: 89b552d919898f78c0733c2af4507728f59a3c8d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743335"
---
# <a name="how-to-delete-rows-from-the-database"></a><span data-ttu-id="76eca-102">方法: 行をデータベースから削除する</span><span class="sxs-lookup"><span data-stu-id="76eca-102">How to: Delete Rows From the Database</span></span>
<span data-ttu-id="76eca-103">データベース内の行を削除するには、対応するから削除[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]テーブルに関連付けられたコレクションからオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="76eca-103">You can delete rows in a database by removing the corresponding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] objects from their table-related collection.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="76eca-104">適切な SQL への変更を変換`DELETE`コマンド。</span><span class="sxs-lookup"><span data-stu-id="76eca-104">translates your changes to the appropriate SQL `DELETE` commands.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="76eca-105">は連鎖削除操作をサポートせず、認識もしません。</span><span class="sxs-lookup"><span data-stu-id="76eca-105">does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="76eca-106">制約を持つテーブルの行を削除するには、次のいずれかのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76eca-106">If you want to delete a row in a table that has constraints against it, you must complete either of the following tasks:</span></span>  
  
- <span data-ttu-id="76eca-107">データベース内の外部キー制約で `ON DELETE CASCADE` 規則を設定する。</span><span class="sxs-lookup"><span data-stu-id="76eca-107">Set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database.</span></span>  
  
- <span data-ttu-id="76eca-108">独自のコードを使用して、親オブジェクトの削除を妨げる子オブジェクトを最初に削除する。</span><span class="sxs-lookup"><span data-stu-id="76eca-108">Use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span>  
  
 <span data-ttu-id="76eca-109">それ以外の場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="76eca-109">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="76eca-110">後で説明する 2 番目のコード例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76eca-110">See the second code example later in this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76eca-111">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の `Insert`、`Update`、および `Delete` の既定のデータベース操作メソッドはオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="76eca-111">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="76eca-112">詳細については、次を参照してください。[のカスタマイズを挿入、更新、および削除を行う](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="76eca-112">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="76eca-113">Visual Studio を使用している開発者は、オブジェクト リレーショナル デザイナーを使用して、同じ目的のストアド プロシージャを開発します。</span><span class="sxs-lookup"><span data-stu-id="76eca-113">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="76eca-114">以下の手順では、有効な <xref:System.Data.Linq.DataContext> で Northwind データベースに接続されるものと想定しています。</span><span class="sxs-lookup"><span data-stu-id="76eca-114">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="76eca-115">詳細については、「[方法 :データベースに接続する](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="76eca-115">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-delete-a-row-in-the-database"></a><span data-ttu-id="76eca-116">データベースから行を削除するには</span><span class="sxs-lookup"><span data-stu-id="76eca-116">To delete a row in the database</span></span>  
  
1. <span data-ttu-id="76eca-117">データベースで削除する行をクエリします。</span><span class="sxs-lookup"><span data-stu-id="76eca-117">Query the database for the row to be deleted.</span></span>  
  
2. <span data-ttu-id="76eca-118"><xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="76eca-118">Call the <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> method.</span></span>  
  
3. <span data-ttu-id="76eca-119">データベースに変更内容を送信します。</span><span class="sxs-lookup"><span data-stu-id="76eca-119">Submit the change to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76eca-120">例</span><span class="sxs-lookup"><span data-stu-id="76eca-120">Example</span></span>  
 <span data-ttu-id="76eca-121">この最初のコード例では、注文 #11000 に属する注文詳細情報をデータベースに照会し、それらの注文詳細情報を削除するようにマークして、変更をデータベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="76eca-121">This first code example queries the database for order details that belong to Order #11000, marks these order details for deletion, and submits these changes to the database.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="76eca-122">例</span><span class="sxs-lookup"><span data-stu-id="76eca-122">Example</span></span>  
 <span data-ttu-id="76eca-123">この 2 番目のコード例の目的は、注文 (#10250) を削除することです。</span><span class="sxs-lookup"><span data-stu-id="76eca-123">In this second example, the objective is to remove an order (#10250).</span></span> <span data-ttu-id="76eca-124">このコードは、まず、`OrderDetails` テーブルを調べて、削除対象の注文に子が存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="76eca-124">The code first examines the `OrderDetails` table to see whether the order to be removed has children there.</span></span> <span data-ttu-id="76eca-125">注文に子が存在する場合は、最初に子を、次に注文を削除するようにマークします。</span><span class="sxs-lookup"><span data-stu-id="76eca-125">If the order has children, first the children and then the order are marked for removal.</span></span> <span data-ttu-id="76eca-126"><xref:System.Data.Linq.DataContext> によって、データベース制約に従って削除コマンドがデータベースに送信され、正しい順序で実際の削除が行われます。</span><span class="sxs-lookup"><span data-stu-id="76eca-126">The <xref:System.Data.Linq.DataContext> puts the actual deletes in correct order so that delete commands sent to the database abide by the database constraints.</span></span>  
  
 [!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
 [!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="76eca-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="76eca-127">See also</span></span>

- [<span data-ttu-id="76eca-128">方法: 変更の競合を管理します。</span><span class="sxs-lookup"><span data-stu-id="76eca-128">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="76eca-129">方法: 更新、挿入、および削除を実行するストアド プロシージャを割り当てる (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="76eca-129">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="76eca-130">データの変更と変更の送信</span><span class="sxs-lookup"><span data-stu-id="76eca-130">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
