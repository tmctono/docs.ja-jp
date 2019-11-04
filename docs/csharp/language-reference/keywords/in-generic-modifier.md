---
title: in (ジェネリック修飾子) - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.openlocfilehash: 0806169b9b1c3521dcf89f5ea0fa5aec188030c2
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422774"
---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="d99b3-102">in (ジェネリック修飾子) (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d99b3-102">in (Generic Modifier) (C# Reference)</span></span>

<span data-ttu-id="d99b3-103">ジェネリック型パラメーターの `in` キーワードは、型パラメーターが反変であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d99b3-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="d99b3-104">`in` キーワードは、ジェネリック インターフェイスとデリゲートで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d99b3-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="d99b3-105">反変性は、ジェネリック パラメーターによって指定された型よりも弱い派生型を使用できるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="d99b3-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="d99b3-106">これにより、反変性のインターフェイスを実装するクラスの暗黙の型変換とデリゲート型の暗黙の型変換が可能となります。</span><span class="sxs-lookup"><span data-stu-id="d99b3-106">This allows for implicit conversion of classes that implement contravariant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="d99b3-107">ジェネリック型パラメーターの共変性および反変性は参照型ではサポートされますが、値型ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d99b3-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="d99b3-108">型をジェネリック インターフェイスまたはデリゲートで反変として宣言できるのは、メソッドの戻り値の型ではなく、メソッドのパラメーターの型を定義する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="d99b3-108">A type can be declared contravariant in a generic interface or delegate only if it defines the type of a method's parameters and not of a method's return type.</span></span> <span data-ttu-id="d99b3-109">`In`、`ref`、`out` パラメーターはインバリアントである必要があります。これは、これらのパラメーターが共変でも反変でもないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d99b3-109">`In`, `ref`, and `out` parameters must be invariant, meaning they are neither covariant or contravariant.</span></span>

<span data-ttu-id="d99b3-110">反変の型パラメーターを持つインターフェイスを使用すると、そのインターフェイスのメソッドは、インターフェイス型パラメーターによって指定された型よりも弱い派生型の引数を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="d99b3-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="d99b3-111">たとえば、<xref:System.Collections.Generic.IComparer%601> インターフェイスでは、T 型が反変なので、`Employee` が `Person` を継承する場合、特別な変換メソッドを使用しなくても `IComparer<Person>` 型のオブジェクトを `IComparer<Employee>` 型のオブジェクトに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d99b3-111">For example, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer<Person>` type to an object of the `IComparer<Employee>` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>

<span data-ttu-id="d99b3-112">反変のデリゲートには、型は同じでありながらより弱い派生ジェネリック型パラメーターを持つ別のデリゲートを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d99b3-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>

<span data-ttu-id="d99b3-113">詳細については、「[共変性と反変性](../../programming-guide/concepts/covariance-contravariance/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d99b3-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="contravariant-generic-interface"></a><span data-ttu-id="d99b3-114">反変のジェネリック インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d99b3-114">Contravariant generic interface</span></span>

<span data-ttu-id="d99b3-115">次の例では、反変のジェネリック インターフェイスを宣言、拡張、および実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d99b3-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="d99b3-116">また、このインターフェイスを実装するクラスの暗黙的な変換を使用する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="d99b3-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>

[!code-csharp[csVarianceKeywords#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#1)]

## <a name="contravariant-generic-delegate"></a><span data-ttu-id="d99b3-117">反変の汎用デリゲート</span><span class="sxs-lookup"><span data-stu-id="d99b3-117">Contravariant generic delegate</span></span>

<span data-ttu-id="d99b3-118">次の例では、反変の汎用デリゲートを宣言、インスタンス化、および呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d99b3-118">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="d99b3-119">また、デリゲート型を暗黙的に変換する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="d99b3-119">It also shows how you can implicitly convert a delegate type.</span></span>

[!code-csharp[csVarianceKeywords#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="d99b3-120">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d99b3-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d99b3-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="d99b3-121">See also</span></span>

- [<span data-ttu-id="d99b3-122">out</span><span class="sxs-lookup"><span data-stu-id="d99b3-122">out</span></span>](out-generic-modifier.md)
- [<span data-ttu-id="d99b3-123">共変性と反変性</span><span class="sxs-lookup"><span data-stu-id="d99b3-123">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="d99b3-124">修飾子</span><span class="sxs-lookup"><span data-stu-id="d99b3-124">Modifiers</span></span>](index.md)
