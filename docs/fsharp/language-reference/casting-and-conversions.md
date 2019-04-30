---
title: キャストと変換
description: について説明しますが、どのようにF#さまざまなプリミティブ型間の算術変換の変換演算子を提供するプログラミング言語。
ms.date: 05/16/2016
ms.openlocfilehash: 2a12d48106a267edfc67c9e7b3d3a7bd41d8261c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966617"
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="b2d24-103">キャストと変換 (F#)</span><span class="sxs-lookup"><span data-stu-id="b2d24-103">Casting and Conversions (F#)</span></span>

<span data-ttu-id="b2d24-104">このトピックでは、F# の型変換のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-104">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="b2d24-105">数値型</span><span class="sxs-lookup"><span data-stu-id="b2d24-105">Arithmetic Types</span></span>

<span data-ttu-id="b2d24-106">F#整数と浮動小数点型の間のように、さまざまなプリミティブ型の間の算術変換の変換演算子を提供します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-106">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="b2d24-107">整数と文字の変換演算子がチェックと unchecked フォームです。浮動小数点の演算子と`enum`変換演算子がありません。</span><span class="sxs-lookup"><span data-stu-id="b2d24-107">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="b2d24-108">チェックを行わないフォームが定義されている`Microsoft.FSharp.Core.Operators`でチェックされているフォームが定義されていると`Microsoft.FSharp.Core.Operators.Checked`します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-108">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="b2d24-109">チェックされているフォームでは、オーバーフローをチェックし、結果の値が対象の型の制限を超えた場合、ランタイム例外を生成します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-109">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="b2d24-110">これらの各演算子は、変換先の型の名前と同じ名前があります。</span><span class="sxs-lookup"><span data-stu-id="b2d24-110">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="b2d24-111">これで、型が明示的に注釈付け、次のコードなどで`byte`で 2 つの異なる意味が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2d24-111">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="b2d24-112">最初に見つかったは型であり、2 つ目は変換演算子。</span><span class="sxs-lookup"><span data-stu-id="b2d24-112">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="b2d24-113">次の表では、F# で定義された変換演算子を示します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-113">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="b2d24-114">演算子</span><span class="sxs-lookup"><span data-stu-id="b2d24-114">Operator</span></span>|<span data-ttu-id="b2d24-115">説明</span><span class="sxs-lookup"><span data-stu-id="b2d24-115">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="b2d24-116">バイトを 8 ビット符号なしの型に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-116">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="b2d24-117">符号付きバイトに変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-117">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="b2d24-118">16 ビット符号付き整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-118">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="b2d24-119">16 ビット符号なし整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-119">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="b2d24-120">32 ビット符号付き整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-120">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="b2d24-121">32 ビット符号なし整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-121">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="b2d24-122">64 ビット符号付き整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-122">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="b2d24-123">64 ビット符号なし整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-123">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="b2d24-124">ネイティブ整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-124">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="b2d24-125">符号なしネイティブ整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-125">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="b2d24-126">64 ビット IEEE 倍精度浮動小数点数に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-126">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="b2d24-127">32 ビット IEEE 単精度浮動小数点数に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-127">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="b2d24-128">変換`System.Decimal`します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-128">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="b2d24-129">変換`System.Char`、Unicode 文字。</span><span class="sxs-lookup"><span data-stu-id="b2d24-129">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="b2d24-130">列挙型に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-130">Convert to an enumerated type.</span></span>|

<span data-ttu-id="b2d24-131">実装する型をこれらの演算子を使用する組み込みのプリミティブ型に加えて`op_Explicit`または`op_Implicit`適切なシグネチャを持つメソッド。</span><span class="sxs-lookup"><span data-stu-id="b2d24-131">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="b2d24-132">たとえば、`int`変換演算子は、静的メソッドを提供する任意の型と連携`op_Explicit`を型をパラメーターとして受け取り、返します`int`します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-132">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="b2d24-133">戻り値の型でメソッドをオーバー ロードできません、一般的な規則に特殊な例外としてこれを行う`op_Explicit`と`op_Implicit`します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-133">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="b2d24-134">列挙型</span><span class="sxs-lookup"><span data-stu-id="b2d24-134">Enumerated Types</span></span>

<span data-ttu-id="b2d24-135">`enum`演算子は、汎用の演算子の型を表す 1 つの型パラメーターを受け取る、`enum`に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-135">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="b2d24-136">列挙型に変換するときの入力の種類を決定しようと推論、`enum`に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-136">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="b2d24-137">次の例では、変数`col1`明示的に注釈がありませんが、それ以降の等値テストから型を推論します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-137">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="b2d24-138">そのため、コンパイラに変換することを推測することができます、`Color`列挙体。</span><span class="sxs-lookup"><span data-stu-id="b2d24-138">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="b2d24-139">型の注釈を指定する代わりと同様`col2`次の例です。</span><span class="sxs-lookup"><span data-stu-id="b2d24-139">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

<span data-ttu-id="b2d24-140">次のコードのように、型パラメーターとして明示的にターゲットの列挙型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b2d24-140">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="b2d24-141">列挙体の基になる型が変換される型と互換性のある場合にのみ、列挙体で作業をキャストすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b2d24-141">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="b2d24-142">次のコードで、変換は失敗の間で不一致が原因でコンパイルする`int32`と`uint32`します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-142">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="b2d24-143">詳細については、次を参照してください。[列挙](enumerations.md)します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-143">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="b2d24-144">オブジェクト型のキャスト</span><span class="sxs-lookup"><span data-stu-id="b2d24-144">Casting Object Types</span></span>

<span data-ttu-id="b2d24-145">オブジェクト階層内の型の間の変換は、オブジェクト指向プログラミングの基盤です。</span><span class="sxs-lookup"><span data-stu-id="b2d24-145">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="b2d24-146">変換の 2 つの基本的な種類があります。 (キャスト) をキャストすると、(ダウン キャスト)。</span><span class="sxs-lookup"><span data-stu-id="b2d24-146">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="b2d24-147">階層へのキャストは、ベース オブジェクトの参照への参照を派生オブジェクトからのキャストを意味します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-147">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="b2d24-148">そのようなキャスト基底クラスが派生クラスの継承階層である限りを操作することが保証されます。</span><span class="sxs-lookup"><span data-stu-id="b2d24-148">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="b2d24-149">派生オブジェクトの参照への参照を基本オブジェクトの階層の下位へのキャストが成功すると、オブジェクトが実際には (派生)、適切な変換先の型または変換先の型から派生した型のインスタンスが場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="b2d24-149">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="b2d24-150">F#これらの種類の変換の演算子を提供します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-150">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="b2d24-151">`:>`演算子は、階層のキャスト、`:?>`演算子が、階層の下位にキャストします。</span><span class="sxs-lookup"><span data-stu-id="b2d24-151">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="b2d24-152">キャスト</span><span class="sxs-lookup"><span data-stu-id="b2d24-152">Upcasting</span></span>

<span data-ttu-id="b2d24-153">多くのオブジェクト指向言語でキャストは暗黙の型です。F# では、規則が若干異なります。</span><span class="sxs-lookup"><span data-stu-id="b2d24-153">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="b2d24-154">オブジェクトの種類のメソッドに引数を渡すときに、キャストが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b2d24-154">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="b2d24-155">ただし、モジュール内の let バインドされた関数、キャスト自動ではありません、パラメーターの型は柔軟な型として宣言されていない場合。</span><span class="sxs-lookup"><span data-stu-id="b2d24-155">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="b2d24-156">詳細については、次を参照してください。[フレキシブル型](flexible-Types.md)します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-156">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="b2d24-157">`:>`演算子はキャスト、つまり、コンパイル時のキャストの成功が決定される静的なを実行します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-157">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="b2d24-158">キャストを使用する場合、 `:>` 、正常にコンパイルし、有効なキャストは、実行時にエラーが発生する可能性がないです。</span><span class="sxs-lookup"><span data-stu-id="b2d24-158">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="b2d24-159">使用することも、`upcast`オペレーターがこのような変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-159">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="b2d24-160">次の式は、階層の上位変換を指定します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-160">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="b2d24-161">Upcast 演算子を使用すると、コンパイラは、コンテキストから変換する型を推論しようとします。</span><span class="sxs-lookup"><span data-stu-id="b2d24-161">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="b2d24-162">コンパイラでターゲットの種類を決定することがない場合、コンパイラはエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-162">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="b2d24-163">ダウン キャスト</span><span class="sxs-lookup"><span data-stu-id="b2d24-163">Downcasting</span></span>

<span data-ttu-id="b2d24-164">`:?>`演算子はキャスト、つまり、実行時のキャストの成功が決定される動的なを実行します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-164">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="b2d24-165">使用するキャスト、`:?>`演算子は、コンパイル時にチェックされませんが、実行時にしようとしましたが、指定した型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="b2d24-165">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="b2d24-166">オブジェクトは、対象の型と互換性が、キャストが成功します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-166">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="b2d24-167">オブジェクトが対象の型と互換性がない場合、ランタイムが発生します、`InvalidCastException`します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-167">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="b2d24-168">使用することも、`downcast`動的な型変換を実行する演算子。</span><span class="sxs-lookup"><span data-stu-id="b2d24-168">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="b2d24-169">次の式は、階層内の下位プログラム コンテキストから推論される型への変換を指定します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-169">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="b2d24-170">場合と同様、`upcast`演算子、コンパイラは、コンテキストから特定のターゲット型を推論されない場合、エラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-170">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="b2d24-171">次のコードの使用を示しています、`:>`と`:?>`演算子。</span><span class="sxs-lookup"><span data-stu-id="b2d24-171">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="b2d24-172">コードを示していますが、`:?>`わかっている場合、変換が成功することをスローするため、演算子が使用される最適`InvalidCastException`変換が失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="b2d24-172">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="b2d24-173">変換が成功するを使用する型テストを把握していない場合、`match`例外を生成するオーバーヘッドを回避するので、式が向上します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-173">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="b2d24-174">ため、ジェネリック演算子`downcast`と`upcast`上記のコードで、引数と戻り値の型を決定する型の推定に依存して、置き換えることができます</span><span class="sxs-lookup"><span data-stu-id="b2d24-174">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="b2d24-175">代入</span><span class="sxs-lookup"><span data-stu-id="b2d24-175">with</span></span>

```fsharp
let base1 = upcast d1
```

<span data-ttu-id="b2d24-176">引数の型と戻り値の型が、上記のコードで`Derived1`と`Base1`、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="b2d24-176">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="b2d24-177">型のテストの詳細については、次を参照してください。[一致式](match-Expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="b2d24-177">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b2d24-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2d24-178">See also</span></span>

- [<span data-ttu-id="b2d24-179">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="b2d24-179">F# Language Reference</span></span>](index.md)
