---
title: 作業の開始
description: このサンプル コードを使用して LINQ to SQL の使用を開始し、LINQ テクノロジを使用して、メモリ内コレクションにアクセスする場合と同じように SQL データベースにアクセスします。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: b886518d4cff687a18f363c3e3ba43b40631a22f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194376"
---
# <a name="getting-started"></a><span data-ttu-id="431be-103">作業の開始</span><span class="sxs-lookup"><span data-stu-id="431be-103">Getting Started</span></span>

<span data-ttu-id="431be-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] を使用すると、LINQ テクノロジを使用して、メモリ内コレクションへのアクセスと同じように SQL データベースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="431be-104">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the LINQ technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="431be-105">たとえば、次のコードでは、`nw` データベースを表す `Northwind` オブジェクトが作成され、`Customers` テーブルが対象とされ、`Customers` からの `London` を選択するように行がフィルター処理され、取得する `CompanyName` の文字列が選択されます。</span><span class="sxs-lookup"><span data-stu-id="431be-105">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="431be-106">ループが実行されると、`CompanyName` の値のコレクションが取得されます。</span><span class="sxs-lookup"><span data-stu-id="431be-106">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="431be-107">次の手順</span><span class="sxs-lookup"><span data-stu-id="431be-107">Next Steps</span></span>  

 <span data-ttu-id="431be-108">挿入や更新など、これ以外の例については、「[LINQ to SQL の主な機能](what-you-can-do-with-linq-to-sql.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="431be-108">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="431be-109">次に、チュートリアルで [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の使用を実際に体験できます。</span><span class="sxs-lookup"><span data-stu-id="431be-109">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="431be-110">「[チュートリアルによる学習](learning-by-walkthroughs.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="431be-110">See [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="431be-111">最後に、独自の [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] プロジェクトで作業を始める方法については、「[典型的な LINQ to SQL の使用手順](typical-steps-for-using-linq-to-sql.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="431be-111">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="431be-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="431be-112">See also</span></span>

- [<span data-ttu-id="431be-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="431be-113">LINQ to SQL</span></span>](index.md)
- [<span data-ttu-id="431be-114">LINQ の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="431be-114">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="431be-115">LINQ の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="431be-115">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="431be-116">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="431be-116">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
