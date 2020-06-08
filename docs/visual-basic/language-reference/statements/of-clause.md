---
title: Of 句
ms.date: 07/20/2015
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
ms.openlocfilehash: d88c43efe858d6b81b7d8d2470b234ff5d40632a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353839"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="98c7a-102">Of 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98c7a-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="98c7a-103">`Of` 句が導入されています。これは、*ジェネリック* クラス、構造体、インターフェイス、デリゲート、またはプロシージャの*型パラメーター*を識別します。</span><span class="sxs-lookup"><span data-stu-id="98c7a-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="98c7a-104">ジェネリック型については、「[Visual Basic におけるジェネリック型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98c7a-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="98c7a-105">Of キーワードの使用</span><span class="sxs-lookup"><span data-stu-id="98c7a-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="98c7a-106">次のコード例では、`Of` キーワードを使用して、2 つの型パラメーターを受け取るクラスの概要を定義しています。</span><span class="sxs-lookup"><span data-stu-id="98c7a-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="98c7a-107">それは、<xref:System.IComparable> インターフェイスによって、`keyType` パラメーターを*制約*します。つまり、使用するコードで、<xref:System.IComparable> を実装する型引数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98c7a-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="98c7a-108">これは、`add` プロシージャで <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> メソッドを呼び出せるようにするために必要です。</span><span class="sxs-lookup"><span data-stu-id="98c7a-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="98c7a-109">制約の詳細については、「 [Type List](../../../visual-basic/language-reference/statements/type-list.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="98c7a-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```vb  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 <span data-ttu-id="98c7a-110">前のクラス定義を完了したら、そこからさまざまな `dictionary` クラスを構築できます。</span><span class="sxs-lookup"><span data-stu-id="98c7a-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="98c7a-111">`entryType` および `keyType` に指定する型によって、クラスで保持されるエントリの型と、各エントリに関連付けられるキーの型が決まります。</span><span class="sxs-lookup"><span data-stu-id="98c7a-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="98c7a-112">制約のため、`keyType` に <xref:System.IComparable> を実装する型を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98c7a-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="98c7a-113">次のコード例では、`String` エントリを保持し、それぞれに `Integer` キーを関連付けるオブジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="98c7a-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="98c7a-114">`Integer` は <xref:System.IComparable> を実装しており、そのため、`keyType` の制約を満たします。</span><span class="sxs-lookup"><span data-stu-id="98c7a-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="98c7a-115">キーワード `Of` は次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="98c7a-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="98c7a-116">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="98c7a-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="98c7a-117">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="98c7a-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="98c7a-118">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="98c7a-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="98c7a-119">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="98c7a-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="98c7a-120">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="98c7a-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="98c7a-121">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="98c7a-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="98c7a-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="98c7a-122">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="98c7a-123">型リスト</span><span class="sxs-lookup"><span data-stu-id="98c7a-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="98c7a-124">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="98c7a-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="98c7a-125">In</span><span class="sxs-lookup"><span data-stu-id="98c7a-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="98c7a-126">Out</span><span class="sxs-lookup"><span data-stu-id="98c7a-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
