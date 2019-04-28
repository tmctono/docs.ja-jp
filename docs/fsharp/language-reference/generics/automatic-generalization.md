---
title: 自動ジェネリック化
description: どの F# 自動的に一般化引数と関数の種類可能であれば、複数の種類で動作させることについて説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 15ecf8e6f07da19bb015fd028a7465ba8b837190
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937541"
---
# <a name="automatic-generalization"></a><span data-ttu-id="9b8e9-103">自動ジェネリック化</span><span class="sxs-lookup"><span data-stu-id="9b8e9-103">Automatic Generalization</span></span>

<span data-ttu-id="9b8e9-104">F#関数と式の型を評価する推論を使用してに入力します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-104">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="9b8e9-105">このトピックでは、どの F# 自動的に一般化引数と関数の種類可能な限り、複数の種類で動作させることについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-105">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>

## <a name="automatic-generalization"></a><span data-ttu-id="9b8e9-106">自動ジェネリック化</span><span class="sxs-lookup"><span data-stu-id="9b8e9-106">Automatic Generalization</span></span>

<span data-ttu-id="9b8e9-107">F#関数の型の推定の実行時に、コンパイラは、指定されたパラメーターをジェネリックにできるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-107">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="9b8e9-108">コンパイラは、各パラメーターを調べ、関数は、そのパラメーターの特定の種類に依存しているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-108">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="9b8e9-109">そうでない場合をジェネリック型が推論されます。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-109">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="9b8e9-110">次のコード例では、ジェネリックと、コンパイラが推論される関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-110">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="9b8e9-111">型が推論`'a -> 'a -> 'a`します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-111">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="9b8e9-112">種類は、同じの不明な型の 2 つの引数を受け取り、その同じ型の値を返します関数であることを示します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-112">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="9b8e9-113">前の関数ができる理由の 1 つジェネリックは、大きい-演算子よりも (`>`) 自体が、ジェネリック。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-113">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="9b8e9-114">大きい-より演算子がある署名`'a -> 'a -> bool`します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-114">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="9b8e9-115">すべての演算子は、ジェネリックとそのパラメーターの型を一般化することはできません、関数のコードは、非ジェネリック関数または演算子とパラメーターの型を使用している場合。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-115">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="9b8e9-116">`max`は汎用的で、これで使える型など`int`、`float`これに、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-116">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="9b8e9-117">ただし、同じ型の 2 つの引数がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-117">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="9b8e9-118">署名が`'a -> 'a -> 'a`ではなく、`'a -> 'b -> 'a`します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-118">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="9b8e9-119">そのため、次のコードは、型が一致しないため、エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-119">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="9b8e9-120">`max`関数でも使用できますか大きい方をサポートする任意の型の演算子よりもします。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-120">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="9b8e9-121">そのためも使用できますが、文字列の次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-121">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a><span data-ttu-id="9b8e9-122">値の制限</span><span class="sxs-lookup"><span data-stu-id="9b8e9-122">Value Restriction</span></span>

<span data-ttu-id="9b8e9-123">コンパイラは、不変の単純な値で明示的な引数を持つ完全な関数定義でのみ自動ジェネリック化を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-123">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="9b8e9-124">これは、十分には、特定の型にするのには制限されませんが、汎化可能ながもコードをコンパイルしようとする場合、コンパイラがエラーを発行することを意味します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-124">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="9b8e9-125">この問題のエラー メッセージがこの制約として値の自動ジェネリック化を参照、*値制限*します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-125">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="9b8e9-126">通常、構成要素は、ジェネリックしたいが、コンパイラが不十分な情報を一般化し、ときに、または意図せずに、非ジェネリック コンストラクトに十分な情報を入力を省略すると、値制限エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-126">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="9b8e9-127">値制限エラーの解決策より完全で、次の方法のいずれかの型の推論の問題は制約より明確な情報を提供することです。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-127">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>

- <span data-ttu-id="9b8e9-128">値またはパラメーターに明示的な型注釈の追加、非ジェネリックの型を制限します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-128">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="9b8e9-129">問題は、関数の合成などの汎用関数を定義する汎化できない構成要素を使用して、または不完全カリー化された関数の引数に適用は、通常の関数定義として関数を書き直してください。 お試しください。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-129">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="9b8e9-130">問題が複雑すぎるために一般化する式の場合は、ように関数に、未使用のパラメーターを追加することで。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-130">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="9b8e9-131">明示的なジェネリック型パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-131">Add explicit generic type parameters.</span></span> <span data-ttu-id="9b8e9-132">このオプションはほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-132">This option is rarely used.</span></span>

- <span data-ttu-id="9b8e9-133">次のコード例は、これらの各シナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-133">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="9b8e9-134">ケース 1:式が複雑すぎます。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-134">Case 1: Too complex an expression.</span></span> <span data-ttu-id="9b8e9-135">この例では、一覧で`counter`を`int option ref`、単純な変更できない値は定義されていませんが。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-135">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="9b8e9-136">ケース 2:汎化できない構成要素を使用して、ジェネリック関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-136">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="9b8e9-137">この例では、コンストラクトは汎化できない構成を関数の引数の部分的なアプリケーションが伴うので。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-137">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="9b8e9-138">ケース 3:未使用のパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-138">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="9b8e9-139">この式が汎化の単純でないため、コンパイラは値制限エラーを発行します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-139">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="9b8e9-140">ケース 4:型パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-140">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="9b8e9-141">最後の場合、値には型関数の場合、次のようになど多くのさまざまな種類の値を作成するために使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9b8e9-141">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="9b8e9-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b8e9-142">See also</span></span>

- [<span data-ttu-id="9b8e9-143">型推論</span><span class="sxs-lookup"><span data-stu-id="9b8e9-143">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="9b8e9-144">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="9b8e9-144">Generics</span></span>](index.md)
- [<span data-ttu-id="9b8e9-145">静的に解決される型パラメーター</span><span class="sxs-lookup"><span data-stu-id="9b8e9-145">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)
- [<span data-ttu-id="9b8e9-146">制約</span><span class="sxs-lookup"><span data-stu-id="9b8e9-146">Constraints</span></span>](constraints.md)