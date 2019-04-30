---
title: 測定単位
description: どの浮動小数点をについて説明しますと F# の符号付き整数値には、測定単位を長さ、ボリューム、および大容量を示すために使用される通常を関連付けることができます。
ms.date: 05/16/2016
ms.openlocfilehash: 935dbff3545f92736ce8c51de86a168429dc194f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982541"
---
# <a name="units-of-measure"></a><span data-ttu-id="fcaa2-103">測定単位</span><span class="sxs-lookup"><span data-stu-id="fcaa2-103">Units of Measure</span></span>

<span data-ttu-id="fcaa2-104">浮動小数点と整数値をサインインF#と長さ、ボリューム、質量などを示すために通常使用されるメジャーの単位を関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="fcaa2-105">算術リレーションシップでは正しいユニットがあるを防ぐことができますを確認するコンパイラを有効にした数量の単位を使用してプログラミング エラーです。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="fcaa2-106">構文</span><span class="sxs-lookup"><span data-stu-id="fcaa2-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="fcaa2-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="fcaa2-107">Remarks</span></span>

<span data-ttu-id="fcaa2-108">前の構文を定義*単位名*メジャーの単位として。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="fcaa2-109">オプションの一部を使用して、以前に定義された単位で新しいメジャーを定義します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="fcaa2-110">たとえば、次の行は、メジャーを定義します。 `cm` (センチメートル)。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="fcaa2-111">次の行のメジャーを定義する`ml`(milliliter) として立方センチメートル (`cm^3`)。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="fcaa2-112">前の構文で*メジャー*ユニットを含む式です。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="fcaa2-113">単位を使用する数式で整数乗がサポートされている (正と負の値)、ユニットの間にスペースが 2 つの単位の製品を示す`*`ユニットの積を示しますと`/`ユニットの商を示します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="fcaa2-114">逆数の単位、負の整数の電源を使用することができますか、または`/`分子と分母の単位の数式を分離することを示します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="fcaa2-115">分母に複数のユニットは、かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="fcaa2-116">ユニットは、後のスペースで区切られた、`/`分母では、次の任意の単位の一部として解釈されます、`*`分子の一部として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="fcaa2-117">または、分子など、他の単位と無次元の数量を示すためだけにいずれかの単位式では、1 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="fcaa2-118">速度の単位として書き込まれますたとえば、`1/s`ここで、`s`秒数を示します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="fcaa2-119">かっこは、単位の数式では使用されません。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="fcaa2-120">単位の数式で数値変換の定数を指定しません。ただし、ユニットとは別に変換定数を定義でき、計算の単位がチェックされたで使用できます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="fcaa2-121">同じことを意味する単位の数式は、さまざまな同等の方法で記述できます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="fcaa2-122">そのため、コンパイラは単位の数式を逆数をグループ単位には、1 つの分子と分母では、負の累乗を変換し、分子と分母の単位をアルファベット順に並べ替えますが、一貫性のある形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="fcaa2-123">単位の数式など`kg m s^-2`と`m /s s * kg`に変換されます両方`kg m/s^2`します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="fcaa2-124">浮動小数点式では、測定単位を使用します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="fcaa2-125">タイプ セーフのもう 1 つのレベルを追加するメジャーの関連付けられている単位と浮動小数点数を使用して、弱く型指定された浮動小数点数を使用するときに、数式で発生する単体の不一致エラーを回避できます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="fcaa2-126">浮動を記述する場合は、単位を使用するポイント式、式の単位が一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="fcaa2-127">次の例に示すように、山かっこで単位の数式を使用したリテラルに注釈を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="fcaa2-128">山かっ; と数の間にスペースを配置しないでください。ただし、リテラルのサフィックスをなどに含めることができます`f`次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="fcaa2-129">このような注釈は、プリミティブ型から、リテラルの型を変更 (など`float`) ディメンションが指定された型になど`float<cm>`または、この場合、`float<miles/hour>`します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="fcaa2-130">単位の注釈の`<1>`無次元数量、およびその型が単位パラメーターがないプリミティブ型と同じことを示します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="fcaa2-131">測定単位の種類は、浮動小数点または符号付き整数型、角かっこで、追加の単体注釈と共にします。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="fcaa2-132">変換の種類を記述するときにそのため、 `g` (グラム) に`kg`(キログラム)、次のように型を記述します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="fcaa2-133">測定単位では、コンパイル単位のチェックに使用されますが、実行時環境では保存されません。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="fcaa2-134">そのため、パフォーマンスは影響ありません。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="fcaa2-135">測定単位は、浮動小数点型の場合は; がだけでなく、任意の型に適用できます。ただし、唯一の浮動小数点型は、整数型、および 10 進数データ型の次元はサポートの数量を署名しました。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="fcaa2-136">したがって、プリミティブ型とこれらのプリミティブ型が含まれている集計は、測定単位を使用する意味のみ実行します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="fcaa2-137">次の例では、測定単位の使用を示します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

<span data-ttu-id="fcaa2-138">次のコード例は、無次元の浮動小数点数からディメンションが指定された浮動小数点値に変換する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="fcaa2-139">乗算、1.0、1.0 に次元を適用します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="fcaa2-140">ような関数を抽象化することができます`degreesFahrenheit`します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="fcaa2-141">また、無次元の浮動小数点数を予想される関数にディメンションが指定された値を渡すと、ときにする必要があります単位をキャンセルまたはにキャスト`float`を使用して、`float`演算子。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="fcaa2-142">除算では、この例では、`1.0<degC>`に対する引数の`printf`ため`printf`無次元の数量が必要です。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="fcaa2-143">次の例のセッションからの出力と次のコードへの入力を示します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-143">The following example session shows the outputs from and inputs to this code.</span></span>

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="fcaa2-144">汎用的な単位を使用します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-144">Using Generic Units</span></span>

<span data-ttu-id="fcaa2-145">関連する測定単位を持つデータを操作するジェネリック関数を記述できます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="fcaa2-146">これを行う、型パラメーターとしてジェネリック単体と型を指定することで、次のコード例で示すようにします。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="fcaa2-147">汎用的な単位に集約型の作成</span><span class="sxs-lookup"><span data-stu-id="fcaa2-147">Creating Aggregate Types with Generic Units</span></span>

<span data-ttu-id="fcaa2-148">次のコードでは、一般的なユニットがある個々 の浮動小数点値で構成される集計の種類を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="fcaa2-149">これにより、さまざまな単位で動作する 1 つの型を作成できます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="fcaa2-150">また、汎用的なユニットでは、単位の 1 つのセットを持つジェネリック型が異なる単位のセットと同じジェネリック型は異なる型であることを確認してタイプ セーフが保持されます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="fcaa2-151">この手法の基礎は、`Measure`型パラメーターに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a><span data-ttu-id="fcaa2-152">実行時の単位</span><span class="sxs-lookup"><span data-stu-id="fcaa2-152">Units at Runtime</span></span>

<span data-ttu-id="fcaa2-153">測定単位は、静的な型をチェックするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="fcaa2-154">浮動小数点値がコンパイルされると、測定単位排除されるので、実行時に単位は失われます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="fcaa2-155">そのため、実行時に単位のチェックに依存する機能を実装するあらゆる試みでは、このことはできません。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="fcaa2-156">たとえば、実装、`ToString`単位を印刷する関数のことはできません。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>

## <a name="conversions"></a><span data-ttu-id="fcaa2-157">変換</span><span class="sxs-lookup"><span data-stu-id="fcaa2-157">Conversions</span></span>

<span data-ttu-id="fcaa2-158">ユニットを持つ型に変換する (たとえば、 `float<'u>`) ユニットがない型には、標準変換関数を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="fcaa2-159">たとえば、使用することができます`float`に変換する、`float`次のコードに示すように 単位がない値。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="fcaa2-160">単位のない値をユニットの値に変換するには、適切な単位で注釈が付けられる 1 つまたは 1.0 の値で乗算できます。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="fcaa2-161">ただし、相互運用性レイヤーを記述するためもユニット単位のない値を値に変換するのに使用できるいくつかの明示的な関数です。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="fcaa2-162">うち、 [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3)モジュール。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-162">These are in the [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) module.</span></span> <span data-ttu-id="fcaa2-163">例では、単位から変換する、`float`を`float<cm>`を使用して、 [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9)次のコードに示すように、します。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a><span data-ttu-id="fcaa2-164">測定単位、F#コア ライブラリ</span><span class="sxs-lookup"><span data-stu-id="fcaa2-164">Units of Measure in the F# Core library</span></span>

<span data-ttu-id="fcaa2-165">単体のライブラリが表示されます、`FSharp.Data.UnitSystems.SI`名前空間。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-165">A unit library is available in the `FSharp.Data.UnitSystems.SI` namespace.</span></span> <span data-ttu-id="fcaa2-166">両方の形式のシンボルの SI 単位が含まれています (など`m`メーター) で、`UnitSymbols`サブ名前空間との完全名 (など`meter`メーター) で、`UnitNames`サブ名前空間。</span><span class="sxs-lookup"><span data-stu-id="fcaa2-166">It includes SI units in both their symbol form (like `m` for meter) in the `UnitSymbols` sub-namespace, and their full name (like `meter` for meter) in the `UnitNames` sub-namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcaa2-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcaa2-167">See also</span></span>

- [<span data-ttu-id="fcaa2-168">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="fcaa2-168">F# Language Reference</span></span>](index.md)