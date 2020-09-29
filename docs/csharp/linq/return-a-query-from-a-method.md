---
title: メソッドからクエリを返す
description: クエリを返す方法。
ms.date: 11/30/2016
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: 646e771d637aa242231e3fe216d4a856bb156649
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203333"
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a>メソッドからクエリを返す方法 (C# プログラミング ガイド)

この例では、メソッドから、クエリを戻り値として返す方法と `out` パラメーターとして返す方法を示します。  
  
 クエリ オブジェクトはコンポーザブルです。つまり、メソッドからクエリを返すことができます。 クエリを表すオブジェクトには、結果のコレクションではなく、必要に応じて結果を生成する手順が格納されます。 メソッドからクエリ オブジェクトを返すメリットは、そのオブジェクトをさらに構成したり変更したりできることです。 そのため、クエリを返すメソッドの戻り値または `out` パラメーターも同じ型である必要があります。 メソッドがクエリを具象型 <xref:System.Collections.Generic.List%601> または <xref:System.Array> に実体化する場合は、そのメソッドは、クエリ自体ではなくクエリ結果を返すと見なされます。 メソッドから返されたクエリ変数は、引き続き構成または変更できます。  
  
## <a name="example"></a>例  

 次の例は、最初のメソッドはクエリを戻り値として返し、2 番目のメソッドはクエリを `out` パラメーターとして返しています。 どちらの場合も返されるのはクエリであり、クエリ結果ではないことに注意してください。  
  
 [!code-csharp[csProgGuideLINQ#80](~/samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a>参照

- [統合言語クエリ (LINQ)](index.md)
