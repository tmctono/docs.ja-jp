---
title: Out (ジェネリック修飾子)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
ms.openlocfilehash: 0460015b44971fa638dba47183690ffcc89ca55f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351422"
---
# <a name="out-generic-modifier-visual-basic"></a><span data-ttu-id="4fb19-102">Out (ジェネリック修飾子) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fb19-102">Out (Generic Modifier) (Visual Basic)</span></span>

<span data-ttu-id="4fb19-103">ジェネリック型パラメーターの場合、`Out` キーワードは、型が共変であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4fb19-103">For generic type parameters, the `Out` keyword specifies that the type is covariant.</span></span>

## <a name="remarks"></a><span data-ttu-id="4fb19-104">コメント</span><span class="sxs-lookup"><span data-stu-id="4fb19-104">Remarks</span></span>

<span data-ttu-id="4fb19-105">共変性は、ジェネリック パラメーターによって指定された型よりも強い派生型を使用できるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="4fb19-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="4fb19-106">これにより、バリアント インターフェイスを実装するクラスの暗黙の型変換とデリゲート型の暗黙の型変換が可能となります。</span><span class="sxs-lookup"><span data-stu-id="4fb19-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>

<span data-ttu-id="4fb19-107">詳細については、「[共変性と反変性](../../programming-guide/concepts/covariance-contravariance/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fb19-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="4fb19-108">ルール</span><span class="sxs-lookup"><span data-stu-id="4fb19-108">Rules</span></span>

<span data-ttu-id="4fb19-109">`Out` キーワードは、ジェネリック インターフェイスとデリゲートで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4fb19-109">You can use the `Out` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="4fb19-110">ジェネリック インターフェイスでは、次の条件を満たす場合に型パラメーターを共変として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="4fb19-110">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>

- <span data-ttu-id="4fb19-111">型パラメーターがインターフェイス メソッドの戻り値の型としてのみ使用され、メソッド引数の型として使用されない。</span><span class="sxs-lookup"><span data-stu-id="4fb19-111">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4fb19-112">この規則には例外が 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="4fb19-112">There is one exception to this rule.</span></span> <span data-ttu-id="4fb19-113">共変のインターフェイスで反変の汎用デリゲートをメソッド パラメーターとして使用する場合は、共変の型をこのデリゲートのジェネリック型パラメーターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="4fb19-113">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="4fb19-114">共変および反変の汎用デリゲートの詳細については、「[デリゲートの変性](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)」および「[Func および Action 汎用デリゲートでの変性の使用](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fb19-114">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

- <span data-ttu-id="4fb19-115">型パラメーターがインターフェイス メソッドのジェネリック制約として使用されない。</span><span class="sxs-lookup"><span data-stu-id="4fb19-115">The type parameter is not used as a generic constraint for the interface methods.</span></span>

<span data-ttu-id="4fb19-116">ジェネリックデリゲートでは、メソッドの戻り値の型としてのみ使用され、メソッドの引数には使用されない場合、型パラメーターを共変として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="4fb19-116">In a generic delegate, a type parameter can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>

<span data-ttu-id="4fb19-117">共変性および反変性は参照型ではサポートされますが、値の型ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="4fb19-117">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="4fb19-118">Visual Basic では、デリゲート型を指定しなくても、共変のインターフェイスでイベントを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="4fb19-118">In Visual Basic, you cannot declare events in covariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="4fb19-119">また、共変のインターフェイスは、入れ子になったクラス、列挙型、または構造体を持つことはできませんが、入れ子になったインターフェイスを持つことができます</span><span class="sxs-lookup"><span data-stu-id="4fb19-119">Also, covariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>

## <a name="behavior"></a><span data-ttu-id="4fb19-120">動作</span><span class="sxs-lookup"><span data-stu-id="4fb19-120">Behavior</span></span>

<span data-ttu-id="4fb19-121">共変の型パラメーターを持つインターフェイスを使用すると、そのインターフェイスのメソッドは、型パラメーターによって指定された型よりも強い派生型を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="4fb19-121">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="4fb19-122">たとえば、.NET Framework 4 の <xref:System.Collections.Generic.IEnumerable%601> では T 型が共変なので、特別な変換メソッドを使用しなくても `IEnumerable(Of String)` 型のオブジェクトを `IEnumerable(Of Object)` 型のオブジェクトに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4fb19-122">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerable(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>

<span data-ttu-id="4fb19-123">共変のデリゲートには、型は同じでありながらより強い派生ジェネリック型パラメーターを持つ別のデリゲートを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4fb19-123">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>

## <a name="example"></a><span data-ttu-id="4fb19-124">例</span><span class="sxs-lookup"><span data-stu-id="4fb19-124">Example</span></span>

<span data-ttu-id="4fb19-125">次の例では、共変のジェネリック インターフェイスを宣言、拡張、および実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4fb19-125">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="4fb19-126">また、共変のインターフェイスを実装するクラスの暗黙的な変換を使用する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="4fb19-126">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>

[!code-vb[vbVarianceKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#3)]

## <a name="example"></a><span data-ttu-id="4fb19-127">例</span><span class="sxs-lookup"><span data-stu-id="4fb19-127">Example</span></span>

<span data-ttu-id="4fb19-128">次の例では、共変の汎用デリゲートを宣言、インスタンス化、および呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4fb19-128">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="4fb19-129">また、デリゲート型に対して暗黙的な変換を使用する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="4fb19-129">It also shows how you can use implicit conversion for delegate types.</span></span>

[!code-vb[vbVarianceKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="4fb19-130">参照</span><span class="sxs-lookup"><span data-stu-id="4fb19-130">See also</span></span>

- [<span data-ttu-id="4fb19-131">ジェネリック インターフェイスの分散</span><span class="sxs-lookup"><span data-stu-id="4fb19-131">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="4fb19-132">In</span><span class="sxs-lookup"><span data-stu-id="4fb19-132">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
