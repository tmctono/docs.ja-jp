---
title: プレーン テキスト形式
description: 'F # のアプリケーションとスクリプトで、printf とその他のプレーンテキスト形式を使用する方法について説明します。'
ms.date: 07/22/2020
ms.openlocfilehash: 90a861736dae69dfbc199a19e24f587c42404737
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063784"
---
# <a name="plain-text-formatting"></a><span data-ttu-id="4bd49-103">プレーンテキストの書式設定</span><span class="sxs-lookup"><span data-stu-id="4bd49-103">Plain text formatting</span></span>

<span data-ttu-id="4bd49-104">F # `printf` では、、、 `printfn` `sprintf` 、および関連する関数を使用して、プレーンテキストの型チェックがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4bd49-104">F# supports type-checked formatting of plain text using `printf`, `printfn`, `sprintf`, and related functions.</span></span>
<span data-ttu-id="4bd49-105">たとえば、</span><span class="sxs-lookup"><span data-stu-id="4bd49-105">For example,</span></span>

```console
dotnet fsi

> printfn "Hello %s, %d + %d is %d" "world" 2 2 (2+2);;
```

<span data-ttu-id="4bd49-106">出力を提供します。</span><span class="sxs-lookup"><span data-stu-id="4bd49-106">gives the output</span></span>

```fsharp
Hello world, 2 + 2 is 4
```

<span data-ttu-id="4bd49-107">F # では、構造化された値をプレーンテキストとして書式設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-107">F# also allows structured values to be formatted as plain text.</span></span>
<span data-ttu-id="4bd49-108">たとえば、次の例では、出力を行列に似た組の表示として書式設定しています。</span><span class="sxs-lookup"><span data-stu-id="4bd49-108">For example, consider the following example that formats the output as a matrix-like display of tuples.</span></span>

```console
dotnet fsi

> printfn "%A" [ for i in 1 .. 5 -> [ for j in 1 .. 5 -> (i, j) ] ];;

[[(1, 1); (1, 2); (1, 3); (1, 4); (1, 5)];
 [(2, 1); (2, 2); (2, 3); (2, 4); (2, 5)];
 [(3, 1); (3, 2); (3, 3); (3, 4); (3, 5)];
 [(4, 1); (4, 2); (4, 3); (4, 4); (4, 5)];
 [(5, 1); (5, 2); (5, 3); (5, 4); (5, 5)]]
```

<span data-ttu-id="4bd49-109">書式設定文字列の形式を使用すると、構造化されたプレーンテキストの書式設定がアクティブになり `%A` `printf` ます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-109">Structured plain text formatting is activated when you use the `%A` format in `printf` formatting strings.</span></span>
<span data-ttu-id="4bd49-110">また、F # interactive で値の出力を書式設定するときにもアクティブになります。出力には追加情報が含まれ、さらにカスタマイズも可能です。</span><span class="sxs-lookup"><span data-stu-id="4bd49-110">It's also activated when formatting the output of values in F# interactive, where the output includes extra information and is additionally customizable.</span></span>
<span data-ttu-id="4bd49-111">プレーンテキストの書式設定は、 `x.ToString()` F # の共用体とレコードの値に対する呼び出しによっても監視できます。これには、デバッグ、ログ記録、およびその他のツールで暗黙的に発生する値も含まれます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-111">Plain text formatting is also observable through any calls to `x.ToString()` on F# union and record values, including those that occur implicitly in debugging, logging, and other tooling.</span></span>

## <a name="checking-of-printf-format-strings"></a><span data-ttu-id="4bd49-112">`printf`書式指定文字列のチェック</span><span class="sxs-lookup"><span data-stu-id="4bd49-112">Checking of `printf`-format strings</span></span>

<span data-ttu-id="4bd49-113">書式指定 `printf` 文字列の printf 書式指定子に一致しない引数で書式関数を使用すると、コンパイル時エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-113">A compile-time error will be reported if a `printf` formatting function is used with an argument that doesn't match the printf format specifiers in the format string.</span></span>  <span data-ttu-id="4bd49-114">たとえば、</span><span class="sxs-lookup"><span data-stu-id="4bd49-114">For example,</span></span>

```fsharp
sprintf "Hello %s" (2+2)
```

<span data-ttu-id="4bd49-115">出力を提供します。</span><span class="sxs-lookup"><span data-stu-id="4bd49-115">gives the output</span></span>

```console
  sprintf "Hello %s" (2+2)
  ----------------------^

stdin(3,25): error FS0001: The type 'string' does not match the type 'int'
```

<span data-ttu-id="4bd49-116">技術的に言えば、 `printf` およびその他の関連する関数を使用する場合、F # コンパイラの特別な規則によって、書式指定文字列として渡されたリテラル文字列がチェックされます。これにより、適用される後続の引数が、使用される書式指定子と一致する正しい型になります。</span><span class="sxs-lookup"><span data-stu-id="4bd49-116">Technically speaking, when using `printf` and other related functions, a special rule in the F# compiler checks the string literal passed as the format string, ensuring the subsequent arguments applied are of the correct type to match the format specifiers used.</span></span>

## <a name="format-specifiers-for-printf"></a><span data-ttu-id="4bd49-117">の書式指定子`printf`</span><span class="sxs-lookup"><span data-stu-id="4bd49-117">Format specifiers for `printf`</span></span>

<span data-ttu-id="4bd49-118">形式の書式指定 `printf` は、形式を示すマーカーを含む文字列です `%` 。</span><span class="sxs-lookup"><span data-stu-id="4bd49-118">Format specifications for `printf` formats are strings with `%` markers that indicate format.</span></span> <span data-ttu-id="4bd49-119">書式のプレースホルダー `%[flags][width][.precision][type]` は、型が次のように解釈される場所で構成されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-119">Format placeholders consist of `%[flags][width][.precision][type]` where the type is interpreted as follows:</span></span>

| <span data-ttu-id="4bd49-120">書式指定子</span><span class="sxs-lookup"><span data-stu-id="4bd49-120">Format specifier</span></span>   | <span data-ttu-id="4bd49-121">型 (s)</span><span class="sxs-lookup"><span data-stu-id="4bd49-121">Type(s)</span></span>        | <span data-ttu-id="4bd49-122">解説</span><span class="sxs-lookup"><span data-stu-id="4bd49-122">Remarks</span></span>                      |
|:-------------------|:---------------|:-----------------------------|
| `%b`               | <span data-ttu-id="4bd49-123">[bool]</span><span class="sxs-lookup"><span data-stu-id="4bd49-123">bool</span></span>      | <span data-ttu-id="4bd49-124">またはとして書式設定されます。 `true``false`</span><span class="sxs-lookup"><span data-stu-id="4bd49-124">Formatted as `true` or `false`</span></span>                |
| `%s`               | <span data-ttu-id="4bd49-125">string</span><span class="sxs-lookup"><span data-stu-id="4bd49-125">string</span></span>    | <span data-ttu-id="4bd49-126">エスケープ解除されたコンテンツとして書式設定</span><span class="sxs-lookup"><span data-stu-id="4bd49-126">Formatted as its unescaped contents</span></span>         |
| `%c`               | <span data-ttu-id="4bd49-127">char</span><span class="sxs-lookup"><span data-stu-id="4bd49-127">char</span></span>      | <span data-ttu-id="4bd49-128">文字リテラルとして書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-128">Formatted as the character literal</span></span>  |
| <span data-ttu-id="4bd49-129">`%d`, `%i`</span><span class="sxs-lookup"><span data-stu-id="4bd49-129">`%d`, `%i`</span></span>         | <span data-ttu-id="4bd49-130">基本整数型</span><span class="sxs-lookup"><span data-stu-id="4bd49-130">a basic integer type</span></span> | <span data-ttu-id="4bd49-131">10進数の整数として書式設定され、基本整数型が符号付きの場合に符号が付きます</span><span class="sxs-lookup"><span data-stu-id="4bd49-131">Formatted as a decimal integer, signed if the basic integer type is signed</span></span> |
| `%u`               | <span data-ttu-id="4bd49-132">基本整数型</span><span class="sxs-lookup"><span data-stu-id="4bd49-132">a basic integer type</span></span> | <span data-ttu-id="4bd49-133">符号なし10進整数として書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-133">Formatted as an unsigned decimal integer</span></span>   |
| <span data-ttu-id="4bd49-134">`%x`, `%X`</span><span class="sxs-lookup"><span data-stu-id="4bd49-134">`%x`, `%X`</span></span>         | <span data-ttu-id="4bd49-135">基本整数型</span><span class="sxs-lookup"><span data-stu-id="4bd49-135">a basic integer type</span></span> | <span data-ttu-id="4bd49-136">符号なし16進数値として書式設定されます (それぞれ16進数の場合は-f または A-F)</span><span class="sxs-lookup"><span data-stu-id="4bd49-136">Formatted as an unsigned hexadecimal number (a-f or A-F for hex digits respectively)</span></span>  |
|  `%o`              | <span data-ttu-id="4bd49-137">基本整数型</span><span class="sxs-lookup"><span data-stu-id="4bd49-137">a basic integer type</span></span> | <span data-ttu-id="4bd49-138">符号なし8進数値として書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-138">Formatted as an unsigned octal number</span></span> |
| <span data-ttu-id="4bd49-139">`%e`, `%E`</span><span class="sxs-lookup"><span data-stu-id="4bd49-139">`%e`, `%E`</span></span>         | <span data-ttu-id="4bd49-140">基本浮動小数点型</span><span class="sxs-lookup"><span data-stu-id="4bd49-140">a basic floating point type</span></span> | <span data-ttu-id="4bd49-141">形式を持つ符号付きの値として書式設定されます。 d は1桁の10進数、dddd は1桁以上の10進数、 `[-]d.dddde[sign]ddd` ddd は正確に3桁の10進数、sign は `+` またはです。`-`</span><span class="sxs-lookup"><span data-stu-id="4bd49-141">Formatted as a signed value having the form `[-]d.dddde[sign]ddd` where d is a single decimal digit, dddd is one or more decimal digits, ddd is exactly three decimal digits, and sign is `+` or `-`</span></span> |
| `%f`               | <span data-ttu-id="4bd49-142">基本浮動小数点型</span><span class="sxs-lookup"><span data-stu-id="4bd49-142">a basic floating point type</span></span> | <span data-ttu-id="4bd49-143">形式を持つ符号付きの値として書式設定 `[-]dddd.dddd` `dddd` されます。ここで、は1つ以上の10進数です。</span><span class="sxs-lookup"><span data-stu-id="4bd49-143">Formatted as a signed value having the form `[-]dddd.dddd`, where `dddd` is one or more decimal digits.</span></span> <span data-ttu-id="4bd49-144">整数部の桁数は、その数値の絶対値によって決定され、小数部の桁数は要求される精度によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-144">The number of digits before the decimal point depends on the magnitude of the number, and the number of digits after the decimal point depends on the requested precision.</span></span> |
| <span data-ttu-id="4bd49-145">`%g`, `%G`</span><span class="sxs-lookup"><span data-stu-id="4bd49-145">`%g`, `%G`</span></span> | <span data-ttu-id="4bd49-146">基本浮動小数点型</span><span class="sxs-lookup"><span data-stu-id="4bd49-146">a basic floating point type</span></span> |  <span data-ttu-id="4bd49-147">を使用して、または形式で出力される符号付きの値として書式設定 `%f` `%e` されます。指定された値と有効桁数に対してはよりコンパクトになります。</span><span class="sxs-lookup"><span data-stu-id="4bd49-147">Formatted using as a signed value printed in `%f` or `%e` format, whichever is more compact for the given value and precision.</span></span> |
| `%M` | <span data-ttu-id="4bd49-148">`System.Decimal`値</span><span class="sxs-lookup"><span data-stu-id="4bd49-148">a `System.Decimal` value</span></span>  |    <span data-ttu-id="4bd49-149">の書式指定子を使用して書式設定されます。 `"G"``System.Decimal.ToString(format)`</span><span class="sxs-lookup"><span data-stu-id="4bd49-149">Formatted using the `"G"` format specifier for `System.Decimal.ToString(format)`</span></span> |
| `%O` | <span data-ttu-id="4bd49-150">任意の値</span><span class="sxs-lookup"><span data-stu-id="4bd49-150">any value</span></span>  |   <span data-ttu-id="4bd49-151">オブジェクトのボックス化とそのメソッドの呼び出しによって書式設定されます。 `System.Object.ToString()`</span><span class="sxs-lookup"><span data-stu-id="4bd49-151">Formatted by boxing the object and calling its `System.Object.ToString()` method</span></span> |
| `%A` | <span data-ttu-id="4bd49-152">任意の値</span><span class="sxs-lookup"><span data-stu-id="4bd49-152">any value</span></span>  |   <span data-ttu-id="4bd49-153">既定のレイアウト設定で構造化された[プレーンテキストの書式](plaintext-formatting.md)設定を使用して書式設定</span><span class="sxs-lookup"><span data-stu-id="4bd49-153">Formatted using [structured plain text formatting](plaintext-formatting.md) with the default layout settings</span></span> |
| `%a` | <span data-ttu-id="4bd49-154">任意の値</span><span class="sxs-lookup"><span data-stu-id="4bd49-154">any value</span></span>  |   <span data-ttu-id="4bd49-155">2つの引数が必要です。コンテキストパラメーターと値を受け入れる書式設定関数と、出力する特定の値です。</span><span class="sxs-lookup"><span data-stu-id="4bd49-155">Requires two arguments: a formatting function accepting a context parameter and the value, and the particular value to print</span></span> |
| `%t` | <span data-ttu-id="4bd49-156">任意の値</span><span class="sxs-lookup"><span data-stu-id="4bd49-156">any value</span></span>  |   <span data-ttu-id="4bd49-157">1つの引数が必要です。適切なテキストを出力または返すコンテキストパラメーターを受け入れる書式設定関数</span><span class="sxs-lookup"><span data-stu-id="4bd49-157">Requires one argument: a formatting function accepting a context parameter that either outputs or returns the appropriate text</span></span> |
| `%%` | <span data-ttu-id="4bd49-158">(なし)</span><span class="sxs-lookup"><span data-stu-id="4bd49-158">(none)</span></span>  |   <span data-ttu-id="4bd49-159">引数を必要とせず、普通のパーセント記号を出力します。`%`</span><span class="sxs-lookup"><span data-stu-id="4bd49-159">Requires no arguments and prints a plain percent sign: `%`</span></span> |

<span data-ttu-id="4bd49-160">基本整数型は、 `byte` ( `System.Byte` )、 `sbyte` ()、 `System.SByte` `int16` ( `System.Int16` )、 `uint16` ( `System.UInt16` )、 `int32` ( `System.Int32` )、( `uint32` `System.UInt32` )、( `int64` `System.Int64` )、( `uint64` `System.UInt64` )、 `nativeint` ()、 `System.IntPtr` および `unativeint` ( `System.UIntPtr` ) です。</span><span class="sxs-lookup"><span data-stu-id="4bd49-160">Basic integer types are `byte` (`System.Byte`), `sbyte` (`System.SByte`), `int16` (`System.Int16`), `uint16` (`System.UInt16`), `int32` (`System.Int32`), `uint32` (`System.UInt32`), `int64` (`System.Int64`), `uint64` (`System.UInt64`), `nativeint`  (`System.IntPtr`), and `unativeint`  (`System.UIntPtr`).</span></span>
<span data-ttu-id="4bd49-161">基本浮動小数点型 `float` は `System.Double` 、() および `float32` ( `System.Single` ) です。</span><span class="sxs-lookup"><span data-stu-id="4bd49-161">Basic floating point types are `float` (`System.Double`) and `float32` (`System.Single`).</span></span>

<span data-ttu-id="4bd49-162">省略可能な幅は、結果の最小幅を示す整数です。</span><span class="sxs-lookup"><span data-stu-id="4bd49-162">The optional width is an integer indicating the minimal width of the result.</span></span> <span data-ttu-id="4bd49-163">たとえば、は `%6d` 整数を出力し、少なくとも6文字を埋めるためにスペースをプレフィックスとして付けます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-163">For instance, `%6d` prints an integer, prefixing it with spaces to fill at least six characters.</span></span> <span data-ttu-id="4bd49-164">Width がの場合は `*` 、対応する幅を指定するために追加の整数引数が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-164">If width is `*`, then an extra integer  argument is taken to specify the corresponding width.</span></span>

<span data-ttu-id="4bd49-165">有効なフラグは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4bd49-165">Valid flags are:</span></span>

| <span data-ttu-id="4bd49-166">フラグ</span><span class="sxs-lookup"><span data-stu-id="4bd49-166">Flag</span></span>   | <span data-ttu-id="4bd49-167">効果</span><span class="sxs-lookup"><span data-stu-id="4bd49-167">Effect</span></span>        | <span data-ttu-id="4bd49-168">解説</span><span class="sxs-lookup"><span data-stu-id="4bd49-168">Remarks</span></span>                      |
|:-------------------|:---------------|:-----------------------------|
| `0`  | <span data-ttu-id="4bd49-169">必要な幅を構成するために、スペースではなくゼロを追加します。</span><span class="sxs-lookup"><span data-stu-id="4bd49-169">Add zeros instead of spaces to make up the required width</span></span> |    |
| `-` |  <span data-ttu-id="4bd49-170">指定された幅の範囲内で結果を左揃えにします</span><span class="sxs-lookup"><span data-stu-id="4bd49-170">Left justify the result within the specified width</span></span> |   |
| `+`  | <span data-ttu-id="4bd49-171">`+`数値が正の場合に文字を追加します ( `-` 負の符号に一致させるため)</span><span class="sxs-lookup"><span data-stu-id="4bd49-171">Add a `+` character if the number is positive (to match a `-` sign for negatives)</span></span> |   |
| <span data-ttu-id="4bd49-172">空白文字</span><span class="sxs-lookup"><span data-stu-id="4bd49-172">space character</span></span> | <span data-ttu-id="4bd49-173">数値が正の値の場合は余分なスペースを追加します (ネガの符号 '-' と一致させるため)</span><span class="sxs-lookup"><span data-stu-id="4bd49-173">Add an extra space if the number is positive (to match a '-' sign for negatives)</span></span> |

<span data-ttu-id="4bd49-174">Printf フラグが無効であり、使用されて `#` いる場合、コンパイル時エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-174">The printf `#` flag is invalid and a compile-time error will be reported if it is used.</span></span>

<span data-ttu-id="4bd49-175">値は、インバリアントカルチャを使用して書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-175">Values are formatted using invariant culture.</span></span> <span data-ttu-id="4bd49-176">カルチャ設定は、書式設定 `printf` の結果に影響を与える場合を除き、書式設定には関係あり `%O` `%A` ません。</span><span class="sxs-lookup"><span data-stu-id="4bd49-176">Culture settings are irrelevant to `printf` formatting except when they affect the results of `%O` and `%A` formatting.</span></span> <span data-ttu-id="4bd49-177">詳細については、「構造化された[プレーンテキストの書式設定](plaintext-formatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bd49-177">For more information, see [structured plain text formatting](plaintext-formatting.md).</span></span>

## <a name="a-formatting"></a><span data-ttu-id="4bd49-178">`%A`書式設定</span><span class="sxs-lookup"><span data-stu-id="4bd49-178">`%A` formatting</span></span>

<span data-ttu-id="4bd49-179">`%A`書式指定子は、ユーザーが判読できる方法で値の書式を設定するために使用されます。また、診断情報の報告にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-179">The `%A` format specifier is used to format values in a human-readable way, and can also be useful for reporting diagnostic information.</span></span>

### <a name="primitive-values"></a><span data-ttu-id="4bd49-180">プリミティブ値</span><span class="sxs-lookup"><span data-stu-id="4bd49-180">Primitive values</span></span>

<span data-ttu-id="4bd49-181">指定子を使用してプレーンテキストの書式を設定すると `%A` 、F # の数値はサフィックスとインバリアントカルチャを使用して書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-181">When formatting plain text using the `%A` specifier, F# numeric values are formatted with their suffix and invariant culture.</span></span> <span data-ttu-id="4bd49-182">浮動小数点値は、浮動小数点の有効桁数の10の位置を使用して書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-182">Floating point values are formatted using 10 places of floating point precision.</span></span> <span data-ttu-id="4bd49-183">たとえば、</span><span class="sxs-lookup"><span data-stu-id="4bd49-183">For example,</span></span>

```fsharp
printfn "%A" (1L, 3n, 5u, 7, 4.03f, 5.000000001, 5.0000000001)
```

<span data-ttu-id="4bd49-184">枝分かれ</span><span class="sxs-lookup"><span data-stu-id="4bd49-184">produces</span></span>

```console
(1L, 3n, 5u, 7, 4.03000021f, 5.000000001, 5.0)
```

<span data-ttu-id="4bd49-185">指定子を使用する場合 `%A` 、文字列は引用符を使用して書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-185">When using the `%A` specifier, strings are formatted using quotes.</span></span> <span data-ttu-id="4bd49-186">エスケープコードは追加されず、生の文字が出力されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-186">Escape codes are not added and instead the raw characters are printed.</span></span> <span data-ttu-id="4bd49-187">たとえば、</span><span class="sxs-lookup"><span data-stu-id="4bd49-187">For example,</span></span>

```fsharp
printfn "%A" ("abc", "a\tb\nc\"d")

```

<span data-ttu-id="4bd49-188">枝分かれ</span><span class="sxs-lookup"><span data-stu-id="4bd49-188">produces</span></span>

```console
("abc", "a      b
c"d")
```

### <a name="net-values"></a><span data-ttu-id="4bd49-189">.NET の値</span><span class="sxs-lookup"><span data-stu-id="4bd49-189">.NET values</span></span>

<span data-ttu-id="4bd49-190">指定子を使用してプレーンテキストを書式設定する場合 `%A` 、F # 以外の .net オブジェクトは、 `x.ToString()` およびで指定された .net の既定の設定を使用して書式設定され `System.Globalization.CultureInfo.CurrentCulture` `System.Globalization.CultureInfo.CurrentUICulture` ます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-190">When formatting plain text using the `%A` specifier, non-F# .NET objects are formatted by using `x.ToString()` using the default settings of .NET given by `System.Globalization.CultureInfo.CurrentCulture` and `System.Globalization.CultureInfo.CurrentUICulture`.</span></span>  <span data-ttu-id="4bd49-191">たとえば、</span><span class="sxs-lookup"><span data-stu-id="4bd49-191">For example,</span></span>

```fsharp
open System.Globalization

let date = System.DateTime(1999, 12, 31)

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("de-DE")
printfn "Culture 1: %A" date

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("en-US")
printfn "Culture 2: %A" date
```

<span data-ttu-id="4bd49-192">枝分かれ</span><span class="sxs-lookup"><span data-stu-id="4bd49-192">produces</span></span>

```console
Culture 1: 31.12.1999 00:00:00
Culture 2: 12/31/1999 12:00:00 AM
```

### <a name="structured-values"></a><span data-ttu-id="4bd49-193">構造化された値</span><span class="sxs-lookup"><span data-stu-id="4bd49-193">Structured values</span></span>

<span data-ttu-id="4bd49-194">指定子を使用してプレーンテキストを書式設定する場合 `%A` 、F # のリストと組に対してブロックインデントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-194">When formatting plain text using the `%A` specifier, block indentation is used for F# lists and tuples.</span></span> <span data-ttu-id="4bd49-195">これは、前の例で示したようになっています。</span><span class="sxs-lookup"><span data-stu-id="4bd49-195">This shown in the previous example.</span></span>
<span data-ttu-id="4bd49-196">多次元配列を含む配列の構造も使用されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-196">The structure of arrays is also used, including multi-dimensional arrays.</span></span>  <span data-ttu-id="4bd49-197">1次元配列は、構文と共に表示され `[| ... |]` ます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-197">Single-dimensional arrays are shown with `[| ... |]` syntax.</span></span> <span data-ttu-id="4bd49-198">たとえば、</span><span class="sxs-lookup"><span data-stu-id="4bd49-198">For example,</span></span>

```fsharp
printfn "%A" [| for i in 1 .. 20 -> (i, i*i) |]
```

<span data-ttu-id="4bd49-199">枝分かれ</span><span class="sxs-lookup"><span data-stu-id="4bd49-199">produces</span></span>

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25); (6, 36); (7, 49); (8, 64); (9, 81);
  (10, 100); (11, 121); (12, 144); (13, 169); (14, 196); (15, 225); (16, 256);
  (17, 289); (18, 324); (19, 361); (20, 400)|]
```

<span data-ttu-id="4bd49-200">既定の印刷幅は80です。</span><span class="sxs-lookup"><span data-stu-id="4bd49-200">The default print width is 80.</span></span>  <span data-ttu-id="4bd49-201">この幅は、書式指定子の印刷幅を使用してカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-201">This width can be customized by using a print width in the format specifier.</span></span> <span data-ttu-id="4bd49-202">たとえば、</span><span class="sxs-lookup"><span data-stu-id="4bd49-202">For example,</span></span>

```fsharp
printfn "%10A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%20A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%50A" [| for i in 1 .. 5 -> (i, i*i) |]
```

<span data-ttu-id="4bd49-203">枝分かれ</span><span class="sxs-lookup"><span data-stu-id="4bd49-203">produces</span></span>

```console
[|(1, 1);
  (2, 4);
  (3, 9);
  (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4);
  (3, 9); (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
```

<span data-ttu-id="4bd49-204">印刷幅を0に指定すると、印刷幅が使用されなくなります。</span><span class="sxs-lookup"><span data-stu-id="4bd49-204">Specifying a print width of 0 results in no print width being used.</span></span> <span data-ttu-id="4bd49-205">出力内の埋め込み文字列に改行が含まれている場合を除き、1行のテキストが生成されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-205">A single line of text will result, except where embedded strings in the output contain line breaks.</span></span>  <span data-ttu-id="4bd49-206">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4bd49-206">For example</span></span>

```fsharp
printfn "%0A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%0A" [| for i in 1 .. 5 -> "abc\ndef" |]
```

<span data-ttu-id="4bd49-207">枝分かれ</span><span class="sxs-lookup"><span data-stu-id="4bd49-207">produces</span></span>

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
[|"abc
def"; "abc
def"; "abc
def"; "abc
def"; "abc
def"|]
```

<span data-ttu-id="4bd49-208">深さの制限4は、として表示される sequence () 値に使用され `IEnumerable` `seq { ...}` ます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-208">A depth limit of 4 is used for sequence (`IEnumerable`) values, which are shown as `seq { ...}`.</span></span> <span data-ttu-id="4bd49-209">深さの制限100は、リストと配列の値に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-209">A depth limit of 100 is used for list and array values.</span></span>
<span data-ttu-id="4bd49-210">たとえば、</span><span class="sxs-lookup"><span data-stu-id="4bd49-210">For example,</span></span>

```fsharp
printfn "%A" (seq { for i in 1 .. 10 -> (i, i*i) })
```

<span data-ttu-id="4bd49-211">枝分かれ</span><span class="sxs-lookup"><span data-stu-id="4bd49-211">produces</span></span>

```console
seq [(1, 1); (2, 4); (3, 9); (4, 16); ...]
```

<span data-ttu-id="4bd49-212">ブロックインデントは、パブリックレコードと共用体の値の構造にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-212">Block indentation is also used for the structure of public record and union values.</span></span> <span data-ttu-id="4bd49-213">たとえば、</span><span class="sxs-lookup"><span data-stu-id="4bd49-213">For example,</span></span>

```fsharp
type R = { X : int list; Y : string list }

printfn "%A" { X =  [ 1;2;3 ]; Y = ["one"; "two"; "three"] }
```

<span data-ttu-id="4bd49-214">枝分かれ</span><span class="sxs-lookup"><span data-stu-id="4bd49-214">produces</span></span>

```console
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

<span data-ttu-id="4bd49-215">を `%+A` 使用すると、レコードと共用体のプライベート構造もリフレクションを使用して明らかになります。</span><span class="sxs-lookup"><span data-stu-id="4bd49-215">If `%+A` is used, then the private structure of records and unions is also revealed by using reflection.</span></span> <span data-ttu-id="4bd49-216">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4bd49-216">For example</span></span>

```fsharp
type internal R =
    { X : int list; Y : string list }
    override _.ToString() = "R"

let internal data = { X = [ 1;2;3 ]; Y = ["one"; "two"; "three"] }

printfn "external view:\n%A" data

printfn "internal view:\n%+A" data

```

<span data-ttu-id="4bd49-217">枝分かれ</span><span class="sxs-lookup"><span data-stu-id="4bd49-217">produces</span></span>

```console
external view:
R

internal view:
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

### <a name="large-cyclic-or-deeply-nested-values"></a><span data-ttu-id="4bd49-218">大きい、循環、または深い入れ子になった値</span><span class="sxs-lookup"><span data-stu-id="4bd49-218">Large, cyclic, or deeply nested values</span></span>

<span data-ttu-id="4bd49-219">大規模な構造化値は、全体のオブジェクトノード数の上限である1万に書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-219">Large structured values are formatted to a maximum overall object node count of 10000.</span></span>
<span data-ttu-id="4bd49-220">深い入れ子になった値は、深さが100に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-220">Deeply nested values are formatted to a depth of 100.</span></span>  <span data-ttu-id="4bd49-221">どちらの場合も `...` 、を使用して出力の一部を除外します。</span><span class="sxs-lookup"><span data-stu-id="4bd49-221">In both cases `...` is used to elide some of the output.</span></span>  <span data-ttu-id="4bd49-222">たとえば、</span><span class="sxs-lookup"><span data-stu-id="4bd49-222">For example,</span></span>

```fsharp
type Tree =
    | Tip
    | Node of Tree * Tree

let rec make n =
    if n = 0 then
        Tip
    else
        Node(Tip, make (n-1))

printfn "%A" (make 1000)
```

<span data-ttu-id="4bd49-223">一部の部分を省略して、大きな出力を生成します。</span><span class="sxs-lookup"><span data-stu-id="4bd49-223">produces a large output with some parts elided:</span></span>

```console
Node(Tip, Node(Tip, ....Node (..., ...)...))
```

<span data-ttu-id="4bd49-224">サイクルは、オブジェクトグラフで検出され、 `...` サイクルが検出された場所で使用されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-224">Cycles are detected in the object graphs and `...` is used at places where cycles are detected.</span></span> <span data-ttu-id="4bd49-225">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4bd49-225">For example</span></span>

```fsharp
type R = { mutable Links: R list }
let r = { Links = [] }
r.Links <- [r]
printfn "%A" r
```

<span data-ttu-id="4bd49-226">枝分かれ</span><span class="sxs-lookup"><span data-stu-id="4bd49-226">produces</span></span>

```console
{ Links = [...] }
```

### <a name="lazy-null-and-function-values"></a><span data-ttu-id="4bd49-227">Lazy、null、および関数の値</span><span class="sxs-lookup"><span data-stu-id="4bd49-227">Lazy, null, and function values</span></span>

<span data-ttu-id="4bd49-228">遅延値は `Value is not created` 、値がまだ評価されていない場合、または同等のテキストとして出力されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-228">Lazy values are printed as `Value is not created` or equivalent text when the value has not yet been evaluated.</span></span>

<span data-ttu-id="4bd49-229">Null 値はとして出力され `null` ます。ただし、値の静的な型が共用体型であると判断された場合 `null` は、が許可された表現になります。</span><span class="sxs-lookup"><span data-stu-id="4bd49-229">Null values are printed as `null` unless the static type of the value is determined to be a union type where `null` is a permitted representation.</span></span>

<span data-ttu-id="4bd49-230">F # 関数の値は、内部で生成されたクロージャ名として出力されます。たとえば、のように `<fun:it@43-7>` なります。</span><span class="sxs-lookup"><span data-stu-id="4bd49-230">F# function values are printed as their internally generated closure name, for example, `<fun:it@43-7>`.</span></span>

### <a name="customize-plain-text-formatting-with-structuredformatdisplay"></a><span data-ttu-id="4bd49-231">プレーンテキストの書式設定をでカスタマイズする`StructuredFormatDisplay`</span><span class="sxs-lookup"><span data-stu-id="4bd49-231">Customize plain text formatting with `StructuredFormatDisplay`</span></span>

<span data-ttu-id="4bd49-232">指定子を使用する場合 `%A` 、 `StructuredFormatDisplay` 型宣言に属性が存在することが尊重されます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-232">When using the `%A` specifier, the presence of the `StructuredFormatDisplay` attribute on type declarations is respected.</span></span>  <span data-ttu-id="4bd49-233">これを使用すると、サロゲートテキストおよびプロパティを指定して値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-233">This can be used to specify surrogate text and property to display a value.</span></span> <span data-ttu-id="4bd49-234">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4bd49-234">For example:</span></span>

```fsharp
[<StructuredFormatDisplay("Counts({Clicks})")>]
type Counts = { Clicks:int list}

printfn "%20A" {Clicks=[0..20]}
```

<span data-ttu-id="4bd49-235">枝分かれ</span><span class="sxs-lookup"><span data-stu-id="4bd49-235">produces</span></span>

```console
Counts([0; 1; 2; 3;
        4; 5; 6; 7;
        8; 9; 10; 11;
        12; 13; 14;
        15; 16; 17;
        18; 19; 20])
```

### <a name="customize-plain-text-formatting-by-overriding-tostring"></a><span data-ttu-id="4bd49-236">オーバーライドしてプレーンテキストの書式設定をカスタマイズする`ToString`</span><span class="sxs-lookup"><span data-stu-id="4bd49-236">Customize plain text formatting by overriding `ToString`</span></span>

<span data-ttu-id="4bd49-237">の既定の実装 `ToString` は、F # プログラミングで監視できます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-237">The default implementation of `ToString` is observable in F# programming.</span></span> <span data-ttu-id="4bd49-238">多くの場合、既定の結果は、プログラマによる情報の表示またはユーザー出力での使用に適しているわけではありません。そのため、既定の実装をオーバーライドするのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="4bd49-238">Often, the default results aren't suitable for use in either programmer-facing information display or user output, and as a result it is common to override the default implementation.</span></span>  

<span data-ttu-id="4bd49-239">既定では、F # のレコード型と共用体型は、を使用する実装でのの実装をオーバーライドし `ToString` `sprintf "%+A"` ます。</span><span class="sxs-lookup"><span data-stu-id="4bd49-239">By default, F# record and union types override the implementation of `ToString` with an implementation that uses `sprintf "%+A"`.</span></span>  <span data-ttu-id="4bd49-240">たとえば、</span><span class="sxs-lookup"><span data-stu-id="4bd49-240">For example,</span></span>

```fsharp
type Counts = { Clicks:int list }

printfn "%s" ({Clicks=[0..10]}.ToString())
```

<span data-ttu-id="4bd49-241">枝分かれ</span><span class="sxs-lookup"><span data-stu-id="4bd49-241">produces</span></span>

```console
{ Clicks = [0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10] }
```

<span data-ttu-id="4bd49-242">クラス型の場合、の既定の実装は提供されず、 `ToString` .net の既定値が使用されます。これは、型の名前を報告します。</span><span class="sxs-lookup"><span data-stu-id="4bd49-242">For class types, no default implementation of `ToString` is provided and the .NET default is used, which reports the name of the type.</span></span> <span data-ttu-id="4bd49-243">たとえば、</span><span class="sxs-lookup"><span data-stu-id="4bd49-243">For example,</span></span>

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Default structured print gives this:\n%A" data
printfn "Default ToString gives:\n%s" (data.ToString())
```

<span data-ttu-id="4bd49-244">枝分かれ</span><span class="sxs-lookup"><span data-stu-id="4bd49-244">produces</span></span>

```console
Default structured print gives this:
[MyClassType; MyClassType]
Default ToString gives:
[MyClassType; MyClassType]
```

<span data-ttu-id="4bd49-245">のオーバーライドを追加すると、 `ToString` 書式設定が向上します。</span><span class="sxs-lookup"><span data-stu-id="4bd49-245">Adding an override for `ToString` can give better formatting.</span></span>

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks
   override _.ToString() = sprintf "MyClassType(%0A)" clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Now structured print gives this:\n%A" data
printfn "Now ToString gives:\n%s" (data.ToString())
```

<span data-ttu-id="4bd49-246">枝分かれ</span><span class="sxs-lookup"><span data-stu-id="4bd49-246">produces</span></span>

```console
Now structured print gives this:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
Now ToString gives:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
```

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="4bd49-247">構造化された印刷の F# インタラクティブ</span><span class="sxs-lookup"><span data-stu-id="4bd49-247">F# Interactive structured printing</span></span>

<span data-ttu-id="4bd49-248">F# インタラクティブ ( `dotnet fsi` ) では、構造化されたプレーンテキスト形式の拡張バージョンを使用して値を報告し、追加のカスタマイズを可能にします。</span><span class="sxs-lookup"><span data-stu-id="4bd49-248">F# Interactive (`dotnet fsi`) uses an extended version of structured plain text formatting to report values and allows additional customizability.</span></span> <span data-ttu-id="4bd49-249">詳細については、「 [F# インタラクティブ](fsharp-interactive-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bd49-249">For more information, see [F# Interactive](fsharp-interactive-options.md).</span></span>

## <a name="customize-debug-displays"></a><span data-ttu-id="4bd49-250">デバッグディスプレイのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4bd49-250">Customize debug displays</span></span>

<span data-ttu-id="4bd49-251">.NET 用のデバッガーは、やなどの属性の使用を尊重 `DebuggerDisplay` `DebuggerTypeProxy` し、デバッガーの検査ウィンドウでのオブジェクトの構造化表示に影響します。</span><span class="sxs-lookup"><span data-stu-id="4bd49-251">Debuggers for .NET respect the use of attributes such as `DebuggerDisplay` and `DebuggerTypeProxy`, and these affect the structured display of objects in debugger inspection windows.</span></span>
<span data-ttu-id="4bd49-252">F # コンパイラは、判別された共用体型とレコード型に対してこれらの属性を自動的に生成しましたが、クラス、インターフェイス、または構造体型には対応していません。</span><span class="sxs-lookup"><span data-stu-id="4bd49-252">The F# compiler automatically generated these attributes for discriminated union and record types, but not class, interface, or struct types.</span></span>

<span data-ttu-id="4bd49-253">F # プレーンテキストの書式設定では、これらの属性は無視されますが、F # の型をデバッグするときに表示を改善するためにこれらのメソッドを実装すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4bd49-253">These attributes are ignored in F# plain text formatting, but it can be useful to implement these methods to improve displays when debugging F# types.</span></span>

## <a name="see-also"></a><span data-ttu-id="4bd49-254">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bd49-254">See also</span></span>

- [<span data-ttu-id="4bd49-255">文字列</span><span class="sxs-lookup"><span data-stu-id="4bd49-255">Strings</span></span>](strings.md)
- [<span data-ttu-id="4bd49-256">レコード</span><span class="sxs-lookup"><span data-stu-id="4bd49-256">Records</span></span>](records.md)
- [<span data-ttu-id="4bd49-257">判別共用体</span><span class="sxs-lookup"><span data-stu-id="4bd49-257">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="4bd49-258">F# Interactive</span><span class="sxs-lookup"><span data-stu-id="4bd49-258">F# Interactive</span></span>](fsharp-interactive-options.md)
