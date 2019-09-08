---
title: 挿入、更新、および削除の各操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
ms.openlocfilehash: fac89f905b85493bc0ec36a85635f369bb354266
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793057"
---
# <a name="insert-update-and-delete-operations"></a><span data-ttu-id="923d2-102">挿入、更新、および削除の各操作</span><span class="sxs-lookup"><span data-stu-id="923d2-102">Insert, Update, and Delete Operations</span></span>

<span data-ttu-id="923d2-103">オブジェクト モデルに対してオブジェクトの追加、変更、および削除を行うには、`Insert` で `Update`、`Delete`、および [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の各操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="923d2-103">You perform `Insert`, `Update`, and `Delete` operations in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] by adding, changing, and removing objects in your object model.</span></span> <span data-ttu-id="923d2-104">既定では、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] によって SQL に対する操作が変換され、変更内容がデータベースに送信されます。</span><span class="sxs-lookup"><span data-stu-id="923d2-104">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates your actions to SQL and submits the changes to the database.</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="923d2-105">では、オブジェクトに対して行った変更を操作して永続化する際に、最大限の柔軟性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="923d2-105">offers maximum flexibility in manipulating and persisting changes that you made to your objects.</span></span> <span data-ttu-id="923d2-106">クエリによって取得するか新規に作成することによりエンティティ オブジェクトが使用可能になった後で、通常のオブジェクトと同じようにそれらのオブジェクトをアプリケーションで変更できます。</span><span class="sxs-lookup"><span data-stu-id="923d2-106">As soon as entity objects are available (either by retrieving them through a query or by constructing them anew), you can change them as typical objects in your application.</span></span> <span data-ttu-id="923d2-107">つまり、値を変更して、コレクションに追加したり、コレクションから削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="923d2-107">That is, you can change their values, you can add them to your collections, and you can remove them from your collections.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="923d2-108">では変更履歴が保持されるため、<xref:System.Data.Linq.DataContext.SubmitChanges%2A> を呼び出すと、変更内容をデータベースに送信できます。</span><span class="sxs-lookup"><span data-stu-id="923d2-108">tracks your changes and is ready to transmit them back to the database when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span>

> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="923d2-109">は連鎖削除操作をサポートせず、認識もしません。</span><span class="sxs-lookup"><span data-stu-id="923d2-109">does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="923d2-110">制約があるテーブル内の行を削除する場合は、データベースの外部キー制約で`ON DELETE CASCADE`ルールを設定するか、独自のコードを使用して親オブジェクトの削除を妨げる子オブジェクトを最初に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="923d2-110">If you want to delete a row in a table that has constraints against it, you must either set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database, or use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span> <span data-ttu-id="923d2-111">それ以外の場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="923d2-111">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="923d2-112">詳細については、「[方法 :データベース](how-to-delete-rows-from-the-database.md)から行を削除します。</span><span class="sxs-lookup"><span data-stu-id="923d2-112">For more information, see [How to: Delete Rows From the Database](how-to-delete-rows-from-the-database.md).</span></span>

<span data-ttu-id="923d2-113">次の例では、Northwind サンプル データベースの `Customer` クラスと `Order` クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="923d2-113">The following excerpts use the `Customer` and `Order` classes from the Northwind sample database.</span></span> <span data-ttu-id="923d2-114">簡潔にするため、ここではクラス定義を省いています。</span><span class="sxs-lookup"><span data-stu-id="923d2-114">Class definitions are not shown for brevity.</span></span>

[!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
[!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]

<span data-ttu-id="923d2-115"><xref:System.Data.Linq.DataContext.SubmitChanges%2A> を呼び出すと、変更内容をデータベースに送信する SQL コマンドが [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] によって自動的に生成され、実行されます。</span><span class="sxs-lookup"><span data-stu-id="923d2-115">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] automatically generates and executes the SQL commands that it must have to transmit your changes back to the database.</span></span>

> [!NOTE]
> <span data-ttu-id="923d2-116">独自に作成したロジック (通常はストアド プロシージャ) を使用して、この動作をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="923d2-116">You can override this behavior by using your own custom logic, typically by way of a stored procedure.</span></span> <span data-ttu-id="923d2-117">詳細については、「[既定の動作をオーバーライドするときの開発者の責任](responsibilities-of-the-developer-in-overriding-default-behavior.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="923d2-117">For more information, see [Responsibilities of the Developer In Overriding Default Behavior](responsibilities-of-the-developer-in-overriding-default-behavior.md).</span></span>
>
> <span data-ttu-id="923d2-118">Visual Studio を使用する開発者は、この目的のためにオブジェクトリレーショナルデザイナーを使用してストアドプロシージャを開発できます。</span><span class="sxs-lookup"><span data-stu-id="923d2-118">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for this purpose.</span></span>

## <a name="see-also"></a><span data-ttu-id="923d2-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="923d2-119">See also</span></span>

- [<span data-ttu-id="923d2-120">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="923d2-120">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="923d2-121">挿入、更新、および削除の各操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="923d2-121">Customizing Insert, Update, and Delete Operations</span></span>](customizing-insert-update-and-delete-operations.md)
