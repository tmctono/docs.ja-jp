---
title: 自動ジェネリック化
description: どの F# 自動的に一般化引数と関数の種類可能であれば、複数の種類で動作させることについて説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 501749a190d9770cbcd9848e3d528cba32fe6762
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630626"
---
# <a name="automatic-generalization"></a><span data-ttu-id="66c60-103">自動ジェネリック化</span><span class="sxs-lookup"><span data-stu-id="66c60-103">Automatic Generalization</span></span>

<span data-ttu-id="66c60-104">F#型の推定を使用して、関数と式の型を評価します。</span><span class="sxs-lookup"><span data-stu-id="66c60-104">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="66c60-105">このトピックでは、どの F# 自動的に一般化引数と関数の種類可能な限り、複数の種類で動作させることについて説明します。</span><span class="sxs-lookup"><span data-stu-id="66c60-105">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>

## <a name="automatic-generalization"></a><span data-ttu-id="66c60-106">自動ジェネリック化</span><span class="sxs-lookup"><span data-stu-id="66c60-106">Automatic Generalization</span></span>

<span data-ttu-id="66c60-107">コンパイラF#は、関数に対して型の推定を実行するときに、指定されたパラメーターをジェネリックにできるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="66c60-107">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="66c60-108">コンパイラは各パラメーターを調べ、関数がそのパラメーターの特定の型に依存しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="66c60-108">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="66c60-109">そうでない場合、型はジェネリックとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="66c60-109">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="66c60-110">次のコード例は、コンパイラがジェネリックと推論する関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="66c60-110">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="66c60-111">型はと`'a -> 'a -> 'a`して推論されます。</span><span class="sxs-lookup"><span data-stu-id="66c60-111">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="66c60-112">型は、これが同じ不明な型の2つの引数を受け取り、同じ型の値を返す関数であることを示します。</span><span class="sxs-lookup"><span data-stu-id="66c60-112">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="66c60-113">前の関数がジェネリックになる理由の1つは、大なり演算子 (`>`) 自体がジェネリックであることです。</span><span class="sxs-lookup"><span data-stu-id="66c60-113">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="66c60-114">大なり演算子にはシグネチャ`'a -> 'a -> bool`があります。</span><span class="sxs-lookup"><span data-stu-id="66c60-114">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="66c60-115">すべての演算子がジェネリックであるとは限りません。関数内のコードが非ジェネリック関数または演算子と共にパラメーター型を使用している場合、そのパラメーターの型を一般化することはできません。</span><span class="sxs-lookup"><span data-stu-id="66c60-115">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="66c60-116">は`max`ジェネリックであるため、次の例に示すよう`int`に`float`、、などの型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="66c60-116">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="66c60-117">ただし、2つの引数は同じ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="66c60-117">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="66c60-118">署名はで`'a -> 'a -> 'a`あり、 `'a -> 'b -> 'a`ではありません。</span><span class="sxs-lookup"><span data-stu-id="66c60-118">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="66c60-119">したがって、次のコードでは、型が一致しないため、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="66c60-119">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="66c60-120">関数`max`は、大なり演算子をサポートするすべての型でも動作します。</span><span class="sxs-lookup"><span data-stu-id="66c60-120">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="66c60-121">したがって、次のコードに示すように、文字列で使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="66c60-121">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a><span data-ttu-id="66c60-122">値の制限</span><span class="sxs-lookup"><span data-stu-id="66c60-122">Value Restriction</span></span>

<span data-ttu-id="66c60-123">コンパイラは、明示的な引数を持つ完全な関数定義と、単純な変更できない値に対してのみ、自動汎化を実行します。</span><span class="sxs-lookup"><span data-stu-id="66c60-123">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="66c60-124">これは、特定の型としては十分に制約されていないが、汎化できないコードをコンパイルしようとすると、コンパイラがエラーを発行することを意味します。</span><span class="sxs-lookup"><span data-stu-id="66c60-124">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="66c60-125">この問題のエラーメッセージは、値の*制限*として、値の自動汎化に対するこの制限を示しています。</span><span class="sxs-lookup"><span data-stu-id="66c60-125">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="66c60-126">通常、値制限エラーは、構造体をジェネリックにする必要があるものの、コンパイラがそれを一般化するための情報が不足している場合、または非ジェネリックコンストラクトで十分な型情報を誤って省略した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="66c60-126">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="66c60-127">値制限エラーの解決策は、次のいずれかの方法で、型推論の問題をより詳細に制限するために、より明示的な情報を提供することです。</span><span class="sxs-lookup"><span data-stu-id="66c60-127">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>

- <span data-ttu-id="66c60-128">明示的な型の注釈を値またはパラメーターに追加することにより、型を非ジェネリックに制約します。</span><span class="sxs-lookup"><span data-stu-id="66c60-128">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="66c60-129">関数コンポジションや不完全なカリー化関数の引数など、ジェネリック関数を定義するために汎化不可能なコンストラクトを使用している場合は、関数を通常の関数定義として書き直してください。</span><span class="sxs-lookup"><span data-stu-id="66c60-129">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="66c60-130">問題が複雑すぎて一般化できない式である場合は、余分な未使用のパラメーターを追加して関数にします。</span><span class="sxs-lookup"><span data-stu-id="66c60-130">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="66c60-131">明示的なジェネリック型パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="66c60-131">Add explicit generic type parameters.</span></span> <span data-ttu-id="66c60-132">このオプションはほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="66c60-132">This option is rarely used.</span></span>

- <span data-ttu-id="66c60-133">次のコード例は、これらの各シナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="66c60-133">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="66c60-134">ケース 1:式が複雑すぎます。</span><span class="sxs-lookup"><span data-stu-id="66c60-134">Case 1: Too complex an expression.</span></span> <span data-ttu-id="66c60-135">この例では、リスト`counter`はであること`int option ref`を意図していますが、単純な変更できない値として定義されていません。</span><span class="sxs-lookup"><span data-stu-id="66c60-135">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="66c60-136">ケース 2:汎化できない構成体を使用してジェネリック関数を定義する。</span><span class="sxs-lookup"><span data-stu-id="66c60-136">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="66c60-137">この例では、構造体は、関数の引数の部分的な適用を伴うため、汎化できません。</span><span class="sxs-lookup"><span data-stu-id="66c60-137">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="66c60-138">ケース 3:使用されていない余分なパラメーターを追加しています。</span><span class="sxs-lookup"><span data-stu-id="66c60-138">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="66c60-139">この式は一般化には不十分であるため、コンパイラは値の制限のエラーを発行します。</span><span class="sxs-lookup"><span data-stu-id="66c60-139">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="66c60-140">ケース 4:型パラメーターを追加しています。</span><span class="sxs-lookup"><span data-stu-id="66c60-140">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="66c60-141">最後の例では、値が型の関数になり、次のように、さまざまな型の値を作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="66c60-141">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="66c60-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="66c60-142">See also</span></span>

- [<span data-ttu-id="66c60-143">型推論</span><span class="sxs-lookup"><span data-stu-id="66c60-143">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="66c60-144">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="66c60-144">Generics</span></span>](index.md)
- [<span data-ttu-id="66c60-145">静的に解決される型パラメーター</span><span class="sxs-lookup"><span data-stu-id="66c60-145">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)
- [<span data-ttu-id="66c60-146">制約</span><span class="sxs-lookup"><span data-stu-id="66c60-146">Constraints</span></span>](constraints.md)
