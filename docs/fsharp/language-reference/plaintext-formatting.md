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
# <a name="plain-text-formatting"></a>プレーンテキストの書式設定

F # `printf` では、、、 `printfn` `sprintf` 、および関連する関数を使用して、プレーンテキストの型チェックがサポートされています。
たとえば、

```console
dotnet fsi

> printfn "Hello %s, %d + %d is %d" "world" 2 2 (2+2);;
```

出力を提供します。

```fsharp
Hello world, 2 + 2 is 4
```

F # では、構造化された値をプレーンテキストとして書式設定することもできます。
たとえば、次の例では、出力を行列に似た組の表示として書式設定しています。

```console
dotnet fsi

> printfn "%A" [ for i in 1 .. 5 -> [ for j in 1 .. 5 -> (i, j) ] ];;

[[(1, 1); (1, 2); (1, 3); (1, 4); (1, 5)];
 [(2, 1); (2, 2); (2, 3); (2, 4); (2, 5)];
 [(3, 1); (3, 2); (3, 3); (3, 4); (3, 5)];
 [(4, 1); (4, 2); (4, 3); (4, 4); (4, 5)];
 [(5, 1); (5, 2); (5, 3); (5, 4); (5, 5)]]
```

書式設定文字列の形式を使用すると、構造化されたプレーンテキストの書式設定がアクティブになり `%A` `printf` ます。
また、F # interactive で値の出力を書式設定するときにもアクティブになります。出力には追加情報が含まれ、さらにカスタマイズも可能です。
プレーンテキストの書式設定は、 `x.ToString()` F # の共用体とレコードの値に対する呼び出しによっても監視できます。これには、デバッグ、ログ記録、およびその他のツールで暗黙的に発生する値も含まれます。

## <a name="checking-of-printf-format-strings"></a>`printf`書式指定文字列のチェック

書式指定 `printf` 文字列の printf 書式指定子に一致しない引数で書式関数を使用すると、コンパイル時エラーが報告されます。  たとえば、

```fsharp
sprintf "Hello %s" (2+2)
```

出力を提供します。

```console
  sprintf "Hello %s" (2+2)
  ----------------------^

stdin(3,25): error FS0001: The type 'string' does not match the type 'int'
```

技術的に言えば、 `printf` およびその他の関連する関数を使用する場合、F # コンパイラの特別な規則によって、書式指定文字列として渡されたリテラル文字列がチェックされます。これにより、適用される後続の引数が、使用される書式指定子と一致する正しい型になります。

## <a name="format-specifiers-for-printf"></a>の書式指定子`printf`

形式の書式指定 `printf` は、形式を示すマーカーを含む文字列です `%` 。 書式のプレースホルダー `%[flags][width][.precision][type]` は、型が次のように解釈される場所で構成されます。

| 書式指定子   | 型 (s)        | 解説                      |
|:-------------------|:---------------|:-----------------------------|
| `%b`               | [bool]      | またはとして書式設定されます。 `true``false`                |
| `%s`               | string    | エスケープ解除されたコンテンツとして書式設定         |
| `%c`               | char      | 文字リテラルとして書式設定されます。  |
| `%d`, `%i`         | 基本整数型 | 10進数の整数として書式設定され、基本整数型が符号付きの場合に符号が付きます |
| `%u`               | 基本整数型 | 符号なし10進整数として書式設定されます。   |
| `%x`, `%X`         | 基本整数型 | 符号なし16進数値として書式設定されます (それぞれ16進数の場合は-f または A-F)  |
|  `%o`              | 基本整数型 | 符号なし8進数値として書式設定されます。 |
| `%e`, `%E`         | 基本浮動小数点型 | 形式を持つ符号付きの値として書式設定されます。 d は1桁の10進数、dddd は1桁以上の10進数、 `[-]d.dddde[sign]ddd` ddd は正確に3桁の10進数、sign は `+` またはです。`-` |
| `%f`               | 基本浮動小数点型 | 形式を持つ符号付きの値として書式設定 `[-]dddd.dddd` `dddd` されます。ここで、は1つ以上の10進数です。 整数部の桁数は、その数値の絶対値によって決定され、小数部の桁数は要求される精度によって決定されます。 |
| `%g`, `%G` | 基本浮動小数点型 |  を使用して、または形式で出力される符号付きの値として書式設定 `%f` `%e` されます。指定された値と有効桁数に対してはよりコンパクトになります。 |
| `%M` | `System.Decimal`値  |    の書式指定子を使用して書式設定されます。 `"G"``System.Decimal.ToString(format)` |
| `%O` | 任意の値  |   オブジェクトのボックス化とそのメソッドの呼び出しによって書式設定されます。 `System.Object.ToString()` |
| `%A` | 任意の値  |   既定のレイアウト設定で構造化された[プレーンテキストの書式](plaintext-formatting.md)設定を使用して書式設定 |
| `%a` | 任意の値  |   2つの引数が必要です。コンテキストパラメーターと値を受け入れる書式設定関数と、出力する特定の値です。 |
| `%t` | 任意の値  |   1つの引数が必要です。適切なテキストを出力または返すコンテキストパラメーターを受け入れる書式設定関数 |
| `%%` | (なし)  |   引数を必要とせず、普通のパーセント記号を出力します。`%` |

基本整数型は、 `byte` ( `System.Byte` )、 `sbyte` ()、 `System.SByte` `int16` ( `System.Int16` )、 `uint16` ( `System.UInt16` )、 `int32` ( `System.Int32` )、( `uint32` `System.UInt32` )、( `int64` `System.Int64` )、( `uint64` `System.UInt64` )、 `nativeint` ()、 `System.IntPtr` および `unativeint` ( `System.UIntPtr` ) です。
基本浮動小数点型 `float` は `System.Double` 、() および `float32` ( `System.Single` ) です。

省略可能な幅は、結果の最小幅を示す整数です。 たとえば、は `%6d` 整数を出力し、少なくとも6文字を埋めるためにスペースをプレフィックスとして付けます。 Width がの場合は `*` 、対応する幅を指定するために追加の整数引数が使用されます。

有効なフラグは次のとおりです。

| フラグ   | 効果        | 解説                      |
|:-------------------|:---------------|:-----------------------------|
| `0`  | 必要な幅を構成するために、スペースではなくゼロを追加します。 |    |
| `-` |  指定された幅の範囲内で結果を左揃えにします |   |
| `+`  | `+`数値が正の場合に文字を追加します ( `-` 負の符号に一致させるため) |   |
| 空白文字 | 数値が正の値の場合は余分なスペースを追加します (ネガの符号 '-' と一致させるため) |

Printf フラグが無効であり、使用されて `#` いる場合、コンパイル時エラーが報告されます。

値は、インバリアントカルチャを使用して書式設定されます。 カルチャ設定は、書式設定 `printf` の結果に影響を与える場合を除き、書式設定には関係あり `%O` `%A` ません。 詳細については、「構造化された[プレーンテキストの書式設定](plaintext-formatting.md)」を参照してください。

## <a name="a-formatting"></a>`%A`書式設定

`%A`書式指定子は、ユーザーが判読できる方法で値の書式を設定するために使用されます。また、診断情報の報告にも役立ちます。

### <a name="primitive-values"></a>プリミティブ値

指定子を使用してプレーンテキストの書式を設定すると `%A` 、F # の数値はサフィックスとインバリアントカルチャを使用して書式設定されます。 浮動小数点値は、浮動小数点の有効桁数の10の位置を使用して書式設定されます。 たとえば、

```fsharp
printfn "%A" (1L, 3n, 5u, 7, 4.03f, 5.000000001, 5.0000000001)
```

枝分かれ

```console
(1L, 3n, 5u, 7, 4.03000021f, 5.000000001, 5.0)
```

指定子を使用する場合 `%A` 、文字列は引用符を使用して書式設定されます。 エスケープコードは追加されず、生の文字が出力されます。 たとえば、

```fsharp
printfn "%A" ("abc", "a\tb\nc\"d")

```

枝分かれ

```console
("abc", "a      b
c"d")
```

### <a name="net-values"></a>.NET の値

指定子を使用してプレーンテキストを書式設定する場合 `%A` 、F # 以外の .net オブジェクトは、 `x.ToString()` およびで指定された .net の既定の設定を使用して書式設定され `System.Globalization.CultureInfo.CurrentCulture` `System.Globalization.CultureInfo.CurrentUICulture` ます。  たとえば、

```fsharp
open System.Globalization

let date = System.DateTime(1999, 12, 31)

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("de-DE")
printfn "Culture 1: %A" date

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("en-US")
printfn "Culture 2: %A" date
```

枝分かれ

```console
Culture 1: 31.12.1999 00:00:00
Culture 2: 12/31/1999 12:00:00 AM
```

### <a name="structured-values"></a>構造化された値

指定子を使用してプレーンテキストを書式設定する場合 `%A` 、F # のリストと組に対してブロックインデントが使用されます。 これは、前の例で示したようになっています。
多次元配列を含む配列の構造も使用されます。  1次元配列は、構文と共に表示され `[| ... |]` ます。 たとえば、

```fsharp
printfn "%A" [| for i in 1 .. 20 -> (i, i*i) |]
```

枝分かれ

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25); (6, 36); (7, 49); (8, 64); (9, 81);
  (10, 100); (11, 121); (12, 144); (13, 169); (14, 196); (15, 225); (16, 256);
  (17, 289); (18, 324); (19, 361); (20, 400)|]
```

既定の印刷幅は80です。  この幅は、書式指定子の印刷幅を使用してカスタマイズできます。 たとえば、

```fsharp
printfn "%10A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%20A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%50A" [| for i in 1 .. 5 -> (i, i*i) |]
```

枝分かれ

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

印刷幅を0に指定すると、印刷幅が使用されなくなります。 出力内の埋め込み文字列に改行が含まれている場合を除き、1行のテキストが生成されます。  次に例を示します。

```fsharp
printfn "%0A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%0A" [| for i in 1 .. 5 -> "abc\ndef" |]
```

枝分かれ

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
[|"abc
def"; "abc
def"; "abc
def"; "abc
def"; "abc
def"|]
```

深さの制限4は、として表示される sequence () 値に使用され `IEnumerable` `seq { ...}` ます。 深さの制限100は、リストと配列の値に使用されます。
たとえば、

```fsharp
printfn "%A" (seq { for i in 1 .. 10 -> (i, i*i) })
```

枝分かれ

```console
seq [(1, 1); (2, 4); (3, 9); (4, 16); ...]
```

ブロックインデントは、パブリックレコードと共用体の値の構造にも使用されます。 たとえば、

```fsharp
type R = { X : int list; Y : string list }

printfn "%A" { X =  [ 1;2;3 ]; Y = ["one"; "two"; "three"] }
```

枝分かれ

```console
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

を `%+A` 使用すると、レコードと共用体のプライベート構造もリフレクションを使用して明らかになります。 次に例を示します。

```fsharp
type internal R =
    { X : int list; Y : string list }
    override _.ToString() = "R"

let internal data = { X = [ 1;2;3 ]; Y = ["one"; "two"; "three"] }

printfn "external view:\n%A" data

printfn "internal view:\n%+A" data

```

枝分かれ

```console
external view:
R

internal view:
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

### <a name="large-cyclic-or-deeply-nested-values"></a>大きい、循環、または深い入れ子になった値

大規模な構造化値は、全体のオブジェクトノード数の上限である1万に書式設定されます。
深い入れ子になった値は、深さが100に設定されます。  どちらの場合も `...` 、を使用して出力の一部を除外します。  たとえば、

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

一部の部分を省略して、大きな出力を生成します。

```console
Node(Tip, Node(Tip, ....Node (..., ...)...))
```

サイクルは、オブジェクトグラフで検出され、 `...` サイクルが検出された場所で使用されます。 次に例を示します。

```fsharp
type R = { mutable Links: R list }
let r = { Links = [] }
r.Links <- [r]
printfn "%A" r
```

枝分かれ

```console
{ Links = [...] }
```

### <a name="lazy-null-and-function-values"></a>Lazy、null、および関数の値

遅延値は `Value is not created` 、値がまだ評価されていない場合、または同等のテキストとして出力されます。

Null 値はとして出力され `null` ます。ただし、値の静的な型が共用体型であると判断された場合 `null` は、が許可された表現になります。

F # 関数の値は、内部で生成されたクロージャ名として出力されます。たとえば、のように `<fun:it@43-7>` なります。

### <a name="customize-plain-text-formatting-with-structuredformatdisplay"></a>プレーンテキストの書式設定をでカスタマイズする`StructuredFormatDisplay`

指定子を使用する場合 `%A` 、 `StructuredFormatDisplay` 型宣言に属性が存在することが尊重されます。  これを使用すると、サロゲートテキストおよびプロパティを指定して値を表示できます。 以下に例を示します。

```fsharp
[<StructuredFormatDisplay("Counts({Clicks})")>]
type Counts = { Clicks:int list}

printfn "%20A" {Clicks=[0..20]}
```

枝分かれ

```console
Counts([0; 1; 2; 3;
        4; 5; 6; 7;
        8; 9; 10; 11;
        12; 13; 14;
        15; 16; 17;
        18; 19; 20])
```

### <a name="customize-plain-text-formatting-by-overriding-tostring"></a>オーバーライドしてプレーンテキストの書式設定をカスタマイズする`ToString`

の既定の実装 `ToString` は、F # プログラミングで監視できます。 多くの場合、既定の結果は、プログラマによる情報の表示またはユーザー出力での使用に適しているわけではありません。そのため、既定の実装をオーバーライドするのが一般的です。  

既定では、F # のレコード型と共用体型は、を使用する実装でのの実装をオーバーライドし `ToString` `sprintf "%+A"` ます。  たとえば、

```fsharp
type Counts = { Clicks:int list }

printfn "%s" ({Clicks=[0..10]}.ToString())
```

枝分かれ

```console
{ Clicks = [0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10] }
```

クラス型の場合、の既定の実装は提供されず、 `ToString` .net の既定値が使用されます。これは、型の名前を報告します。 たとえば、

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Default structured print gives this:\n%A" data
printfn "Default ToString gives:\n%s" (data.ToString())
```

枝分かれ

```console
Default structured print gives this:
[MyClassType; MyClassType]
Default ToString gives:
[MyClassType; MyClassType]
```

のオーバーライドを追加すると、 `ToString` 書式設定が向上します。

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks
   override _.ToString() = sprintf "MyClassType(%0A)" clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Now structured print gives this:\n%A" data
printfn "Now ToString gives:\n%s" (data.ToString())
```

枝分かれ

```console
Now structured print gives this:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
Now ToString gives:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
```

## <a name="f-interactive-structured-printing"></a>構造化された印刷の F# インタラクティブ

F# インタラクティブ ( `dotnet fsi` ) では、構造化されたプレーンテキスト形式の拡張バージョンを使用して値を報告し、追加のカスタマイズを可能にします。 詳細については、「 [F# インタラクティブ](fsharp-interactive-options.md)」を参照してください。

## <a name="customize-debug-displays"></a>デバッグディスプレイのカスタマイズ

.NET 用のデバッガーは、やなどの属性の使用を尊重 `DebuggerDisplay` `DebuggerTypeProxy` し、デバッガーの検査ウィンドウでのオブジェクトの構造化表示に影響します。
F # コンパイラは、判別された共用体型とレコード型に対してこれらの属性を自動的に生成しましたが、クラス、インターフェイス、または構造体型には対応していません。

F # プレーンテキストの書式設定では、これらの属性は無視されますが、F # の型をデバッグするときに表示を改善するためにこれらのメソッドを実装すると便利な場合があります。

## <a name="see-also"></a>関連項目

- [文字列](strings.md)
- [レコード](records.md)
- [判別共用体](discriminated-unions.md)
- [F# Interactive](fsharp-interactive-options.md)
