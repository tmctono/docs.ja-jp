---
title: '方法: クエリで情報を取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: d45fdfa8b8976e3cdc86b905443bf7bcea578714
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166405"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="7ab52-102">方法: クエリで情報を取得する</span><span class="sxs-lookup"><span data-stu-id="7ab52-102">How to: Query for Information</span></span>

<span data-ttu-id="7ab52-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] でのクエリでは、LINQ でのクエリと同じ構文が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7ab52-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in LINQ.</span></span> <span data-ttu-id="7ab52-104">異なる点は、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] クエリ内で参照されるオブジェクトは、データベース内の要素に割り当てられるという点だけです。</span><span class="sxs-lookup"><span data-stu-id="7ab52-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="7ab52-105">詳細については、「[LINQ クエリの概要 (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ab52-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7ab52-106">は、作成したクエリを同等の SQL クエリに変換し、それをサーバーに送って処理します。</span><span class="sxs-lookup"><span data-stu-id="7ab52-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="7ab52-107">LINQ クエリの機能の中には、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションで特に注意を要するものがあります。</span><span class="sxs-lookup"><span data-stu-id="7ab52-107">Some features of LINQ queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="7ab52-108">詳しくは、「[クエリの概念](query-concepts.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7ab52-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ab52-109">例</span><span class="sxs-lookup"><span data-stu-id="7ab52-109">Example</span></span>  

 <span data-ttu-id="7ab52-110">次のクエリは、ロンドンからの顧客のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="7ab52-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="7ab52-111">この例の `Customers` は、Northwind サンプル データベース内のテーブルです。</span><span class="sxs-lookup"><span data-stu-id="7ab52-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7ab52-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ab52-112">See also</span></span>

- [<span data-ttu-id="7ab52-113">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="7ab52-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="7ab52-114">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="7ab52-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="7ab52-115">データベースに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="7ab52-115">Querying the Database</span></span>](querying-the-database.md)
