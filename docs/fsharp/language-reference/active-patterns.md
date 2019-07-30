---
title: アクティブ パターン
description: アクティブ パターンを使用して、F# プログラミング言語で入力データを分割する名前付きのパーティションを定義する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 12f423abe05e649e0b527ed04124b991feb5d592
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629951"
---
# <a name="active-patterns"></a><span data-ttu-id="d8649-103">アクティブ パターン</span><span class="sxs-lookup"><span data-stu-id="d8649-103">Active Patterns</span></span>

<span data-ttu-id="d8649-104">*アクティブパターン*を使用すると、入力データを分割する名前付きパーティションを定義できます。これにより、判別共用体の場合と同様に、パターン一致式でこれらの名前を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d8649-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="d8649-105">アクティブ パターンを使用すると、パーティションごとにカスタマイズした方法でデータを分解できます。</span><span class="sxs-lookup"><span data-stu-id="d8649-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="d8649-106">構文</span><span class="sxs-lookup"><span data-stu-id="d8649-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="d8649-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d8649-107">Remarks</span></span>

<span data-ttu-id="d8649-108">前の構文では、識別子は*引数*によって表される入力データのパーティションの名前、つまり、引数のすべての値のセットのサブセットの名前です。</span><span class="sxs-lookup"><span data-stu-id="d8649-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="d8649-109">アクティブなパターン定義には、最大7つのパーティションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d8649-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="d8649-110">*式*では、データを分解するフォームを記述します。</span><span class="sxs-lookup"><span data-stu-id="d8649-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="d8649-111">アクティブパターン定義を使用すると、引数として指定された値を持つ名前付きパーティションを決定するための規則を定義できます。</span><span class="sxs-lookup"><span data-stu-id="d8649-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="d8649-112">(| および |) 記号は*バナナクリップ*と呼ばれ、この型の let バインドによって作成される関数は、*アクティブレコグナイザー*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d8649-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="d8649-113">例として、引数を持つ次のアクティブパターンについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="d8649-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="d8649-114">次の例に示すように、パターンマッチング式でアクティブパターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8649-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="d8649-115">このプログラムの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d8649-115">The output of this program is as follows:</span></span>

```
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="d8649-116">アクティブパターンのもう1つの用途は、データ型を複数の方法で分解することです。たとえば、同じ基になるデータにさまざまな表現が含まれている場合などです。</span><span class="sxs-lookup"><span data-stu-id="d8649-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="d8649-117">たとえば、オブジェクトを`Color` RGB 表現または HSB 表現に分解することができます。</span><span class="sxs-lookup"><span data-stu-id="d8649-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="d8649-118">上記のプログラムの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d8649-118">The output of the above program is as follows:</span></span>

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

<span data-ttu-id="d8649-119">これらの2つの方法でアクティブパターンを使用することにより、データを適切な形式に分割および分解し、計算に最も便利な形式の適切なデータに対して適切な計算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d8649-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="d8649-120">結果として得られるパターン一致式により、非常に読みやすい方法でデータを書き込むことができるため、複雑な分岐やデータ分析コードを大幅に簡素化できます。</span><span class="sxs-lookup"><span data-stu-id="d8649-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="d8649-121">部分的なアクティブパターン</span><span class="sxs-lookup"><span data-stu-id="d8649-121">Partial Active Patterns</span></span>

<span data-ttu-id="d8649-122">場合によっては、入力領域の一部だけをパーティション分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8649-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="d8649-123">その場合は、それぞれの入力に一致し、他の入力と一致しない部分パターンのセットを記述します。</span><span class="sxs-lookup"><span data-stu-id="d8649-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="d8649-124">常に値を生成しないアクティブパターンは、*部分的なアクティブパターン*と呼ばれます。これらの値は、オプションの型である戻り値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="d8649-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="d8649-125">部分的なアクティブパターンを定義するには、バナナクリップ\_内のパターンの一覧の末尾にワイルドカード文字 () を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8649-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="d8649-126">次のコードは、部分的なアクティブパターンの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d8649-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="d8649-127">前の例の出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d8649-127">The output of the previous example is as follows:</span></span>

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="d8649-128">部分的なアクティブパターンを使用する場合、個別の選択肢を相互に不整合にしたり、相互に排他的に指定したりすることはできますが、そうする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d8649-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="d8649-129">次の例では、パターンの Square と pattern キューブは、2つの数値 (64 など) の両方を持つため、不整合にはなりません。</span><span class="sxs-lookup"><span data-stu-id="d8649-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="d8649-130">次のプログラムでは、パターンとパターンを使用して、正方形とキューブのパターンを結合しています。</span><span class="sxs-lookup"><span data-stu-id="d8649-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="d8649-131">四角形とキューブの両方であり、キューブのみであるすべての整数が1000まで出力されます。</span><span class="sxs-lookup"><span data-stu-id="d8649-131">It print out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span> 

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="d8649-132">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d8649-132">The output is as follows:</span></span>

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

## <a name="parameterized-active-patterns"></a><span data-ttu-id="d8649-133">パラメーター化されたアクティブパターン</span><span class="sxs-lookup"><span data-stu-id="d8649-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="d8649-134">アクティブパターンは、一致する項目に対して少なくとも1つの引数を受け取りますが、追加の引数を受け取る可能性があります。この場合、パラメーター化された*アクティブパターン*という名前が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8649-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="d8649-135">追加の引数を使用すると、一般的なパターンを特殊化できます。</span><span class="sxs-lookup"><span data-stu-id="d8649-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="d8649-136">たとえば、正規表現を使用して文字列を解析するアクティブパターンでは、次のコードに示すように、正規表現を追加のパラメーターとして使用`Integer`することがよくあります。これは、前のコード例で定義された部分的なアクティブパターンも使用します。</span><span class="sxs-lookup"><span data-stu-id="d8649-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="d8649-137">この例では、さまざまな日付形式の正規表現を使用する文字列が、general ParseRegex アクティブパターンをカスタマイズするために指定されています。</span><span class="sxs-lookup"><span data-stu-id="d8649-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="d8649-138">整数アクティブパターンは、一致した文字列を DateTime コンストラクターに渡すことができる整数に変換するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8649-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="d8649-139">前のコードの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d8649-139">The output of the previous code is as follows:</span></span>

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="d8649-140">アクティブパターンは、パターンマッチング式のみに制限されていません。 let バインドで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8649-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="d8649-141">前のコードの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d8649-141">The output of the previous code is as follows:</span></span>

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="d8649-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8649-142">See also</span></span>

- [<span data-ttu-id="d8649-143">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="d8649-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d8649-144">match 式</span><span class="sxs-lookup"><span data-stu-id="d8649-144">Match Expressions</span></span>](match-expressions.md)
