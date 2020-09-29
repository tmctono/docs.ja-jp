---
title: . (メンバー アクセス) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: 82cd2f17b2b5ea484a8202b50619047b428fe94a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192153"
---
# <a name="-member-access-entity-sql"></a>. (メンバー アクセス) (Entity SQL)

ドット演算子 (.) は、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] のメンバー アクセス演算子です。 メンバー アクセス演算子を使用すると、構造型概念モデル型のインスタンスのプロパティ値またはフィールド値を生成できます。  
  
## <a name="syntax"></a>構文  
  
```sql  
expression.identifier  
```  
  
## <a name="arguments"></a>引数  

 `expression`  
 構造型概念モデル型のインスタンス。  
  
 `identifier`  
 オブジェクト インスタンスに属するプロパティまたはフィールド。  
  
## <a name="remarks"></a>Remarks  

 ドット (.) 演算子は、複合型またはエンティティ型のプロパティの抽出と同様に、レコードからフィールドを抽出するために使用できます。 たとえば、Name 型の n が Person 型のメンバーであり、p が Person 型のインスタンスである場合、p.n は有効なメンバー アクセス式として Name 型の値を生成します。  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a>関連項目

- [Entity SQL リファレンス](entity-sql-reference.md)
