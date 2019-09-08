---
title: '方法: 行をデータベースに挿入する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: 8186b90a666a7b75ce626cccb7cc28af38de7c5b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781867"
---
# <a name="how-to-insert-rows-into-the-database"></a><span data-ttu-id="a5c5c-102">方法: 行をデータベースに挿入する</span><span class="sxs-lookup"><span data-stu-id="a5c5c-102">How to: Insert Rows Into the Database</span></span>

<span data-ttu-id="a5c5c-103">データベースに行を挿入するには、関連付けら[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]れている<xref:System.Data.Linq.Table%601>コレクションにオブジェクトを追加し、変更をデータベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="a5c5c-103">You insert rows into a database by adding objects to the associated [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a5c5c-104">では、変更内容が適切`INSERT`な SQL コマンドに変換されます。</span><span class="sxs-lookup"><span data-stu-id="a5c5c-104">translates your changes into the appropriate SQL `INSERT` commands.</span></span>

> [!NOTE]
> <span data-ttu-id="a5c5c-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の `Insert`、`Update`、および `Delete` の既定のデータベース操作メソッドはオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="a5c5c-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="a5c5c-106">詳細については、「[挿入、更新、および削除の操作をカスタマイズ](customizing-insert-update-and-delete-operations.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5c5c-106">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="a5c5c-107">Visual Studio を使用する開発者は、オブジェクトリレーショナルデザイナーを使用して、同じ目的でストアドプロシージャを開発できます。</span><span class="sxs-lookup"><span data-stu-id="a5c5c-107">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

<span data-ttu-id="a5c5c-108">以下の手順では、有効な <xref:System.Data.Linq.DataContext> で Northwind データベースに接続されるものと想定しています。</span><span class="sxs-lookup"><span data-stu-id="a5c5c-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="a5c5c-109">詳細については、「[方法 :データベース](how-to-connect-to-a-database.md)に接続します。</span><span class="sxs-lookup"><span data-stu-id="a5c5c-109">For more information, see [How to: Connect to a Database](how-to-connect-to-a-database.md).</span></span>

### <a name="to-insert-a-row-into-the-database"></a><span data-ttu-id="a5c5c-110">行をデータベースに挿入するには</span><span class="sxs-lookup"><span data-stu-id="a5c5c-110">To insert a row into the database</span></span>

1. <span data-ttu-id="a5c5c-111">送信する列データを含む新しいオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5c5c-111">Create a new object that includes the column data to be submitted.</span></span>

2. <span data-ttu-id="a5c5c-112">データベース内のターゲットテーブルに[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]関連付けられている`Table`コレクションに、新しいオブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="a5c5c-112">Add the new object to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` collection associated with the target table in the database.</span></span>

3. <span data-ttu-id="a5c5c-113">データベースに変更内容を送信します。</span><span class="sxs-lookup"><span data-stu-id="a5c5c-113">Submit the change to the database.</span></span>

## <a name="example"></a><span data-ttu-id="a5c5c-114">例</span><span class="sxs-lookup"><span data-stu-id="a5c5c-114">Example</span></span>

<span data-ttu-id="a5c5c-115">次のサンプル コードでは、`Order` 型の新しいオブジェクトを作成し、適切な値をこのオブジェクトに設定します。</span><span class="sxs-lookup"><span data-stu-id="a5c5c-115">The following code example creates a new object of type `Order` and populates it with appropriate values.</span></span> <span data-ttu-id="a5c5c-116">その後で、新しいオブジェクトを `Order` コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="a5c5c-116">It then adds the new object to the `Order` collection.</span></span> <span data-ttu-id="a5c5c-117">最後にこの変更内容を `Orders` テーブルの新しい行としてデータベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="a5c5c-117">Finally, it submits the change to the database as a new row in the `Orders` table.</span></span>

[!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
[!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="a5c5c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5c5c-118">See also</span></span>

- [<span data-ttu-id="a5c5c-119">方法: 変更の競合を管理する</span><span class="sxs-lookup"><span data-stu-id="a5c5c-119">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="a5c5c-120">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="a5c5c-120">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="a5c5c-121">方法: 更新、挿入、および削除を実行するストアド プロシージャを割り当てる (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="a5c5c-121">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="a5c5c-122">データの変更と変更の送信</span><span class="sxs-lookup"><span data-stu-id="a5c5c-122">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
