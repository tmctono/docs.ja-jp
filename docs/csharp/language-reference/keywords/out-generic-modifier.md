---
description: out キーワード (ジェネリック修飾子) - C# リファレンス
title: out キーワード (ジェネリック修飾子) - C# リファレンス
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
ms.openlocfilehash: 84f3647309c0772f6ae61d3614f8649fe277f153
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142337"
---
# <a name="out-generic-modifier-c-reference"></a><span data-ttu-id="2e5f0-103">out (ジェネリック修飾子) (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="2e5f0-103">out (generic modifier) (C# Reference)</span></span>

<span data-ttu-id="2e5f0-104">ジェネリック型パラメーターの `out` キーワードは、型パラメーターが共変であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-104">For generic type parameters, the `out` keyword specifies that the type parameter is covariant.</span></span> <span data-ttu-id="2e5f0-105">`out` キーワードは、ジェネリック インターフェイスとデリゲートで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-105">You can use the `out` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="2e5f0-106">共変性は、ジェネリック パラメーターによって指定された型よりも強い派生型を使用できるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-106">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="2e5f0-107">これにより、共変性のインターフェイスを実装するクラスの暗黙の型変換とデリゲート型の暗黙の型変換が可能となります。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-107">This allows for implicit conversion of classes that implement covariant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="2e5f0-108">共変性および反変性は参照型ではサポートされますが、値の型ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-108">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="2e5f0-109">共変の型パラメーターを持つインターフェイスを使用すると、そのインターフェイスのメソッドは、型パラメーターによって指定された型よりも強い派生型を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-109">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="2e5f0-110">たとえば、.NET Framework 4 の <xref:System.Collections.Generic.IEnumerable%601> では T 型が共変なので、特別な変換メソッドを使用しなくても `IEnumerable(Of String)` 型のオブジェクトを `IEnumerable(Of Object)` 型のオブジェクトに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-110">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerable(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>

<span data-ttu-id="2e5f0-111">共変のデリゲートには、型は同じでありながらより強い派生ジェネリック型パラメーターを持つ別のデリゲートを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-111">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>

<span data-ttu-id="2e5f0-112">詳細については、「[共変性と反変性](../../programming-guide/concepts/covariance-contravariance/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-112">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="example---covariant-generic-interface"></a><span data-ttu-id="2e5f0-113">例 - 共変のジェネリック インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2e5f0-113">Example - covariant generic interface</span></span>

<span data-ttu-id="2e5f0-114">次の例では、共変のジェネリック インターフェイスを宣言、拡張、および実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-114">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="2e5f0-115">また、共変のインターフェイスを実装するクラスの暗黙的な変換を使用する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-115">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>

[!code-csharp[csVarianceKeywords#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#3)]

<span data-ttu-id="2e5f0-116">ジェネリック インターフェイスでは、次の条件を満たす場合に型パラメーターを共変として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-116">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>

- <span data-ttu-id="2e5f0-117">型パラメーターがインターフェイス メソッドの戻り値の型としてのみ使用され、メソッド引数の型として使用されない。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-117">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e5f0-118">この規則には例外が 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-118">There is one exception to this rule.</span></span> <span data-ttu-id="2e5f0-119">共変のインターフェイスで反変の汎用デリゲートをメソッド パラメーターとして使用する場合は、共変の型をこのデリゲートのジェネリック型パラメーターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-119">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="2e5f0-120">共変および反変の汎用デリゲートの詳細については、「[デリゲートの変性](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)」および「[Func および Action 汎用デリゲートでの変性の使用](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-120">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

- <span data-ttu-id="2e5f0-121">型パラメーターがインターフェイス メソッドのジェネリック制約として使用されない。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-121">The type parameter is not used as a generic constraint for the interface methods.</span></span>

## <a name="example---covariant-generic-delegate"></a><span data-ttu-id="2e5f0-122">例 - 共変の汎用デリゲート</span><span class="sxs-lookup"><span data-stu-id="2e5f0-122">Example - covariant generic delegate</span></span>

<span data-ttu-id="2e5f0-123">次の例では、共変の汎用デリゲートを宣言、インスタンス化、および呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-123">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="2e5f0-124">また、デリゲート型を暗黙的に変換する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-124">It also shows how to implicitly convert delegate types.</span></span>

[!code-csharp[csVarianceKeywords#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#4)]

<span data-ttu-id="2e5f0-125">汎用デリゲートでは、メソッドの戻り値の型としてのみ使用され、メソッド引数には使用されない型を共変として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="2e5f0-125">In a generic delegate, a type can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2e5f0-126">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="2e5f0-126">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2e5f0-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e5f0-127">See also</span></span>

- [<span data-ttu-id="2e5f0-128">ジェネリック インターフェイスの変性</span><span class="sxs-lookup"><span data-stu-id="2e5f0-128">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="2e5f0-129">in</span><span class="sxs-lookup"><span data-stu-id="2e5f0-129">in</span></span>](in-generic-modifier.md)
- [<span data-ttu-id="2e5f0-130">修飾子</span><span class="sxs-lookup"><span data-stu-id="2e5f0-130">Modifiers</span></span>](index.md)
