---
title: ポインターに関連する演算子 - C# リファレンス
description: ポインターを操作するときに使用できる C# の演算子について説明します。
ms.date: 05/20/2019
author: pkulikov
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- pointer related operators [C#]
- address-of operator [C#]
- '& operator [C#]'
- pointer indirection operator [C#]
- dereference operator [C#]
- '* operator [C#]'
- pointer member access operator [C#]
- -> operator [C#]
- pointer element access [C#]
- '[] operator [C#]'
- pointer arithmetic [C#]
- pointer increment [C#]
- pointer decrement [C#]
- pointer comparison [C#]
ms.openlocfilehash: 9851fcd056eeee33b8f3d7e9d541f9fa43b36d29
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036157"
---
# <a name="pointer-related-operators-c-reference"></a><span data-ttu-id="35cad-103">ポインターに関連する演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="35cad-103">Pointer related operators (C# reference)</span></span>

<span data-ttu-id="35cad-104">次の演算子を使って、ポインターを操作することができます。</span><span class="sxs-lookup"><span data-stu-id="35cad-104">You can use the following operators to work with pointers:</span></span>

- <span data-ttu-id="35cad-105">単項 [`&` (アドレス取得)](#address-of-operator-) 演算子: 変数のアドレスを取得します</span><span class="sxs-lookup"><span data-stu-id="35cad-105">Unary [`&` (address-of)](#address-of-operator-) operator: to get the address of a variable</span></span>
- <span data-ttu-id="35cad-106">単項 [`*` (ポインター間接参照)](#pointer-indirection-operator-) 演算子: ポインターが指す位置にある変数を取得します</span><span class="sxs-lookup"><span data-stu-id="35cad-106">Unary [`*` (pointer indirection)](#pointer-indirection-operator-) operator: to obtain the variable pointed by a pointer</span></span>
- <span data-ttu-id="35cad-107">[`->` (メンバー アクセス)](#pointer-member-access-operator--) および [`[]` (要素アクセス)](#pointer-element-access-operator-) 演算子</span><span class="sxs-lookup"><span data-stu-id="35cad-107">The [`->` (member access)](#pointer-member-access-operator--) and [`[]` (element access)](#pointer-element-access-operator-) operators</span></span>
- <span data-ttu-id="35cad-108">算術演算子 [`+`、`-`、`++`、`--`](#pointer-arithmetic-operators)</span><span class="sxs-lookup"><span data-stu-id="35cad-108">Arithmetic operators [`+`, `-`, `++`, and `--`](#pointer-arithmetic-operators)</span></span>
- <span data-ttu-id="35cad-109">比較演算子 [`==`、`!=`、`<`、`>`、`<=`、`>=`](#pointer-comparison-operators)</span><span class="sxs-lookup"><span data-stu-id="35cad-109">Comparison operators [`==`, `!=`, `<`, `>`, `<=`, and `>=`](#pointer-comparison-operators)</span></span>

<span data-ttu-id="35cad-110">ポインター型については、「[ポインター型](../../programming-guide/unsafe-code-pointers/pointer-types.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35cad-110">For information about pointer types, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

> [!NOTE]
> <span data-ttu-id="35cad-111">ポインターに関するすべての操作には、[unsafe](../keywords/unsafe.md) コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="35cad-111">Any operation with pointers requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="35cad-112">unsafe ブロックを含むコードは、[`-unsafe`](../compiler-options/unsafe-compiler-option.md) コンパイラ オプションでコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="35cad-112">The code that contains unsafe blocks must be compiled with the [`-unsafe`](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span>

## <a name="address-of-operator-"></a> <span data-ttu-id="35cad-113">アドレス取得演算子 &amp;</span><span class="sxs-lookup"><span data-stu-id="35cad-113">Address-of operator &amp;</span></span>

<span data-ttu-id="35cad-114">単項の `&` 演算子からは、そのオペランドのアドレスが返されます。</span><span class="sxs-lookup"><span data-stu-id="35cad-114">The unary `&` operator returns the address of its operand:</span></span>

[!code-csharp[address of local](~/samples/csharp/language-reference/operators/PointerOperators.cs#AddressOf)]

<span data-ttu-id="35cad-115">`&` 演算子のオペランドは、固定変数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="35cad-115">The operand of the `&` operator must be a fixed variable.</span></span> <span data-ttu-id="35cad-116">"*固定*" 変数とは、[ガベージ コレクター](../../../standard/garbage-collection/index.md)の操作によって影響を受けない記憶域の場所に存在する変数です。</span><span class="sxs-lookup"><span data-stu-id="35cad-116">*Fixed* variables are variables that reside in storage locations that are unaffected by operation of the [garbage collector](../../../standard/garbage-collection/index.md).</span></span> <span data-ttu-id="35cad-117">前の例では、ローカル変数 `number` はスタックに存在するので固定変数です。</span><span class="sxs-lookup"><span data-stu-id="35cad-117">In the preceding example, the local variable `number` is a fixed variable, because it resides on the stack.</span></span> <span data-ttu-id="35cad-118">ガベージ コレクターによって影響を受ける可能性がある (たとえば再配置) 記憶域の場所にある変数は、"*移動可能*" 変数と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="35cad-118">Variables that reside in storage locations that can be affected by the garbage collector (for example, relocated) are called *movable* variables.</span></span> <span data-ttu-id="35cad-119">オブジェクト フィールドや配列の要素は、移動可能変数の例です。</span><span class="sxs-lookup"><span data-stu-id="35cad-119">Object fields and array elements are examples of movable variables.</span></span> <span data-ttu-id="35cad-120">[`fixed` ステートメント](../keywords/fixed-statement.md)で移動可能変数を "固定" または "ピン留め" した場合は、移動可能変数のアドレスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="35cad-120">You can get the address of a movable variable if you "fix", or "pin", it with a [`fixed` statement](../keywords/fixed-statement.md).</span></span> <span data-ttu-id="35cad-121">取得したアドレスは、`fixed` ステートメントのブロック内でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="35cad-121">The obtained address is valid only inside the block of a `fixed` statement.</span></span> <span data-ttu-id="35cad-122">`fixed` ステートメントと `&` 演算子の使い方の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="35cad-122">The following example shows how to use a `fixed` statement and the `&` operator:</span></span>

[!code-csharp[address of fixed](~/samples/csharp/language-reference/operators/PointerOperators.cs#AddressOfFixed)]

<span data-ttu-id="35cad-123">定数または値のアドレスを取得できません。</span><span class="sxs-lookup"><span data-stu-id="35cad-123">You can't get the address of a constant or a value.</span></span>

<span data-ttu-id="35cad-124">固定変数と移動可能変数について詳しくは、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の「[Fixed and moveable variables (固定変数と移動可能変数)](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35cad-124">For more information about fixed and movable variables, see the [Fixed and moveable variables](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="35cad-125">2 項 `&` 演算子では、ブール型オペランドの[論理 AND](boolean-logical-operators.md#logical-and-operator-) または整数オペランドの[ビットごとの論理 AND](bitwise-and-shift-operators.md#logical-and-operator-) が計算されます。</span><span class="sxs-lookup"><span data-stu-id="35cad-125">The binary `&` operator computes the [logical AND](boolean-logical-operators.md#logical-and-operator-) of its Boolean operands or the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its integral operands.</span></span>

## <a name="pointer-indirection-operator-"></a><span data-ttu-id="35cad-126">ポインター間接参照演算子 \*</span><span class="sxs-lookup"><span data-stu-id="35cad-126">Pointer indirection operator \*</span></span>

<span data-ttu-id="35cad-127">単項ポインター間接参照演算子 `*` では、オペランドが指し示す変数が取得されます。</span><span class="sxs-lookup"><span data-stu-id="35cad-127">The unary pointer indirection operator `*` obtains the variable to which its operand points.</span></span> <span data-ttu-id="35cad-128">逆参照演算子とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="35cad-128">It's also known as the dereference operator.</span></span> <span data-ttu-id="35cad-129">`*` 演算子のオペランドは、ポインター型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="35cad-129">The operand of the `*` operator must be of a pointer type.</span></span>

[!code-csharp[pointer indirection](~/samples/csharp/language-reference/operators/PointerOperators.cs#PointerIndirection)]

<span data-ttu-id="35cad-130">`void*` 型の式に `*` 演算子を適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="35cad-130">You cannot apply the `*` operator to an expression of type `void*`.</span></span>

<span data-ttu-id="35cad-131">2 項 `*` 演算子では、数値オペランドの[積](arithmetic-operators.md#multiplication-operator-)が計算されます。</span><span class="sxs-lookup"><span data-stu-id="35cad-131">The binary `*` operator computes the [product](arithmetic-operators.md#multiplication-operator-) of its numeric operands.</span></span>

## <a name="pointer-member-access-operator--"></a><span data-ttu-id="35cad-132">ポインター メンバー アクセス演算子 -></span><span class="sxs-lookup"><span data-stu-id="35cad-132">Pointer member access operator -></span></span>

<span data-ttu-id="35cad-133">`->` 演算子では、[ポインターの間接参照](#pointer-indirection-operator-)と[メンバー アクセス](member-access-operators.md#member-access-operator-)が組み合わされます。</span><span class="sxs-lookup"><span data-stu-id="35cad-133">The `->` operator combines [pointer indirection](#pointer-indirection-operator-) and [member access](member-access-operators.md#member-access-operator-).</span></span> <span data-ttu-id="35cad-134">つまり、`x` が `T*` 型のポインターで、`y` が `T` 型のアクセス可能なメンバーである場合に、次のような形式の式を考えます</span><span class="sxs-lookup"><span data-stu-id="35cad-134">That is, if `x` is a pointer of type `T*` and `y` is an accessible member of type `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="35cad-135">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="35cad-135">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="35cad-136">`->` 演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="35cad-136">The following example demonstrates the usage of the `->` operator:</span></span>

[!code-csharp[pointer member access](~/samples/csharp/language-reference/operators/PointerOperators.cs#MemberAccess)]

<span data-ttu-id="35cad-137">`void*` 型の式に `->` 演算子を適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="35cad-137">You cannot apply the `->` operator to an expression of type `void*`.</span></span>

## <a name="pointer-element-access-operator-"></a><span data-ttu-id="35cad-138">ポインター要素アクセス演算子 []</span><span class="sxs-lookup"><span data-stu-id="35cad-138">Pointer element access operator []</span></span>

<span data-ttu-id="35cad-139">ポインター型の式 `p` の場合、`p[n]` の形式のポインター要素アクセスは、`*(p + n)` と評価されます。`n` は、`int`、`uint`、`long`、または `ulong` に暗黙的に変換できる型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="35cad-139">For an expression `p` of a pointer type, a pointer element access of the form `p[n]` is evaluated as `*(p + n)`, where `n` must be of a type implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="35cad-140">ポインターでの `+` 演算子の動作については、「[ポインターに対する整数値の加算または減算](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35cad-140">For information about the behavior of the `+` operator with pointers, see the [Addition or subtraction of an integral value to or from a pointer](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) section.</span></span>

<span data-ttu-id="35cad-141">次の例では、ポインターと `[]` 演算子による配列要素へのアクセス方法を示します。</span><span class="sxs-lookup"><span data-stu-id="35cad-141">The following example demonstrates how to access array elements with a pointer and the `[]` operator:</span></span>

[!code-csharp[pointer element access](~/samples/csharp/language-reference/operators/PointerOperators.cs#ElementAccess)]

<span data-ttu-id="35cad-142">この例では、[`stackalloc` 演算子](stackalloc.md)を使って、スタックにメモリ ブロックを割り当てています。</span><span class="sxs-lookup"><span data-stu-id="35cad-142">The example uses the [`stackalloc` operator](stackalloc.md) to allocate a block of memory on the stack.</span></span>

> [!NOTE]
> <span data-ttu-id="35cad-143">ポインター要素アクセス演算子では、範囲外のエラーはチェックされません。</span><span class="sxs-lookup"><span data-stu-id="35cad-143">The pointer element access operator doesn't check for out-of-bounds errors.</span></span>

<span data-ttu-id="35cad-144">`void*` 型の式でポインター要素アクセスに `[]` を使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="35cad-144">You cannot use `[]` for pointer element access with an expression of type `void*`.</span></span>

<span data-ttu-id="35cad-145">また、[配列要素またはインデクサー アクセス](member-access-operators.md#indexer-operator-)には `[]` 演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="35cad-145">You also can use the `[]` operator for [array element or indexer access](member-access-operators.md#indexer-operator-).</span></span>

## <a name="pointer-arithmetic-operators"></a><span data-ttu-id="35cad-146">ポインター算術演算子</span><span class="sxs-lookup"><span data-stu-id="35cad-146">Pointer arithmetic operators</span></span>

<span data-ttu-id="35cad-147">ポインターで次の算術演算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="35cad-147">You can perform the following arithmetic operations with pointers:</span></span>

- <span data-ttu-id="35cad-148">ポインターに整数値を加算する、またはポインターから整数値を減算する</span><span class="sxs-lookup"><span data-stu-id="35cad-148">Add or subtract an integral value to or from a pointer</span></span>
- <span data-ttu-id="35cad-149">2 個のポインターを減算する</span><span class="sxs-lookup"><span data-stu-id="35cad-149">Subtract two pointers</span></span>
- <span data-ttu-id="35cad-150">ポインターをインクリメントまたはデクリメントする</span><span class="sxs-lookup"><span data-stu-id="35cad-150">Increment or decrement a pointer</span></span>

<span data-ttu-id="35cad-151">`void*` 型のポインターでこれらの演算を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="35cad-151">You cannot perform those operations with pointers of type `void*`.</span></span>

<span data-ttu-id="35cad-152">数値型でサポートされている算術演算については、「[算術演算子](arithmetic-operators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35cad-152">For information about supported arithmetic operations with numeric types, see [Arithmetic operators](arithmetic-operators.md).</span></span>

### <a name="addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer"></a><span data-ttu-id="35cad-153">ポインターへの整数値の加算またはポインターからの整数値の減算</span><span class="sxs-lookup"><span data-stu-id="35cad-153">Addition or subtraction of an integral value to or from a pointer</span></span>

<span data-ttu-id="35cad-154">`T*` 型のポインター `p` と、`int`、`uint`、`long`、または `ulong` に暗黙的に変換できる型の式`n` の場合、加算と減算は次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="35cad-154">For a pointer `p` of type `T*` and an expression `n` of a type implicitly convertible to `int`, `uint`, `long`, or `ulong`, addition and subtraction are defined as follows:</span></span>

- <span data-ttu-id="35cad-155">式 `p + n` および `n + p` では、どちらの場合も、`p` によって与えられるアドレスに `n * sizeof(T)` を加算した結果である、`T*` 型のポインターが生成されます。</span><span class="sxs-lookup"><span data-stu-id="35cad-155">Both `p + n` and `n + p` expressions produce a pointer of type `T*` that results from adding `n * sizeof(T)` to the address given by `p`.</span></span>
- <span data-ttu-id="35cad-156">式 `p - n` では、`p` によって与えられるアドレスから `n * sizeof(T)` を減算した結果である、`T*` 型のポインターが生成されます。</span><span class="sxs-lookup"><span data-stu-id="35cad-156">The `p - n` expression produces a pointer of type `T*` that results from subtracting `n * sizeof(T)` from the address given by `p`.</span></span>

<span data-ttu-id="35cad-157">[`sizeof` 演算子](sizeof.md)では、型のサイズ (バイト単位) が取得されます。</span><span class="sxs-lookup"><span data-stu-id="35cad-157">The [`sizeof` operator](sizeof.md) obtains the size of a type in bytes.</span></span>

<span data-ttu-id="35cad-158">次の例では、ポインターでの `+` 演算子の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="35cad-158">The following example demonstrates the usage of the `+` operator with a pointer:</span></span>

[!code-csharp[pointer addition](~/samples/csharp/language-reference/operators/PointerOperators.cs#AddNumber)]

### <a name="pointer-subtraction"></a><span data-ttu-id="35cad-159">ポインターの減算</span><span class="sxs-lookup"><span data-stu-id="35cad-159">Pointer subtraction</span></span>

<span data-ttu-id="35cad-160">`T*` 型の 2 つのポインター `p1` と `p2` の場合、式 `p1 - p2` では、`p1` と `p2` によって指定されるアドレスの間の差を `sizeof(T)` によって除算した値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="35cad-160">For two pointers `p1` and `p2` of type `T*`, the expression `p1 - p2` produces the difference between the addresses given by `p1` and `p2` divided by `sizeof(T)`.</span></span> <span data-ttu-id="35cad-161">結果の型は `long` です。</span><span class="sxs-lookup"><span data-stu-id="35cad-161">The type of the result is `long`.</span></span> <span data-ttu-id="35cad-162">つまり、`p1 - p2` は `((long)(p1) - (long)(p2)) / sizeof(T)` として計算されます。</span><span class="sxs-lookup"><span data-stu-id="35cad-162">That is, `p1 - p2` is computed as `((long)(p1) - (long)(p2)) / sizeof(T)`.</span></span>

<span data-ttu-id="35cad-163">ポインターの減算の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="35cad-163">The following example demonstrates the pointer subtraction:</span></span>

[!code-csharp[pointer subtraction](~/samples/csharp/language-reference/operators/PointerOperators.cs#SubtractPointers)]

### <a name="pointer-increment-and-decrement"></a><span data-ttu-id="35cad-164">ポインターのインクリメントとデクリメント</span><span class="sxs-lookup"><span data-stu-id="35cad-164">Pointer increment and decrement</span></span>

<span data-ttu-id="35cad-165">`++` インクリメント演算子では、ポインター オペランドに 1 が[加算](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer)されます。</span><span class="sxs-lookup"><span data-stu-id="35cad-165">The `++` increment operator [adds](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 to its pointer operand.</span></span> <span data-ttu-id="35cad-166">`--` デクリメント演算子では、ポインター オペランドから 1 が[減算](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer)されます。</span><span class="sxs-lookup"><span data-stu-id="35cad-166">The `--` decrement operator [subtracts](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 from its pointer operand.</span></span>

<span data-ttu-id="35cad-167">どちらの演算子も、後置 (`p++` および `p--`) と前置 (`++p` および `--p`) の 2 つの形式でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="35cad-167">Both operators are supported in two forms: postfix (`p++` and `p--`) and prefix (`++p` and `--p`).</span></span> <span data-ttu-id="35cad-168">`p++` および `p--` の結果は、演算の "*前*" の `p` の値です。</span><span class="sxs-lookup"><span data-stu-id="35cad-168">The result of `p++` and `p--` is the value of `p` *before* the operation.</span></span> <span data-ttu-id="35cad-169">`++p` および `--p` の結果は、演算の "*後*" の `p` の値です。</span><span class="sxs-lookup"><span data-stu-id="35cad-169">The result of `++p` and `--p` is the value of `p` *after* the operation.</span></span>

<span data-ttu-id="35cad-170">次の例では、後置と前置両方のインクリメント演算子の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="35cad-170">The following example demonstrates the behavior of both postfix and prefix increment operators:</span></span>

[!code-csharp[pointer increment](~/samples/csharp/language-reference/operators/PointerOperators.cs#Increment)]

## <a name="pointer-comparison-operators"></a><span data-ttu-id="35cad-171">ポインター比較演算子</span><span class="sxs-lookup"><span data-stu-id="35cad-171">Pointer comparison operators</span></span>

<span data-ttu-id="35cad-172">`==`、`!=`、`<`、`>`、`<=`、`>=` 演算子を使って、`void*` を含む任意のポインター型のオペランドを比較できます。</span><span class="sxs-lookup"><span data-stu-id="35cad-172">You can use the `==`, `!=`, `<`, `>`, `<=`, and `>=` operators to compare operands of any pointer type, including `void*`.</span></span> <span data-ttu-id="35cad-173">これらの演算子では、2 つのオペランドによって指定されるアドレスが、符号なし整数のように比較されます。</span><span class="sxs-lookup"><span data-stu-id="35cad-173">Those operators compare the addresses given by the two operands as if they were unsigned integers.</span></span>

<span data-ttu-id="35cad-174">他の型のオペランドに対するこれらの演算子の動作については、「[等値演算子](equality-operators.md)」および「[比較演算子](comparison-operators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35cad-174">For information about the behavior of those operators for operands of other types, see the [Equality operators](equality-operators.md) and [Comparison operators](comparison-operators.md) articles.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="35cad-175">演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="35cad-175">Operator precedence</span></span>

<span data-ttu-id="35cad-176">次のポインター関連演算子の一覧は、優先度が高い順に並べられています。</span><span class="sxs-lookup"><span data-stu-id="35cad-176">The following list orders pointer related operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="35cad-177">後置インクリメント `x++` およびデクリメント `x--` 演算子、`->` および `[]` 演算子</span><span class="sxs-lookup"><span data-stu-id="35cad-177">Postfix increment `x++` and decrement `x--` operators and the `->` and `[]` operators</span></span>
- <span data-ttu-id="35cad-178">前置インクリメント `++x` およびデクリメント `--x` 演算子、`&` および `*` 演算子</span><span class="sxs-lookup"><span data-stu-id="35cad-178">Prefix increment `++x` and decrement `--x` operators and the `&` and `*` operators</span></span>
- <span data-ttu-id="35cad-179">加法 `+` および `-` 演算子</span><span class="sxs-lookup"><span data-stu-id="35cad-179">Additive `+` and `-` operators</span></span>
- <span data-ttu-id="35cad-180">比較 `<`、`>`、`<=`、`>=` 演算子</span><span class="sxs-lookup"><span data-stu-id="35cad-180">Comparison `<`, `>`, `<=`, and `>=` operators</span></span>
- <span data-ttu-id="35cad-181">等値 `==` および `!=` 演算子</span><span class="sxs-lookup"><span data-stu-id="35cad-181">Equality `==` and `!=` operators</span></span>

<span data-ttu-id="35cad-182">演算子の優先順位によって定められた評価の順序を変更するには、かっこ `()` を使用します。</span><span class="sxs-lookup"><span data-stu-id="35cad-182">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence.</span></span>

<span data-ttu-id="35cad-183">優先度順に並べられた C# 演算子の完全な一覧については、「[C# 演算子](index.md)」の記事の「[演算子の優先順位](index.md#operator-precedence)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35cad-183">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="35cad-184">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="35cad-184">Operator overloadability</span></span>

<span data-ttu-id="35cad-185">ユーザー定義型では、ポインター関連演算子 `&`、`*`、`->`、`[]` をオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="35cad-185">A user-defined type cannot overload the pointer related operators `&`, `*`, `->`, and `[]`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="35cad-186">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="35cad-186">C# language specification</span></span>

<span data-ttu-id="35cad-187">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35cad-187">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="35cad-188">固定変数と移動可能変数</span><span class="sxs-lookup"><span data-stu-id="35cad-188">Fixed and moveable variables</span></span>](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables)
- [<span data-ttu-id="35cad-189">アドレス取得演算子</span><span class="sxs-lookup"><span data-stu-id="35cad-189">The address-of operator</span></span>](~/_csharplang/spec/unsafe-code.md#the-address-of-operator)
- [<span data-ttu-id="35cad-190">ポインター間接参照</span><span class="sxs-lookup"><span data-stu-id="35cad-190">Pointer indirection</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-indirection)
- [<span data-ttu-id="35cad-191">ポインター メンバー アクセス</span><span class="sxs-lookup"><span data-stu-id="35cad-191">Pointer member access</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-member-access)
- [<span data-ttu-id="35cad-192">ポインター要素アクセス</span><span class="sxs-lookup"><span data-stu-id="35cad-192">Pointer element access</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-element-access)
- [<span data-ttu-id="35cad-193">ポインター算術</span><span class="sxs-lookup"><span data-stu-id="35cad-193">Pointer arithmetic</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-arithmetic)
- [<span data-ttu-id="35cad-194">ポインター インクリメントおよびデクリメント</span><span class="sxs-lookup"><span data-stu-id="35cad-194">Pointer increment and decrement</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-increment-and-decrement)
- [<span data-ttu-id="35cad-195">ポインター比較</span><span class="sxs-lookup"><span data-stu-id="35cad-195">Pointer comparison</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-comparison)

## <a name="see-also"></a><span data-ttu-id="35cad-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="35cad-196">See also</span></span>

- [<span data-ttu-id="35cad-197">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="35cad-197">C# reference</span></span>](../index.md)
- [<span data-ttu-id="35cad-198">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="35cad-198">C# operators</span></span>](index.md)
- [<span data-ttu-id="35cad-199">ポインター型</span><span class="sxs-lookup"><span data-stu-id="35cad-199">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="35cad-200">unsafe キーワード</span><span class="sxs-lookup"><span data-stu-id="35cad-200">unsafe keyword</span></span>](../keywords/unsafe.md)
- [<span data-ttu-id="35cad-201">fixed キーワード</span><span class="sxs-lookup"><span data-stu-id="35cad-201">fixed keyword</span></span>](../keywords/fixed-statement.md)
- [<span data-ttu-id="35cad-202">stackalloc 演算子</span><span class="sxs-lookup"><span data-stu-id="35cad-202">stackalloc operator</span></span>](stackalloc.md)
- [<span data-ttu-id="35cad-203">sizeof 演算子</span><span class="sxs-lookup"><span data-stu-id="35cad-203">sizeof operator</span></span>](sizeof.md)
