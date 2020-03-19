---
title: アクティブ パターン
description: アクティブ パターンを使用して、F# プログラミング言語で入力データを細分化する名前付きパーティションを定義する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 898ef201369683bfd49d53e863e86f919f5837fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187060"
---
# <a name="active-patterns"></a><span data-ttu-id="0fad4-103">アクティブ パターン</span><span class="sxs-lookup"><span data-stu-id="0fad4-103">Active Patterns</span></span>

<span data-ttu-id="0fad4-104">*アクティブなパターン*を使用すると、入力データを細分化する名前付きパーティションを定義できるため、これらの名前を、判別共用体の場合と同じようにパターン一致式で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0fad4-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="0fad4-105">アクティブ パターンを使用すると、パーティションごとにカスタマイズした方法でデータを分解できます。</span><span class="sxs-lookup"><span data-stu-id="0fad4-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="0fad4-106">構文</span><span class="sxs-lookup"><span data-stu-id="0fad4-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="0fad4-107">解説</span><span class="sxs-lookup"><span data-stu-id="0fad4-107">Remarks</span></span>

<span data-ttu-id="0fad4-108">前の構文では、識別子は、引数 、つまり *、引数*のすべての値のセットのサブセットの名前で表される入力データのパーティションの名前です。</span><span class="sxs-lookup"><span data-stu-id="0fad4-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="0fad4-109">アクティブなパターン定義には、最大 7 つのパーティションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0fad4-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="0fad4-110">*式*は、データを分解するフォームを表します。</span><span class="sxs-lookup"><span data-stu-id="0fad4-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="0fad4-111">アクティブなパターン定義を使用して、引数として指定された値が属する名前付きパーティションを決定するための規則を定義できます。</span><span class="sxs-lookup"><span data-stu-id="0fad4-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="0fad4-112">(|) 記号は*バナナ クリップ*と呼ばれ、このタイプの let バインドによって作成される関数は*アクティブ な認識エンジン*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="0fad4-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="0fad4-113">例として、引数を持つ次のアクティブなパターンを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="0fad4-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="0fad4-114">次の例のように、パターンマッチング式でアクティブなパターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0fad4-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="0fad4-115">このプログラムの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0fad4-115">The output of this program is as follows:</span></span>

```console
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="0fad4-116">アクティブパターンのもう 1 つの用途は、基になるデータにさまざまな表現がある場合など、複数の方法でデータ型を分解することです。</span><span class="sxs-lookup"><span data-stu-id="0fad4-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="0fad4-117">たとえば、オブジェクトを`Color`RGB 表現または HSB 表現に分解できます。</span><span class="sxs-lookup"><span data-stu-id="0fad4-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="0fad4-118">上記のプログラムの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0fad4-118">The output of the above program is as follows:</span></span>

```console
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

<span data-ttu-id="0fad4-119">この 2 つのアクティブ パターンを組み合わせて使用すると、データを適切な形式に分割して分解し、計算に最も便利な形式で適切なデータに対して適切な計算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="0fad4-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="0fad4-120">結果として得られるパターン・マッチング式により、データを非常に読みやすく、複雑な分岐やデータ分析コードを大幅に簡素化する便利な方法でデータを書き込むことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="0fad4-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="0fad4-121">部分的なアクティブ パターン</span><span class="sxs-lookup"><span data-stu-id="0fad4-121">Partial Active Patterns</span></span>

<span data-ttu-id="0fad4-122">場合によっては、入力スペースの一部だけをパーティション分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fad4-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="0fad4-123">その場合は、一連の部分パターンを記述し、各パターンは一部の入力に一致しますが、他の入力と一致しません。</span><span class="sxs-lookup"><span data-stu-id="0fad4-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="0fad4-124">常に値を生成しないアクティブなパターンは *、部分アクティブパターン*と呼ばれます。これらの値には、オプション型の戻り値があります。</span><span class="sxs-lookup"><span data-stu-id="0fad4-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="0fad4-125">部分的にアクティブなパターンを定義するには、バナナクリップ内の\_パターンリストの最後にワイルドカード文字 () を使用します。</span><span class="sxs-lookup"><span data-stu-id="0fad4-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="0fad4-126">次のコードは、部分的なアクティブ パターンの使用を示しています。</span><span class="sxs-lookup"><span data-stu-id="0fad4-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="0fad4-127">前の例の出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0fad4-127">The output of the previous example is as follows:</span></span>

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="0fad4-128">部分的なアクティブパターンを使用する場合、個々の選択肢が分離または相互に排他的である場合がありますが、必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0fad4-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="0fad4-129">次の例では、一部の数値は 64 などの正方形と立方体の両方であるため、パターンの正方形とパターン Cube は不整合ではありません。</span><span class="sxs-lookup"><span data-stu-id="0fad4-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="0fad4-130">次のプログラムでは、AND パターンを使用して、四角形と立方体のパターンを組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="0fad4-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="0fad4-131">これは、正方形とキューブの両方である1000までの整数と、唯一のキューブである整数を出力します。</span><span class="sxs-lookup"><span data-stu-id="0fad4-131">It prints out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="0fad4-132">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0fad4-132">The output is as follows:</span></span>

```console
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

## <a name="parameterized-active-patterns"></a><span data-ttu-id="0fad4-133">パラメータ化されたアクティブ パターン</span><span class="sxs-lookup"><span data-stu-id="0fad4-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="0fad4-134">アクティブパターンは、常に、一致する項目に対して少なくとも 1 つの引数を取りますが、追加の引数を取ることがあり、その場合は *、名前パラメーター化されたアクティブパターン*が適用されます。</span><span class="sxs-lookup"><span data-stu-id="0fad4-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="0fad4-135">追加の引数を使用すると、一般的なパターンを特殊化できます。</span><span class="sxs-lookup"><span data-stu-id="0fad4-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="0fad4-136">たとえば、正規表現を使用して文字列を解析するアクティブ パターンには、次のコード`Integer`のように正規表現が追加のパラメーターとして含まれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="0fad4-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="0fad4-137">この例では、さまざまな日付形式に正規表現を使用する文字列を指定して、一般的な ParseRegex アクティブ パターンをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="0fad4-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="0fad4-138">整数アクティブ パターンは、一致した文字列を DateTime コンストラクタに渡すことができる整数に変換するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fad4-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="0fad4-139">上記のコードの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0fad4-139">The output of the previous code is as follows:</span></span>

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="0fad4-140">アクティブパターンはパターンマッチング式だけに限定されず、let-binding で使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="0fad4-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="0fad4-141">上記のコードの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0fad4-141">The output of the previous code is as follows:</span></span>

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="0fad4-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="0fad4-142">See also</span></span>

- [<span data-ttu-id="0fad4-143">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="0fad4-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="0fad4-144">match 式</span><span class="sxs-lookup"><span data-stu-id="0fad4-144">Match Expressions</span></span>](match-expressions.md)
