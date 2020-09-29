---
title: シーケンス内の要素数のカウント
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: d983bc14f4fda04bda0a6f363db4c11f062c4c48
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164351"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a>シーケンス内の要素数のカウント

<xref:System.Linq.Enumerable.Count%2A> 演算子を使用すると、シーケンス内の要素数をカウントできます。  
  
 Northwind サンプル データベースに対してこのクエリを実行すると、出力は `91` になります。  
  
## <a name="example"></a>例  

 データベース内の `Customers` の数をカウントする例を次に示します。  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a>例  

 データベース内の製品のうち、生産中止になっていない製品の数をカウントする例を次に示します。  
  
 Northwind サンプル データベースに対してこのクエリを実行すると、出力は `69` になります。  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>関連項目

- [集計クエリ](aggregate-queries.md)
- [サンプル データベースのダウンロード](downloading-sample-databases.md)
