---
title: Of 句 (Visual Basic)
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
ms.openlocfilehash: c0cfbb5109d5b49f995028944e735c96440c9ab2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583506"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="99617-102">Of 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99617-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="99617-103">では、*ジェネリック*クラス、構造体、インターフェイス、デリゲート、またはプロシージャの*型パラメーター*を識別する `Of` 句が導入されています。</span><span class="sxs-lookup"><span data-stu-id="99617-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="99617-104">ジェネリック型の詳細については、「 [Visual Basic のジェネリック型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99617-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="99617-105">Of キーワードを使用する</span><span class="sxs-lookup"><span data-stu-id="99617-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="99617-106">次のコード例では、`Of` キーワードを使用して、2つの型パラメーターを受け取るクラスのアウトラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="99617-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="99617-107">@No__t_1 パラメーターは <xref:System.IComparable> インターフェイスによって*制限*されます。つまり、コンシューマー側のコードは <xref:System.IComparable> を実装する型引数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99617-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="99617-108">これは、`add` プロシージャが <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> メソッドを呼び出すことができるようにするために必要です。</span><span class="sxs-lookup"><span data-stu-id="99617-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="99617-109">制約の詳細については、「 [Type List](../../../visual-basic/language-reference/statements/type-list.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="99617-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
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
  
 <span data-ttu-id="99617-110">前のクラス定義を完了すると、そこからさまざまな `dictionary` クラスを構築できます。</span><span class="sxs-lookup"><span data-stu-id="99617-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="99617-111">@No__t_0 するために指定する型は、クラスに保持されているエントリの種類と、各エントリに関連付けられているキーの種類を決定 `keyType` ます。</span><span class="sxs-lookup"><span data-stu-id="99617-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="99617-112">制約があるため、<xref:System.IComparable> を実装する型を `keyType` するには、を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99617-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="99617-113">次のコード例は、`String` エントリーを持ち、`Integer` キーを互いに関連づけるオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="99617-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="99617-114">`Integer` は <xref:System.IComparable> を実装し、それゆえに `keyType` の制約を満たします。</span><span class="sxs-lookup"><span data-stu-id="99617-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="99617-115">キーワード `Of` は次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="99617-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="99617-116">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="99617-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="99617-117">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="99617-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="99617-118">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="99617-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="99617-119">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="99617-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="99617-120">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="99617-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="99617-121">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="99617-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="99617-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="99617-122">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="99617-123">型リスト</span><span class="sxs-lookup"><span data-stu-id="99617-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="99617-124">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="99617-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="99617-125">In</span><span class="sxs-lookup"><span data-stu-id="99617-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="99617-126">Out</span><span class="sxs-lookup"><span data-stu-id="99617-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
