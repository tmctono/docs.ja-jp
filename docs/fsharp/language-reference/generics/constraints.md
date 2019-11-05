---
title: 制約
description: ジェネリック型F#パラメーターに適用される制約について説明し、ジェネリック型または関数の型引数の要件を指定します。
ms.date: 05/16/2016
ms.openlocfilehash: 70a8bec1ad67d7e814cb7a96b1876bb22399c5e7
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425015"
---
# <a name="constraints"></a><span data-ttu-id="a957e-103">制約</span><span class="sxs-lookup"><span data-stu-id="a957e-103">Constraints</span></span>

<span data-ttu-id="a957e-104">このトピックでは、ジェネリック型パラメーターに適用して、ジェネリック型またはジェネリック関数の型引数の要件を指定できる制約について説明します。</span><span class="sxs-lookup"><span data-stu-id="a957e-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="a957e-105">構文</span><span class="sxs-lookup"><span data-stu-id="a957e-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="a957e-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="a957e-106">Remarks</span></span>

<span data-ttu-id="a957e-107">ジェネリック型で使用できる型を制限するために、いくつかの異なる制約を適用できます。</span><span class="sxs-lookup"><span data-stu-id="a957e-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="a957e-108">次の表に、これらの制約の一覧とその説明を示します。</span><span class="sxs-lookup"><span data-stu-id="a957e-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="a957e-109">制約</span><span class="sxs-lookup"><span data-stu-id="a957e-109">Constraint</span></span>|<span data-ttu-id="a957e-110">構文</span><span class="sxs-lookup"><span data-stu-id="a957e-110">Syntax</span></span>|<span data-ttu-id="a957e-111">説明</span><span class="sxs-lookup"><span data-stu-id="a957e-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="a957e-112">型の制約</span><span class="sxs-lookup"><span data-stu-id="a957e-112">Type Constraint</span></span>|<span data-ttu-id="a957e-113">*型パラメーター* :&gt;*型*</span><span class="sxs-lookup"><span data-stu-id="a957e-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="a957e-114">指定された型は、指定された型と同じか、または指定された型と同じである必要があります。または、型がインターフェイスの場合は、指定された型がインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a957e-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="a957e-115">Null 制約</span><span class="sxs-lookup"><span data-stu-id="a957e-115">Null Constraint</span></span>|<span data-ttu-id="a957e-116">*型パラメーター* : null</span><span class="sxs-lookup"><span data-stu-id="a957e-116">*type-parameter* : null</span></span>|<span data-ttu-id="a957e-117">指定された型は、null リテラルをサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a957e-117">The provided type must support the null literal.</span></span> <span data-ttu-id="a957e-118">これには、すべての .NET オブジェクトF#の種類が含まれますが、list、tuple、function、class、record、または union 型は含まれません。</span><span class="sxs-lookup"><span data-stu-id="a957e-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="a957e-119">明示的なメンバー制約</span><span class="sxs-lookup"><span data-stu-id="a957e-119">Explicit Member Constraint</span></span>|<span data-ttu-id="a957e-120">[(]*型パラメーター* [または...または*型パラメーター*)]: (*メンバー-signature*)</span><span class="sxs-lookup"><span data-stu-id="a957e-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature*)</span></span>|<span data-ttu-id="a957e-121">指定された型引数の少なくとも1つに、指定されたシグネチャを持つメンバーが必要です。一般的な使用を目的としたものではありません。</span><span class="sxs-lookup"><span data-stu-id="a957e-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="a957e-122">メンバーは、明示的なメンバー制約の有効なターゲットとなるように、型または暗黙的な型拡張の一部に対して明示的に定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a957e-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="a957e-123">コンストラクターの制約</span><span class="sxs-lookup"><span data-stu-id="a957e-123">Constructor Constraint</span></span>|<span data-ttu-id="a957e-124">*型パラメーター* : (new: unit-&gt; ' a)</span><span class="sxs-lookup"><span data-stu-id="a957e-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="a957e-125">指定された型には、パラメーターなしのコンストラクターが必要です。</span><span class="sxs-lookup"><span data-stu-id="a957e-125">The provided type must have a parameterless constructor.</span></span>|
|<span data-ttu-id="a957e-126">値型の制約</span><span class="sxs-lookup"><span data-stu-id="a957e-126">Value Type Constraint</span></span>|<span data-ttu-id="a957e-127">: struct</span><span class="sxs-lookup"><span data-stu-id="a957e-127">: struct</span></span>|<span data-ttu-id="a957e-128">指定された型は .NET 値型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a957e-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="a957e-129">参照型の制約</span><span class="sxs-lookup"><span data-stu-id="a957e-129">Reference Type Constraint</span></span>|<span data-ttu-id="a957e-130">: 構造体ではありません。</span><span class="sxs-lookup"><span data-stu-id="a957e-130">: not struct</span></span>|<span data-ttu-id="a957e-131">指定された型は .NET 参照型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a957e-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="a957e-132">列挙型の制約</span><span class="sxs-lookup"><span data-stu-id="a957e-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="a957e-133">: enum&lt;*基になる型*&gt;</span><span class="sxs-lookup"><span data-stu-id="a957e-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="a957e-134">指定された型は、指定された基になる型を持つ列挙型でなければなりません。一般的な使用を目的としたものではありません。</span><span class="sxs-lookup"><span data-stu-id="a957e-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="a957e-135">デリゲート制約</span><span class="sxs-lookup"><span data-stu-id="a957e-135">Delegate Constraint</span></span>|<span data-ttu-id="a957e-136">:&lt;*タプル*のデリゲート、*戻り値の型*&gt;</span><span class="sxs-lookup"><span data-stu-id="a957e-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="a957e-137">指定された型は、指定された引数と戻り値を持つデリゲート型である必要があります。一般的な使用を目的としたものではありません。</span><span class="sxs-lookup"><span data-stu-id="a957e-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="a957e-138">比較制約</span><span class="sxs-lookup"><span data-stu-id="a957e-138">Comparison Constraint</span></span>|<span data-ttu-id="a957e-139">: 比較</span><span class="sxs-lookup"><span data-stu-id="a957e-139">: comparison</span></span>|<span data-ttu-id="a957e-140">指定された型は、比較をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a957e-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="a957e-141">等値制約</span><span class="sxs-lookup"><span data-stu-id="a957e-141">Equality Constraint</span></span>|<span data-ttu-id="a957e-142">: 等値</span><span class="sxs-lookup"><span data-stu-id="a957e-142">: equality</span></span>|<span data-ttu-id="a957e-143">指定された型は、等価性をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a957e-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="a957e-144">アンマネージド制約</span><span class="sxs-lookup"><span data-stu-id="a957e-144">Unmanaged Constraint</span></span>|<span data-ttu-id="a957e-145">: アンマネージド</span><span class="sxs-lookup"><span data-stu-id="a957e-145">: unmanaged</span></span>|<span data-ttu-id="a957e-146">指定された型はアンマネージ型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a957e-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="a957e-147">アンマネージ型は、特定のプリミティブ型 (`sbyte`、`byte`、`char`、`nativeint`、`unativeint`、`float32`、`float`、`int16`、`uint16`、`int32`、`uint32`、`int64`、`uint64`、、または `decimal`)、列挙型、`nativeptr<_>`、またはフィールドがすべてのアンマネージ型である非ジェネリック構造体。</span><span class="sxs-lookup"><span data-stu-id="a957e-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr<_>`, or a non-generic structure whose fields are all unmanaged types.</span></span>|

<span data-ttu-id="a957e-148">制約を追加する必要があるのは、制約の種類では使用できても、一般的な型では使用できない機能をコードで使用する必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="a957e-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="a957e-149">たとえば、型制約を使用してクラス型を指定する場合は、ジェネリック関数またはジェネリック型で、そのクラスのメソッドのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a957e-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="a957e-150">制約を指定することは、型パラメーターを明示的に記述するときに必要になることがあります。これは、制約がないため、コンパイラは、実行時に型に対して提供される可能性があるすべての型で使用できることを検証する方法がないためです。引き.</span><span class="sxs-lookup"><span data-stu-id="a957e-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="a957e-151">コードでF#使用する最も一般的な制約は、基本クラスまたはインターフェイスを指定する型制約です。</span><span class="sxs-lookup"><span data-stu-id="a957e-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="a957e-152">他の制約は、特定の機能F#を実装するためにライブラリによって使用されます。たとえば、算術演算子に対して演算子のオーバーロードを実装するためにF#使用される明示的なメンバー制約や、主に共通言語ランタイムでサポートされている制約の完全なセットをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a957e-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="a957e-153">型の推論プロセスでは、一部の制約がコンパイラによって自動的に推論されます。</span><span class="sxs-lookup"><span data-stu-id="a957e-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="a957e-154">たとえば、関数で `+` 演算子を使用した場合、コンパイラは、式で使用されている変数型の明示的なメンバー制約を推論します。</span><span class="sxs-lookup"><span data-stu-id="a957e-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="a957e-155">次のコードは、いくつかの制約宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="a957e-155">The following code illustrates some constraint declarations:</span></span>

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> =
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a><span data-ttu-id="a957e-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="a957e-156">See also</span></span>

- [<span data-ttu-id="a957e-157">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="a957e-157">Generics</span></span>](index.md)
- [<span data-ttu-id="a957e-158">制約</span><span class="sxs-lookup"><span data-stu-id="a957e-158">Constraints</span></span>](constraints.md)
