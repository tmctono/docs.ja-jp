---
title: タプル
description: '名前のないが順序付けられた値をグループ化する F # のタプルについて説明します。型は異なる可能性があります。'
ms.date: 05/16/2016
ms.openlocfilehash: 5d26fd5d7ec5b4939a895a6d2a6a0d7fc6c6c733
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173290"
---
# <a name="tuples"></a><span data-ttu-id="251dd-103">タプル</span><span class="sxs-lookup"><span data-stu-id="251dd-103">Tuples</span></span>

<span data-ttu-id="251dd-104">*組*は、名前のないが順序付けられた値をグループ化したものであり、型が異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="251dd-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="251dd-105">タプルは、参照型または構造体にすることができます。</span><span class="sxs-lookup"><span data-stu-id="251dd-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="251dd-106">構文</span><span class="sxs-lookup"><span data-stu-id="251dd-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a><span data-ttu-id="251dd-107">解説</span><span class="sxs-lookup"><span data-stu-id="251dd-107">Remarks</span></span>

<span data-ttu-id="251dd-108">前の構文の各*要素*は、任意の有効な F # 式にすることができます。</span><span class="sxs-lookup"><span data-stu-id="251dd-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="251dd-109">例</span><span class="sxs-lookup"><span data-stu-id="251dd-109">Examples</span></span>

<span data-ttu-id="251dd-110">組の例としては、同じ型または異なる型のペア、3要素などがあります。</span><span class="sxs-lookup"><span data-stu-id="251dd-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="251dd-111">次のコードに例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="251dd-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a><span data-ttu-id="251dd-112">個別の値の取得</span><span class="sxs-lookup"><span data-stu-id="251dd-112">Obtaining Individual Values</span></span>

<span data-ttu-id="251dd-113">次のコードに示すように、パターンマッチングを使用すると、タプル要素の名前にアクセスして割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="251dd-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="251dd-114">また、binding を使用して、式の外側にあるパターン一致を使用してタプルを分解することもでき `match` `let` ます。</span><span class="sxs-lookup"><span data-stu-id="251dd-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="251dd-115">または、組の一致を関数への入力としてパターン化できます。</span><span class="sxs-lookup"><span data-stu-id="251dd-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="251dd-116">タプルの要素が1つだけ必要な場合は、不要な値に新しい名前を作成しないように、ワイルドカード文字 (アンダースコア) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="251dd-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="251dd-117">参照タプルから構造体タプルに要素をコピーすることも簡単です。</span><span class="sxs-lookup"><span data-stu-id="251dd-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="251dd-118">関数 `fst` と `snd` (参照タプルのみ) は、組の1番目と2番目の要素をそれぞれ返します。</span><span class="sxs-lookup"><span data-stu-id="251dd-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="251dd-119">トリプルの3番目の要素を返す組み込み関数はありませんが、次のように簡単に記述できます。</span><span class="sxs-lookup"><span data-stu-id="251dd-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="251dd-120">通常、個々のタプル要素にアクセスするには、パターンマッチングを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="251dd-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="251dd-121">タプルの使用</span><span class="sxs-lookup"><span data-stu-id="251dd-121">Using Tuples</span></span>

<span data-ttu-id="251dd-122">タプルは、次の例に示すように、関数から複数の値を返す便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="251dd-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="251dd-123">この例では、整数除算を実行し、組の最初のメンバーとして演算の丸められた結果を返し、その剰余をペアの2番目のメンバーとして返します。</span><span class="sxs-lookup"><span data-stu-id="251dd-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="251dd-124">通常の関数構文によって暗黙的に指定される関数の引数の暗黙のカリー化を回避する場合は、関数の引数としてタプルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="251dd-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="251dd-125">関数を定義するための通常の構文を使用すると、 `let sum a b = a + b` 次のコードに示すように、関数の最初の引数の部分的なアプリケーションである関数を定義できます。</span><span class="sxs-lookup"><span data-stu-id="251dd-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="251dd-126">パラメーターとしてタプルを使用すると、カリー化が無効になります。</span><span class="sxs-lookup"><span data-stu-id="251dd-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="251dd-127">詳細については、「[関数](./functions/index.md)」の「引数の部分的な適用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="251dd-127">For more information, see "Partial Application of Arguments" in [Functions](./functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="251dd-128">タプル型の名前</span><span class="sxs-lookup"><span data-stu-id="251dd-128">Names of Tuple Types</span></span>

<span data-ttu-id="251dd-129">組である型の名前を記述する場合は、記号を使用して `*` 要素を区切ります。</span><span class="sxs-lookup"><span data-stu-id="251dd-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="251dd-130">、、およびなどので構成される組の場合、 `int` 型は次のように `float` 書き込まれ `string` `(10, 10.0, "ten")` ます。</span><span class="sxs-lookup"><span data-stu-id="251dd-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="251dd-131">C# タプルとの相互運用</span><span class="sxs-lookup"><span data-stu-id="251dd-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="251dd-132">C# 7.0 では、言語にタプルが導入されました。</span><span class="sxs-lookup"><span data-stu-id="251dd-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="251dd-133">C# の組は構造体であり、F # の構造体のタプルに相当します。</span><span class="sxs-lookup"><span data-stu-id="251dd-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="251dd-134">C# と相互運用する必要がある場合は、構造体の組を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="251dd-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="251dd-135">これは簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="251dd-135">This is easy to do.</span></span>  <span data-ttu-id="251dd-136">たとえば、組を C# クラスに渡して、その結果を使用する必要があるとします。これは組でもあります。</span><span class="sxs-lookup"><span data-stu-id="251dd-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

```csharp
namespace CSharpTupleInterop
{
    public static class Example
    {
        public static (int, int) AddOneToXAndY((int x, int y) a) =>
            (a.x + 1, a.y + 1);
    }
}
```

<span data-ttu-id="251dd-137">F # コードでは、パラメーターとして構造体のタプルを渡し、その結果を構造体のタプルとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="251dd-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="251dd-138">参照タプルと構造体組の間の変換</span><span class="sxs-lookup"><span data-stu-id="251dd-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="251dd-139">参照タプルと構造体タプルはまったく異なる基になる表現を持つため、暗黙的に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="251dd-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="251dd-140">つまり、次のようなコードはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="251dd-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="251dd-141">1つのタプルに対してパターン一致をパターン化し、構成要素を使用してもう一方を構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="251dd-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="251dd-142">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="251dd-142">For example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="251dd-143">参照タプルのコンパイルされた形式</span><span class="sxs-lookup"><span data-stu-id="251dd-143">Compiled Form of Reference Tuples</span></span>

<span data-ttu-id="251dd-144">このセクションでは、コンパイル時の組の形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="251dd-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="251dd-145">ここに記載されている情報は、.NET Framework 3.5 以下を対象としている場合を除き、読み取る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="251dd-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="251dd-146">組は、複数のジェネリック型のいずれかのオブジェクトにコンパイルされ、 `System.Tuple` アリティでオーバーロードされます。また、型パラメーターの数も示されます。</span><span class="sxs-lookup"><span data-stu-id="251dd-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="251dd-147">タプル型は、C# や Visual Basic などの別の言語から表示する場合や、F # コンストラクトを認識しないツールを使用する場合に、この形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="251dd-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="251dd-148">これらの `Tuple` 型は .NET Framework 4 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="251dd-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="251dd-149">以前のバージョンの .NET Framework を対象としている場合、コンパイラは、F # コアライブラリの2.0 バージョンの[system.string のバージョンを使用](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3)します。</span><span class="sxs-lookup"><span data-stu-id="251dd-149">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="251dd-150">このライブラリの型は、.NET Framework の2.0、3.0、3.5 の各バージョンを対象とするアプリケーションにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="251dd-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="251dd-151">型の転送は、.NET Framework 2.0 と .NET Framework 4 F # のコンポーネント間のバイナリの互換性を確保するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="251dd-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="251dd-152">構造体のコンパイルされた形式のタプル</span><span class="sxs-lookup"><span data-stu-id="251dd-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="251dd-153">構造体の組 (たとえば、 `struct (x, y)` ) は、参照タプルとは基本的に異なります。</span><span class="sxs-lookup"><span data-stu-id="251dd-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="251dd-154">これらは、型、 <xref:System.ValueTuple> アリティによってオーバーロードされる、または型パラメーターの数にコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="251dd-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="251dd-155">これらは、 [C# 7.0 の組](../../csharp/language-reference/builtin-types/value-tuples.md)と[Visual Basic 2017 のタプル](../../visual-basic/programming-guide/language-features/data-types/tuples.md)に相当し、双方向の相互運用が可能です。</span><span class="sxs-lookup"><span data-stu-id="251dd-155">They are equivalent to [C# 7.0 Tuples](../../csharp/language-reference/builtin-types/value-tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="251dd-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="251dd-156">See also</span></span>

- [<span data-ttu-id="251dd-157">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="251dd-157">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="251dd-158">F# の型</span><span class="sxs-lookup"><span data-stu-id="251dd-158">F# Types</span></span>](fsharp-types.md)
