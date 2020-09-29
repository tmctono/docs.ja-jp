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
# <a name="how-to-query-for-information"></a>方法: クエリで情報を取得する

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] でのクエリでは、LINQ でのクエリと同じ構文が使用されます。 異なる点は、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] クエリ内で参照されるオブジェクトは、データベース内の要素に割り当てられるという点だけです。 詳細については、「[LINQ クエリの概要 (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)」を参照してください。  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] は、作成したクエリを同等の SQL クエリに変換し、それをサーバーに送って処理します。  
  
 LINQ クエリの機能の中には、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションで特に注意を要するものがあります。 詳しくは、「[クエリの概念](query-concepts.md)」をご覧ください。  
  
## <a name="example"></a>例  

 次のクエリは、ロンドンからの顧客のリストを取得します。 この例の `Customers` は、Northwind サンプル データベース内のテーブルです。  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>関連項目

- [オブジェクト モデルの作成](creating-the-object-model.md)
- [サンプル データベースのダウンロード](downloading-sample-databases.md)
- [データベースに対するクエリの実行](querying-the-database.md)
