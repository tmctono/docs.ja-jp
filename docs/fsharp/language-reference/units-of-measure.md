---
title: 測定単位
description: 'F # の浮動小数点値と符号付き整数値に関連付けられた測定単位を使用する方法について説明します。これは通常、長さ、量、および質量を示すために使用されます。'
ms.date: 08/15/2020
ms.openlocfilehash: 0262f89e80697dd86161c93fe37381122972b56f
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811575"
---
# <a name="units-of-measure"></a><span data-ttu-id="d21f1-103">測定単位</span><span class="sxs-lookup"><span data-stu-id="d21f1-103">Units of Measure</span></span>

<span data-ttu-id="d21f1-104">F # の浮動小数点と符号付き整数値には、関連付けられた測定単位を含めることができます。これは通常、長さ、ボリューム、質量などを示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="d21f1-105">単位付きの数量を使用することにより、コンパイラは、算術リレーションシップの単位が正しいことを確認できます。これにより、プログラミングエラーを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="d21f1-106">構文</span><span class="sxs-lookup"><span data-stu-id="d21f1-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="d21f1-107">解説</span><span class="sxs-lookup"><span data-stu-id="d21f1-107">Remarks</span></span>

<span data-ttu-id="d21f1-108">前の構文では、 *単位名* を測定単位として定義しています。</span><span class="sxs-lookup"><span data-stu-id="d21f1-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="d21f1-109">省略可能な部分は、以前に定義した単位に基づいて新しいメジャーを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="d21f1-110">たとえば、次の行では、メジャー `cm` (センチメートル) を定義しています。</span><span class="sxs-lookup"><span data-stu-id="d21f1-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="d21f1-111">次の行では、メジャー `ml` (milliliter) を3次 () として定義して `cm^3` います。</span><span class="sxs-lookup"><span data-stu-id="d21f1-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="d21f1-112">前の構文では、 *measure* は単位を含む数式です。</span><span class="sxs-lookup"><span data-stu-id="d21f1-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="d21f1-113">単位が関係する数式では、整数の累乗がサポートされています (正と負)。単位間のスペースは、2つの単位の積、つまり `*` 単位の積を示すと同時に、 `/` 単位の商を示します。</span><span class="sxs-lookup"><span data-stu-id="d21f1-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="d21f1-114">逆数単位の場合は、負の整数の累乗を使用するか、または `/` 単位の数式の分子と分母を区別するを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="d21f1-115">分母に複数の単位を指定する場合は、かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d21f1-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="d21f1-116">の後のスペースで区切ら `/` れた単位は、分母の一部として解釈されますが、の後に続く単位 `*` は、分子の一部として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="d21f1-117">1つの単位式で1を使用すると、dimensionless の数量を示すことも、分子などの他の単位と組み合わせて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="d21f1-118">たとえば、レートの単位はとして書き込ま `1/s` れます。ここで、は `s` 秒を示します。</span><span class="sxs-lookup"><span data-stu-id="d21f1-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="d21f1-119">かっこは、単位の数式では使用されません。</span><span class="sxs-lookup"><span data-stu-id="d21f1-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="d21f1-120">単位の数式で数値変換定数を指定することはできません。ただし、単位を個別に指定して変換定数を定義し、単位チェックされた計算で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="d21f1-121">同じことを意味する単位の数式は、さまざまな方法で記述できます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="d21f1-122">したがって、コンパイラは、単位の数式を一貫性のある形式に変換します。これにより、負の値が reciprocals に変換され、単位が1つの分子と分母にグループ化され、分子と分母の単位が alphabetizes されます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="d21f1-123">たとえば、単位の数式 `kg m s^-2` と `m /s s * kg` は両方ともに変換され `kg m/s^2` ます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="d21f1-124">浮動小数点式では測定単位を使用します。</span><span class="sxs-lookup"><span data-stu-id="d21f1-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="d21f1-125">浮動小数点数を関連する測定単位と共に使用すると、タイプセーフの別のレベルが追加され、弱く型指定された浮動小数点数を使用するときに、式で発生する可能性がある単位不一致エラーを回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="d21f1-126">単位を使用する浮動小数点式を記述する場合は、式の単位が一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d21f1-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="d21f1-127">次の例に示すように、山かっこで囲まれた単位の数式でリテラルに注釈を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="d21f1-128">数字と山かっこの間にスペースを入れないでください。ただし、次の例に示すように、などのリテラルサフィックスを含めることができ `f` ます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="d21f1-129">このような注釈は、リテラルの型をプリミティブ型 (など) から `float` 次元型 (この場合はなど) に変更し `float<cm>` `float<miles/hour>` ます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="d21f1-130">の単位注釈は `<1>` dimensionless quantity を示し、その型は、unit パラメーターを持たないプリミティブ型に相当します。</span><span class="sxs-lookup"><span data-stu-id="d21f1-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="d21f1-131">測定単位の型は、浮動小数点型または符号付き整数型であり、追加の単位注釈が角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="d21f1-132">したがって、変換の種類を `g` (グラム) から (キログラム) に記述する場合は、次のように `kg` 型を記述します。</span><span class="sxs-lookup"><span data-stu-id="d21f1-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="d21f1-133">測定単位は、コンパイル時の単位チェックに使用されますが、実行時環境には保存されません。</span><span class="sxs-lookup"><span data-stu-id="d21f1-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="d21f1-134">そのため、パフォーマンスには影響しません。</span><span class="sxs-lookup"><span data-stu-id="d21f1-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="d21f1-135">測定単位は、浮動小数点型だけでなく、任意の型に適用できます。ただし、浮動小数点型、符号付き整数型、および10進数型のみが次元の数量をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d21f1-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="d21f1-136">したがって、プリミティブ型と、これらのプリミティブ型を含む集計では、測定単位を使用するのが理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="d21f1-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="d21f1-137">次の例は、測定単位の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d21f1-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

<span data-ttu-id="d21f1-138">次のコード例は、dimensionless 浮動小数点数から次元浮動小数点値に変換する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d21f1-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="d21f1-139">1.0 で乗算するだけで、1.0 にディメンションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="d21f1-140">これは、のような関数に要約でき `degreesFahrenheit` ます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="d21f1-141">また、dimensionless 浮動小数点数を予期する関数に次元値を渡す場合は、演算子を使用して、その単位をキャンセルするか、にキャストする必要があり `float` `float` ます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="d21f1-142">この例では、 `1.0<degC>` が `printf` dimensionless 数量を想定しているため、の引数としてをで除算し `printf` ます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="d21f1-143">次のセッション例は、からの出力とこのコードへの入力を示しています。</span><span class="sxs-lookup"><span data-stu-id="d21f1-143">The following example session shows the outputs from and inputs to this code.</span></span>

```console
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="d21f1-144">汎用単位の使用</span><span class="sxs-lookup"><span data-stu-id="d21f1-144">Using Generic Units</span></span>

<span data-ttu-id="d21f1-145">関連する測定単位を持つデータを操作するジェネリック関数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="d21f1-146">これを行うには、次のコード例に示すように、型パラメーターとしてジェネリック単位を使用して型を指定します。</span><span class="sxs-lookup"><span data-stu-id="d21f1-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="d21f1-147">汎用単位を使用した集計型の作成</span><span class="sxs-lookup"><span data-stu-id="d21f1-147">Creating Aggregate Types with Generic Units</span></span>

<span data-ttu-id="d21f1-148">次のコードは、ジェネリックである単位を持つ個々の浮動小数点値で構成される集計型を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d21f1-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="d21f1-149">これにより、さまざまな単位で動作する1つの型を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="d21f1-150">また、1つの単位セットを持つジェネリック型が、異なる単位のセットを持つ同じジェネリック型とは異なる型であることを保証することで、ジェネリックユニットはタイプセーフを保持します。</span><span class="sxs-lookup"><span data-stu-id="d21f1-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="d21f1-151">この手法の基礎は、属性を `Measure` 型パラメーターに適用できることです。</span><span class="sxs-lookup"><span data-stu-id="d21f1-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a><span data-ttu-id="d21f1-152">実行時の単位数</span><span class="sxs-lookup"><span data-stu-id="d21f1-152">Units at Runtime</span></span>

<span data-ttu-id="d21f1-153">静的な型チェックには、測定単位が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="d21f1-154">浮動小数点値をコンパイルすると、測定単位が削除されるため、実行時に単位が失われます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="d21f1-155">したがって、実行時の単位のチェックに依存する機能を実装しようとすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d21f1-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="d21f1-156">たとえば、 `ToString` 単位を出力する関数を実装することはできません。</span><span class="sxs-lookup"><span data-stu-id="d21f1-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>

## <a name="conversions"></a><span data-ttu-id="d21f1-157">コンバージョン</span><span class="sxs-lookup"><span data-stu-id="d21f1-157">Conversions</span></span>

<span data-ttu-id="d21f1-158">単位を持つ型 (など) を、単位の `float<'u>` ない型に変換するには、標準変換関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="d21f1-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="d21f1-159">たとえば、 `float` 次のコードに示すように、を使用して、 `float` 単位を持たない値に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="d21f1-160">単位を含む値に単位なしの値を変換するには、適切な単位で注釈が付けられた1または1.0 の値を乗算します。</span><span class="sxs-lookup"><span data-stu-id="d21f1-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="d21f1-161">ただし、相互運用性レイヤーを記述する場合は、単位の値を単位の値に変換するために使用できる明示的な関数もいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="d21f1-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="d21f1-162">これらは、 [Fsharp.core プリミティブ](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html) モジュールにあります。</span><span class="sxs-lookup"><span data-stu-id="d21f1-162">These are in the [FSharp.Core.LanguagePrimitives](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html) module.</span></span> <span data-ttu-id="d21f1-163">たとえば、単位なしからに変換するには、 `float` `float<cm>` 次のコードに示すように、 [FloatWithMeasure](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html#FloatWithMeasure)を使用します。</span><span class="sxs-lookup"><span data-stu-id="d21f1-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html#FloatWithMeasure), as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a><span data-ttu-id="d21f1-164">F # コアライブラリの測定単位</span><span class="sxs-lookup"><span data-stu-id="d21f1-164">Units of Measure in the F# Core library</span></span>

<span data-ttu-id="d21f1-165">名前空間では、ユニットライブラリを使用でき `FSharp.Data.UnitSystems.SI` ます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-165">A unit library is available in the `FSharp.Data.UnitSystems.SI` namespace.</span></span> <span data-ttu-id="d21f1-166">この例では、副名前空間のシンボル形式 ( `m` メーターの場合) `UnitSymbols` と、 `meter` サブ名前空間のフルネーム (メーターのような) の両方に SI 単位が含まれてい `UnitNames` ます。</span><span class="sxs-lookup"><span data-stu-id="d21f1-166">It includes SI units in both their symbol form (like `m` for meter) in the `UnitSymbols` sub-namespace, and their full name (like `meter` for meter) in the `UnitNames` sub-namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="d21f1-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="d21f1-167">See also</span></span>

- [<span data-ttu-id="d21f1-168">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="d21f1-168">F# Language Reference</span></span>](index.md)
