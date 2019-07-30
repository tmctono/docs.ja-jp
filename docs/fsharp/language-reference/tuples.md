---
title: タプル
description: 名前のないF#が順序付けられた値 (場合によっては異なる型) をグループ化したタプルについて説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 7a15d7e0c6c9b42118dd75066f02cbb2e05335fc
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630238"
---
# <a name="tuples"></a><span data-ttu-id="e3a72-103">タプル</span><span class="sxs-lookup"><span data-stu-id="e3a72-103">Tuples</span></span>

<span data-ttu-id="e3a72-104">*タプル*は、名前はないが順序付けられた値のさまざまな種類のグループです。</span><span class="sxs-lookup"><span data-stu-id="e3a72-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="e3a72-105">タプルは参照型か構造体のどちらかです。</span><span class="sxs-lookup"><span data-stu-id="e3a72-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="e3a72-106">構文</span><span class="sxs-lookup"><span data-stu-id="e3a72-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a><span data-ttu-id="e3a72-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e3a72-107">Remarks</span></span>

<span data-ttu-id="e3a72-108">各*要素*前の構文では有効な F# 式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e3a72-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="e3a72-109">使用例</span><span class="sxs-lookup"><span data-stu-id="e3a72-109">Examples</span></span>

<span data-ttu-id="e3a72-110">組の例としては、同じ型または異なる型のペア、3要素などがあります。</span><span class="sxs-lookup"><span data-stu-id="e3a72-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="e3a72-111">次のコードに例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="e3a72-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a><span data-ttu-id="e3a72-112">個別の値の取得</span><span class="sxs-lookup"><span data-stu-id="e3a72-112">Obtaining Individual Values</span></span>

<span data-ttu-id="e3a72-113">次のコードに示すように、パターンマッチングを使用すると、タプル要素の名前にアクセスして割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e3a72-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="e3a72-114">また、binding を使用`match` `let`して、式の外側にあるパターン一致を使用してタプルを分解することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3a72-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="e3a72-115">または、組の一致を関数への入力としてパターン化できます。</span><span class="sxs-lookup"><span data-stu-id="e3a72-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="e3a72-116">タプルの要素が1つだけ必要な場合は、不要な値に新しい名前を作成しないように、ワイルドカード文字 (アンダースコア) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3a72-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="e3a72-117">参照タプルから構造体タプルに要素をコピーすることも簡単です。</span><span class="sxs-lookup"><span data-stu-id="e3a72-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="e3a72-118">関数`fst` と`snd` (参照タプルのみ) は、組の1番目と2番目の要素をそれぞれ返します。</span><span class="sxs-lookup"><span data-stu-id="e3a72-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="e3a72-119">トリプルの3番目の要素を返す組み込み関数はありませんが、次のように簡単に記述できます。</span><span class="sxs-lookup"><span data-stu-id="e3a72-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="e3a72-120">通常、個々のタプル要素にアクセスするには、パターンマッチングを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3a72-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="e3a72-121">タプルの使用</span><span class="sxs-lookup"><span data-stu-id="e3a72-121">Using Tuples</span></span>

<span data-ttu-id="e3a72-122">タプルは、次の例に示すように、関数から複数の値を返す便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e3a72-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="e3a72-123">この例では、整数除算を実行し、組の最初のメンバーとして演算の丸められた結果を返し、その剰余をペアの2番目のメンバーとして返します。</span><span class="sxs-lookup"><span data-stu-id="e3a72-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="e3a72-124">通常の関数構文によって暗黙的に指定される関数の引数の暗黙のカリー化を回避する場合は、関数の引数としてタプルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3a72-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="e3a72-125">関数`let sum a b = a + b`を定義するための通常の構文を使用すると、次のコードに示すように、関数の最初の引数の部分的なアプリケーションである関数を定義できます。</span><span class="sxs-lookup"><span data-stu-id="e3a72-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="e3a72-126">パラメーターとしてタプルを使用すると、カリー化が無効になります。</span><span class="sxs-lookup"><span data-stu-id="e3a72-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="e3a72-127">詳細については、「[関数](./functions/index.md)」の「引数の部分的な適用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3a72-127">For more information, see "Partial Application of Arguments" in [Functions](./functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="e3a72-128">タプル型の名前</span><span class="sxs-lookup"><span data-stu-id="e3a72-128">Names of Tuple Types</span></span>

<span data-ttu-id="e3a72-129">組である型の名前を記述する場合は、 `*`記号を使用して要素を区切ります。</span><span class="sxs-lookup"><span data-stu-id="e3a72-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="e3a72-130">`int`、、および`string`などので構成される組の場合、型は次のように書き込まれます。 `(10, 10.0, "ten")` `float`</span><span class="sxs-lookup"><span data-stu-id="e3a72-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="e3a72-131">組とC#の相互運用</span><span class="sxs-lookup"><span data-stu-id="e3a72-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="e3a72-132">C#7.0 では、言語にタプルが導入されました。</span><span class="sxs-lookup"><span data-stu-id="e3a72-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="e3a72-133">C# のタプルは構造体と F# の構造体のタプルに同じです。</span><span class="sxs-lookup"><span data-stu-id="e3a72-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="e3a72-134">とC#相互運用する必要がある場合は、構造体の組を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3a72-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="e3a72-135">これは簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e3a72-135">This is easy to do.</span></span>  <span data-ttu-id="e3a72-136">たとえば、C# クラスに組を渡すし、これは、タプルでも、その結果を消費する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="e3a72-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

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

<span data-ttu-id="e3a72-137">F#コードでは、パラメーターとして構造体のタプルを渡し、その結果を構造体のタプルとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3a72-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="e3a72-138">参照タプルと構造体組の間の変換</span><span class="sxs-lookup"><span data-stu-id="e3a72-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="e3a72-139">参照タプルと構造体タプルはまったく異なる基になる表現を持つため、暗黙的に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="e3a72-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="e3a72-140">つまり、次のようなコードはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="e3a72-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="e3a72-141">1つのタプルに対してパターン一致をパターン化し、構成要素を使用してもう一方を構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3a72-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="e3a72-142">例:</span><span class="sxs-lookup"><span data-stu-id="e3a72-142">For example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="e3a72-143">参照タプルのコンパイルされた形式</span><span class="sxs-lookup"><span data-stu-id="e3a72-143">Compiled Form of Reference Tuples</span></span>

<span data-ttu-id="e3a72-144">このセクションでは、コンパイル時の組の形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3a72-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="e3a72-145">ここに記載されている情報は、.NET Framework 3.5 以下を対象としている場合を除き、読み取る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e3a72-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="e3a72-146">組は、複数のジェネリック型のいずれかのオブジェクトにコンパイル`System.Tuple`され、アリティでオーバーロードされます。また、型パラメーターの数も示されます。</span><span class="sxs-lookup"><span data-stu-id="e3a72-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="e3a72-147">タプル型は、C# または Visual Basic の場合など、別の言語からそれらを表示するとき、またはを F# の構成要素に対応していないツールを使用しているときに、このフォームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3a72-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="e3a72-148">これら`Tuple`の型は .NET Framework 4 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e3a72-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="e3a72-149">コンパイラのバージョンを使用して .NET Framework の以前のバージョンをターゲットにする場合[System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) F# コア ライブラリのバージョン 2.0 から。</span><span class="sxs-lookup"><span data-stu-id="e3a72-149">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="e3a72-150">このライブラリの型は、.NET Framework の2.0、3.0、3.5 の各バージョンを対象とするアプリケーションにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3a72-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="e3a72-151">型の転送を使用して、.NET Framework 2.0 と .NET Framework 4 F# コンポーネント間のバイナリの互換性を確保します。</span><span class="sxs-lookup"><span data-stu-id="e3a72-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="e3a72-152">構造体のコンパイルされた形式のタプル</span><span class="sxs-lookup"><span data-stu-id="e3a72-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="e3a72-153">構造体のタプル (たとえば、 `struct (x, y)`)は、参照タプルとは根本的に異なります。</span><span class="sxs-lookup"><span data-stu-id="e3a72-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="e3a72-154">それらは<xref:System.ValueTuple>型にコンパイルされるか、アリティによってオーバーロードされるか、または型パラメーターの数になります。</span><span class="sxs-lookup"><span data-stu-id="e3a72-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="e3a72-155">これらは [C# 7.0 のタプル](../../csharp/tuples.md)および[Visual Basic 2017のタプル](../../visual-basic/programming-guide/language-features/data-types/tuples.md)と同等であり、双方向で相互運用できます。</span><span class="sxs-lookup"><span data-stu-id="e3a72-155">They are equivalent to [C# 7.0 Tuples](../../csharp/tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3a72-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3a72-156">See also</span></span>

- [<span data-ttu-id="e3a72-157">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="e3a72-157">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="e3a72-158">F# の型</span><span class="sxs-lookup"><span data-stu-id="e3a72-158">F# Types</span></span>](fsharp-types.md)
