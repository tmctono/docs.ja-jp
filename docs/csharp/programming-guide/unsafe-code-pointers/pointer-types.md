---
title: ポインター型 - C# プログラミング ガイド
description: ポインター型について説明します。 さまざまなポインターの例とコード例を確認し、使用可能なその他のリソースを参照してください。
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 9c62a31f9a4a090fe56fb10ac45fe2f93f1b036e
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382036"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="e7a0b-104">ポインター型 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e7a0b-104">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="e7a0b-105">unsafe コンテキストの型には、ポインター型、値型、または参照型を設定できます。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-105">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="e7a0b-106">ポインター型の宣言は、次のいずれかの形式になります。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-106">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="e7a0b-107">ポインター型の `*` の前に指定された型は、**参照型**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-107">The type specified before the `*` in a pointer type is called the **referent type**.</span></span> <span data-ttu-id="e7a0b-108">参照型にできるのは[アンマネージド型](../../language-reference/builtin-types/unmanaged-types.md)だけです。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-108">Only an [unmanaged type](../../language-reference/builtin-types/unmanaged-types.md) can be a referent type.</span></span>

<span data-ttu-id="e7a0b-109">ポインター型は [object](../../language-reference/builtin-types/reference-types.md) を継承せず、ポインター型と `object` の間で変換を行う方法はありません。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-109">Pointer types do not inherit from [object](../../language-reference/builtin-types/reference-types.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="e7a0b-110">また、ボックス化とボックス化解除もポインターをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-110">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="e7a0b-111">ただし、異なるポインター型の間で変換したり、ポインター型と整数型の間で変換したりすることはできます。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-111">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="e7a0b-112">同じ 1 つの宣言で複数のポインターを宣言する場合、アスタリスク (\*) は基底の型だけに記述します。各ポインター名のプレフィックスとしては使用しません。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-112">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="e7a0b-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-113">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="e7a0b-114">オブジェクト参照は、それを指すポインターがあってもガベージ コレクションされる可能性があるため、ポインターによって参照や参照を含む[構造体](../../language-reference/builtin-types/struct.md)を指すことはできません。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-114">A pointer cannot point to a reference or to a [struct](../../language-reference/builtin-types/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="e7a0b-115">ガベージ コレクターは、オブジェクトを指すポインター型があるかどうかを追跡しません。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-115">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="e7a0b-116">`myType*` 型のポインター変数の値は、`myType` 型の変数のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-116">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="e7a0b-117">ポインター型の宣言の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-117">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="e7a0b-118">例</span><span class="sxs-lookup"><span data-stu-id="e7a0b-118">Example</span></span>|<span data-ttu-id="e7a0b-119">説明</span><span class="sxs-lookup"><span data-stu-id="e7a0b-119">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="e7a0b-120">`p` は、整数へのポインターです。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-120">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="e7a0b-121">`p` は、整数へのポインターのポインターです。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-121">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="e7a0b-122">`p` は、整数へのポインターの 1 次元配列です。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-122">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="e7a0b-123">`p` は、char へのポインターです。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-123">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="e7a0b-124">`p` は、未知の型へのポインターです。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-124">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="e7a0b-125">ポインター間接演算子 \* を使用すると、ポインター変数が指す位置にあるコンテンツにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-125">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="e7a0b-126">たとえば、次のような宣言があるとします。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-126">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="e7a0b-127">この例の式 `*myVariable` は、`int` に含まれているアドレスの位置にある `myVariable` 変数を示しています。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-127">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="e7a0b-128">トピック「[fixed ステートメント](../../language-reference/keywords/fixed-statement.md)」および「[ポインター変換](./pointer-conversions.md)」に、ポインターの例がいくつか記載されています。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-128">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](./pointer-conversions.md).</span></span> <span data-ttu-id="e7a0b-129">次の例は、`unsafe` キーワードと `fixed` ステートメントの使用例と、内部ポインターのインクリメント方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-129">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="e7a0b-130">このコードは、コンソール アプリケーションの Main 関数に貼り付けて実行することができます</span><span class="sxs-lookup"><span data-stu-id="e7a0b-130">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="e7a0b-131">これらの例は、[-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) コンパイラ オプションを設定してコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-131">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](snippets/FixedKeywordExamples.cs#5)]

<span data-ttu-id="e7a0b-132">間接演算子は、`void*` 型のポインターに適用できません。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-132">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="e7a0b-133">ただし、void ポインターと他のポインター型はキャストを使用して相互に変換できます。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-133">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="e7a0b-134">ポインターは、`null` にできます。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-134">A pointer can be `null`.</span></span> <span data-ttu-id="e7a0b-135">null ポインターに間接演算子を適用すると、実装で定義されている動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-135">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="e7a0b-136">ポインターをメソッド間で引き渡すと、未定義の動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-136">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="e7a0b-137">たとえば、`in`、`out` または `ref` パラメーターを介してポインターをローカル変数に返したり、関数の結果として返したりするメソッドがあるとします。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-137">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="e7a0b-138">ポインターが固定ブロックに設定されていた場合は、そのポインターが指す変数が既に固定されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-138">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="e7a0b-139">次の表は、unsafe コンテキストでポインターに使用できる演算子とステートメントの一覧を示しています。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-139">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="e7a0b-140">演算子/ステートメント</span><span class="sxs-lookup"><span data-stu-id="e7a0b-140">Operator/Statement</span></span>|<span data-ttu-id="e7a0b-141">使用</span><span class="sxs-lookup"><span data-stu-id="e7a0b-141">Use</span></span>|
|-------------------------|---------|
|`*`|<span data-ttu-id="e7a0b-142">ポインターの間接参照を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-142">Performs pointer indirection.</span></span>|
|`->`|<span data-ttu-id="e7a0b-143">ポインター経由で構造体のメンバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-143">Accesses a member of a struct through a pointer.</span></span>|
|`[]`|<span data-ttu-id="e7a0b-144">ポインターにインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-144">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="e7a0b-145">変数のアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-145">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="e7a0b-146">`++` および `--`</span><span class="sxs-lookup"><span data-stu-id="e7a0b-146">`++` and `--`</span></span>|<span data-ttu-id="e7a0b-147">ポインターをインクリメントおよびデクリメントします。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-147">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="e7a0b-148">`+` および `-`</span><span class="sxs-lookup"><span data-stu-id="e7a0b-148">`+` and `-`</span></span>|<span data-ttu-id="e7a0b-149">ポインター演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-149">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="e7a0b-150">`==`、`!=`、`<`、`>`、`<=`、`>=`</span><span class="sxs-lookup"><span data-stu-id="e7a0b-150">`==`, `!=`, `<`, `>`, `<=`, and `>=`</span></span>|<span data-ttu-id="e7a0b-151">ポインターを比較します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-151">Compares pointers.</span></span>|
|[`stackalloc`](../../language-reference/operators/stackalloc.md)|<span data-ttu-id="e7a0b-152">スタックにメモリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-152">Allocates memory on the stack.</span></span>|
|[<span data-ttu-id="e7a0b-153">`fixed` ステートメント</span><span class="sxs-lookup"><span data-stu-id="e7a0b-153">`fixed` statement</span></span>](../../language-reference/keywords/fixed-statement.md)|<span data-ttu-id="e7a0b-154">変数を一時的に固定して、そのアドレスを取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-154">Temporarily fixes a variable so that its address may be found.</span></span>|

<span data-ttu-id="e7a0b-155">ポインター関連の演算子について詳しくは、「[ポインターに関連する演算子](../../language-reference/operators/pointer-related-operators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-155">For more information about pointer related operators, see [Pointer related operators](../../language-reference/operators/pointer-related-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e7a0b-156">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="e7a0b-156">C# language specification</span></span>

<span data-ttu-id="e7a0b-157">詳しくは、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の「[ポインター型](~/_csharplang/spec/unsafe-code.md#pointer-types)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-157">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7a0b-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7a0b-158">See also</span></span>

- [<span data-ttu-id="e7a0b-159">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e7a0b-159">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e7a0b-160">アンセーフ コードとポインター</span><span class="sxs-lookup"><span data-stu-id="e7a0b-160">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="e7a0b-161">ポインター変換</span><span class="sxs-lookup"><span data-stu-id="e7a0b-161">Pointer Conversions</span></span>](pointer-conversions.md)
- [<span data-ttu-id="e7a0b-162">参照型</span><span class="sxs-lookup"><span data-stu-id="e7a0b-162">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="e7a0b-163">値型</span><span class="sxs-lookup"><span data-stu-id="e7a0b-163">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="e7a0b-164">unsafe</span><span class="sxs-lookup"><span data-stu-id="e7a0b-164">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
