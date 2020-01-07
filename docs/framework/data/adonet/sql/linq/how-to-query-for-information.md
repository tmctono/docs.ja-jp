---
title: '方法 : クエリで情報を取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 3380b486da33a5dc083ed51f6705e666978df197
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634652"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="6a338-102">方法 : クエリで情報を取得する</span><span class="sxs-lookup"><span data-stu-id="6a338-102">How to: Query for Information</span></span>
<span data-ttu-id="6a338-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のクエリでは、LINQ のクエリと同じ構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a338-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in LINQ.</span></span> <span data-ttu-id="6a338-104">唯一の違いは、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] クエリで参照されるオブジェクトがデータベース内の要素にマップされる点です。</span><span class="sxs-lookup"><span data-stu-id="6a338-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="6a338-105">詳細については、「[LINQ クエリの概要 (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a338-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="6a338-106">は、作成したクエリを同等の SQL クエリに変換し、それをサーバーに送って処理します。</span><span class="sxs-lookup"><span data-stu-id="6a338-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="6a338-107">LINQ クエリの機能の中には、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションで特に注意が必要なものもあります。</span><span class="sxs-lookup"><span data-stu-id="6a338-107">Some features of LINQ queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="6a338-108">詳細については、「[クエリの概念](query-concepts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a338-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a338-109">使用例</span><span class="sxs-lookup"><span data-stu-id="6a338-109">Example</span></span>  
 <span data-ttu-id="6a338-110">次のクエリは、ロンドンからの顧客のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a338-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="6a338-111">この例の `Customers` は、Northwind サンプル データベース内のテーブルです。</span><span class="sxs-lookup"><span data-stu-id="6a338-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6a338-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a338-112">See also</span></span>

- [<span data-ttu-id="6a338-113">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="6a338-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="6a338-114">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="6a338-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="6a338-115">データベースに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="6a338-115">Querying the Database</span></span>](querying-the-database.md)
