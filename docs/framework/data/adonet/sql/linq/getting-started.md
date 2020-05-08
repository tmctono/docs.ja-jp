---
title: 作業の開始
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: 3bff4e9f268e9eac84c244cb58eed8b4384e717d
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634692"
---
# <a name="getting-started"></a><span data-ttu-id="a28d7-102">作業の開始</span><span class="sxs-lookup"><span data-stu-id="a28d7-102">Getting Started</span></span>
<span data-ttu-id="a28d7-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] を使用すると、LINQ テクノロジを使用して、メモリ内コレクションへのアクセスと同じように SQL データベースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a28d7-103">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the LINQ technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="a28d7-104">たとえば、次のコードでは、`nw` データベースを表す `Northwind` オブジェクトが作成され、`Customers` テーブルが対象とされ、`Customers` からの `London` を選択するように行がフィルター処理され、取得する `CompanyName` の文字列が選択されます。</span><span class="sxs-lookup"><span data-stu-id="a28d7-104">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="a28d7-105">ループが実行されると、`CompanyName` の値のコレクションが取得されます。</span><span class="sxs-lookup"><span data-stu-id="a28d7-105">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="a28d7-106">次の手順</span><span class="sxs-lookup"><span data-stu-id="a28d7-106">Next Steps</span></span>  
 <span data-ttu-id="a28d7-107">挿入や更新など、これ以外の例については、「[LINQ to SQL の主な機能](what-you-can-do-with-linq-to-sql.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a28d7-107">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="a28d7-108">次に、チュートリアルで [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の使用を実際に体験できます。</span><span class="sxs-lookup"><span data-stu-id="a28d7-108">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="a28d7-109">「[チュートリアルによる学習](learning-by-walkthroughs.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a28d7-109">See [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="a28d7-110">最後に、独自の [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] プロジェクトで作業を始める方法については、「[典型的な LINQ to SQL の使用手順](typical-steps-for-using-linq-to-sql.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a28d7-110">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a28d7-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="a28d7-111">See also</span></span>

- [<span data-ttu-id="a28d7-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a28d7-112">LINQ to SQL</span></span>](index.md)
- [<span data-ttu-id="a28d7-113">LINQ の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="a28d7-113">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="a28d7-114">LINQ の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a28d7-114">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="a28d7-115">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="a28d7-115">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
