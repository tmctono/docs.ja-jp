---
title: C# の型と変数 - C# 言語のツアー
description: C# における型の定義と変数の宣言について説明します
ms.date: 08/10/2016
ms.assetid: f8a8051e-0049-43f1-b594-9c84cc7b1224
ms.openlocfilehash: 5623b4a1e85508ea7206df2c73b7aaffcbc3fbb1
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881976"
---
# <a name="types-and-variables"></a><span data-ttu-id="45f44-103">型と変数</span><span class="sxs-lookup"><span data-stu-id="45f44-103">Types and variables</span></span>

<span data-ttu-id="45f44-104">C# には、*値型*と*参照型*という 2 種類の型があります。</span><span class="sxs-lookup"><span data-stu-id="45f44-104">There are two kinds of types in C#: *value types* and *reference types*.</span></span> <span data-ttu-id="45f44-105">値型の変数が直接データを格納するのに対して、参照型の変数はデータへの参照を格納し、後者はオブジェクトとして知られています。</span><span class="sxs-lookup"><span data-stu-id="45f44-105">Variables of value types directly contain their data whereas variables of reference types store references to their data, the latter being known as objects.</span></span> <span data-ttu-id="45f44-106">参照型を使用すると 2 つの変数が同じオブジェクトを参照できるため、1 つの変数に対する演算によって、もう一方の変数によって参照されるオブジェクトに影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="45f44-106">With reference types, it is possible for two variables to reference the same object and thus possible for operations on one variable to affect the object referenced by the other variable.</span></span> <span data-ttu-id="45f44-107">値型の場合、各変数が独自のデータ コピーを保持し、1 つの変数に対する演算で別の変数に影響を与えることはできません (`ref` と `out` のパラメーターの変数の場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="45f44-107">With value types, the variables each have their own copy of the data, and it is not possible for operations on one to affect the other (except in the case of `ref` and `out` parameter variables).</span></span>

<span data-ttu-id="45f44-108">C# の値型はさらに、*単純型*、*列挙型*、*構造体型*、および *null 許容値型* に分けられます。</span><span class="sxs-lookup"><span data-stu-id="45f44-108">C#’s value types are further divided into *simple types*, *enum types*, *struct types*, and *nullable value types*.</span></span> <span data-ttu-id="45f44-109">C# の参照型はさらに、*クラス型*、*インターフェイス型*、*配列型*、および*デリゲート型*に分けられます。</span><span class="sxs-lookup"><span data-stu-id="45f44-109">C#’s reference types are further divided into *class types*, *interface types*, *array types*, and *delegate types*.</span></span>

<span data-ttu-id="45f44-110">以下は、C# の型システムの概要です。</span><span class="sxs-lookup"><span data-stu-id="45f44-110">The following provides an overview of C#’s type system.</span></span>

* <span data-ttu-id="45f44-111">[値型][ValueTypes]</span><span class="sxs-lookup"><span data-stu-id="45f44-111">[Value types][ValueTypes]</span></span>
  - <span data-ttu-id="45f44-112">[単純型][SimpleTypes]</span><span class="sxs-lookup"><span data-stu-id="45f44-112">[Simple types][SimpleTypes]</span></span>
    * <span data-ttu-id="45f44-113">符号付きの整数: `sbyte`、`short`、`int`、`long`</span><span class="sxs-lookup"><span data-stu-id="45f44-113">Signed integral: `sbyte`, `short`, `int`, `long`</span></span>
    * <span data-ttu-id="45f44-114">符号なしの整数: `byte`、`ushort`、`uint`、`ulong`</span><span class="sxs-lookup"><span data-stu-id="45f44-114">Unsigned integral: `byte`, `ushort`, `uint`, `ulong`</span></span>
    * <span data-ttu-id="45f44-115">Unicode 文字: `char`</span><span class="sxs-lookup"><span data-stu-id="45f44-115">Unicode characters: `char`</span></span>
    * <span data-ttu-id="45f44-116">IEEE バイナリ浮動小数点数: `float`、`double`</span><span class="sxs-lookup"><span data-stu-id="45f44-116">IEEE binary floating-point: `float`, `double`</span></span>
    * <span data-ttu-id="45f44-117">高精度 10 進浮動小数点数: `decimal`</span><span class="sxs-lookup"><span data-stu-id="45f44-117">High-precision decimal floating-point: `decimal`</span></span>
    * <span data-ttu-id="45f44-118">ブール値: `bool`</span><span class="sxs-lookup"><span data-stu-id="45f44-118">Boolean: `bool`</span></span>
  - <span data-ttu-id="45f44-119">[列挙型][EnumTypes]</span><span class="sxs-lookup"><span data-stu-id="45f44-119">[Enum types][EnumTypes]</span></span>
    * <span data-ttu-id="45f44-120">`enum E {...}` 形式のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="45f44-120">User-defined types of the form `enum E {...}`</span></span>
  - <span data-ttu-id="45f44-121">[構造体の型][StructTypes]</span><span class="sxs-lookup"><span data-stu-id="45f44-121">[Struct types][StructTypes]</span></span>
    * <span data-ttu-id="45f44-122">`struct S {...}` 形式のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="45f44-122">User-defined types of the form `struct S {...}`</span></span>
  - <span data-ttu-id="45f44-123">[null 許容値型][NullableTypes]</span><span class="sxs-lookup"><span data-stu-id="45f44-123">[Nullable value types][NullableTypes]</span></span>
    * <span data-ttu-id="45f44-124">`null` 値を持つその他すべての値型の拡張子</span><span class="sxs-lookup"><span data-stu-id="45f44-124">Extensions of all other value types with a `null` value</span></span>
* <span data-ttu-id="45f44-125">[参照型][ReferenceTypes]</span><span class="sxs-lookup"><span data-stu-id="45f44-125">[Reference types][ReferenceTypes]</span></span>
  - <span data-ttu-id="45f44-126">[クラス型][ClassTypes]</span><span class="sxs-lookup"><span data-stu-id="45f44-126">[Class types][ClassTypes]</span></span>
    * <span data-ttu-id="45f44-127">その他すべての型の最終的な基底クラス: `object`</span><span class="sxs-lookup"><span data-stu-id="45f44-127">Ultimate base class of all other types: `object`</span></span>
    * <span data-ttu-id="45f44-128">Unicode 文字列: `string`</span><span class="sxs-lookup"><span data-stu-id="45f44-128">Unicode strings: `string`</span></span>
    * <span data-ttu-id="45f44-129">`class C {...}` 形式のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="45f44-129">User-defined types of the form `class C {...}`</span></span>
  - <span data-ttu-id="45f44-130">[インターフェイス型][InterfaceTypes]</span><span class="sxs-lookup"><span data-stu-id="45f44-130">[Interface types][InterfaceTypes]</span></span>
    * <span data-ttu-id="45f44-131">`interface I {...}` 形式のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="45f44-131">User-defined types of the form `interface I {...}`</span></span>
  - <span data-ttu-id="45f44-132">[配列型][ArrayTypes]</span><span class="sxs-lookup"><span data-stu-id="45f44-132">[Array types][ArrayTypes]</span></span>
    * <span data-ttu-id="45f44-133">1 次元または多次元、たとえば `int[]` および `int[,]`</span><span class="sxs-lookup"><span data-stu-id="45f44-133">Single- and multi-dimensional, for example, `int[]` and `int[,]`</span></span>
  - <span data-ttu-id="45f44-134">[デリゲート型][DelegateTypes]</span><span class="sxs-lookup"><span data-stu-id="45f44-134">[Delegate types][DelegateTypes]</span></span>
    * <span data-ttu-id="45f44-135">`delegate int D(...)` 形式のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="45f44-135">User-defined types of the form `delegate int D(...)`</span></span>

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

<span data-ttu-id="45f44-136">数値型について詳しくは、「[整数型の一覧表](../language-reference/keywords/integral-types-table.md)」および「[浮動小数点型の一覧表](../language-reference/keywords/floating-point-types-table.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="45f44-136">For more information about numeric types, see [Integral types table](../language-reference/keywords/integral-types-table.md) and [Floating-point types table](../language-reference/keywords/floating-point-types-table.md).</span></span>

<span data-ttu-id="45f44-137">C# の `bool` 型はブール値を表すのに使用します。値は `true` か `false` のどちらかです。</span><span class="sxs-lookup"><span data-stu-id="45f44-137">C#’s `bool` type is used to represent Boolean values—values that are either `true` or `false`.</span></span>

<span data-ttu-id="45f44-138">C# における文字および文字列の処理では、Unicode エンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="45f44-138">Character and string processing in C# uses Unicode encoding.</span></span> <span data-ttu-id="45f44-139">`char` 型は UTF-16 コード単位を表し、`string` 型は一連の UTF-16 コード単位を表します。</span><span class="sxs-lookup"><span data-stu-id="45f44-139">The `char` type represents a UTF-16 code unit, and the `string` type represents a sequence of UTF-16 code units.</span></span>

<span data-ttu-id="45f44-140">C# プログラムでは*型宣言*を使用して新しい型を作成します。</span><span class="sxs-lookup"><span data-stu-id="45f44-140">C# programs use *type declarations* to create new types.</span></span> <span data-ttu-id="45f44-141">型宣言は、新しい型の名前とメンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="45f44-141">A type declaration specifies the name and the members of the new type.</span></span> <span data-ttu-id="45f44-142">C# の型カテゴリのうち 5 つはユーザー定義が可能です。クラス型、構造体型、インターフェイス型、列挙型、そしてデリゲート型です。</span><span class="sxs-lookup"><span data-stu-id="45f44-142">Five of C#’s categories of types are user-definable: class types, struct types, interface types, enum types, and delegate types.</span></span>

<span data-ttu-id="45f44-143">`class` 型は、データ メンバー (フィールド) と関数メンバー (メソッド、プロパティ、その他) を含むデータ構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="45f44-143">A `class` type defines a data structure that contains data members (fields) and function members (methods, properties, and others).</span></span> <span data-ttu-id="45f44-144">クラス型では、単一継承とポリモーフィズムをサポートします。このメカニズムによって派生クラスが基底クラスを拡張して特殊化できます。</span><span class="sxs-lookup"><span data-stu-id="45f44-144">Class types support single inheritance and polymorphism, mechanisms whereby derived classes can extend and specialize base classes.</span></span>

<span data-ttu-id="45f44-145">`struct` 型は、データ メンバーおよび関数メンバーで構造体を表す点において、クラス型に似ています。</span><span class="sxs-lookup"><span data-stu-id="45f44-145">A `struct` type is similar to a class type in that it represents a structure with data members and function members.</span></span> <span data-ttu-id="45f44-146">ただしクラスと異なり、構造体は値型で、通常はヒープ割り当てが不要です。</span><span class="sxs-lookup"><span data-stu-id="45f44-146">However, unlike classes, structs are value types and do not typically require heap allocation.</span></span> <span data-ttu-id="45f44-147">構造体型はユーザー指定の継承をサポートせず、すべての構造体型は暗黙的に `object` 型を継承します。</span><span class="sxs-lookup"><span data-stu-id="45f44-147">Struct types do not support user-specified inheritance, and all struct types implicitly inherit from type `object`.</span></span>

<span data-ttu-id="45f44-148">`interface` 型は、パブリック関数メンバーの名前付きセットとしてコントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="45f44-148">An `interface` type defines a contract as a named set of public function members.</span></span> <span data-ttu-id="45f44-149">`interface` を実装する `class` または `struct` は、インターフェイスの関数メンバーの実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45f44-149">A `class` or `struct` that implements an `interface` must provide implementations of the interface’s function members.</span></span> <span data-ttu-id="45f44-150">`interface` は複数の基底インターフェイスから継承することがあり、`class` または `struct` は複数のインターフェイスを実装することがあります。</span><span class="sxs-lookup"><span data-stu-id="45f44-150">An `interface` may inherit from multiple base interfaces, and a `class` or `struct` may implement multiple interfaces.</span></span>

<span data-ttu-id="45f44-151">`delegate` 型は、特定のパラメーター リストおよび戻り値を使用してメソッドへの参照を表します。</span><span class="sxs-lookup"><span data-stu-id="45f44-151">A `delegate` type represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="45f44-152">デリゲートを使用すると、変数に割り当ててパラメーターとして渡すことのできるエンティティとして、メソッドを処理できます。</span><span class="sxs-lookup"><span data-stu-id="45f44-152">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="45f44-153">デリゲートは、関数型言語で提供される関数の型に似ています。</span><span class="sxs-lookup"><span data-stu-id="45f44-153">Delegates are analogous to function types provided by functional languages.</span></span> <span data-ttu-id="45f44-154">さらに、他のいくつかの言語にみられる関数ポインターの概念に似ていますが、関数ポインターと異なり、デリゲートはオブジェクト指向でタイプ セーフです。</span><span class="sxs-lookup"><span data-stu-id="45f44-154">They are also similar to the concept of function pointers found in some other languages, but unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="45f44-155">`class`、`struct`、`interface` および `delegate`の型はすべてジェネリックをサポートし、他の型と共にパラメーター化できます。</span><span class="sxs-lookup"><span data-stu-id="45f44-155">The `class`, `struct`, `interface` and `delegate` types all support generics, whereby they can be parameterized with other types.</span></span>

<span data-ttu-id="45f44-156">`enum` 型は、名前付き定数を持つ固有の型です。</span><span class="sxs-lookup"><span data-stu-id="45f44-156">An `enum` type is a distinct type with named constants.</span></span> <span data-ttu-id="45f44-157">`enum` 型にはそれぞれ基になる型があり、これは 8 つの整数型のいずれかでなければいけません。</span><span class="sxs-lookup"><span data-stu-id="45f44-157">Every `enum` type has an underlying type, which must be one of the eight integral types.</span></span> <span data-ttu-id="45f44-158">`enum` 型の値のセットは、その基になる型の値のセットと同じです。</span><span class="sxs-lookup"><span data-stu-id="45f44-158">The set of values of an `enum` type is the same as the set of values of the underlying type.</span></span>

<span data-ttu-id="45f44-159">C# は、あらゆる型の 1 次元および多次元の配列をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="45f44-159">C# supports single- and multi-dimensional arrays of any type.</span></span> <span data-ttu-id="45f44-160">上記の型とは異なり、配列型は使用前に宣言する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="45f44-160">Unlike the types listed above, array types do not have to be declared before they can be used.</span></span> <span data-ttu-id="45f44-161">代わりに配列型は、角かっこで囲んだ型名を後に付けることにより構成されます。</span><span class="sxs-lookup"><span data-stu-id="45f44-161">Instead, array types are constructed by following a type name with square brackets.</span></span> <span data-ttu-id="45f44-162">たとえば、`int[]` は `int` の 1 次元配列で、`int[,]` は `int` の 2 次元配列、そして `int[][]` は `int` の 1 次元配列の 1 次元配列です。</span><span class="sxs-lookup"><span data-stu-id="45f44-162">For example, `int[]` is a single-dimensional array of `int`, `int[,]` is a two-dimensional array of `int`, and `int[][]` is a single-dimensional array of single-dimensional array of `int`.</span></span>

<span data-ttu-id="45f44-163">null 許容値型もまた、使用前に宣言する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="45f44-163">Nullable value types also do not have to be declared before they can be used.</span></span> <span data-ttu-id="45f44-164">null 非許容値型 `T` のそれぞれについて、対応する null 許容値型 `T?` があり、これは追加値 `null` を保持することができます。</span><span class="sxs-lookup"><span data-stu-id="45f44-164">For each non-nullable value type `T` there is a corresponding nullable value type `T?`, which can hold an additional value, `null`.</span></span> <span data-ttu-id="45f44-165">たとえば、`int?` は任意の 32 ビット整数または `null` 値を保持できる型です。</span><span class="sxs-lookup"><span data-stu-id="45f44-165">For instance, `int?` is a type that can hold any 32-bit integer or the value `null`.</span></span>

<span data-ttu-id="45f44-166">C# の型システムは、任意の型の値を `object` として扱うように統一されています。</span><span class="sxs-lookup"><span data-stu-id="45f44-166">C#’s type system is unified such that a value of any type can be treated as an `object`.</span></span> <span data-ttu-id="45f44-167">C# における型はすべて、直接的または間接的に `object` クラス型から派生し、`object` はすべての型の究極の基底クラスです。</span><span class="sxs-lookup"><span data-stu-id="45f44-167">Every type in C# directly or indirectly derives from the `object` class type, and `object` is the ultimate base class of all types.</span></span> <span data-ttu-id="45f44-168">参照型の値は、値を単純に `object` 型としてみなすことによってオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="45f44-168">Values of reference types are treated as objects simply by viewing the values as type `object`.</span></span> <span data-ttu-id="45f44-169">値型の値は、*ボックス化*と*ボックス化解除操作*を実行することによって、オブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="45f44-169">Values of value types are treated as objects by performing *boxing* and *unboxing operations*.</span></span> <span data-ttu-id="45f44-170">次の例では、`int` 値は `object` 値に変換され、また `int` に戻されます。</span><span class="sxs-lookup"><span data-stu-id="45f44-170">In the following example, an `int` value is converted to `object` and back again to `int`.</span></span>

[!code-csharp[Boxing](../../../samples/snippets/csharp/tour/types-and-variables/Program.cs#L1-L10)]

<span data-ttu-id="45f44-171">値型の値を `object` 型に変換すると、"ボックス" とも呼ばれる `object` インスタンスが値を保持するために割り当てられ、値がそのボックスにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="45f44-171">When a value of a value type is converted to type `object`, an `object` instance, also called a "box", is allocated to hold the value, and the value is copied into that box.</span></span> <span data-ttu-id="45f44-172">逆に、`object` 参照が値型にキャストされると、参照先の `object` が適切な値型のボックスかどうかが確認され、確認が成功すると、ボックスの値がコピーされます。</span><span class="sxs-lookup"><span data-stu-id="45f44-172">Conversely, when an `object` reference is cast to a value type, a check is made that the referenced `object` is a box of the correct value type, and, if the check succeeds, the value in the box is copied out.</span></span>

<span data-ttu-id="45f44-173">C# の型システムが統一されたということは、実質的には値型が “オンデマンドで” オブジェクトになることができるということです。</span><span class="sxs-lookup"><span data-stu-id="45f44-173">C#’s unified type system effectively means that value types can become objects "on demand."</span></span> <span data-ttu-id="45f44-174">こうした統一性があるため、`object` 型を使用する汎用的なライブラリは、参照型と値型の両方で使用できます。</span><span class="sxs-lookup"><span data-stu-id="45f44-174">Because of the unification, general-purpose libraries that use type `object` can be used with both reference types and value types.</span></span>

<span data-ttu-id="45f44-175">C# には、フィールド、配列要素、ローカル変数、パラメーターなどの、いくつかの種類の*変数*があります。</span><span class="sxs-lookup"><span data-stu-id="45f44-175">There are several kinds of *variables* in C#, including fields, array elements, local variables, and parameters.</span></span> <span data-ttu-id="45f44-176">変数は記憶域の場所を表し、次のように、すべての変数には、その変数に格納できる値を指定する型があります。</span><span class="sxs-lookup"><span data-stu-id="45f44-176">Variables represent storage locations, and every variable has a type that determines what values can be stored in the variable, as shown below.</span></span>

* <span data-ttu-id="45f44-177">null 非許容値型</span><span class="sxs-lookup"><span data-stu-id="45f44-177">Non-nullable value type</span></span>
  - <span data-ttu-id="45f44-178">型そのものの値</span><span class="sxs-lookup"><span data-stu-id="45f44-178">A value of that exact type</span></span>
* <span data-ttu-id="45f44-179">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="45f44-179">Nullable value type</span></span>
  - <span data-ttu-id="45f44-180">`null` 値、またはその型そのものの値</span><span class="sxs-lookup"><span data-stu-id="45f44-180">A `null` value or a value of that exact type</span></span>
* <span data-ttu-id="45f44-181">object</span><span class="sxs-lookup"><span data-stu-id="45f44-181">object</span></span>
  - <span data-ttu-id="45f44-182">`null` 参照、任意の参照型のオブジェクトへの参照、または任意の値型のボックス化された値への参照</span><span class="sxs-lookup"><span data-stu-id="45f44-182">A `null` reference, a reference to an object of any reference type, or a reference to a boxed value of any value type</span></span>
* <span data-ttu-id="45f44-183">クラス型</span><span class="sxs-lookup"><span data-stu-id="45f44-183">Class type</span></span>
  - <span data-ttu-id="45f44-184">`null` 参照、そのクラス型のインスタンスへの参照、またはそのクラス型から派生したクラスのインスタンスへの参照</span><span class="sxs-lookup"><span data-stu-id="45f44-184">A `null` reference, a reference to an instance of that class type, or a reference to an instance of a class derived from that class type</span></span>
* <span data-ttu-id="45f44-185">インターフェイスの型</span><span class="sxs-lookup"><span data-stu-id="45f44-185">Interface type</span></span>
  - <span data-ttu-id="45f44-186">`null` 参照、そのインターフェイスの型を実装するクラス型のインスタンスへの参照、またはそのインターフェイス型を実装する値型のボックス化された値への参照</span><span class="sxs-lookup"><span data-stu-id="45f44-186">A `null` reference, a reference to an instance of a class type that implements that interface type, or a reference to a boxed value of a value type that implements that interface type</span></span>
* <span data-ttu-id="45f44-187">配列型</span><span class="sxs-lookup"><span data-stu-id="45f44-187">Array type</span></span>
  - <span data-ttu-id="45f44-188">`null` 参照、その配列型のインスタンスへの参照、または互換性のある配列型のインスタンスへの参照</span><span class="sxs-lookup"><span data-stu-id="45f44-188">A `null` reference, a reference to an instance of that array type, or a reference to an instance of a compatible array type</span></span>
* <span data-ttu-id="45f44-189">デリゲート型</span><span class="sxs-lookup"><span data-stu-id="45f44-189">Delegate type</span></span>
  - <span data-ttu-id="45f44-190">`null` 参照、またはそのデリゲート型と互換性のあるインスタンスへの参照</span><span class="sxs-lookup"><span data-stu-id="45f44-190">A `null` reference or a reference to an instance of a compatible delegate type</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="45f44-191">[前へ](program-structure.md)
> [次へ](expressions.md)</span><span class="sxs-lookup"><span data-stu-id="45f44-191">[Previous](program-structure.md)
[Next](expressions.md)</span></span>
