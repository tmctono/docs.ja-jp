---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: bdab81ed8acae5e757de0a669922dc79d0303ee4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203593"
---
# <a name="using-entity-sql"></a>USING (Entity SQL)

クエリ式で使用する名前空間を指定します。  
  
## <a name="syntax"></a>構文  
  
```sql  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a>引数  

 `alias`  
 名前空間を修飾する短い別名。  
  
 `namespace`  
 任意の有効な名前空間。  
  
## <a name="example"></a>例  

 次の Entity SQL クエリでは、USING 演算子を使用して、クエリ式に使用する名前空間が指定されています。 このクエリをコンパイルして実行するには、次の手順を実行します。  
  
1. 「[方法: PrimitiveType 結果を返すクエリを実行する](../how-to-execute-a-query-that-returns-primitivetype-results.md)」の手順に従います。  
  
2. 次のクエリを引数として `ExecutePrimitiveTypeQuery` メソッドに渡します。  
  
```csharp
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a>関連項目

- [名前空間](namespaces-entity-sql.md)
- [Entity SQL リファレンス](entity-sql-reference.md)
