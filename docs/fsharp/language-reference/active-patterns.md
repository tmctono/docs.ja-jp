---
title: アクティブ パターン
description: アクティブ パターンを使用して、F# プログラミング言語で入力データを分割する名前付きのパーティションを定義する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 25ab255574390d3761fe788aeb413c8ee04fda2a
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690414"
---
# <a name="active-patterns"></a><span data-ttu-id="6ee6d-103">アクティブ パターン</span><span class="sxs-lookup"><span data-stu-id="6ee6d-103">Active Patterns</span></span>

<span data-ttu-id="6ee6d-104">*アクティブ パターン*パターン一致式の判別共用体と同様に、これらの名前を使用できるように、入力のデータを分割する名前付きパーティションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="6ee6d-105">アクティブ パターンを使用すると、パーティションごとにカスタマイズした方法でデータを分解できます。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="6ee6d-106">構文</span><span class="sxs-lookup"><span data-stu-id="6ee6d-106">Syntax</span></span>

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch= expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a><span data-ttu-id="6ee6d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="6ee6d-107">Remarks</span></span>

<span data-ttu-id="6ee6d-108">前の構文では、識別子は、名前で表される入力データのパーティションに*引数*、または、つまり、名、引数のすべての値のセットのサブセットをします。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="6ee6d-109">アクティブ パターン定義で最大 7 つのパーティションがあります。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="6ee6d-110">*式*をデータを分解する形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="6ee6d-111">名前付きのパーティションのうちに引数が属しているように指定された値を決定する規則を定義するのにアクティブ パターンの定義を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="6ee6d-112">(| と |) 記号と呼びます*バナナ クリップ*この種類の let バインドによって作成された関数が呼び出されると、*認識エンジンのアクティブな*します。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="6ee6d-113">たとえば、引数を持つアクティブ パターンを検討してください。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="6ee6d-114">アクティブ パターンは、次の例のように、式に一致するパターンで使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="6ee6d-115">このプログラムの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-115">The output of this program is as follows:</span></span>

```
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="6ee6d-116">アクティブ パターンの別の使用など、同じ基になるデータがさまざまな可能な表現を持っている場合、複数の方法でデータ型を分解することです。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="6ee6d-117">たとえば、`Color`オブジェクトは、RGB 表現や、HSB 表現に分解する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="6ee6d-118">上記のプログラムの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-118">The output of the above program is as follows:</span></span>

```
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

<span data-ttu-id="6ee6d-119">組み合わせでは、アクティブ パターンを使用してこれら 2 つの方法はパーティションに有効にする、適切なフォームだけにデータを分解し、計算のため最も便利な形式で適切なデータに対して適切な計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="6ee6d-120">結果として得られるパターン マッチング式は、非常に判読しやすくに大幅に簡素化する可能性のある複雑な分岐構造とデータ分析のコードは、便利な方法で書き込まれるデータを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="6ee6d-121">部分的なアクティブ パターン</span><span class="sxs-lookup"><span data-stu-id="6ee6d-121">Partial Active Patterns</span></span>

<span data-ttu-id="6ee6d-122">場合によっては、入力領域の一部のみをパーティション分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="6ee6d-123">その場合は、うちのいくつかの入力に一致が他の入力と一致しない部分のパターンのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="6ee6d-124">常に値を生成しないアクティブ パターンが呼び出される*アクティブ パターンの部分的な*; オプションの種類である戻り値があります。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="6ee6d-125">ワイルドカード文字を使用する部分的なアクティブ パターンを定義する (\_) バナナ クリップ内のパターンの一覧の最後にします。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="6ee6d-126">次のコードでは、部分的なアクティブ パターンの使用を示します。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="6ee6d-127">前の例の出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-127">The output of the previous example is as follows:</span></span>

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="6ee6d-128">部分的なアクティブ パターンを使用する場合、個々 の選択肢があります不整合のあるまたは相互に排他的ですが、必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="6ee6d-129">次の例では、パターンの四角形とキューブのパターンのない不整合のある、いくつかの数字は四角形と、64 などのキューブの両方であるためです。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="6ee6d-130">次のプログラムは、四角形と立方パターンを組み合わせて、AND パターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="6ee6d-131">これは、最大 1,000 両方平方和、キューブとキューブのみであるものであるすべての整数を出力します。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-131">It print out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span> 

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="6ee6d-132">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-132">The output is as follows:</span></span>

```
1 is a cube and a square
8 is a cube
27 is a cube
64 is a cube and a square
125 is a cube
216 is a cube
343 is a cube
512 is a cube
729 is a cube and a square
1000 is a cube
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="6ee6d-133">パラメーター化されたアクティブ パターン</span><span class="sxs-lookup"><span data-stu-id="6ee6d-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="6ee6d-134">アクティブ パターンは、常に一致する項目の少なくとも 1 つの引数を受け取りますが、この場合、名前でも、追加の引数がかかる*パラメーター化されたアクティブ パターン*適用されます。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="6ee6d-135">追加の引数は、特殊化する一般的なパターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="6ee6d-136">たとえば、多くの場合、文字列を解析する正規表現を使用するアクティブ パターンに含める部分アクティブ パターンを使用する次のコードのように、追加のパラメーターとして正規`Integer`上記のコード例で定義されています。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="6ee6d-137">この例では、一般的なである ParseRegex アクティブ パターンをカスタマイズする正規表現を使用して、さまざまな日付形式の文字列が与えられます。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="6ee6d-138">一致した文字列を DateTime コンス トラクターに渡すことができる整数に変換するには、整数アクティブ パターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="6ee6d-139">前のコードの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-139">The output of the previous code is as follows:</span></span>

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="6ee6d-140">アクティブ パターンは、パターン マッチング式のみに制限することはありません、let バインドで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="6ee6d-141">前のコードの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6ee6d-141">The output of the previous code is as follows:</span></span>

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="6ee6d-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ee6d-142">See also</span></span>

- [<span data-ttu-id="6ee6d-143">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="6ee6d-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="6ee6d-144">match 式</span><span class="sxs-lookup"><span data-stu-id="6ee6d-144">Match Expressions</span></span>](match-expressions.md)
