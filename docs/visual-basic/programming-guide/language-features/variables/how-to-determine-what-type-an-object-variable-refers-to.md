---
title: '方法 : オブジェクト変数で参照している型を確認する'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: b3778a170759f685db78e7dcde219138196f9eca
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344200"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="6c6ee-102">方法: オブジェクト変数で参照している型を確認する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c6ee-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>

<span data-ttu-id="6c6ee-103">オブジェクト変数には、他の場所に格納されているデータへのポインターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c6ee-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="6c6ee-104">データの種類は、実行時に変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c6ee-104">The type of that data can change during run time.</span></span> <span data-ttu-id="6c6ee-105">現時点では、<xref:System.Type.GetTypeCode%2A> メソッドを使用して現在のランタイム型を判断したり、 [TypeOf 演算子](../../../../visual-basic/language-reference/operators/typeof-operator.md)を使用して、現在の実行時の型が指定した型と互換性があるかどうかを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="6c6ee-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="6c6ee-106">オブジェクト変数で現在参照されている正確な型を確認するには</span><span class="sxs-lookup"><span data-stu-id="6c6ee-106">To determine the exact type an object variable currently refers to</span></span>

1. <span data-ttu-id="6c6ee-107">オブジェクト変数で、<xref:System.Object.GetType%2A> メソッドを呼び出して、<xref:System.Type?displayProperty=nameWithType> オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="6c6ee-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. <span data-ttu-id="6c6ee-108"><xref:System.Type?displayProperty=nameWithType> クラスで、共有メソッド <xref:System.Type.GetTypeCode%2A> を呼び出して、オブジェクトの型の <xref:System.TypeCode> 列挙値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6c6ee-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    <span data-ttu-id="6c6ee-109"><xref:System.TypeCode> 列挙値は、`Double`など、目的の列挙体のメンバーに対してテストできます。</span><span class="sxs-lookup"><span data-stu-id="6c6ee-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="6c6ee-110">オブジェクト変数の型が指定した型と互換性があるかどうかを判断するには</span><span class="sxs-lookup"><span data-stu-id="6c6ee-110">To determine whether an object variable's type is compatible with a specified type</span></span>

- <span data-ttu-id="6c6ee-111">`TypeOf` 演算子を[Is 演算子](../../../../visual-basic/language-reference/operators/is-operator.md)と組み合わせて使用し、`TypeOf`...`Is` 式を使用してオブジェクトをテストします。</span><span class="sxs-lookup"><span data-stu-id="6c6ee-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    <span data-ttu-id="6c6ee-112">`TypeOf`...`Is` 式は、オブジェクトの実行時の型が指定した型と互換性がある場合に `True` を返します。</span><span class="sxs-lookup"><span data-stu-id="6c6ee-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>

    <span data-ttu-id="6c6ee-113">互換性の基準は、指定された型がクラス、構造体、またはインターフェイスのいずれであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6c6ee-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="6c6ee-114">一般に、オブジェクトがと同じ型であるか、指定された型を継承するか、または実装する場合、型は互換性があります。</span><span class="sxs-lookup"><span data-stu-id="6c6ee-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="6c6ee-115">詳細については、「 [TypeOf 演算子](../../../../visual-basic/language-reference/operators/typeof-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c6ee-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="6c6ee-116">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="6c6ee-116">Compile the code</span></span>

<span data-ttu-id="6c6ee-117">指定された型を変数または式にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6c6ee-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="6c6ee-118">クラス、構造体、インターフェイスなど、定義された型の名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c6ee-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="6c6ee-119">これには、`Integer` や `String`などの組み込み型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6c6ee-119">This includes intrinsic types such as `Integer` and `String`.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c6ee-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c6ee-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="6c6ee-121">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="6c6ee-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="6c6ee-122">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="6c6ee-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="6c6ee-123">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="6c6ee-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
