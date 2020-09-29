---
title: 変数 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: af6d586a22f14a04bfc7ec339d0aa8e9ba7c66c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180999"
---
# <a name="variables-entity-sql"></a>変数 (Entity SQL)

## <a name="variable"></a>変数  

 変数式は、現在のスコープで定義されている名前付きの式への参照です。 変数参照は、[識別子](identifiers-entity-sql.md)で定義された有効な [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 識別子である必要があります。  
  
 次の例は、式における変数の使用方法を示しています。 FROM 句の `c` は変数の定義です。 SELECT 句内で使用された `c` は、変数参照を表します。  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a>関連項目

- [識別子](identifiers-entity-sql.md)
- [パラメーター](parameters-entity-sql.md)
- [Entity SQL の概要](entity-sql-overview.md)
