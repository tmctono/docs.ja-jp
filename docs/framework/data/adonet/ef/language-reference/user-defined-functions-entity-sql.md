---
title: ユーザー定義関数 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 9e5ad1f6edb0e719733edd2518c5d62a7fc6bdf7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180973"
---
# <a name="user-defined-functions-entity-sql"></a>ユーザー定義関数 (Entity SQL)

Entity SQL では、クエリ内でのユーザー定義関数の呼び出しがサポートされます。 これらの関数は、クエリを使用してインラインで定義する (「[方法:ユーザー定義関数を呼び出す](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))」を参照) ことも、概念モデルの一部として定義する (「[方法:概念モデルでカスタム関数を定義する](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))」を参照) こともできます。 概念モデル関数は、概念モデルの [Function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) 要素の [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) 要素における Entity SQL コマンドとして定義されます。  
  
 Entity SQL を使用すると、関数をクエリ コマンド自体で定義することができます。 [FUNCTION](function-entity-sql.md) 演算子では、インライン関数が定義されます。 複数の関数を 1 つのコマンドで定義することができます。関数の署名が一意であれば、これら複数の関数に同じ名前を付けることができます。 詳細については、「 [Function Overload Resolution](function-overload-resolution-entity-sql.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- [関数](functions-entity-sql.md)
