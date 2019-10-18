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
ms.openlocfilehash: 880570c714292b0c11eef4e2cd4c4b410bb075f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784151"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="59973-102">Of 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59973-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="59973-103">導入されています、`Of`句は、識別、*パラメーターを入力*上、*ジェネリック*クラス、構造体、インターフェイス、デリゲート、またはプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="59973-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="59973-104">ジェネリック型については、次を参照してください。 [Visual Basic におけるジェネリック型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="59973-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="59973-105">使用して、キーワードの</span><span class="sxs-lookup"><span data-stu-id="59973-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="59973-106">次のコード例では、`Of`キーワードを 2 つの型パラメーターを受け取るクラスのアウトラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="59973-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="59973-107">これは、*制約*、`keyType`パラメーターで、<xref:System.IComparable>インターフェイスで、使用側コードが実装する型引数を指定する必要がありますが、 <xref:System.IComparable>。</span><span class="sxs-lookup"><span data-stu-id="59973-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="59973-108">これは、必要なように、`add`プロシージャを呼び出すことができます、<xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="59973-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="59973-109">制約の詳細については、「 [Type List](../../../visual-basic/language-reference/statements/type-list.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="59973-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```  
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
  
 <span data-ttu-id="59973-110">上記のクラス定義を完了すると、そこから様々な `dictionary` クラスを構築することができます。</span><span class="sxs-lookup"><span data-stu-id="59973-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="59973-111">`entryType` と `keyType` に与える型が、そのクラスが持つエントリーの型と、互いのエントリーと関連するキーの型を決定します。</span><span class="sxs-lookup"><span data-stu-id="59973-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="59973-112">制約により、`keyType` には <xref:System.IComparable> を実装する型を与えなければなりません。</span><span class="sxs-lookup"><span data-stu-id="59973-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="59973-113">次のコード例は、保持するオブジェクトを作成します。`String`エントリと、`Integer`がそれぞれのキー。</span><span class="sxs-lookup"><span data-stu-id="59973-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="59973-114">`Integer` 実装<xref:System.IComparable>し、そのために、制約を満たす`keyType`します。</span><span class="sxs-lookup"><span data-stu-id="59973-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="59973-115">キーワード `Of` は次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="59973-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="59973-116">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="59973-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="59973-117">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="59973-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="59973-118">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="59973-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="59973-119">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="59973-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="59973-120">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="59973-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="59973-121">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="59973-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="59973-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="59973-122">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="59973-123">型リスト</span><span class="sxs-lookup"><span data-stu-id="59973-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="59973-124">Visual Basic におけるジェネリック型</span><span class="sxs-lookup"><span data-stu-id="59973-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="59973-125">In</span><span class="sxs-lookup"><span data-stu-id="59973-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="59973-126">Out</span><span class="sxs-lookup"><span data-stu-id="59973-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
