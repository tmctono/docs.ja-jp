---
title: 構造体型 - C# リファレンス
ms.date: 03/26/2020
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- struct type [C#]
- structure type [C#]
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 6a2c97b93a8f6d1d62bd8a96865a4fe6587f55d3
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345139"
---
# <a name="structure-types-c-reference"></a><span data-ttu-id="446ba-102">構造体型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="446ba-102">Structure types (C# reference)</span></span>

<span data-ttu-id="446ba-103">"*構造体型*" (または "*構造体型*") とは、データおよび関連する機能をカプセル化できる[値の型](value-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="446ba-103">A *structure type* (or *struct type*) is a [value type](value-types.md) that can encapsulate data and related functionality.</span></span> <span data-ttu-id="446ba-104">構造体型を定義するには、`struct` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="446ba-104">You use the `struct` keyword to define a structure type:</span></span>

[!code-csharp[struct example](snippets/StructType.cs#StructExample)]

<span data-ttu-id="446ba-105">構造体型には、"*値のセマンティクス*" があります。</span><span class="sxs-lookup"><span data-stu-id="446ba-105">Structure types have *value semantics*.</span></span> <span data-ttu-id="446ba-106">つまり、構造体型の変数には、型のインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="446ba-106">That is, a variable of a structure type contains an instance of the type.</span></span> <span data-ttu-id="446ba-107">既定では、変数値が代入時にコピーされ、引数がメソッドに渡され、メソッドの結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="446ba-107">By default, variable values are copied on assignment, passing an argument to a method, and returning a method result.</span></span> <span data-ttu-id="446ba-108">構造体型の変数の場合は、型のインスタンスがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="446ba-108">In the case of a structure-type variable, an instance of the type is copied.</span></span> <span data-ttu-id="446ba-109">詳細については、[値の型](value-types.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="446ba-109">For more information, see [Value types](value-types.md).</span></span>

<span data-ttu-id="446ba-110">通常は、構造体型を使用して、ほとんどまたはまったく動作を提供しない小さなデータ中心型を設計します。</span><span class="sxs-lookup"><span data-stu-id="446ba-110">Typically, you use structure types to design small data-centric types that provide little or no behavior.</span></span> <span data-ttu-id="446ba-111">たとえば、.NET では、構造体型を使用して数値 ([整数](integral-numeric-types.md)と[実数](floating-point-numeric-types.md)の両方)、[ブール値](bool.md)、[Unicode 文字](char.md)、[時刻インスタンス](xref:System.DateTime)が表現されます。</span><span class="sxs-lookup"><span data-stu-id="446ba-111">For example, .NET uses structure types to represent a number (both [integer](integral-numeric-types.md) and [real](floating-point-numeric-types.md)), a [Boolean value](bool.md), a [Unicode character](char.md), a [time instance](xref:System.DateTime).</span></span> <span data-ttu-id="446ba-112">型の動作に重点を置いている場合は、[class](../keywords/class.md) を定義することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="446ba-112">If you're focused on the behavior of a type, consider defining a [class](../keywords/class.md).</span></span> <span data-ttu-id="446ba-113">クラス型には "*参照セマンティクス*" があります。</span><span class="sxs-lookup"><span data-stu-id="446ba-113">Class types have *reference semantics*.</span></span> <span data-ttu-id="446ba-114">つまり、クラス型の変数には、インスタンス自体ではなく、型のインスタンスへの参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="446ba-114">That is, a variable of a class type contains a reference to an instance of the type, not the instance itself.</span></span>

<span data-ttu-id="446ba-115">構造体型には値セマンティクスがあるため、"*変更不可*" の構造体型を定義することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="446ba-115">Because structure types have value semantics, we recommend you to define *immutable* structure types.</span></span>

## <a name="readonly-struct"></a><span data-ttu-id="446ba-116">`readonly` 構造体</span><span class="sxs-lookup"><span data-stu-id="446ba-116">`readonly` struct</span></span>

<span data-ttu-id="446ba-117">C# 7.2 以降では、構造体型が変更不可であることを宣言するには、`readonly` 修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="446ba-117">Beginning with C# 7.2, you use the `readonly` modifier to declare that a structure type is immutable:</span></span>

[!code-csharp[readonly struct](snippets/StructType.cs#ReadonlyStruct)]

<span data-ttu-id="446ba-118">`readonly` 構造体のすべてのデータ メンバーを、次のように読み取り専用にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="446ba-118">All data members of a `readonly` struct must be read-only as follows:</span></span>

- <span data-ttu-id="446ba-119">すべてのフィールド宣言には、[`readonly` 修飾子が必要です](../keywords/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="446ba-119">Any field declaration must have the [`readonly` modifier](../keywords/readonly.md)</span></span>
- <span data-ttu-id="446ba-120">自動的に実装されるプロパティも含めて、すべてのプロパティは、読み取り専用である必要があります</span><span class="sxs-lookup"><span data-stu-id="446ba-120">Any property, including auto-implemented ones, must be read-only</span></span>

<span data-ttu-id="446ba-121">それにより、`readonly` 構造体のどのメンバーも構造体の状態を変更しないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="446ba-121">That guarantees that no member of a `readonly` struct modifies the state of the struct.</span></span>

> [!NOTE]
> <span data-ttu-id="446ba-122">`readonly` 構造体でも、変更可能な参照型のデータ メンバーは、それ自身の状態を変更できます。</span><span class="sxs-lookup"><span data-stu-id="446ba-122">In a `readonly` struct, a data member of a mutable reference type still can mutate its own state.</span></span> <span data-ttu-id="446ba-123">たとえば、<xref:System.Collections.Generic.List%601> インスタンスを置き換えることはできませんが、新しい要素をそれに追加することはできます。</span><span class="sxs-lookup"><span data-stu-id="446ba-123">For example, you cannot replace a <xref:System.Collections.Generic.List%601> instance, but you can add new elements to it.</span></span>

## <a name="limitations-with-the-design-of-a-structure-type"></a><span data-ttu-id="446ba-124">構造体型の設計に関する制限事項</span><span class="sxs-lookup"><span data-stu-id="446ba-124">Limitations with the design of a structure type</span></span>

<span data-ttu-id="446ba-125">構造体型を設計する場合は、[class](../keywords/class.md) 型と同じ機能を使用できますが、次の例外があります。</span><span class="sxs-lookup"><span data-stu-id="446ba-125">When you design a structure type, you have the same capabilities as with a [class](../keywords/class.md) type, with the following exceptions:</span></span>

- <span data-ttu-id="446ba-126">パラメーターなしのコンストラクターを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="446ba-126">You cannot declare a parameterless constructor.</span></span> <span data-ttu-id="446ba-127">すべての構造体型には、型の[既定値](default-values.md)を生成する暗黙的なパラメーターなしのコンストラクターが既に備わっています。</span><span class="sxs-lookup"><span data-stu-id="446ba-127">Every structure type already provides an implicit parameterless constructor that produces the [default value](default-values.md) of the type.</span></span>

- <span data-ttu-id="446ba-128">インスタンス フィールドまたはプロパティを、それらの宣言で初期化することはできません。</span><span class="sxs-lookup"><span data-stu-id="446ba-128">You cannot initialize an instance field or property at its declaration.</span></span> <span data-ttu-id="446ba-129">ただし、[static](../keywords/static.md) または [const](../keywords/const.md) フィールド、あるいは静的プロパティについては、それらの宣言で初期化することができます。</span><span class="sxs-lookup"><span data-stu-id="446ba-129">However, you can initialize a [static](../keywords/static.md) or [const](../keywords/const.md) field or a static property at its declaration.</span></span>

- <span data-ttu-id="446ba-130">構造体型のコンストラクターでは、型のすべてのインスタンス フィールドを初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="446ba-130">A constructor of a structure type must initialize all instance fields of the type.</span></span>

- <span data-ttu-id="446ba-131">構造体型は、他のクラスまたは構造体型から継承することができないほか、クラスのベースとすることもできません。</span><span class="sxs-lookup"><span data-stu-id="446ba-131">A structure type cannot inherit from other class or structure type and it cannot be the base of a class.</span></span> <span data-ttu-id="446ba-132">ただし、構造体型では [interfaces](../keywords/interface.md) を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="446ba-132">However, a structure type can implement [interfaces](../keywords/interface.md).</span></span>

- <span data-ttu-id="446ba-133">構造体型内で[ファイナライザー](../../programming-guide/classes-and-structs/destructors.md)を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="446ba-133">You cannot declare a [finalizer](../../programming-guide/classes-and-structs/destructors.md) within a structure type.</span></span>

## <a name="instantiation-of-a-structure-type"></a><span data-ttu-id="446ba-134">構造体型のインスタンス化</span><span class="sxs-lookup"><span data-stu-id="446ba-134">Instantiation of a structure type</span></span>

<span data-ttu-id="446ba-135">C# では、宣言された変数を使用するには、事前にこれを初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="446ba-135">In C#, you must initialize a declared variable before it can be used.</span></span> <span data-ttu-id="446ba-136">構造体型の変数は `null` とすることができないため (それが [null 許容値型](nullable-value-types.md)の変数でない限り)、対応する型のインスタンスをインスタンス化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="446ba-136">Because a structure-type variable cannot be `null` (unless it's a variable of a [nullable value type](nullable-value-types.md)), you must instantiate an instance of the corresponding type.</span></span> <span data-ttu-id="446ba-137">それにはいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="446ba-137">There are several ways to do that.</span></span>

<span data-ttu-id="446ba-138">通常は、[`new`](../operators/new-operator.md) 演算子を使用して適切なコンストラクターを呼び出すことによって、構造体型をインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="446ba-138">Typically, you instantiate a structure type by calling an appropriate constructor with the [`new`](../operators/new-operator.md) operator.</span></span> <span data-ttu-id="446ba-139">すべての構造体型に、少なくとも 1 つのコンストラクターがあります。</span><span class="sxs-lookup"><span data-stu-id="446ba-139">Every structure type has at least one constructor.</span></span> <span data-ttu-id="446ba-140">それは暗黙的なパラメーターなしのコンストラクターであり、型の[既定値](default-values.md)を生成するものです。</span><span class="sxs-lookup"><span data-stu-id="446ba-140">That's an implicit parameterless constructor, which produces the [default value](default-values.md) of the type.</span></span> <span data-ttu-id="446ba-141">また、[既定の値式](../operators/default.md)を使用して、型の既定値を生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="446ba-141">You can also use a [default value expression](../operators/default.md) to produce the default value of a type.</span></span>

<span data-ttu-id="446ba-142">構造体型のすべてのインスタンス フィールドにアクセスできる場合は、それを `new` 演算子なしでインスタンス化することもできます。</span><span class="sxs-lookup"><span data-stu-id="446ba-142">If all instance fields of a structure type are accessible, you can also instantiate it without the `new` operator.</span></span> <span data-ttu-id="446ba-143">その場合は、インスタンスを初めて使用する前に、すべてのインスタンス フィールドを初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="446ba-143">In that case you must initialize all instance fields before the first use of the instance.</span></span> <span data-ttu-id="446ba-144">その方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="446ba-144">The following example shows how to do that:</span></span>

[!code-csharp[without new](snippets/StructType.cs#WithoutNew)]

<span data-ttu-id="446ba-145">[組み込みの値型](value-types.md#built-in-value-types)の場合は、対応するリテラルを使用して型の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="446ba-145">In the case of the [built-in value types](value-types.md#built-in-value-types), use the corresponding literals to specify a value of the type.</span></span>

## <a name="passing-structure-type-variables-by-reference"></a><span data-ttu-id="446ba-146">構造体型の変数を参照渡しする</span><span class="sxs-lookup"><span data-stu-id="446ba-146">Passing structure-type variables by reference</span></span>

<span data-ttu-id="446ba-147">構造体型の変数を引数としてメソッドに渡す場合、またはメソッドから構造体型の値を返す場合は、構造体型のインスタンス全体がコピーされます。</span><span class="sxs-lookup"><span data-stu-id="446ba-147">When you pass a structure-type variable to a method as an argument or return a structure-type value from a method, the whole instance of a structure type is copied.</span></span> <span data-ttu-id="446ba-148">これは、大規模な構造体型を必要とするハイパフォーマンスのシナリオの場合、ご利用のコードのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="446ba-148">That can affect the performance of your code in high-performance scenarios that involve large structure types.</span></span> <span data-ttu-id="446ba-149">値のコピーを回避するには、構造体型の変数を参照渡しします。</span><span class="sxs-lookup"><span data-stu-id="446ba-149">You can avoid value copying by passing a structure-type variable by reference.</span></span> <span data-ttu-id="446ba-150">引数を参照渡しする必要があることを示すには、[`ref`](../keywords/ref.md#passing-an-argument-by-reference)、[`out`](../keywords/out-parameter-modifier.md)、または [`in`](../keywords/in-parameter-modifier.md) のメソッド パラメーター修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="446ba-150">Use the [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md), or [`in`](../keywords/in-parameter-modifier.md) method parameter modifiers to indicate that an argument must be passed by reference.</span></span> <span data-ttu-id="446ba-151">メソッドの結果を参照渡しによって返すには、[ref 戻り値](../../programming-guide/classes-and-structs/ref-returns.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="446ba-151">Use [ref returns](../../programming-guide/classes-and-structs/ref-returns.md) to return a method result by reference.</span></span> <span data-ttu-id="446ba-152">詳細については、「[安全で効率的な C# コードを記述する](../../write-safe-efficient-code.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="446ba-152">For more information, see [Write safe and efficient C# code](../../write-safe-efficient-code.md).</span></span>

## <a name="conversions"></a><span data-ttu-id="446ba-153">変換</span><span class="sxs-lookup"><span data-stu-id="446ba-153">Conversions</span></span>

<span data-ttu-id="446ba-154">どの構造体型にも、<xref:System.ValueType?displayProperty=nameWithType> 型と <xref:System.Object?displayProperty=nameWithType> 型の間に[ボックス化およびボックス化解除](../../programming-guide/types/boxing-and-unboxing.md)の変換が存在します。</span><span class="sxs-lookup"><span data-stu-id="446ba-154">For any structure type, there exist [boxing and unboxing](../../programming-guide/types/boxing-and-unboxing.md) conversions to and from the <xref:System.ValueType?displayProperty=nameWithType> and <xref:System.Object?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="446ba-155">また、構造体型と、これによって実装されるインターフェイスとの間にも、ボックス化とボックス化解除の変換が存在します。</span><span class="sxs-lookup"><span data-stu-id="446ba-155">There exist also boxing and unboxing conversions between a structure type and any interface that it implements.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="446ba-156">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="446ba-156">C# language specification</span></span>

<span data-ttu-id="446ba-157">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の「[構造体](~/_csharplang/spec/structs.md)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="446ba-157">For more information, see the [Structs](~/_csharplang/spec/structs.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="446ba-158">`readonly` 構造体について詳しくは、[機能提案メモ](~/_csharplang/proposals/csharp-7.2/readonly-ref.md#readonly-structs)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="446ba-158">For more information about `readonly` structs, see the [feature proposal note](~/_csharplang/proposals/csharp-7.2/readonly-ref.md#readonly-structs).</span></span>

## <a name="see-also"></a><span data-ttu-id="446ba-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="446ba-159">See also</span></span>

- [<span data-ttu-id="446ba-160">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="446ba-160">C# reference</span></span>](../index.md)
- [<span data-ttu-id="446ba-161">デザインのガイドライン - クラスまたは構造体の選択</span><span class="sxs-lookup"><span data-stu-id="446ba-161">Design guidelines - Choosing between class and struct</span></span>](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [<span data-ttu-id="446ba-162">デザインのガイドライン - 構造体のデザイン</span><span class="sxs-lookup"><span data-stu-id="446ba-162">Design guidelines - Struct design</span></span>](../../../standard/design-guidelines/struct.md)
- [<span data-ttu-id="446ba-163">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="446ba-163">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)
