---
title: C# の型と変数 - C# 言語のツアー
description: C# における型の定義と変数の宣言について説明します
ms.date: 08/10/2016
ms.assetid: f8a8051e-0049-43f1-b594-9c84cc7b1224
ms.openlocfilehash: ae44dd273a2460e5718adc7324fae324e3de5bba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59672369"
---
# <a name="types-and-variables"></a><span data-ttu-id="6ebee-103">型と変数</span><span class="sxs-lookup"><span data-stu-id="6ebee-103">Types and variables</span></span>

<span data-ttu-id="6ebee-104">C# には、*値型*と*参照型*という 2 種類の型があります。</span><span class="sxs-lookup"><span data-stu-id="6ebee-104">There are two kinds of types in C#: *value types* and *reference types*.</span></span> <span data-ttu-id="6ebee-105">値型の変数が直接データを格納するのに対して、参照型の変数はデータへの参照を格納し、後者はオブジェクトとして知られています。</span><span class="sxs-lookup"><span data-stu-id="6ebee-105">Variables of value types directly contain their data whereas variables of reference types store references to their data, the latter being known as objects.</span></span> <span data-ttu-id="6ebee-106">参照型を使用すると 2 つの変数が同じオブジェクトを参照できるため、1 つの変数に対する演算によって、もう一方の変数によって参照されるオブジェクトに影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-106">With reference types, it is possible for two variables to reference the same object and thus possible for operations on one variable to affect the object referenced by the other variable.</span></span> <span data-ttu-id="6ebee-107">値型の場合、各変数が独自のデータ コピーを保持し、1 つの変数に対する演算で別の変数に影響を与えることはできません (`ref` と `out` のパラメーターの変数の場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="6ebee-107">With value types, the variables each have their own copy of the data, and it is not possible for operations on one to affect the other (except in the case of `ref` and `out` parameter variables).</span></span>

<span data-ttu-id="6ebee-108">C# の値型はさらに、*単純型*、*列挙型*、*構造体型*、および *null 許容値型* に分けられます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-108">C#’s value types are further divided into *simple types*, *enum types*, *struct types*, and *nullable value types*.</span></span> <span data-ttu-id="6ebee-109">C# の参照型はさらに、*クラス型*、*インターフェイス型*、*配列型*、および*デリゲート型*に分けられます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-109">C#’s reference types are further divided into *class types*, *interface types*, *array types*, and *delegate types*.</span></span>

<span data-ttu-id="6ebee-110">以下は、C# の型システムの概要です。</span><span class="sxs-lookup"><span data-stu-id="6ebee-110">The following provides an overview of C#’s type system.</span></span>

* <span data-ttu-id="6ebee-111">[値型][ValueTypes]</span><span class="sxs-lookup"><span data-stu-id="6ebee-111">[Value types][ValueTypes]</span></span>
  - <span data-ttu-id="6ebee-112">[単純型][SimpleTypes]</span><span class="sxs-lookup"><span data-stu-id="6ebee-112">[Simple types][SimpleTypes]</span></span>
    * <span data-ttu-id="6ebee-113">符号付きの整数: `sbyte`、`short`、`int`、`long`</span><span class="sxs-lookup"><span data-stu-id="6ebee-113">Signed integral: `sbyte`, `short`, `int`, `long`</span></span>
    * <span data-ttu-id="6ebee-114">符号なしの整数: `byte`、`ushort`、`uint`、`ulong`</span><span class="sxs-lookup"><span data-stu-id="6ebee-114">Unsigned integral: `byte`, `ushort`, `uint`, `ulong`</span></span>
    * <span data-ttu-id="6ebee-115">Unicode 文字: `char`</span><span class="sxs-lookup"><span data-stu-id="6ebee-115">Unicode characters: `char`</span></span>
    * <span data-ttu-id="6ebee-116">IEEE 浮動小数点: `float`、`double`</span><span class="sxs-lookup"><span data-stu-id="6ebee-116">IEEE floating point: `float`, `double`</span></span>
    * <span data-ttu-id="6ebee-117">高精度の 10 進数: `decimal`</span><span class="sxs-lookup"><span data-stu-id="6ebee-117">High-precision decimal: `decimal`</span></span>
    * <span data-ttu-id="6ebee-118">ブール値: `bool`</span><span class="sxs-lookup"><span data-stu-id="6ebee-118">Boolean: `bool`</span></span>
  - <span data-ttu-id="6ebee-119">[列挙型][EnumTypes]</span><span class="sxs-lookup"><span data-stu-id="6ebee-119">[Enum types][EnumTypes]</span></span>
    * <span data-ttu-id="6ebee-120">`enum E {...}` 形式のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="6ebee-120">User-defined types of the form `enum E {...}`</span></span>
  - <span data-ttu-id="6ebee-121">[構造体の型][StructTypes]</span><span class="sxs-lookup"><span data-stu-id="6ebee-121">[Struct types][StructTypes]</span></span>
    * <span data-ttu-id="6ebee-122">`struct S {...}` 形式のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="6ebee-122">User-defined types of the form `struct S {...}`</span></span>
  - <span data-ttu-id="6ebee-123">[null 許容値型][NullableTypes]</span><span class="sxs-lookup"><span data-stu-id="6ebee-123">[Nullable value types][NullableTypes]</span></span>
    * <span data-ttu-id="6ebee-124">`null` 値を持つその他すべての値型の拡張子</span><span class="sxs-lookup"><span data-stu-id="6ebee-124">Extensions of all other value types with a `null` value</span></span>
* <span data-ttu-id="6ebee-125">[参照型][ReferenceTypes]</span><span class="sxs-lookup"><span data-stu-id="6ebee-125">[Reference types][ReferenceTypes]</span></span>
  - <span data-ttu-id="6ebee-126">[クラス型][ClassTypes]</span><span class="sxs-lookup"><span data-stu-id="6ebee-126">[Class types][ClassTypes]</span></span>
    * <span data-ttu-id="6ebee-127">その他すべての型の最終的な基底クラス: `object`</span><span class="sxs-lookup"><span data-stu-id="6ebee-127">Ultimate base class of all other types: `object`</span></span>
    * <span data-ttu-id="6ebee-128">Unicode 文字列: `string`</span><span class="sxs-lookup"><span data-stu-id="6ebee-128">Unicode strings: `string`</span></span>
    * <span data-ttu-id="6ebee-129">`class C {...}` 形式のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="6ebee-129">User-defined types of the form `class C {...}`</span></span>
  - <span data-ttu-id="6ebee-130">[インターフェイス型][InterfaceTypes]</span><span class="sxs-lookup"><span data-stu-id="6ebee-130">[Interface types][InterfaceTypes]</span></span>
    * <span data-ttu-id="6ebee-131">`interface I {...}` 形式のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="6ebee-131">User-defined types of the form `interface I {...}`</span></span>
  - <span data-ttu-id="6ebee-132">[配列型][ArrayTypes]</span><span class="sxs-lookup"><span data-stu-id="6ebee-132">[Array types][ArrayTypes]</span></span>
    * <span data-ttu-id="6ebee-133">1 次元または多次元、たとえば `int[]` および `int[,]`</span><span class="sxs-lookup"><span data-stu-id="6ebee-133">Single- and multi-dimensional, for example, `int[]` and `int[,]`</span></span>
  - <span data-ttu-id="6ebee-134">[デリゲート型][DelegateTypes]</span><span class="sxs-lookup"><span data-stu-id="6ebee-134">[Delegate types][DelegateTypes]</span></span>
    * <span data-ttu-id="6ebee-135">`delegate int D(...)` 形式のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="6ebee-135">User-defined types of the form `delegate int D(...)`</span></span>

[ValueTypes]: ../language-reference/keywords/value-types-table.md
[SimpleTypes]: ../language-reference/keywords/value-types.md#simple-types
[EnumTypes]: ../language-reference/keywords/enum.md
[StructTypes]: ../language-reference/keywords/struct.md
[NullableTypes]: ../programming-guide/nullable-types/index.md
[ReferenceTypes]: ../language-reference/keywords/reference-types.md
[ClassTypes]: ../language-reference/keywords/class.md
[InterfaceTypes]: ../language-reference/keywords/interface.md
[DelegateTypes]: ../language-reference/keywords/delegate.md
[ArrayTypes]: ../programming-guide/arrays/index.md

<span data-ttu-id="6ebee-136">8 つの整数型は、符号付きまたは符号なしの形式で、8 ビット、16 ビット、32 ビットおよび 64 ビットの値をサポートします。</span><span class="sxs-lookup"><span data-stu-id="6ebee-136">The eight integral types provide support for 8-bit, 16-bit, 32-bit, and 64-bit values in signed or unsigned form.</span></span>

<span data-ttu-id="6ebee-137">2 つの浮動小数点型 `float` と `double` は、それぞれ、32 ビット単精度と 64 ビット倍精度の IEC-60559 形式を使用して表されます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-137">The two floating-point types, `float` and `double`, are represented using the 32-bit single-precision and 64-bit double-precision IEC-60559 formats, respectively.</span></span>

<span data-ttu-id="6ebee-138">`decimal` 型は 128 ビットのデータ型で、財務や通貨の計算に適しています。</span><span class="sxs-lookup"><span data-stu-id="6ebee-138">The `decimal` type is a 128-bit data type suitable for financial and monetary calculations.</span></span>

<span data-ttu-id="6ebee-139">C# の `bool` 型はブール値を表すのに使用します。値は `true` か `false` のどちらかです。</span><span class="sxs-lookup"><span data-stu-id="6ebee-139">C#’s `bool` type is used to represent Boolean values—values that are either `true` or `false`.</span></span>

<span data-ttu-id="6ebee-140">C# における文字および文字列の処理では、Unicode エンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ebee-140">Character and string processing in C# uses Unicode encoding.</span></span> <span data-ttu-id="6ebee-141">`char` 型は UTF-16 コード単位を表し、`string` 型は一連の UTF-16 コード単位を表します。</span><span class="sxs-lookup"><span data-stu-id="6ebee-141">The `char` type represents a UTF-16 code unit, and the `string` type represents a sequence of UTF-16 code units.</span></span>

<span data-ttu-id="6ebee-142">C# の数値型をまとめると次の通りです。</span><span class="sxs-lookup"><span data-stu-id="6ebee-142">This summarizes C#’s numeric types.</span></span>

* <span data-ttu-id="6ebee-143">符号付きの整数</span><span class="sxs-lookup"><span data-stu-id="6ebee-143">Signed Integral</span></span>
  - <span data-ttu-id="6ebee-144">`sbyte`:8 ビット、範囲は -128 ～ 127</span><span class="sxs-lookup"><span data-stu-id="6ebee-144">`sbyte`:  8 bits, range from -128 to 127</span></span>
  - <span data-ttu-id="6ebee-145">`short`:16 ビット、範囲は -32,768 ～ 32,767</span><span class="sxs-lookup"><span data-stu-id="6ebee-145">`short`: 16 bits, range from -32,768 to 32,767</span></span>
  - <span data-ttu-id="6ebee-146">`int`  :32 ビット、範囲は -2,147,483,648 ～ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="6ebee-146">`int`  : 32 bits, range from -2,147,483,648 to 2,147,483,647</span></span>
  - <span data-ttu-id="6ebee-147">`long` は、次のとおりです。64 ビット、範囲は -9,223,372,036,854,775,808 ～ 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="6ebee-147">`long` : 64 bits, range from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>
* <span data-ttu-id="6ebee-148">符号なしの整数</span><span class="sxs-lookup"><span data-stu-id="6ebee-148">Unsigned integral</span></span>
  - <span data-ttu-id="6ebee-149">`byte`   :8 ビット、範囲は 0 ～ 255</span><span class="sxs-lookup"><span data-stu-id="6ebee-149">`byte`   :  8 bits, range from 0 to 255</span></span>
  - <span data-ttu-id="6ebee-150">`ushort` は、次のとおりです。16 ビット、範囲は 0 ～ 65,535</span><span class="sxs-lookup"><span data-stu-id="6ebee-150">`ushort` : 16 bits, range from 0 to 65,535</span></span>
  - <span data-ttu-id="6ebee-151">`uint`   :32 ビット、範囲は 0 ～ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="6ebee-151">`uint`   : 32 bits, range from 0 to 4,294,967,295</span></span>
  - <span data-ttu-id="6ebee-152">`ulong`  :64 ビット、範囲は 0 ～ 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="6ebee-152">`ulong`  : 64 bits, range from 0 to 18,446,744,073,709,551,615</span></span>
* <span data-ttu-id="6ebee-153">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="6ebee-153">Floating point</span></span>
  - <span data-ttu-id="6ebee-154">`float`  :32 ビット、範囲は 1.5 × 10<sup>-45</sup> ～ 3.4 × 10<sup>38</sup>、有効桁数は 7</span><span class="sxs-lookup"><span data-stu-id="6ebee-154">`float`  : 32 bits, range from 1.5 × 10<sup>-45</sup> to 3.4 × 10<sup>38</sup>,    7-digit precision</span></span>
  - <span data-ttu-id="6ebee-155">`double` は、次のとおりです。64 ビット、範囲は 5.0 × 10<sup>-324</sup> ～ 1.7 × 10<sup>308</sup>、有効桁数は 15</span><span class="sxs-lookup"><span data-stu-id="6ebee-155">`double` : 64 bits, range from 5.0 × 10<sup>-324</sup> to 1.7 × 10<sup>308</sup>, 15-digit precision</span></span>
* <span data-ttu-id="6ebee-156">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="6ebee-156">Decimal</span></span>
  - <span data-ttu-id="6ebee-157">`decimal` は、次のとおりです。128 ビット、範囲は少なくとも -7.9 × 10<sup>-28</sup> ～ 7.9 × 10<sup>28</sup>、有効桁数は少なくとも 28</span><span class="sxs-lookup"><span data-stu-id="6ebee-157">`decimal` : 128 bits, range is at least -7.9 × 10<sup>-28</sup> to 7.9 × 10<sup>28</sup>, with at least 28-digit precision</span></span>

<span data-ttu-id="6ebee-158">C# プログラムでは*型宣言*を使用して新しい型を作成します。</span><span class="sxs-lookup"><span data-stu-id="6ebee-158">C# programs use *type declarations* to create new types.</span></span> <span data-ttu-id="6ebee-159">型宣言は、新しい型の名前とメンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ebee-159">A type declaration specifies the name and the members of the new type.</span></span> <span data-ttu-id="6ebee-160">C# の型カテゴリのうち 5 つはユーザー定義が可能です。クラス型、構造体型、インターフェイス型、列挙型、そしてデリゲート型です。</span><span class="sxs-lookup"><span data-stu-id="6ebee-160">Five of C#’s categories of types are user-definable: class types, struct types, interface types, enum types, and delegate types.</span></span>

<span data-ttu-id="6ebee-161">`class` 型は、データ メンバー (フィールド) と関数メンバー (メソッド、プロパティ、その他) を含むデータ構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="6ebee-161">A `class` type defines a data structure that contains data members (fields) and function members (methods, properties, and others).</span></span> <span data-ttu-id="6ebee-162">クラス型では、単一継承とポリモーフィズムをサポートします。このメカニズムによって派生クラスが基底クラスを拡張して特殊化できます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-162">Class types support single inheritance and polymorphism, mechanisms whereby derived classes can extend and specialize base classes.</span></span>

<span data-ttu-id="6ebee-163">`struct` 型は、データ メンバーおよび関数メンバーで構造体を表す点において、クラス型に似ています。</span><span class="sxs-lookup"><span data-stu-id="6ebee-163">A `struct` type is similar to a class type in that it represents a structure with data members and function members.</span></span> <span data-ttu-id="6ebee-164">ただしクラスと異なり、構造体は値型で、通常はヒープ割り当てが不要です。</span><span class="sxs-lookup"><span data-stu-id="6ebee-164">However, unlike classes, structs are value types and do not typically require heap allocation.</span></span> <span data-ttu-id="6ebee-165">構造体型はユーザー指定の継承をサポートせず、すべての構造体型は暗黙的に `object` 型を継承します。</span><span class="sxs-lookup"><span data-stu-id="6ebee-165">Struct types do not support user-specified inheritance, and all struct types implicitly inherit from type `object`.</span></span>

<span data-ttu-id="6ebee-166">`interface` 型は、パブリック関数メンバーの名前付きセットとしてコントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="6ebee-166">An `interface` type defines a contract as a named set of public function members.</span></span> <span data-ttu-id="6ebee-167">`interface` を実装する `class` または `struct` は、インターフェイスの関数メンバーの実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ebee-167">A `class` or `struct` that implements an `interface` must provide implementations of the interface’s function members.</span></span> <span data-ttu-id="6ebee-168">`interface` は複数の基底インターフェイスから継承することがあり、`class` または `struct` は複数のインターフェイスを実装することがあります。</span><span class="sxs-lookup"><span data-stu-id="6ebee-168">An `interface` may inherit from multiple base interfaces, and a `class` or `struct` may implement multiple interfaces.</span></span>

<span data-ttu-id="6ebee-169">`delegate` 型は、特定のパラメーター リストおよび戻り値を使用してメソッドへの参照を表します。</span><span class="sxs-lookup"><span data-stu-id="6ebee-169">A `delegate` type represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="6ebee-170">デリゲートを使用すると、変数に割り当ててパラメーターとして渡すことのできるエンティティとして、メソッドを処理できます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-170">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="6ebee-171">デリゲートは、関数型言語で提供される関数の型に似ています。</span><span class="sxs-lookup"><span data-stu-id="6ebee-171">Delegates are analogous to function types provided by functional languages.</span></span> <span data-ttu-id="6ebee-172">さらに、他のいくつかの言語にみられる関数ポインターの概念に似ていますが、関数ポインターと異なり、デリゲートはオブジェクト指向でタイプ セーフです。</span><span class="sxs-lookup"><span data-stu-id="6ebee-172">They are also similar to the concept of function pointers found in some other languages, but unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="6ebee-173">`class`、`struct`、`interface` および `delegate`の型はすべてジェネリックをサポートし、他の型と共にパラメーター化できます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-173">The `class`, `struct`, `interface` and `delegate` types all support generics, whereby they can be parameterized with other types.</span></span>

<span data-ttu-id="6ebee-174">`enum` 型は、名前付き定数を持つ固有の型です。</span><span class="sxs-lookup"><span data-stu-id="6ebee-174">An `enum` type is a distinct type with named constants.</span></span> <span data-ttu-id="6ebee-175">`enum` 型にはそれぞれ基になる型があり、これは 8 つの整数型のいずれかでなければいけません。</span><span class="sxs-lookup"><span data-stu-id="6ebee-175">Every `enum` type has an underlying type, which must be one of the eight integral types.</span></span> <span data-ttu-id="6ebee-176">`enum` 型の値のセットは、その基になる型の値のセットと同じです。</span><span class="sxs-lookup"><span data-stu-id="6ebee-176">The set of values of an `enum` type is the same as the set of values of the underlying type.</span></span>

<span data-ttu-id="6ebee-177">C# は、あらゆる型の 1 次元および多次元の配列をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6ebee-177">C# supports single- and multi-dimensional arrays of any type.</span></span> <span data-ttu-id="6ebee-178">上記の型とは異なり、配列型は使用前に宣言する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="6ebee-178">Unlike the types listed above, array types do not have to be declared before they can be used.</span></span> <span data-ttu-id="6ebee-179">代わりに配列型は、角かっこで囲んだ型名を後に付けることにより構成されます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-179">Instead, array types are constructed by following a type name with square brackets.</span></span> <span data-ttu-id="6ebee-180">たとえば、`int[]` は `int` の 1 次元配列で、`int[,]` は `int` の 2 次元配列、そして `int[][]` は `int` の 1 次元配列の 1 次元配列です。</span><span class="sxs-lookup"><span data-stu-id="6ebee-180">For example, `int[]` is a single-dimensional array of `int`, `int[,]` is a two-dimensional array of `int`, and `int[][]` is a single-dimensional array of single-dimensional array of `int`.</span></span>

<span data-ttu-id="6ebee-181">null 許容値型もまた、使用前に宣言する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="6ebee-181">Nullable value types also do not have to be declared before they can be used.</span></span> <span data-ttu-id="6ebee-182">null 非許容値型 `T` のそれぞれについて、対応する null 許容値型 `T?` があり、これは追加値 `null` を保持することができます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-182">For each non-nullable value type `T` there is a corresponding nullable value type `T?`, which can hold an additional value, `null`.</span></span> <span data-ttu-id="6ebee-183">たとえば、`int?` は任意の 32 ビット整数または `null` 値を保持できる型です。</span><span class="sxs-lookup"><span data-stu-id="6ebee-183">For instance, `int?` is a type that can hold any 32-bit integer or the value `null`.</span></span>

<span data-ttu-id="6ebee-184">C# の型システムは、任意の型の値を `object` として扱うように統一されています。</span><span class="sxs-lookup"><span data-stu-id="6ebee-184">C#’s type system is unified such that a value of any type can be treated as an `object`.</span></span> <span data-ttu-id="6ebee-185">C# における型はすべて、直接的または間接的に `object` クラス型から派生し、`object` はすべての型の究極の基底クラスです。</span><span class="sxs-lookup"><span data-stu-id="6ebee-185">Every type in C# directly or indirectly derives from the `object` class type, and `object` is the ultimate base class of all types.</span></span> <span data-ttu-id="6ebee-186">参照型の値は、値を単純に `object` 型としてみなすことによってオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-186">Values of reference types are treated as objects simply by viewing the values as type `object`.</span></span> <span data-ttu-id="6ebee-187">値型の値は、*ボックス化*と*ボックス化解除操作*を実行することによって、オブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-187">Values of value types are treated as objects by performing *boxing* and *unboxing operations*.</span></span> <span data-ttu-id="6ebee-188">次の例では、`int` 値は `object` 値に変換され、また `int` に戻されます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-188">In the following example, an `int` value is converted to `object` and back again to `int`.</span></span>

[!code-csharp[Boxing](../../../samples/snippets/csharp/tour/types-and-variables/Program.cs#L1-L10)]

<span data-ttu-id="6ebee-189">値型の値を `object` 型に変換すると、"ボックス" とも呼ばれる `object` インスタンスが値を保持するために割り当てられ、値がそのボックスにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-189">When a value of a value type is converted to type `object`, an `object` instance, also called a "box", is allocated to hold the value, and the value is copied into that box.</span></span> <span data-ttu-id="6ebee-190">逆に、`object` 参照が値型にキャストされると、参照先の `object` が適切な値型のボックスかどうかが確認され、確認が成功すると、ボックスの値がコピーされます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-190">Conversely, when an `object` reference is cast to a value type, a check is made that the referenced `object` is a box of the correct value type, and, if the check succeeds, the value in the box is copied out.</span></span>

<span data-ttu-id="6ebee-191">C# の型システムが統一されたということは、実質的には値型が “オンデマンドで” オブジェクトになることができるということです。</span><span class="sxs-lookup"><span data-stu-id="6ebee-191">C#’s unified type system effectively means that value types can become objects "on demand."</span></span> <span data-ttu-id="6ebee-192">こうした統一性があるため、`object` 型を使用する汎用的なライブラリは、参照型と値型の両方で使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ebee-192">Because of the unification, general-purpose libraries that use type `object` can be used with both reference types and value types.</span></span>

<span data-ttu-id="6ebee-193">C# には、フィールド、配列要素、ローカル変数、パラメーターなどの、いくつかの種類の*変数*があります。</span><span class="sxs-lookup"><span data-stu-id="6ebee-193">There are several kinds of *variables* in C#, including fields, array elements, local variables, and parameters.</span></span> <span data-ttu-id="6ebee-194">変数は記憶域の場所を表し、次のように、すべての変数には、その変数に格納できる値を指定する型があります。</span><span class="sxs-lookup"><span data-stu-id="6ebee-194">Variables represent storage locations, and every variable has a type that determines what values can be stored in the variable, as shown below.</span></span>

* <span data-ttu-id="6ebee-195">null 非許容値型</span><span class="sxs-lookup"><span data-stu-id="6ebee-195">Non-nullable value type</span></span>
  - <span data-ttu-id="6ebee-196">型そのものの値</span><span class="sxs-lookup"><span data-stu-id="6ebee-196">A value of that exact type</span></span>
* <span data-ttu-id="6ebee-197">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="6ebee-197">Nullable value type</span></span>
  - <span data-ttu-id="6ebee-198">`null` 値、またはその型そのものの値</span><span class="sxs-lookup"><span data-stu-id="6ebee-198">A `null` value or a value of that exact type</span></span>
* <span data-ttu-id="6ebee-199">object</span><span class="sxs-lookup"><span data-stu-id="6ebee-199">object</span></span>
  - <span data-ttu-id="6ebee-200">`null` 参照、任意の参照型のオブジェクトへの参照、または任意の値型のボックス化された値への参照</span><span class="sxs-lookup"><span data-stu-id="6ebee-200">A `null` reference, a reference to an object of any reference type, or a reference to a boxed value of any value type</span></span>
* <span data-ttu-id="6ebee-201">クラス型</span><span class="sxs-lookup"><span data-stu-id="6ebee-201">Class type</span></span>
  - <span data-ttu-id="6ebee-202">`null` 参照、そのクラス型のインスタンスへの参照、またはそのクラス型から派生したクラスのインスタンスへの参照</span><span class="sxs-lookup"><span data-stu-id="6ebee-202">A `null` reference, a reference to an instance of that class type, or a reference to an instance of a class derived from that class type</span></span>
* <span data-ttu-id="6ebee-203">インターフェイスの型</span><span class="sxs-lookup"><span data-stu-id="6ebee-203">Interface type</span></span>
  - <span data-ttu-id="6ebee-204">`null` 参照、そのインターフェイスの型を実装するクラス型のインスタンスへの参照、またはそのインターフェイス型を実装する値型のボックス化された値への参照</span><span class="sxs-lookup"><span data-stu-id="6ebee-204">A `null` reference, a reference to an instance of a class type that implements that interface type, or a reference to a boxed value of a value type that implements that interface type</span></span>
* <span data-ttu-id="6ebee-205">配列型</span><span class="sxs-lookup"><span data-stu-id="6ebee-205">Array type</span></span>
  - <span data-ttu-id="6ebee-206">`null` 参照、その配列型のインスタンスへの参照、または互換性のある配列型のインスタンスへの参照</span><span class="sxs-lookup"><span data-stu-id="6ebee-206">A `null` reference, a reference to an instance of that array type, or a reference to an instance of a compatible array type</span></span>
* <span data-ttu-id="6ebee-207">デリゲート型</span><span class="sxs-lookup"><span data-stu-id="6ebee-207">Delegate type</span></span>
  - <span data-ttu-id="6ebee-208">`null` 参照、またはそのデリゲート型と互換性のあるインスタンスへの参照</span><span class="sxs-lookup"><span data-stu-id="6ebee-208">A `null` reference or a reference to an instance of a compatible delegate type</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="6ebee-209">[前へ](program-structure.md)
> [次へ](expressions.md)</span><span class="sxs-lookup"><span data-stu-id="6ebee-209">[Previous](program-structure.md)
[Next](expressions.md)</span></span>
