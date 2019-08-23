---
title: '方法: クエリで情報を取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 2987e43c83bf84e32cd05a870b24da40dd37d8b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943555"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="0c6bc-102">方法: クエリで情報を取得する</span><span class="sxs-lookup"><span data-stu-id="0c6bc-102">How to: Query for Information</span></span>
<span data-ttu-id="0c6bc-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] クエリでは、[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] クエリと同じ構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="0c6bc-104">唯一の違いは、クエリで[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]参照されるオブジェクトがデータベース内の要素にマップされることです。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="0c6bc-105">詳細については、「[LINQ クエリの概要 (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0c6bc-106">は、作成したクエリを同等の SQL クエリに変換し、それをサーバーに送って処理します。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="0c6bc-107">[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] クエリの機能の中には、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションで特に注意を要するものがあります。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-107">Some features of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="0c6bc-108">詳細については、「[クエリの概念](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-108">For more information, see [Query Concepts](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c6bc-109">例</span><span class="sxs-lookup"><span data-stu-id="0c6bc-109">Example</span></span>  
 <span data-ttu-id="0c6bc-110">次のクエリは、ロンドンからの顧客のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="0c6bc-111">この例の `Customers` は、Northwind サンプル データベース内のテーブルです。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0c6bc-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c6bc-112">See also</span></span>

- [<span data-ttu-id="0c6bc-113">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="0c6bc-113">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [<span data-ttu-id="0c6bc-114">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="0c6bc-114">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="0c6bc-115">データベースに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="0c6bc-115">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
