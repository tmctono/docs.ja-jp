---
title: キャストと変換
description: さまざまなプリミティブF#型間の算術変換のための変換演算子をプログラミング言語がどのように提供するかについて説明します。
ms.date: 02/20/2020
ms.openlocfilehash: 5f9727d14a7ae070e0f0f71fa0a0abe04f662071
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543587"
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="163c4-103">キャストと変換 (F#)</span><span class="sxs-lookup"><span data-stu-id="163c4-103">Casting and Conversions (F#)</span></span>

<span data-ttu-id="163c4-104">このトピックでは、でF#の型変換のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="163c4-104">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="163c4-105">算術型</span><span class="sxs-lookup"><span data-stu-id="163c4-105">Arithmetic Types</span></span>

<span data-ttu-id="163c4-106">F#整数型と浮動小数点型の間など、さまざまなプリミティブ型間の算術変換のための変換演算子を提供します。</span><span class="sxs-lookup"><span data-stu-id="163c4-106">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="163c4-107">整数および文字の変換演算子は、チェックされたフォームと unchecked 形式を持っています。浮動小数点演算子と `enum` 変換演算子にはありません。</span><span class="sxs-lookup"><span data-stu-id="163c4-107">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="163c4-108">オフになっているフォームは `Microsoft.FSharp.Core.Operators` で定義され、チェックされたフォームは `Microsoft.FSharp.Core.Operators.Checked`で定義されます。</span><span class="sxs-lookup"><span data-stu-id="163c4-108">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="163c4-109">結果の値が対象の型の制限を超えた場合に、チェックされたフォームがオーバーフローをチェックし、ランタイム例外を生成します。</span><span class="sxs-lookup"><span data-stu-id="163c4-109">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="163c4-110">これらの各演算子には、変換先の型の名前と同じ名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="163c4-110">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="163c4-111">たとえば、次のコードでは、型に明示的に注釈が付けられているため、`byte` は2つの異なる意味で表示されます。</span><span class="sxs-lookup"><span data-stu-id="163c4-111">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="163c4-112">最初の出現は型で、2番目は変換演算子です。</span><span class="sxs-lookup"><span data-stu-id="163c4-112">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="163c4-113">次の表に、でF#定義されている変換演算子を示します。</span><span class="sxs-lookup"><span data-stu-id="163c4-113">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="163c4-114">演算子</span><span class="sxs-lookup"><span data-stu-id="163c4-114">Operator</span></span>|<span data-ttu-id="163c4-115">説明</span><span class="sxs-lookup"><span data-stu-id="163c4-115">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="163c4-116">8ビットの符号なしの型である byte に変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-116">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="163c4-117">符号付きバイトに変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-117">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="163c4-118">16ビット符号付き整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-118">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="163c4-119">16ビット符号なし整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-119">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="163c4-120">32ビット符号付き整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-120">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="163c4-121">32ビット符号なし整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-121">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="163c4-122">64ビット符号付き整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-122">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="163c4-123">64ビット符号なし整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-123">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="163c4-124">ネイティブの整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-124">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="163c4-125">符号なしのネイティブ整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-125">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="163c4-126">64ビットの倍精度 IEEE 浮動小数点数に変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-126">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="163c4-127">32ビットの単精度 IEEE 浮動小数点数に変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-127">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="163c4-128">`System.Decimal`に変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-128">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="163c4-129">Unicode 文字 `System.Char`に変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-129">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="163c4-130">列挙型に変換します。</span><span class="sxs-lookup"><span data-stu-id="163c4-130">Convert to an enumerated type.</span></span>|

<span data-ttu-id="163c4-131">これらの演算子は、組み込みのプリミティブ型に加えて、適切なシグネチャを持つ `op_Explicit` または `op_Implicit` メソッドを実装する型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="163c4-131">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="163c4-132">たとえば、`int` 変換演算子は、型をパラメーターとして受け取り、`int`を返す静的メソッド `op_Explicit` を提供する任意の型で動作します。</span><span class="sxs-lookup"><span data-stu-id="163c4-132">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="163c4-133">メソッドが戻り値の型によってオーバーロードできないという一般的な規則に対する特別な例外として、`op_Explicit` と `op_Implicit`に対してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="163c4-133">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="163c4-134">列挙型</span><span class="sxs-lookup"><span data-stu-id="163c4-134">Enumerated Types</span></span>

<span data-ttu-id="163c4-135">`enum` 演算子は、変換先の `enum` の型を表す1つの型パラメーターを受け取る汎用演算子です。</span><span class="sxs-lookup"><span data-stu-id="163c4-135">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="163c4-136">列挙型に変換すると、型推論は、変換先の `enum` の型を決定しようとします。</span><span class="sxs-lookup"><span data-stu-id="163c4-136">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="163c4-137">次の例では、変数 `col1` に明示的に注釈が付けられていませんが、その型は後の等値テストから推論されます。</span><span class="sxs-lookup"><span data-stu-id="163c4-137">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="163c4-138">したがって、コンパイラは、`Color` 列挙型に変換していることを推測できます。</span><span class="sxs-lookup"><span data-stu-id="163c4-138">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="163c4-139">または、次の例の `col2` のように、型の注釈を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="163c4-139">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

<span data-ttu-id="163c4-140">次のコードのように、ターゲットの列挙型を明示的に型パラメーターとして指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="163c4-140">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="163c4-141">列挙キャストは、列挙型の基になる型が変換される型と互換性がある場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="163c4-141">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="163c4-142">次のコードでは、`int32` と `uint32`が一致しないため、変換に失敗します。</span><span class="sxs-lookup"><span data-stu-id="163c4-142">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="163c4-143">詳細については、「[列挙型](enumerations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="163c4-143">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="163c4-144">キャスト (オブジェクト型を)</span><span class="sxs-lookup"><span data-stu-id="163c4-144">Casting Object Types</span></span>

<span data-ttu-id="163c4-145">オブジェクト階層内の型間の変換は、オブジェクト指向プログラミングの基本となります。</span><span class="sxs-lookup"><span data-stu-id="163c4-145">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="163c4-146">変換には、キャスト (キャスト) とキャストダウン (ダウンキャスト) の2つの基本的な種類があります。</span><span class="sxs-lookup"><span data-stu-id="163c4-146">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="163c4-147">階層をキャストすることは、派生オブジェクト参照からベースオブジェクト参照へのキャストを意味します。</span><span class="sxs-lookup"><span data-stu-id="163c4-147">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="163c4-148">このようなキャストは、基底クラスが派生クラスの継承階層内にある限り、確実に動作します。</span><span class="sxs-lookup"><span data-stu-id="163c4-148">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="163c4-149">基底オブジェクト参照から派生オブジェクト参照への階層のキャストは、オブジェクトが実際には正しい宛先 (派生) 型のインスタンスであるか、または変換先の型から派生した型である場合にのみ成功します。</span><span class="sxs-lookup"><span data-stu-id="163c4-149">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="163c4-150">F#は、これらの種類の変換のための演算子を提供します。</span><span class="sxs-lookup"><span data-stu-id="163c4-150">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="163c4-151">`:>` 演算子は階層をキャストし、`:?>` 演算子は階層を下位にキャストします。</span><span class="sxs-lookup"><span data-stu-id="163c4-151">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="163c4-152">キャスト</span><span class="sxs-lookup"><span data-stu-id="163c4-152">Upcasting</span></span>

<span data-ttu-id="163c4-153">多くのオブジェクト指向言語では、キャストは暗黙的です。でF#は、ルールが若干異なります。</span><span class="sxs-lookup"><span data-stu-id="163c4-153">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="163c4-154">キャストは、オブジェクト型のメソッドに引数を渡すときに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="163c4-154">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="163c4-155">ただし、モジュール内の let バインド関数の場合、パラメーターの型が柔軟な型として宣言されていない限り、キャストは自動ではありません。</span><span class="sxs-lookup"><span data-stu-id="163c4-155">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="163c4-156">詳細については、「[柔軟な型](flexible-Types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="163c4-156">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="163c4-157">`:>` 演算子は静的なキャストを実行します。これは、キャストの成功がコンパイル時に決定されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="163c4-157">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="163c4-158">`:>` を使用するキャストが正常にコンパイルされた場合、それは有効なキャストであり、実行時に失敗する可能性はありません。</span><span class="sxs-lookup"><span data-stu-id="163c4-158">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="163c4-159">また、`upcast` 演算子を使用して、このような変換を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="163c4-159">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="163c4-160">次の式では、階層の上位変換が指定されています。</span><span class="sxs-lookup"><span data-stu-id="163c4-160">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="163c4-161">アップキャスト演算子を使用すると、コンパイラはコンテキストから変換先の型を推論しようとします。</span><span class="sxs-lookup"><span data-stu-id="163c4-161">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="163c4-162">コンパイラがターゲットの型を判断できない場合、コンパイラはエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="163c4-162">If the compiler is unable to determine the target type, the compiler reports an error.</span></span> <span data-ttu-id="163c4-163">型の注釈が必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="163c4-163">A type annotation may be required.</span></span>

### <a name="downcasting"></a><span data-ttu-id="163c4-164">ダウンキャスト</span><span class="sxs-lookup"><span data-stu-id="163c4-164">Downcasting</span></span>

<span data-ttu-id="163c4-165">`:?>` 演算子は動的キャストを実行します。これは、キャストの成功が実行時に決定されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="163c4-165">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="163c4-166">`:?>` 演算子を使用するキャストは、コンパイル時にはチェックされません。ただし、実行時には、指定された型にキャストしようとしました。</span><span class="sxs-lookup"><span data-stu-id="163c4-166">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="163c4-167">オブジェクトがターゲット型と互換性がある場合、キャストは成功します。</span><span class="sxs-lookup"><span data-stu-id="163c4-167">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="163c4-168">オブジェクトがターゲット型と互換性がない場合、ランタイムは `InvalidCastException`を発生させます。</span><span class="sxs-lookup"><span data-stu-id="163c4-168">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="163c4-169">`downcast` 演算子を使用して、動的な型変換を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="163c4-169">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="163c4-170">次の式は、階層の下位への変換を、プログラムコンテキストから推論される型に指定します。</span><span class="sxs-lookup"><span data-stu-id="163c4-170">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="163c4-171">`upcast` 演算子と同様に、コンパイラがコンテキストから特定のターゲット型を推論できない場合は、エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="163c4-171">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span> <span data-ttu-id="163c4-172">型の注釈が必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="163c4-172">A type annotation may be required.</span></span>

<span data-ttu-id="163c4-173">次のコードは、`:>` 演算子と `:?>` 演算子の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="163c4-173">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="163c4-174">このコードは、変換が成功することがわかっている場合に `:?>` 演算子が最適に使用されることを示しています。変換に失敗した場合は `InvalidCastException` がスローされるためです。</span><span class="sxs-lookup"><span data-stu-id="163c4-174">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="163c4-175">変換が成功したことがわからない場合は、例外を生成するオーバーヘッドを回避するため、`match` 式を使用する型テストの方が適しています。</span><span class="sxs-lookup"><span data-stu-id="163c4-175">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="163c4-176">ジェネリック演算子 `downcast` と `upcast` は型の推定に依存して引数と戻り値の型を決定するため、上記のコードでは、</span><span class="sxs-lookup"><span data-stu-id="163c4-176">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="163c4-177">with</span><span class="sxs-lookup"><span data-stu-id="163c4-177">with</span></span>

```fsharp
let base1: Base1 = upcast d1
```

<span data-ttu-id="163c4-178">型の注釈が必要であることに注意してください。これは `upcast` 自体が基底クラスを特定できなかったためです。</span><span class="sxs-lookup"><span data-stu-id="163c4-178">Note that a type annotation is required, since `upcast` by itself could not determine the base class.</span></span>

## <a name="see-also"></a><span data-ttu-id="163c4-179">参照</span><span class="sxs-lookup"><span data-stu-id="163c4-179">See also</span></span>

- [<span data-ttu-id="163c4-180">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="163c4-180">F# Language Reference</span></span>](index.md)
