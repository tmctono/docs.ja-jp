---
title: パラメーターと引数
description: パラメーターを定義して、関数、メソッド、およびプロパティに引数を渡すのための F# 言語サポートについて説明します。
ms.date: 05/16/2016
ms.openlocfilehash: b68b3fdd14a66a7312efa5adb709adaeceaae282
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666262"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="22db2-103">パラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="22db2-103">Parameters and Arguments</span></span>

<span data-ttu-id="22db2-104">このトピックでは、パラメーターを定義して、関数、メソッド、およびプロパティに引数を渡すのための言語サポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="22db2-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="22db2-105">定義して、可変個の引数を取ることがメソッドを使用する方法と、参照渡しする方法の詳細情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="22db2-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>

## <a name="parameters-and-arguments"></a><span data-ttu-id="22db2-106">パラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="22db2-106">Parameters and Arguments</span></span>

<span data-ttu-id="22db2-107">用語*パラメーター*を指定すると予想される値の名前を表すために使用します。</span><span class="sxs-lookup"><span data-stu-id="22db2-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="22db2-108">用語*引数*に各パラメーターに指定された値のために使用します。</span><span class="sxs-lookup"><span data-stu-id="22db2-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="22db2-109">タプル、カリー化形式、または 2 つの組み合わせで、パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="22db2-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="22db2-110">明示的なパラメーターの名前を使用して引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="22db2-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="22db2-111">メソッドのパラメーターを省略可能として指定し、既定値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="22db2-111">Parameters of methods can be specified as optional and given a default value.</span></span>

## <a name="parameter-patterns"></a><span data-ttu-id="22db2-112">パラメーターのパターン</span><span class="sxs-lookup"><span data-stu-id="22db2-112">Parameter Patterns</span></span>

<span data-ttu-id="22db2-113">関数やメソッドに指定されたパラメーターとは、一般に、スペースで区切られたパターンを指します。</span><span class="sxs-lookup"><span data-stu-id="22db2-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="22db2-114">これは、原則として、パターンのいずれかの説明では意味[一致式](match-expressions.md)関数またはメンバーのパラメーター リストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="22db2-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="22db2-115">メソッドは、通常は引数の受け渡しの組形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="22db2-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="22db2-116">タプル形式の .NET メソッドで引数が渡される方法に一致するため、他の .NET 言語の観点からのわかりやすい結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="22db2-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="22db2-117">カリー化されたフォームを使用して作成した関数でよく使用`let`バインドします。</span><span class="sxs-lookup"><span data-stu-id="22db2-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="22db2-118">次の疑似コードは、タプルとカリー化された引数の例を示します。</span><span class="sxs-lookup"><span data-stu-id="22db2-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="22db2-119">タプルにいくつかの引数があり、一部がする場合は、結合されたフォームです。</span><span class="sxs-lookup"><span data-stu-id="22db2-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="22db2-120">その他のパターンは、パラメーター リストでも使用できますが、実行時に不完全な一致が存在できる可能性がありますパラメーターのパターンが可能なすべての入力が一致しない場合。</span><span class="sxs-lookup"><span data-stu-id="22db2-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="22db2-121">例外`MatchFailureException`引数の値がパラメーター リストで指定されたパターンと一致しない場合に生成されます。</span><span class="sxs-lookup"><span data-stu-id="22db2-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="22db2-122">パラメーターのパターンは、不完全な一致の場合、コンパイラは警告を発行します。</span><span class="sxs-lookup"><span data-stu-id="22db2-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="22db2-123">他に少なくとも 1 つのパターンは、パラメーター リストの一般的に便利ですし、ワイルドカード パターンです。</span><span class="sxs-lookup"><span data-stu-id="22db2-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="22db2-124">提供される引数を無視するだけの場合にパラメーター リストでワイルドカード パターンを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="22db2-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="22db2-125">次のコードでは、引数リスト内のワイルドカード パターンの使用を示します。</span><span class="sxs-lookup"><span data-stu-id="22db2-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="22db2-126">ワイルドカード パターンには、通常次のコードのように、文字列の配列として指定されるコマンドライン引数が必要ないときに、プログラムのメイン エントリ ポイントなど、渡された引数を必要としないときに便利です。 を指定できます。</span><span class="sxs-lookup"><span data-stu-id="22db2-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="22db2-127">引数で使用されることが他のパターンは、`as`パターン、および判別共用体とアクティブ パターンに関連付けられた識別子パターン。</span><span class="sxs-lookup"><span data-stu-id="22db2-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="22db2-128">次のように単一ケースの判別共用体パターンを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="22db2-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="22db2-129">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="22db2-129">The output is as follows.</span></span>

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="22db2-130">アクティブ パターンは、引数を次の例のように、目的の形式に変換するときに、たとえば、パラメーターとして役立ちます。</span><span class="sxs-lookup"><span data-stu-id="22db2-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="22db2-131">使用することができます、`as`パターンを次のコード行に示すように、ローカルの値として、一致した値を格納します。</span><span class="sxs-lookup"><span data-stu-id="22db2-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="22db2-132">使用されることがもう 1 つのパターンは、関数の本文として提供して、名前のない最後の引数を関数では、すぐに、暗黙的な引数をパターン マッチングを実行するラムダ式です。</span><span class="sxs-lookup"><span data-stu-id="22db2-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="22db2-133">この例では、次のコード行です。</span><span class="sxs-lookup"><span data-stu-id="22db2-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="22db2-134">このコードをジェネリック リストを受け取りを返す関数を定義する`true`リストが空の場合と`false`それ以外の場合。</span><span class="sxs-lookup"><span data-stu-id="22db2-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="22db2-135">このような手法を使用すると、コードが読みにくくします。</span><span class="sxs-lookup"><span data-stu-id="22db2-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="22db2-136">場合によっては、不完全な一致を含むパターンは便利です、たとえば、プログラムに含まれる一覧は、のみの 3 つの要素である場合は、可能性がありますで使用する、次のようなパターン パラメーター リスト。</span><span class="sxs-lookup"><span data-stu-id="22db2-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="22db2-137">不完全な一致パターンの使用は、クイック プロトタイプを作成し、その他の一時的な使用に最適な予約されています。</span><span class="sxs-lookup"><span data-stu-id="22db2-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="22db2-138">コンパイラでは、このようなコードの警告を発行します。</span><span class="sxs-lookup"><span data-stu-id="22db2-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="22db2-139">このようなパターンは、すべての可能な入力の一般的なケースを取り上げることはできません、そのため、コンポーネント Api に適したはありません。</span><span class="sxs-lookup"><span data-stu-id="22db2-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="22db2-140">名前付き引数</span><span class="sxs-lookup"><span data-stu-id="22db2-140">Named Arguments</span></span>

<span data-ttu-id="22db2-141">メソッドの引数は、引数のコンマ区切りリストでは、位置によって指定できます。 またはができるメソッドに渡される、明示的に続けて等号 (=) とで渡される値の名前。</span><span class="sxs-lookup"><span data-stu-id="22db2-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="22db2-142">名前を提供することで指定した場合は、宣言で使用するとは異なる順序で表示されることができます。</span><span class="sxs-lookup"><span data-stu-id="22db2-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="22db2-143">名前付き引数できるようにコードより読みやすくより適応性のある特定の種類のメソッドのパラメーターの順序変更など、API の変更します。</span><span class="sxs-lookup"><span data-stu-id="22db2-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="22db2-144">名前付き引数がなく、メソッドに対してのみ許可されます`let`-関数、関数値、またはラムダ式をバインドします。</span><span class="sxs-lookup"><span data-stu-id="22db2-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="22db2-145">次のコード例では、名前付き引数の使用を示します。</span><span class="sxs-lookup"><span data-stu-id="22db2-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="22db2-146">クラスのコンス トラクターの呼び出しでは、名前付き引数と同様の構文を使用して、クラスのプロパティの値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="22db2-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="22db2-147">次の例では、この構文を示します。</span><span class="sxs-lookup"><span data-stu-id="22db2-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="22db2-148">詳細については、[コンス トラクター (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22db2-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="22db2-149">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="22db2-149">Optional Parameters</span></span>

<span data-ttu-id="22db2-150">パラメーター名の前に疑問符を使用して、メソッドのオプションのパラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="22db2-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="22db2-151">使用して、オプションの種類がクエリを通常の方法でそのクエリを実行できるように、省略可能なパラメーターは F# オプションの種類として解釈されます、`match`式`Some`と`None`します。</span><span class="sxs-lookup"><span data-stu-id="22db2-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="22db2-152">省略可能なパラメーターを使用して作成した関数ではなく、メンバーでのみ許可`let`バインドします。</span><span class="sxs-lookup"><span data-stu-id="22db2-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="22db2-153">既存の省略可能な値に渡せるメソッドをパラメーター名のなど`?arg=None`または`?arg=Some(3)`または`?arg=arg`します。</span><span class="sxs-lookup"><span data-stu-id="22db2-153">You can pass existing optional values to method by parameter name, such as `?arg=None` or `?arg=Some(3)` or `?arg=arg`.</span></span> <span data-ttu-id="22db2-154">これは、別のメソッドに省略可能な引数を渡すメソッドを構築するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="22db2-154">This can be useful when building a method that passes optional arguments to another method.</span></span>

<span data-ttu-id="22db2-155">関数を使用することもできます。 `defaultArg`、省略可能な引数の既定値を設定します。</span><span class="sxs-lookup"><span data-stu-id="22db2-155">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="22db2-156">`defaultArg`関数は、最初の引数と省略可能なパラメーターと、2 つ目として、既定値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="22db2-156">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="22db2-157">次の例では、省略可能なパラメーターの使用を示します。</span><span class="sxs-lookup"><span data-stu-id="22db2-157">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="22db2-158">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="22db2-158">The output is as follows.</span></span>

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

<span data-ttu-id="22db2-159">目的でC#および属性を使用する Visual Basic の相互運用`[<Optional; DefaultParameterValue<(...)>]`でF#、呼び出し元がオプションとして、引数を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22db2-159">For the purposes of C# and Visual Basic interop you can use the attributes `[<Optional; DefaultParameterValue<(...)>]` in F#, so that callers will see an argument as optional.</span></span> <span data-ttu-id="22db2-160">オプションとして、引数を定義するのと同じC#うに`MyMethod(int i = 3)`します。</span><span class="sxs-lookup"><span data-stu-id="22db2-160">This is equivalent to defining the argument as optional in C# as in `MyMethod(int i = 3)`.</span></span>

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

<span data-ttu-id="22db2-161">パラメーターの既定値として、新しいオブジェクトを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="22db2-161">You can also specify a new object as a default parameter value.</span></span> <span data-ttu-id="22db2-162">たとえば、`Foo`メンバーが省略可能なことが`CancellationToken`代わりに入力として。</span><span class="sxs-lookup"><span data-stu-id="22db2-162">For example, the `Foo` member could have an optional `CancellationToken` as input instead:</span></span>

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

<span data-ttu-id="22db2-163">引数として指定された値`DefaultParameterValue`パラメーターの型に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22db2-163">The value given as argument to `DefaultParameterValue` must match the type of the parameter.</span></span> <span data-ttu-id="22db2-164">たとえば、次は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="22db2-164">For example, the following is not allowed:</span></span>

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

<span data-ttu-id="22db2-165">この場合、コンパイラは警告が生成され、両方の属性を完全に無視されます。</span><span class="sxs-lookup"><span data-stu-id="22db2-165">In this case, the compiler generates a warning and will ignore both attributes altogether.</span></span> <span data-ttu-id="22db2-166">なお、既定値`null`型の注釈がある必要がありますそれ以外の場合、問題の型の推測コンパイラつまり`[<Optional; DefaultParameterValue(null:obj)>] o:obj`します。</span><span class="sxs-lookup"><span data-stu-id="22db2-166">Note that the default value `null` needs to be type-annotated, as otherwise the compiler infers the wrong type, i.e. `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span></span>

## <a name="passing-by-reference"></a><span data-ttu-id="22db2-167">参照渡しで渡す</span><span class="sxs-lookup"><span data-stu-id="22db2-167">Passing by Reference</span></span>

<span data-ttu-id="22db2-168">渡す、F#参照によって値が含まれます[byref](byrefs.md)、マネージ ポインター型であります。</span><span class="sxs-lookup"><span data-stu-id="22db2-168">Passing an F# value by reference involves [byrefs](byrefs.md), which are managed pointer types.</span></span> <span data-ttu-id="22db2-169">使用する型は次のようにガイダンス:</span><span class="sxs-lookup"><span data-stu-id="22db2-169">Guidance for which type to use is as follows:</span></span>

* <span data-ttu-id="22db2-170">使用`inref<'T>`のみをポインターを読み取る必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="22db2-170">Use `inref<'T>` if you only need to read the pointer.</span></span>
* <span data-ttu-id="22db2-171">使用`outref<'T>`のみ、ポインターを記述する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="22db2-171">Use `outref<'T>` if you only need to write to the pointer.</span></span>
* <span data-ttu-id="22db2-172">使用`byref<'T>`から読み取るし、ポインターへの書き込みの両方に必要な場合。</span><span class="sxs-lookup"><span data-stu-id="22db2-172">Use `byref<'T>` if you need to both read from and write to the pointer.</span></span>

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

// No need to make it mutable, since it's read-only
let x = 1
example1 &x

// Needs to be mutable, since we write to it
let mutable y = 2
example2 &y
example3 &y // Now 'y' is 3
```

<span data-ttu-id="22db2-173">パラメーターがポインター値が変更可能なため、値への変更は、関数の実行後に保持されます。</span><span class="sxs-lookup"><span data-stu-id="22db2-173">Because the parameter is a pointer and the value is mutable, any changes to the value are retained after the execution of the function.</span></span>

<span data-ttu-id="22db2-174">戻り値として組を使用して格納できる`out`.NET ライブラリのメソッドのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="22db2-174">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="22db2-175">または、扱うことができます、`out`パラメーターとして、`byref`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="22db2-175">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="22db2-176">次のコード例では、両方の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="22db2-176">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="22db2-177">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="22db2-177">Parameter Arrays</span></span>

<span data-ttu-id="22db2-178">場合によっては任意の数の異機種混在型のパラメーターを受け取る関数を定義する必要です。</span><span class="sxs-lookup"><span data-stu-id="22db2-178">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="22db2-179">アカウントのために使用できるすべての種類を使用できるオーバー ロードされたメソッドを作成するは実用的はできません。</span><span class="sxs-lookup"><span data-stu-id="22db2-179">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="22db2-180">.NET 実装では、パラメーター配列の機能では、このようなメソッドがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="22db2-180">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="22db2-181">任意の数のパラメーターでは、そのシグニチャにパラメーター配列を受け取るメソッドを提供できます。</span><span class="sxs-lookup"><span data-stu-id="22db2-181">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="22db2-182">パラメーターは、配列に格納されます。</span><span class="sxs-lookup"><span data-stu-id="22db2-182">The parameters are put into an array.</span></span> <span data-ttu-id="22db2-183">配列の要素の型は、関数に渡すことができるパラメーターの型を決定します。</span><span class="sxs-lookup"><span data-stu-id="22db2-183">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="22db2-184">パラメーター配列を定義する場合`System.Object`要素の型として、クライアント コードできます値を渡す任意の型。</span><span class="sxs-lookup"><span data-stu-id="22db2-184">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="22db2-185">F#、パラメーター配列は、メソッドでのみ定義できます。</span><span class="sxs-lookup"><span data-stu-id="22db2-185">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="22db2-186">これらは、スタンドアロン関数またはモジュールで定義されている関数で使用できません。</span><span class="sxs-lookup"><span data-stu-id="22db2-186">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="22db2-187">使用して、パラメーター配列を定義する、`ParamArray`属性。</span><span class="sxs-lookup"><span data-stu-id="22db2-187">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="22db2-188">`ParamArray`属性は、最後のパラメーターにのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="22db2-188">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="22db2-189">次のコードは、パラメーター配列を受け取るメソッドを持つ F# では、パラメーター配列と型の定義を .NET メソッドを呼び出して両方を示しています。</span><span class="sxs-lookup"><span data-stu-id="22db2-189">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="22db2-190">プロジェクトで実行すると、前のコードの出力のとおりです。</span><span class="sxs-lookup"><span data-stu-id="22db2-190">When run in a project, the output of the previous code is as follows:</span></span>

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="22db2-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="22db2-191">See also</span></span>

- [<span data-ttu-id="22db2-192">メンバー</span><span class="sxs-lookup"><span data-stu-id="22db2-192">Members</span></span>](members/index.md)
