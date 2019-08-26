---
title: ポインター型 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 4d0801cd81e00c84be278b44730058798b0acfa9
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588197"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="fe4a8-102">ポインター型 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="fe4a8-102">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="fe4a8-103">unsafe コンテキストの型には、ポインター型、値型、または参照型を設定できます。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="fe4a8-104">ポインター型の宣言は、次のいずれかの形式になります。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-104">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="fe4a8-105">ポインター型の `*` の前に指定された型は、**参照型**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-105">The type specified before the `*` in a pointer type is called the **referent type**.</span></span> <span data-ttu-id="fe4a8-106">参照型にできるのは[アンマネージド型](../../language-reference/builtin-types/unmanaged-types.md)だけです。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-106">Only an [unmanaged type](../../language-reference/builtin-types/unmanaged-types.md) can be a referent type.</span></span>

<span data-ttu-id="fe4a8-107">ポインター型は [object](../../language-reference/keywords/object.md) を継承せず、ポインター型と `object` の間で変換を行う方法はありません。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-107">Pointer types do not inherit from [object](../../language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="fe4a8-108">また、ボックス化とボックス化解除もポインターをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-108">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="fe4a8-109">ただし、異なるポインター型の間で変換したり、ポインター型と整数型の間で変換したりすることはできます。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-109">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="fe4a8-110">同じ 1 つの宣言で複数のポインターを宣言する場合、アスタリスク (\*) は基底の型だけに記述します。各ポインター名のプレフィックスとしては使用しません。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-110">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="fe4a8-111">例:</span><span class="sxs-lookup"><span data-stu-id="fe4a8-111">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="fe4a8-112">オブジェクト参照は、それを指すポインターがあってもガベージ コレクションされる可能性があるため、ポインターによって参照や参照を含む[構造体](../../language-reference/keywords/struct.md)を指すことはできません。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-112">A pointer cannot point to a reference or to a [struct](../../language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="fe4a8-113">ガベージ コレクターは、オブジェクトを指すポインター型があるかどうかを追跡しません。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-113">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="fe4a8-114">`myType*` 型のポインター変数の値は、`myType` 型の変数のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-114">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="fe4a8-115">ポインター型の宣言の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-115">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="fe4a8-116">例</span><span class="sxs-lookup"><span data-stu-id="fe4a8-116">Example</span></span>|<span data-ttu-id="fe4a8-117">説明</span><span class="sxs-lookup"><span data-stu-id="fe4a8-117">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="fe4a8-118">`p` は、整数へのポインターです。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-118">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="fe4a8-119">`p` は、整数へのポインターのポインターです。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-119">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="fe4a8-120">`p` は、整数へのポインターの 1 次元配列です。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-120">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="fe4a8-121">`p` は、char へのポインターです。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-121">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="fe4a8-122">`p` は、未知の型へのポインターです。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-122">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="fe4a8-123">ポインター間接演算子 \* を使用すると、ポインター変数が指す位置にあるコンテンツにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-123">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="fe4a8-124">たとえば、次のような宣言があるとします。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-124">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="fe4a8-125">この例の式 `*myVariable` は、`int` に含まれているアドレスの位置にある `myVariable` 変数を示しています。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-125">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="fe4a8-126">トピック「[fixed ステートメント](../../language-reference/keywords/fixed-statement.md)」および「[ポインター変換](./pointer-conversions.md)」に、ポインターの例がいくつか記載されています。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-126">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](./pointer-conversions.md).</span></span> <span data-ttu-id="fe4a8-127">次の例は、`unsafe` キーワードと `fixed` ステートメントの使用例と、内部ポインターのインクリメント方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-127">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="fe4a8-128">このコードは、コンソール アプリケーションの Main 関数に貼り付けて実行することができます</span><span class="sxs-lookup"><span data-stu-id="fe4a8-128">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="fe4a8-129">これらの例は、[-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) コンパイラ オプションを設定してコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-129">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#5)]

<span data-ttu-id="fe4a8-130">間接演算子は、`void*` 型のポインターに適用できません。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-130">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="fe4a8-131">ただし、void ポインターと他のポインター型はキャストを使用して相互に変換できます。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-131">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="fe4a8-132">ポインターは、`null` にできます。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-132">A pointer can be `null`.</span></span> <span data-ttu-id="fe4a8-133">null ポインターに間接演算子を適用すると、実装で定義されている動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-133">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="fe4a8-134">ポインターをメソッド間で引き渡すと、未定義の動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-134">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="fe4a8-135">たとえば、`in`、`out` または `ref` パラメーターを介してポインターをローカル変数に返したり、関数の結果として返したりするメソッドがあるとします。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-135">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="fe4a8-136">ポインターが固定ブロックに設定されていた場合は、そのポインターが指す変数が既に固定されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-136">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="fe4a8-137">次の表は、unsafe コンテキストでポインターに使用できる演算子とステートメントの一覧を示しています。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-137">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="fe4a8-138">演算子/ステートメント</span><span class="sxs-lookup"><span data-stu-id="fe4a8-138">Operator/Statement</span></span>|<span data-ttu-id="fe4a8-139">用途</span><span class="sxs-lookup"><span data-stu-id="fe4a8-139">Use</span></span>|
|-------------------------|---------|
|`*`|<span data-ttu-id="fe4a8-140">ポインターの間接参照を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-140">Performs pointer indirection.</span></span>|
|`->`|<span data-ttu-id="fe4a8-141">ポインター経由で構造体のメンバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-141">Accesses a member of a struct through a pointer.</span></span>|
|`[]`|<span data-ttu-id="fe4a8-142">ポインターにインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-142">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="fe4a8-143">変数のアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-143">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="fe4a8-144">`++` と `--`</span><span class="sxs-lookup"><span data-stu-id="fe4a8-144">`++` and `--`</span></span>|<span data-ttu-id="fe4a8-145">ポインターをインクリメントおよびデクリメントします。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-145">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="fe4a8-146">`+` と `-`</span><span class="sxs-lookup"><span data-stu-id="fe4a8-146">`+` and `-`</span></span>|<span data-ttu-id="fe4a8-147">ポインター演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-147">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="fe4a8-148">`==`、`!=`、`<`、`>`、`<=`、`>=`</span><span class="sxs-lookup"><span data-stu-id="fe4a8-148">`==`, `!=`, `<`, `>`, `<=`, and `>=`</span></span>|<span data-ttu-id="fe4a8-149">ポインターを比較します。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-149">Compares pointers.</span></span>|
|[<span data-ttu-id="fe4a8-150">`stackalloc` 演算子</span><span class="sxs-lookup"><span data-stu-id="fe4a8-150">`stackalloc` operator</span></span>](../../language-reference/operators/stackalloc.md)|<span data-ttu-id="fe4a8-151">スタックにメモリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-151">Allocates memory on the stack.</span></span>|
|[<span data-ttu-id="fe4a8-152">`fixed` ステートメント</span><span class="sxs-lookup"><span data-stu-id="fe4a8-152">`fixed` statement</span></span>](../../language-reference/keywords/fixed-statement.md)|<span data-ttu-id="fe4a8-153">変数を一時的に固定して、そのアドレスを取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-153">Temporarily fixes a variable so that its address may be found.</span></span>|

<span data-ttu-id="fe4a8-154">ポインター関連の演算子について詳しくは、「[ポインターに関連する演算子](../../language-reference/operators/pointer-related-operators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-154">For more information about pointer related operators, see [Pointer related operators](../../language-reference/operators/pointer-related-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fe4a8-155">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="fe4a8-155">C# language specification</span></span>

<span data-ttu-id="fe4a8-156">詳しくは、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の「[ポインター型](~/_csharplang/spec/unsafe-code.md#pointer-types)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fe4a8-156">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fe4a8-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe4a8-157">See also</span></span>

- [<span data-ttu-id="fe4a8-158">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="fe4a8-158">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fe4a8-159">アンセーフ コードとポインター</span><span class="sxs-lookup"><span data-stu-id="fe4a8-159">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="fe4a8-160">ポインター変換</span><span class="sxs-lookup"><span data-stu-id="fe4a8-160">Pointer Conversions</span></span>](pointer-conversions.md)
- [<span data-ttu-id="fe4a8-161">型</span><span class="sxs-lookup"><span data-stu-id="fe4a8-161">Types</span></span>](../../language-reference/keywords/types.md)
- [<span data-ttu-id="fe4a8-162">unsafe</span><span class="sxs-lookup"><span data-stu-id="fe4a8-162">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
