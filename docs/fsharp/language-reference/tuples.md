---
title: タプル
description: については、F#タプル、名前のないが、順序付けされた値のさまざまな種類のグループ化します。
ms.date: 05/16/2016
ms.openlocfilehash: 950451ad1672e0c9fc609773f1bc32fc13636ddb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645113"
---
# <a name="tuples"></a><span data-ttu-id="bb5a7-103">タプル</span><span class="sxs-lookup"><span data-stu-id="bb5a7-103">Tuples</span></span>

<span data-ttu-id="bb5a7-104">*タプル*は、名前はないが順序付けられた値のさまざまな種類のグループです。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="bb5a7-105">タプルは参照型か構造体のどちらかです。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb5a7-106">構文</span><span class="sxs-lookup"><span data-stu-id="bb5a7-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a><span data-ttu-id="bb5a7-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="bb5a7-107">Remarks</span></span>

<span data-ttu-id="bb5a7-108">各*要素*前の構文では有効な F# 式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="bb5a7-109">使用例</span><span class="sxs-lookup"><span data-stu-id="bb5a7-109">Examples</span></span>

<span data-ttu-id="bb5a7-110">ペア、3 要素、および同じまたは別の型のタプルの例が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="bb5a7-111">いくつかの例は、次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a><span data-ttu-id="bb5a7-112">個々 の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-112">Obtaining Individual Values</span></span>

<span data-ttu-id="bb5a7-113">使えばパターン マッチングにアクセスしたり、タプルの要素の名前を割り当てる次のコードに示すようにできます。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="bb5a7-114">外部のパターン マッチングを使用してタプルを分解することもできます、`match`式を使用して`let`バインド。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="bb5a7-115">パターンを作成できますまたは関数への入力として組の一致します。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="bb5a7-116">タプルの 1 つだけの要素が必要な場合、必要のない値の新しい名前を作成しないようにする、ワイルドカード文字 (アンダー スコア) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="bb5a7-117">構造体タプルに参照組から要素のコピーも簡単です。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="bb5a7-118">関数は、`fst`と`snd`(組のみを参照)、最初し、2 番目、タプルの要素のそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="bb5a7-119">3 つの要素の 3 番目の要素を返す組み込み関数はありませんが、次のように簡単に書き込む 1 つ。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="bb5a7-120">一般に、パターン マッチングを使用して、タプルの個々 の要素にアクセスすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="bb5a7-121">タプルを使用してください。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-121">Using Tuples</span></span>

<span data-ttu-id="bb5a7-122">タプルは、次の例に示すように、関数から複数の値を返す便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="bb5a7-123">この例では、整数除算を実行し、結果を丸め、タプルのペアの最初のメンバーとして操作と、ペアの 2 番目のメンバーとして残りの部分を返します。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="bb5a7-124">暗黙的なカリー化関数の引数は、通常の関数の構文で指定されるを回避する場合、組も関数の引数として使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="bb5a7-125">関数を定義するには、通常の構文`let sum a b = a + b`次のコードに示すように、関数の最初の引数の部分的なアプリケーションである関数を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="bb5a7-126">パラメーターとして組を使用するには、カリー化が無効にします。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="bb5a7-127">詳細については、「部分的な引数アプリケーション」を参照してください[関数](functions/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-127">For more information, see "Partial Application of Arguments" in [Functions](functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="bb5a7-128">タプル型の名前</span><span class="sxs-lookup"><span data-stu-id="bb5a7-128">Names of Tuple Types</span></span>

<span data-ttu-id="bb5a7-129">使用する組である型の名前を記述するときに、`*`要素を区切る記号。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="bb5a7-130">構成される組の`int`、 `float`、および`string`など`(10, 10.0, "ten")`種類は次のように書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="bb5a7-131">C# のタプルとの相互運用</span><span class="sxs-lookup"><span data-stu-id="bb5a7-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="bb5a7-132">C# 7.0 では、言語に組が導入されました。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="bb5a7-133">C# のタプルは構造体と F# の構造体のタプルに同じです。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="bb5a7-134">C# を使用した相互運用する必要がある場合は、構造体のタプルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="bb5a7-135">これは、簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-135">This is easy to do.</span></span>  <span data-ttu-id="bb5a7-136">たとえば、C# クラスに組を渡すし、これは、タプルでも、その結果を消費する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

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

<span data-ttu-id="bb5a7-137">F#コード、パラメーターとして構造体の組を渡すし、構造体タプルとして結果を消費することができます。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="bb5a7-138">参照の組と構造体のタプル間の変換</span><span class="sxs-lookup"><span data-stu-id="bb5a7-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="bb5a7-139">参照の組と構造体のタプルは、完全に別の基になる表現であるため、暗黙的に変換可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="bb5a7-140">これは、次のコードはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="bb5a7-141">パターンを作成する必要があります 1 つのタプルが一致し、他の構成要素を構築します。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="bb5a7-142">例:</span><span class="sxs-lookup"><span data-stu-id="bb5a7-142">For example:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="bb5a7-143">参照の組のコンパイル済みの形式</span><span class="sxs-lookup"><span data-stu-id="bb5a7-143">Compiled Form of Reference Tuples</span></span>

<span data-ttu-id="bb5a7-144">このセクションでは、している、コンパイル時に、タプルの形式が説明します。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="bb5a7-145">ここにある情報は、.NET Framework 3.5 を対象としている場合を除き、読み取りに必要なまたは下限はありません。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="bb5a7-146">タプルは、すべての名前付き、いくつかのジェネリック型のいずれかのオブジェクトにコンパイル`System.Tuple`アリティ、または型パラメーターの数をオーバー ロードされます。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="bb5a7-147">タプル型は、C# または Visual Basic の場合など、別の言語からそれらを表示するとき、またはを F# の構成要素に対応していないツールを使用しているときに、このフォームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="bb5a7-148">`Tuple`型が .NET Framework 4 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="bb5a7-149">コンパイラのバージョンを使用して .NET Framework の以前のバージョンをターゲットにする場合[System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) F# コア ライブラリのバージョン 2.0 から。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-149">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="bb5a7-150">このライブラリ内の型は、2.0、3.0、および .NET Framework 3.5 のバージョンを対象とするアプリケーションに対してのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="bb5a7-151">型の転送を使用して、.NET Framework 2.0 と .NET Framework 4 F# コンポーネント間のバイナリの互換性を確保します。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="bb5a7-152">構造体のタプルのコンパイル済みの形式</span><span class="sxs-lookup"><span data-stu-id="bb5a7-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="bb5a7-153">構造体のタプル (たとえば、 `struct (x, y)`)は、参照タプルとは根本的に異なります。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="bb5a7-154">それらは<xref:System.ValueTuple>型にコンパイルされるか、アリティによってオーバーロードされるか、または型パラメーターの数になります。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="bb5a7-155">これらは [C# 7.0 のタプル](../../csharp/tuples.md)および[Visual Basic 2017のタプル](../../visual-basic/programming-guide/language-features/data-types/tuples.md)と同等であり、双方向で相互運用できます。</span><span class="sxs-lookup"><span data-stu-id="bb5a7-155">They are equivalent to [C# 7.0 Tuples](../../csharp/tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb5a7-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb5a7-156">See also</span></span>

- [<span data-ttu-id="bb5a7-157">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="bb5a7-157">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="bb5a7-158">F# の型</span><span class="sxs-lookup"><span data-stu-id="bb5a7-158">F# Types</span></span>](fsharp-types.md)
