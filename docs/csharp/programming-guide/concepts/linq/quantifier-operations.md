---
title: 量指定子操作 (C#)
description: 量指定子操作について説明します。 これらの操作では、シーケンス内の要素の一部またはすべてが条件を満たしているかどうかを示すブール値が返されます。
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: ce06f887d3ad7b10cbdedf9e33072df2c0819ef1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299150"
---
# <a name="quantifier-operations-c"></a>量指定子操作 (C#)
量指定子操作は、シーケンス内の要素の一部またはすべてが条件を満たしているかどうかを示す <xref:System.Boolean> 値を返します。  
  
 次の図は、2 つの異なるソース シーケンスに対する、2 つの異なる量指定子操作を示しています。 最初の操作では、1 つ以上の要素が文字 'A' であるかどうかを尋ねていて、その結果は `true` です。 2 番目の操作では、すべての要素が文字 'A' であるかどうかを尋ねていて、その結果は `true` です。  
  
 ![LINQ 量指定子操作](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 次のセクションでは、量指定子操作を実行する標準クエリ演算子のメソッドの一覧を示します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド名|説明|C# のクエリ式の構文|説明|  
|-----------------|-----------------|---------------------------------|----------------------|  
|すべて|シーケンス内のすべての要素が条件を満たしているかどうかを調べます。|該当なし。|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|どれでも可|シーケンス内のいずれかの要素が条件を満たしているかどうかを調べます。|該当なし。|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|内容|指定した要素がシーケンスに格納されているかどうかを調べます。|該当なし。|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a>クエリ式の構文例  
  
### <a name="all"></a>すべて  
次の例では、`All` を使用して、すべての文字列が特定の長さであることを確認します。
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a>どれでも可  
次の例では、`Any` を使用して、任意の文字列が "o" で開始されることを確認します。  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a>内容  
次の例では、`Contains` を使用して、配列に特定の要素が含まれることを確認します。  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Linq>
- [標準クエリ演算子の概要 (C#)](./standard-query-operators-overview.md)
- [実行時における述語フィルターの動的指定](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [指定されたワードのセットを含む文章を照会する方法 (LINQ) (C#)](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
