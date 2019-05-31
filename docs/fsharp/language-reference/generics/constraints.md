---
title: 制約
description: についてF#ジェネリック型または関数の型引数の要件を指定するジェネリック型パラメーターに適用される制約。
ms.date: 05/16/2016
ms.openlocfilehash: bb6625636f0465dd608ae2e8a8986d043b62b6e4
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "66378195"
---
# <a name="constraints"></a><span data-ttu-id="aeff4-103">制約</span><span class="sxs-lookup"><span data-stu-id="aeff4-103">Constraints</span></span>

<span data-ttu-id="aeff4-104">このトピックでは、ジェネリックに適用できる制約を説明します、ジェネリック型または関数の型引数の要件を指定するパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="aeff4-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="aeff4-105">構文</span><span class="sxs-lookup"><span data-stu-id="aeff4-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="aeff4-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="aeff4-106">Remarks</span></span>

<span data-ttu-id="aeff4-107">ジェネリック型で使用できる型の制限に適用できるいくつかのさまざまな制約があります。</span><span class="sxs-lookup"><span data-stu-id="aeff4-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="aeff4-108">次の表は、これらの制約の一覧です。</span><span class="sxs-lookup"><span data-stu-id="aeff4-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="aeff4-109">制約</span><span class="sxs-lookup"><span data-stu-id="aeff4-109">Constraint</span></span>|<span data-ttu-id="aeff4-110">構文</span><span class="sxs-lookup"><span data-stu-id="aeff4-110">Syntax</span></span>|<span data-ttu-id="aeff4-111">説明</span><span class="sxs-lookup"><span data-stu-id="aeff4-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="aeff4-112">型制約</span><span class="sxs-lookup"><span data-stu-id="aeff4-112">Type Constraint</span></span>|<span data-ttu-id="aeff4-113">*type-parameter* :&gt; *type*</span><span class="sxs-lookup"><span data-stu-id="aeff4-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="aeff4-114">指定された型は、指定した型から同じか、または派生をする必要があります。 または、型がインターフェイスである場合は、指定された型がインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeff4-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="aeff4-115">Null の制約</span><span class="sxs-lookup"><span data-stu-id="aeff4-115">Null Constraint</span></span>|<span data-ttu-id="aeff4-116">*型パラメーター* : null</span><span class="sxs-lookup"><span data-stu-id="aeff4-116">*type-parameter* : null</span></span>|<span data-ttu-id="aeff4-117">指定された型には、null リテラルをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeff4-117">The provided type must support the null literal.</span></span> <span data-ttu-id="aeff4-118">これには、すべて .NET オブジェクトの種類がない F# リスト、タプル、関数、クラス、レコード、または共用体の型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="aeff4-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="aeff4-119">明示的なメンバー制約</span><span class="sxs-lookup"><span data-stu-id="aeff4-119">Explicit Member Constraint</span></span>|<span data-ttu-id="aeff4-120">[(]*型パラメーター* [または... または*型パラメーター*)]: (*メンバー シグネチャ*)</span><span class="sxs-lookup"><span data-stu-id="aeff4-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature*)</span></span>|<span data-ttu-id="aeff4-121">指定された型引数の少なくとも 1 つを指定したシグネチャを持つメンバーがあります。一般的な用途は想定されていません。</span><span class="sxs-lookup"><span data-stu-id="aeff4-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="aeff4-122">メンバーする必要がありますか、明示的に定義するメンバーの明示的な制約の有効なターゲットにするには、型または暗黙的な型の拡張機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="aeff4-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="aeff4-123">コンス トラクターの制約</span><span class="sxs-lookup"><span data-stu-id="aeff4-123">Constructor Constraint</span></span>|<span data-ttu-id="aeff4-124">*type-parameter* : ( new : unit -&gt; 'a )</span><span class="sxs-lookup"><span data-stu-id="aeff4-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="aeff4-125">指定された型には、既定のコンス トラクターが必要です。</span><span class="sxs-lookup"><span data-stu-id="aeff4-125">The provided type must have a default constructor.</span></span>|
|<span data-ttu-id="aeff4-126">値型の制約</span><span class="sxs-lookup"><span data-stu-id="aeff4-126">Value Type Constraint</span></span>|<span data-ttu-id="aeff4-127">: 構造体</span><span class="sxs-lookup"><span data-stu-id="aeff4-127">: struct</span></span>|<span data-ttu-id="aeff4-128">指定された型は、.NET 値型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeff4-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="aeff4-129">参照型の制約</span><span class="sxs-lookup"><span data-stu-id="aeff4-129">Reference Type Constraint</span></span>|<span data-ttu-id="aeff4-130">: 構造体ではありません</span><span class="sxs-lookup"><span data-stu-id="aeff4-130">: not struct</span></span>|<span data-ttu-id="aeff4-131">指定された型は、.NET 参照型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeff4-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="aeff4-132">列挙型の制約</span><span class="sxs-lookup"><span data-stu-id="aeff4-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="aeff4-133">: enum&lt;*underlying-type*&gt;</span><span class="sxs-lookup"><span data-stu-id="aeff4-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="aeff4-134">指定された型を指定した基になる型を持つ列挙型である必要があります。一般的な用途は想定されていません。</span><span class="sxs-lookup"><span data-stu-id="aeff4-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="aeff4-135">デリゲートの制約</span><span class="sxs-lookup"><span data-stu-id="aeff4-135">Delegate Constraint</span></span>|<span data-ttu-id="aeff4-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span><span class="sxs-lookup"><span data-stu-id="aeff4-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="aeff4-137">必要がありますを指定した引数を持つデリゲート型であるし、戻り値を指定された型一般的な用途は想定されていません。</span><span class="sxs-lookup"><span data-stu-id="aeff4-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="aeff4-138">比較の制約</span><span class="sxs-lookup"><span data-stu-id="aeff4-138">Comparison Constraint</span></span>|<span data-ttu-id="aeff4-139">: 比較</span><span class="sxs-lookup"><span data-stu-id="aeff4-139">: comparison</span></span>|<span data-ttu-id="aeff4-140">指定された型には、比較をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeff4-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="aeff4-141">等しいかどうかの制約</span><span class="sxs-lookup"><span data-stu-id="aeff4-141">Equality Constraint</span></span>|<span data-ttu-id="aeff4-142">: 等しいかどうか</span><span class="sxs-lookup"><span data-stu-id="aeff4-142">: equality</span></span>|<span data-ttu-id="aeff4-143">指定された型には、等しいかどうかをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeff4-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="aeff4-144">アンマネージド制約</span><span class="sxs-lookup"><span data-stu-id="aeff4-144">Unmanaged Constraint</span></span>|<span data-ttu-id="aeff4-145">: 管理されていません。</span><span class="sxs-lookup"><span data-stu-id="aeff4-145">: unmanaged</span></span>|<span data-ttu-id="aeff4-146">指定された型は、アンマネージ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeff4-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="aeff4-147">アンマネージ型は、プリミティブ型 (`sbyte`、 `byte`、 `char`、 `nativeint`、 `unativeint`、 `float32`、 `float`、 `int16`、 `uint16`、 `int32`、 `uint32`、 `int64`、 `uint64`、または`decimal`)、列挙型、 `nativeptr<_>`、または非ジェネリック構造体のフィールドは、すべてのアンマネージ型。</span><span class="sxs-lookup"><span data-stu-id="aeff4-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr<_>`, or a non-generic structure whose fields are all unmanaged types.</span></span>|

<span data-ttu-id="aeff4-148">一般に、制約の種類がない型で使用できる機能を使用するコードがある場合に制約を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeff4-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="aeff4-149">たとえば、クラス型を指定する型の制約を使用する場合は、ジェネリック関数または型では、そのクラスのメソッドのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="aeff4-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="aeff4-150">制約を指定する場合があります必要な型パラメーターを明示的に記述する場合、制約、コンパイラがあるないため使用している機能は型の実行時に指定する場合がある任意の型では使用できないことを検証する方法にパラメーター。</span><span class="sxs-lookup"><span data-stu-id="aeff4-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="aeff4-151">使用する最も一般的な制約F#コードが型制約が基底クラスまたはインターフェイスを指定します。</span><span class="sxs-lookup"><span data-stu-id="aeff4-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="aeff4-152">その他の制約が、演算子、算術演算子のオーバー ロードを実装するために使用または主に F# をサポート、完了するために提供される明示的なメンバー制約など、特定の機能を実装するために F# ライブラリによって使用されるか、共通言語ランタイムでサポートされている制約のセット。</span><span class="sxs-lookup"><span data-stu-id="aeff4-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="aeff4-153">型の推論プロセス中にいくつかの制約は、コンパイラによって自動的に推論されます。</span><span class="sxs-lookup"><span data-stu-id="aeff4-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="aeff4-154">たとえば、使用する場合、`+`演算子関数で、コンパイラは、明示的なメンバー制約式で使用される変数の型を推測します。</span><span class="sxs-lookup"><span data-stu-id="aeff4-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="aeff4-155">次のコードは、いくつかの制約の宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="aeff4-155">The following code illustrates some constraint declarations.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="aeff4-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="aeff4-156">See also</span></span>

- [<span data-ttu-id="aeff4-157">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="aeff4-157">Generics</span></span>](index.md)
- [<span data-ttu-id="aeff4-158">制約</span><span class="sxs-lookup"><span data-stu-id="aeff4-158">Constraints</span></span>](constraints.md)
