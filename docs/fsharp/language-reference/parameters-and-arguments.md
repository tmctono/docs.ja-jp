---
title: パラメーターと引数
description: パラメーターの定義と、関数、メソッド、およびプロパティへの引数の引き渡しに関する F# 言語のサポートについて説明します。
ms.date: 12/04/2019
ms.openlocfilehash: b234ef939128e7cf09d35f9580d4d5010d7dc639
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401053"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="d65c1-103">パラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="d65c1-103">Parameters and Arguments</span></span>

<span data-ttu-id="d65c1-104">このトピックでは、パラメーターを定義し、関数、メソッド、およびプロパティに引数を渡すための言語サポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d65c1-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="d65c1-105">参照渡し方法、および可変個の引数を受け取るメソッドの定義方法と使用方法に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d65c1-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>

## <a name="parameters-and-arguments"></a><span data-ttu-id="d65c1-106">パラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="d65c1-106">Parameters and Arguments</span></span>

<span data-ttu-id="d65c1-107">*パラメーター*という用語は、指定される値の名前を記述するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="d65c1-108">引数という*用語*は、各パラメーターに指定された値に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="d65c1-109">パラメーターは、タプルまたはカリー化された形式で指定することも、2 つの組み合わせで指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="d65c1-110">引数は、明示的なパラメーター名を使用して渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="d65c1-111">メソッドのパラメーターは、オプションとして指定でき、デフォルト値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-111">Parameters of methods can be specified as optional and given a default value.</span></span>

## <a name="parameter-patterns"></a><span data-ttu-id="d65c1-112">パラメータパターン</span><span class="sxs-lookup"><span data-stu-id="d65c1-112">Parameter Patterns</span></span>

<span data-ttu-id="d65c1-113">関数やメソッドに渡されるパラメータは、一般に、スペースで区切られたパターンです。</span><span class="sxs-lookup"><span data-stu-id="d65c1-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="d65c1-114">つまり、原則として、「[一致式](match-expressions.md)」で説明されているパターンは、関数またはメンバーのパラメーター・リストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="d65c1-115">メソッドは、通常、引数を渡すタプル形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="d65c1-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="d65c1-116">これにより、タプル形式が .NET メソッドでの引数の渡し方と一致するため、他の .NET 言語の観点からより明確な結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="d65c1-117">カリー化された形式は、バインディングを使用して作成された関数で`let`最もよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="d65c1-118">次の擬似コードは、組とカリー化された引数の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="d65c1-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="d65c1-119">組の中に一部の引数があり、一部の引数が組に含まれていない場合は、結合形式が可能です。</span><span class="sxs-lookup"><span data-stu-id="d65c1-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="d65c1-120">パラメーター・リストでも他のパターンを使用できますが、パラメーター・パターンがすべての入力に一致しない場合は、実行時に不完全な一致が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d65c1-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="d65c1-121">例外`MatchFailureException`は、引数の値がパラメーター・リストで指定されたパターンと一致しない場合に生成されます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="d65c1-122">パラメーター パターンで不完全な一致が許可されると、コンパイラは警告を発行します。</span><span class="sxs-lookup"><span data-stu-id="d65c1-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="d65c1-123">パラメーター・リストには、他のパターンが少なくとも 1 つ使用され、ワイルドカード・パターンとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="d65c1-124">指定された引数を無視するだけの場合は、パラメーター リストでワイルドカード パターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="d65c1-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="d65c1-125">次のコードは、引数リストでのワイルドカード パターンの使用を示しています。</span><span class="sxs-lookup"><span data-stu-id="d65c1-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="d65c1-126">ワイルドカード パターンは、次のコードのように、通常は文字列配列として指定されるコマンド ライン引数に関心がない場合に、プログラムへのメイン エントリ ポイントなどで渡される引数が必要ない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d65c1-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="d65c1-127">引数で使用されるパターン、および判別共用体`as`とアクティブなパターンに関連付けられた識別子パターンは、他にもあります。</span><span class="sxs-lookup"><span data-stu-id="d65c1-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="d65c1-128">単一ケースの判別共用体パターンは、次のように使用できます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="d65c1-129">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d65c1-129">The output is as follows.</span></span>

```console
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="d65c1-130">アクティブパターンは、たとえば、次の例のように、引数を目的の形式に変換する場合に、パラメータとして役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="d65c1-131">次の`as`コード行に示すように、パターンを使用して、一致した値をローカル値として格納できます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="d65c1-132">時折使用されるもう 1 つのパターンは、関数の本体として、暗黙的な引数に対してパターン一致を即座に実行するラムダ式を提供することによって、最後の引数を無名のままにする関数です。</span><span class="sxs-lookup"><span data-stu-id="d65c1-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="d65c1-133">この例は、次のコード行です。</span><span class="sxs-lookup"><span data-stu-id="d65c1-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="d65c1-134">このコードは、汎用リストを受け取り、`true`リストが空の場合、または`false`そうでない場合に返す関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="d65c1-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="d65c1-135">このような手法を使用すると、コードの読み取りが困難になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d65c1-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="d65c1-136">不完全な一致を伴うパターンが役立つ場合があります。例えば、プログラム内のリストに 3 つの要素しか含めならない場合は、パラメーター・リストで次のようなパターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="d65c1-137">不完全な一致を持つパターンの使用は、迅速なプロトタイプ作成やその他の一時的な使用のために予約するのが最善です。</span><span class="sxs-lookup"><span data-stu-id="d65c1-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="d65c1-138">コンパイラは、このようなコードに対して警告を発行します。</span><span class="sxs-lookup"><span data-stu-id="d65c1-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="d65c1-139">このようなパターンは、すべての入力可能な一般的なケースをカバーできないため、コンポーネント API には適していません。</span><span class="sxs-lookup"><span data-stu-id="d65c1-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="d65c1-140">名前付き引数</span><span class="sxs-lookup"><span data-stu-id="d65c1-140">Named Arguments</span></span>

<span data-ttu-id="d65c1-141">メソッドの引数は、コンマ区切りの引数リスト内の位置によって指定することも、名前を指定してメソッドに明示的に渡し、その後に等号と渡す値を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="d65c1-142">名前を指定して指定した場合は、宣言で使用されている順序とは異なる順序で表示できます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="d65c1-143">名前付き引数を使用すると、メソッド パラメーターの並べ替えなど、API の特定の種類の変更に対して、コードをより読みやすく、適応性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="d65c1-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="d65c1-144">名前付き引数はメソッド`let`に対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="d65c1-145">名前付き引数の使用方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="d65c1-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="d65c1-146">クラス コンストラクターの呼び出しでは、名前付き引数と同様の構文を使用して、クラスのプロパティの値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="d65c1-147">この構文の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d65c1-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="d65c1-148">詳細については、「コンストラクター [(F#)」](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d65c1-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="d65c1-149">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="d65c1-149">Optional Parameters</span></span>

<span data-ttu-id="d65c1-150">パラメーター名の前に疑問符を使用して、メソッドのオプション・パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="d65c1-151">オプション のパラメーターは F# オプション型として解釈されるため、 と`match``Some``None`を指定して式を使用して、オプション型をクエリする通常の方法でクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="d65c1-152">オプションのパラメーターは、バインディングを使用`let`して作成された関数ではなく、メンバーに対してのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="d65c1-153">または などの`?arg=None``?arg=Some(3)`パラメーター名によって既存のオプション値をメソッドに渡すことができます`?arg=arg`。</span><span class="sxs-lookup"><span data-stu-id="d65c1-153">You can pass existing optional values to method by parameter name, such as `?arg=None` or `?arg=Some(3)` or `?arg=arg`.</span></span> <span data-ttu-id="d65c1-154">これは、別のメソッドに省略可能な引数を渡すメソッドを構築する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-154">This can be useful when building a method that passes optional arguments to another method.</span></span>

<span data-ttu-id="d65c1-155">オプション引数の既定値を設定`defaultArg`する関数 を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-155">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="d65c1-156">この`defaultArg`関数は、オプションのパラメータを最初の引数として、デフォルト値を 2 番目の引数として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d65c1-156">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="d65c1-157">次の例は、省略可能なパラメーターの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d65c1-157">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="d65c1-158">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d65c1-158">The output is as follows.</span></span>

```console
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

<span data-ttu-id="d65c1-159">C# と Visual Basic 相互運用機能の目的で、F# の属性`[<Optional; DefaultParameterValue<(...)>]`を使用して、呼び出し元に引数を省略可能と見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-159">For the purposes of C# and Visual Basic interop you can use the attributes `[<Optional; DefaultParameterValue<(...)>]` in F#, so that callers will see an argument as optional.</span></span> <span data-ttu-id="d65c1-160">これは、引数を C# での オプションとして定義する`MyMethod(int i = 3)`のと同じです。</span><span class="sxs-lookup"><span data-stu-id="d65c1-160">This is equivalent to defining the argument as optional in C# as in `MyMethod(int i = 3)`.</span></span>

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

<span data-ttu-id="d65c1-161">新しいオブジェクトをデフォルトのパラメータ値として指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-161">You can also specify a new object as a default parameter value.</span></span> <span data-ttu-id="d65c1-162">たとえば、メンバーは`Foo`代わりに入力としてオプション`CancellationToken`を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-162">For example, the `Foo` member could have an optional `CancellationToken` as input instead:</span></span>

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

<span data-ttu-id="d65c1-163">引数として指定する値は`DefaultParameterValue`、パラメーターの型と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d65c1-163">The value given as argument to `DefaultParameterValue` must match the type of the parameter.</span></span> <span data-ttu-id="d65c1-164">たとえば、次の項目は許可されません。</span><span class="sxs-lookup"><span data-stu-id="d65c1-164">For example, the following is not allowed:</span></span>

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

<span data-ttu-id="d65c1-165">この場合、コンパイラは警告を生成し、両方の属性を完全に無視します。</span><span class="sxs-lookup"><span data-stu-id="d65c1-165">In this case, the compiler generates a warning and will ignore both attributes altogether.</span></span> <span data-ttu-id="d65c1-166">コンパイラが誤った型`null`、すなわちを推測するので、デフォルト値は型注釈付きである必要があることに注意してください。 `[<Optional; DefaultParameterValue(null:obj)>] o:obj`</span><span class="sxs-lookup"><span data-stu-id="d65c1-166">Note that the default value `null` needs to be type-annotated, as otherwise the compiler infers the wrong type, i.e. `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span></span>

## <a name="passing-by-reference"></a><span data-ttu-id="d65c1-167">参照渡し</span><span class="sxs-lookup"><span data-stu-id="d65c1-167">Passing by Reference</span></span>

<span data-ttu-id="d65c1-168">参照によって F# 値を渡すと、マネージ ポインター型である[byrefs](byrefs.md)が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-168">Passing an F# value by reference involves [byrefs](byrefs.md), which are managed pointer types.</span></span> <span data-ttu-id="d65c1-169">使用するタイプのガイダンスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d65c1-169">Guidance for which type to use is as follows:</span></span>

- <span data-ttu-id="d65c1-170">ポインタ`inref<'T>`を読み取るだけで済む場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d65c1-170">Use `inref<'T>` if you only need to read the pointer.</span></span>
- <span data-ttu-id="d65c1-171">ポインタ`outref<'T>`に書き込むだけで済む場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d65c1-171">Use `outref<'T>` if you only need to write to the pointer.</span></span>
- <span data-ttu-id="d65c1-172">ポインター`byref<'T>`の読み取りと書き込みの両方が必要な場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d65c1-172">Use `byref<'T>` if you need to both read from and write to the pointer.</span></span>

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

let test () =
    // No need to make it mutable, since it's read-only
    let x = 1
    example1 &x

    // Needs to be mutable, since we write to it
    let mutable y = 2
    example2 &y
    example3 &y // Now 'y' is 3
```

<span data-ttu-id="d65c1-173">パラメーターがポインターであり、値が変更可能であるため、値に対する変更は関数の実行後も保持されます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-173">Because the parameter is a pointer and the value is mutable, any changes to the value are retained after the execution of the function.</span></span>

<span data-ttu-id="d65c1-174">戻り値としてタプルを使用して、.NET ライブラリ`out`メソッドにパラメーターを格納できます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-174">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="d65c1-175">または、パラメータを`out``byref`パラメータとして扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-175">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="d65c1-176">両方の方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="d65c1-176">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="d65c1-177">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="d65c1-177">Parameter Arrays</span></span>

<span data-ttu-id="d65c1-178">場合によっては、異種型の任意の数のパラメータを受け取る関数を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d65c1-178">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="d65c1-179">使用できるすべての型を考慮するために、オーバーロードされた可能性のあるメソッドをすべて作成することは現実的ではありません。</span><span class="sxs-lookup"><span data-stu-id="d65c1-179">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="d65c1-180">.NET の実装では、パラメーター配列機能を使用して、このようなメソッドをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d65c1-180">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="d65c1-181">シグネチャのパラメータ配列を受け取るメソッドは、任意の数のパラメータを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-181">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="d65c1-182">パラメータは配列に格納されます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-182">The parameters are put into an array.</span></span> <span data-ttu-id="d65c1-183">配列要素の型によって、関数に渡すことができるパラメーターの型が決まります。</span><span class="sxs-lookup"><span data-stu-id="d65c1-183">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="d65c1-184">要素型として`System.Object`パラメーター配列を定義する場合、クライアント コードは任意の型の値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-184">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="d65c1-185">F# では、パラメーター配列はメソッドでのみ定義できます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-185">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="d65c1-186">スタンドアロン関数やモジュールで定義されている関数では使用できません。</span><span class="sxs-lookup"><span data-stu-id="d65c1-186">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="d65c1-187">パラメーター配列は、 属性を使用`ParamArray`して定義します。</span><span class="sxs-lookup"><span data-stu-id="d65c1-187">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="d65c1-188">属性`ParamArray`は最後のパラメーターにのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="d65c1-188">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="d65c1-189">次のコードは、パラメーター配列を受け取る .NET メソッドの呼び出しと、パラメーター配列を受け取るメソッドを持つ F# の型の定義の両方を示しています。</span><span class="sxs-lookup"><span data-stu-id="d65c1-189">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="d65c1-190">プロジェクトで実行する場合、前のコードの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d65c1-190">When run in a project, the output of the previous code is as follows:</span></span>

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="d65c1-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="d65c1-191">See also</span></span>

- [<span data-ttu-id="d65c1-192">メンバー</span><span class="sxs-lookup"><span data-stu-id="d65c1-192">Members</span></span>](./members/index.md)
