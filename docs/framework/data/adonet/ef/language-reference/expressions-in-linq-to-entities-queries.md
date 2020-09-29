---
title: LINQ to Entities クエリ内の式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: f65759d37661271588d56965eadcccbe997623f4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166652"
---
# <a name="expressions-in-linq-to-entities-queries"></a>LINQ to Entities クエリ内の式

式は、単一の値、オブジェクト、メソッド、または名前空間として評価されるコード フラグメントです。 式には、リテラル値、メソッド呼び出し、演算子とそのオペランド、または単純な名前を含めることができます。 単純な名前には、変数、型メンバー、メソッド パラメーター、名前空間、または型の名前を指定できます。 式では、他の式をパラメーターとして使用する演算子、またはパラメーターが他のメソッド呼び出しであるメソッド呼び出しを使用できます。 したがって、単純な式だけでなく、非常に複雑な式も作成できます。  
  
 LINQ to Entities のクエリの式では、ラムダ式など、<xref:System.Linq.Expressions> 名前空間内の型で許容されている要素であれば何でも使用できます。 LINQ to Entities のクエリで使用可能な式は、Entity Framework のクエリに使用可能な式のスーパーセットです。Entity Framework に対するクエリの一部である式は、`ObjectQuery<T>` および基になるデータ ソースでサポートされている演算に制限されます。  
  
 次の例では、`Where` 句で使用される比較の式を示します。  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
> C# の `unchecked` などの特殊な言語構造は、LINQ to Entities では意味がありません。  
  
## <a name="in-this-section"></a>このセクションの内容  

 [定数式](constant-expressions.md)  
  
 [比較式](comparison-expressions.md)  
  
 [NULL 比較](null-comparisons.md)  
  
 [初期化式](initialization-expressions.md)  
  
 [リレーションシップ、ナビゲーション プロパティ、および外部キー](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a>関連項目

- [ADO.NET Entity Framework](../index.md)
