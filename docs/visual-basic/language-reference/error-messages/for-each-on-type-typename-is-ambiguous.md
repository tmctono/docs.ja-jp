---
title: 型が、'System.Collections.Generic.IEnumerable(Of T)' の複数のインスタンス生成を実装するため、型 '<typename>' の 'For Each' は不適切です。
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: bdfb6e9b1332db1f049bb2575e97215026efe0dd
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591759"
---
# <a name="for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a><span data-ttu-id="963b5-102">型 '\<typename>' の 'For Each' は、型が 'System.Collections.Generic.IEnumerable(Of T)' の複数のインスタンス生成を実装するため、不適切です</span><span class="sxs-lookup"><span data-stu-id="963b5-102">'For Each' on type '\<typename>' is ambiguous because the type implements multiple instantiations of 'System.Collections.Generic.IEnumerable(Of T)'</span></span>
<span data-ttu-id="963b5-103">`For Each` ステートメントで、複数の <xref:System.Collections.IEnumerable.GetEnumerator%2A> メソッドを含む反復子変数を指定しています。</span><span class="sxs-lookup"><span data-stu-id="963b5-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="963b5-104">反復子変数は、.NET Framework の `Collections` 名前空間のいずれかに <xref:System.Collections.IEnumerable?displayProperty=nameWithType> または <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> インターフェイスを実装する型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="963b5-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the .NET Framework.</span></span> <span data-ttu-id="963b5-105">1 つのクラスで複数の構築されたジェネリック インターフェイスを、それぞれの構築に異なる型引数を使用して実装することができます。</span><span class="sxs-lookup"><span data-stu-id="963b5-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="963b5-106">これを行うクラスが反復子変数に使用されている場合、その変数には複数の <xref:System.Collections.IEnumerable.GetEnumerator%2A> メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="963b5-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="963b5-107">このような場合、Visual Basic で呼び出すメソッドを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="963b5-107">In such a case, Visual Basic cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="963b5-108">**エラー ID:** BC32096</span><span class="sxs-lookup"><span data-stu-id="963b5-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="963b5-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="963b5-109">To correct this error</span></span>  
  
- <span data-ttu-id="963b5-110">[DirectCast 演算子](../../../visual-basic/language-reference/operators/directcast-operator.md)または [TryCast 演算子](../../../visual-basic/language-reference/operators/trycast-operator.md)を使用して、反復子変数の型を、使用する <xref:System.Collections.IEnumerable.GetEnumerator%2A> メソッドを定義するインターフェイスにキャストします。</span><span class="sxs-lookup"><span data-stu-id="963b5-110">Use [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="963b5-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="963b5-111">See also</span></span>

- [<span data-ttu-id="963b5-112">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="963b5-112">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="963b5-113">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="963b5-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
