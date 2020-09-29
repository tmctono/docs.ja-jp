---
title: データ型と関数
ms.date: 03/30/2017
ms.assetid: 683413c5-0312-4e60-8619-9a97bdc6e62a
ms.openlocfilehash: 456cf5acf42221379e68ff79ee57c084664e30e5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147763"
---
# <a name="data-types-and-functions"></a>データ型と関数

次の表の各トピックでは、共通言語ランタイム (CLR) のメンバー、コンストラクト、およびキャストに対する LINQ to SQL でのサポートについて説明します。 サポートされているメンバーおよびコンストラクトは、LINQ to SQL クエリで使用できます。  
  
 この表でサポートされていないアイテムは、LINQ to SQL では、SQL Server で実行するために CLR のメンバー、コンストラクト、またはキャストを変換できないことを意味します。 それらをコード内で使用することはできる場合もありますが、クエリが Transact-SQL に変換される前、またはデータベースから結果が取得された後に評価する必要があります。  
  
|トピック|説明|  
|-----------|-----------------|  
|[SQL と CLR の型マッピング](sql-clr-type-mapping.md)|CLR 型と SQL Server 型のマッピングを、行列形式で示します。|  
|[基本データ型](basic-data-types.md)|.NET Framework の動作との相違の概要を示します。|  
|[ブール データ型](boolean-data-types.md)|.NET Framework の動作との相違の概要を示します。|  
|[null セマンティクス](null-semantics.md)|null および null 許容に関する問題が記載されている [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] トピックへのリンクを示します。|  
|[数値演算子および比較演算子](numeric-and-comparison-operators.md)|.NET Framework の動作との相違の概要を示します。|  
|[シーケンス演算子](sequence-operators.md)|.NET Framework の動作との相違の概要を示します。|  
|[System.Convert メソッド](system-convert-methods.md)|.NET Framework の動作との相違の概要を示します。|  
|[System.DateTime メソッド](system-datetime-methods.md)|<xref:System.DateTime?displayProperty=nameWithType> 構造体のメンバーに対する LINQ to SQL でのサポートについて説明します。|  
|[System.DateTimeOffset メソッド](system-datetimeoffset-methods.md)|<xref:System.DateTimeOffset?displayProperty=nameWithType> 構造体のメンバーに対する LINQ to SQL でのサポートについて説明します。|  
|[System.Math メソッド](system-math-methods.md)|.NET Framework の動作との相違の概要を示します。|  
|[System.Object メソッド](system-object-methods.md)|.NET Framework の動作との相違の概要を示します。|  
|[System.String メソッド](system-string-methods.md)|.NET Framework の動作との相違の概要を示します。|  
|[System.TimeSpan メソッド](system-timespan-methods.md)|<xref:System.TimeSpan?displayProperty=nameWithType> 構造体のメンバーに対する LINQ to SQL でのサポートについて説明します。|  
|[サポートされていない機能](unsupported-functionality.md)|[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] でサポートされていない機能について説明します。|  
  
## <a name="see-also"></a>関連項目

- [SQL と CLR の型の不一致](sql-clr-type-mismatches.md)
- [参照](reference.md)
