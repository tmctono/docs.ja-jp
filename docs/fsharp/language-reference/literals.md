---
title: リテラル
description: 'F # プログラミング言語のリテラル型について説明します。'
ms.date: 06/28/2019
ms.openlocfilehash: 98d609a1cf0beb00c0dd4d45ea343aaa2280b62e
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855024"
---
# <a name="literals"></a>リテラル

この記事では、F # でリテラルの型を指定する方法を示す表を示します。

> [!NOTE]
> F # の docs.microsoft.com API リファレンスが完全ではありません。 壊れたリンクが見つかった場合は、代わりに[F # コアライブラリのドキュメント](https://fsharp.github.io/fsharp-core-docs/)を参照してください。

## <a name="literal-types"></a>リテラル型

F# のリテラル型を次の表に示します。 16 進表記で桁を表す文字は、大文字と小文字を区別しません。型を識別する文字は、大文字と小文字を区別します。

|Type|説明|サフィックスまたはプリフィックス|例|
|----|-----------|----------------|--------|
|sbyte|符号付き 8 ビット整数|Y|`86y`<br /><br />`0b00000101y`|
|byte|符号なし 8 ビット自然数|uy|`86uy`<br /><br />`0b00000101uy`|
|int16|符号付き16ビット整数|s|`86s`|
|uint16|符号なし16ビット自然数|us|`86us`|
|INT<br /><br />int32|符号付き32ビット整数|l または none|`86`<br /><br />`86l`|
|uint<br /><br />uint32|符号なし32ビット自然数|u または ul|`86u`<br /><br />`86ul`|
|nativeint|符号付き自然数へのネイティブポインター|n|`123n`|
|unativeint|符号なし自然数としてのネイティブ ポインター|un|`0x00002D3Fun`|
|int64|符号付き64ビット整数|L|`86L`|
|uint64|符号なし64ビット自然数|UL|`86UL`|
|single、float32|32 ビット浮動小数点数|F または f|`4.14F` または `4.14f`|
|||lf|`0x00000000lf`|
|float、double|64ビットの浮動小数点数|なし|`4.14` または `2.3E+32` または `2.3e+32`|
|||LF|`0x0000000000000000LF`|
|bigint|64 ビット表現に制限されない整数|I|`9999999999999999999999999999I`|
|decimal|固定小数点数または有理数として表現される小数|M または m|`0.7833M` または `0.7833m`|
|Char|Unicode 文字|なし|`'a'` または `'\u0061'`|
|String|Unicode 文字列|なし|`"text\n"`<br /><br />or<br /><br />`@"c:\filename"`<br /><br />or<br /><br />`"""<book title="Paradise Lost">"""`<br /><br />or<br /><br />`"string1" + "string2"`<br /><br />「[文字列](Strings.md)」も参照してください。|
|byte|ASCII 文字|B|`'a'B`|
|byte[]|ASCII 文字列|B|`"text"B`|
|String または byte[]|逐語的文字列|@ プリフィックス|`@"\\server\share"`対応<br /><br />`@"\\server\share"B`ASCII|

## <a name="named-literals"></a>名前付きリテラル

定数として使用する値は、[リテラル](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285)属性でマークできます。 この属性には、値が定数としてコンパイルされる効果があります。

パターン マッチ式では、小文字で始まる識別子は、リテラルとしてではなく常にバインドされる変数として扱われます。そのため、一般的に、リテラルを定義する場合は先頭大文字を使用する必要があります。

```fsharp
[<Literal>]
let SomeJson = """{"numbers":[1,2,3,4,5]}"""

[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

## <a name="remarks"></a>Remarks

Unicode 文字列には、を使用して指定できる明示的なエンコーディングを含めることができます。それに32は、の後に `\u` 16 ビットの16進コード (0000-FFFF)、またはを使用して指定することができ、その `\U` 後に unicode コードポイント (00000000-0010FFFF) を表す32ビットの16進コードを指定できます

以外のビットごとの演算子の使用は許可されていません `|||` 。

## <a name="integers-in-other-bases"></a>その他のベースの整数

符号付き32ビット整数は `0x` 、、、またはプレフィックスを使用して、16進数、8進数、またはバイナリで指定することもでき `0o` `0b` ます。

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a>数値リテラルのアンダースコア

数字はアンダースコア文字 () で区切ることができ `_` ます。

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a>関連項目

- [LiteralAttribute クラス](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
