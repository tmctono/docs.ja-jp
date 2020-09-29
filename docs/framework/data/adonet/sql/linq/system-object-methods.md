---
title: System.Object メソッド
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: d2b96ca9e7bedd0e0438b47698d4b963844c92f3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155641"
---
# <a name="systemobject-methods"></a>System.Object メソッド

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では、次の <xref:System.Object> メソッドがサポートされます。  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] は、次の <xref:System.Object> メソッドをサポートしていません。  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>、`BINARY`、`VARBINARY`、`IMAGE` などのバイナリ型の `TIMESTAMP`||  
  
## <a name="differences-from-net"></a>.NET との相違  

 SQL では、double 型に対する <xref:System.Object.ToString?displayProperty=nameWithType> の出力で、SQL `CONVERT` (NVARCHAR(30), @x, 2) が使用されます。 このとき、SQL は常に 16 桁と指数表記を使用します (たとえば、0 に対して "0.000000000000000e+000" を使用)。 そのため、<xref:System.Object.ToString?displayProperty=nameWithType> 変換では、.NET Framework 内の <xref:System.Convert.ToString%2A?displayProperty=nameWithType>  と同じ文字列は作成されません。  
  
## <a name="see-also"></a>関連項目

- [データ型と関数](data-types-and-functions.md)
