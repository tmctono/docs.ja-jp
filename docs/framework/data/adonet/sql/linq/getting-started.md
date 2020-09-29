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
# <a name="getting-started"></a>作業の開始

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] を使用すると、LINQ テクノロジを使用して、メモリ内コレクションへのアクセスと同じように SQL データベースにアクセスできます。  
  
 たとえば、次のコードでは、`nw` データベースを表す `Northwind` オブジェクトが作成され、`Customers` テーブルが対象とされ、`Customers` からの `London` を選択するように行がフィルター処理され、取得する `CompanyName` の文字列が選択されます。  
  
 ループが実行されると、`CompanyName` の値のコレクションが取得されます。  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a>次の手順  

 挿入や更新など、これ以外の例については、「[LINQ to SQL の主な機能](what-you-can-do-with-linq-to-sql.md)」をご覧ください。  
  
 次に、チュートリアルで [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の使用を実際に体験できます。 「[チュートリアルによる学習](learning-by-walkthroughs.md)」をご覧ください。  
  
 最後に、独自の [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] プロジェクトで作業を始める方法については、「[典型的な LINQ to SQL の使用手順](typical-steps-for-using-linq-to-sql.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目

- [LINQ to SQL](index.md)
- [LINQ の概要 (C#)](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [LINQ の概要 (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [LINQ to SQL オブジェクト モデル](the-linq-to-sql-object-model.md)
