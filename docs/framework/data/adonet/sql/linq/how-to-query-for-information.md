---
title: '方法: 情報のクエリ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 9476144d84454aedc331214a55c77547697c378f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608415"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="a240a-102">方法: 情報のクエリ</span><span class="sxs-lookup"><span data-stu-id="a240a-102">How to: Query for Information</span></span>
<span data-ttu-id="a240a-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] クエリでは、[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] クエリと同じ構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="a240a-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="a240a-104">唯一の違いは、オブジェクトで参照されている[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]クエリ データベース内の要素にマップされます。</span><span class="sxs-lookup"><span data-stu-id="a240a-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="a240a-105">詳細については、「[LINQ クエリの概要 (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a240a-105">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="a240a-106">は、作成したクエリを同等の SQL クエリに変換し、それをサーバーに送って処理します。</span><span class="sxs-lookup"><span data-stu-id="a240a-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="a240a-107">[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] クエリの機能の中には、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションで特に注意を要するものがあります。</span><span class="sxs-lookup"><span data-stu-id="a240a-107">Some features of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="a240a-108">詳細については、[クエリの概念](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a240a-108">For more information, see [Query Concepts](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a240a-109">例</span><span class="sxs-lookup"><span data-stu-id="a240a-109">Example</span></span>  
 <span data-ttu-id="a240a-110">次のクエリは、ロンドンからの顧客のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="a240a-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="a240a-111">この例の `Customers` は、Northwind サンプル データベース内のテーブルです。</span><span class="sxs-lookup"><span data-stu-id="a240a-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a240a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a240a-112">See also</span></span>
- [<span data-ttu-id="a240a-113">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="a240a-113">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [<span data-ttu-id="a240a-114">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="a240a-114">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="a240a-115">データベースに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="a240a-115">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
