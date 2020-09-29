---
title: サポートされていない機能
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: d4fe3d91b80197d962989cd2d3bc9bb2df6e3ffe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164156"
---
# <a name="unsupported-functionality"></a>サポートされていない機能

LINQ to SQL では、次の SQL 機能は、既存の共通言語ランタイム (CLR) および .NET Framework の構成要素の変換からは公開できません。  
  
- `STDDEV`  
  
- `LIKE`  
  
     `LIKE` は直接変換によってサポートされませんが、同様の機能が <xref:System.Data.Linq.SqlClient.SqlMethods> クラスにあります。 詳細については、「<xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>」を参照してください。  
  
- `DATEDIFF`  
  
     LINQ to SQL では、`DATEDIFF` のサポートが制限されています。 同様の機能が <xref:System.Data.Linq.SqlClient.SqlMethods> クラスにあります。  
  
- `ROUND`  
  
     LINQ to SQL では、`ROUND` のサポートが制限されています。 詳細については、「[System.Math メソッド](system-math-methods.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- [データ型と関数](data-types-and-functions.md)
