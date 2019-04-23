---
title: '方法: オブジェクト変数の参照 (Visual Basic) にどのような種類を決定します。'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 6499dfce880cc9ce16e5d77887afc0598692f48e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342870"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="f91af-102">方法: オブジェクト変数の参照 (Visual Basic) にどのような種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="f91af-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>
<span data-ttu-id="f91af-103">オブジェクト変数には、別の場所に格納されているデータへのポインターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f91af-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="f91af-104">実行時にそのデータの種類を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f91af-104">The type of that data can change during run time.</span></span> <span data-ttu-id="f91af-105">任意の時点では、使用することができます、<xref:System.Type.GetTypeCode%2A>する現在の実行時の型を判断するメソッド、または[TypeOf 演算子](../../../../visual-basic/language-reference/operators/typeof-operator.md)ことを確認する現在の実行時の型が指定された型との互換性。</span><span class="sxs-lookup"><span data-stu-id="f91af-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="f91af-106">現在オブジェクト変数を入力を正確なを判断するには</span><span class="sxs-lookup"><span data-stu-id="f91af-106">To determine the exact type an object variable currently refers to</span></span>  
  
1. <span data-ttu-id="f91af-107">オブジェクト変数を呼び出して、<xref:System.Object.GetType%2A>を取得するメソッド、<xref:System.Type?displayProperty=nameWithType>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f91af-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2. <span data-ttu-id="f91af-108"><xref:System.Type?displayProperty=nameWithType>クラス、共有メソッドを呼び出す<xref:System.Type.GetTypeCode%2A>を取得する、<xref:System.TypeCode>オブジェクトの型の列挙値。</span><span class="sxs-lookup"><span data-stu-id="f91af-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     <span data-ttu-id="f91af-109">テストすることができます、<xref:System.TypeCode>などは、関心のある方の列挙体メンバーに対して列挙値`Double`します。</span><span class="sxs-lookup"><span data-stu-id="f91af-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="f91af-110">変数の型が指定した型と互換性がオブジェクトかどうかを判断するには</span><span class="sxs-lookup"><span data-stu-id="f91af-110">To determine whether an object variable's type is compatible with a specified type</span></span>  
  
-   <span data-ttu-id="f91af-111">使用して、`TypeOf`演算子と組み合わせて、 [Is 演算子](../../../../visual-basic/language-reference/operators/is-operator.md)でオブジェクトをテストする、 `TypeOf`.`Is`式。</span><span class="sxs-lookup"><span data-stu-id="f91af-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     <span data-ttu-id="f91af-112">`TypeOf`.`Is`式を返します`True`型に指定した型と互換性がある場合は、オブジェクトの実行時。</span><span class="sxs-lookup"><span data-stu-id="f91af-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>  
  
     <span data-ttu-id="f91af-113">互換性のための条件は、指定した型がクラス、構造体、またはインターフェイスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f91af-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="f91af-114">一般に、型が互換性のあるオブジェクトと同じ型の継承、または指定した型を実装する場合。</span><span class="sxs-lookup"><span data-stu-id="f91af-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="f91af-115">詳細については、次を参照してください。 [TypeOf 演算子](../../../../visual-basic/language-reference/operators/typeof-operator.md)します。</span><span class="sxs-lookup"><span data-stu-id="f91af-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f91af-116">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f91af-116">Compiling the Code</span></span>  
 <span data-ttu-id="f91af-117">指定した型が変数または式ができないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f91af-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="f91af-118">クラス、構造体、インターフェイスなどの定義済みの型の名前があります。</span><span class="sxs-lookup"><span data-stu-id="f91af-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="f91af-119">などの組み込みの型が含まれます`Integer`と`String`します。</span><span class="sxs-lookup"><span data-stu-id="f91af-119">This includes intrinsic types such as `Integer` and `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f91af-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f91af-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="f91af-121">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="f91af-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="f91af-122">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="f91af-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="f91af-123">Object 型</span><span class="sxs-lookup"><span data-stu-id="f91af-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
