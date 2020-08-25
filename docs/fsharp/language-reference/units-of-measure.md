---
title: 測定単位
description: 'F # の浮動小数点値と符号付き整数値に関連付けられた測定単位を使用する方法について説明します。これは通常、長さ、量、および質量を示すために使用されます。'
ms.date: 08/15/2020
ms.openlocfilehash: 0262f89e80697dd86161c93fe37381122972b56f
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811575"
---
# <a name="units-of-measure"></a>測定単位

F # の浮動小数点と符号付き整数値には、関連付けられた測定単位を含めることができます。これは通常、長さ、ボリューム、質量などを示すために使用されます。 単位付きの数量を使用することにより、コンパイラは、算術リレーションシップの単位が正しいことを確認できます。これにより、プログラミングエラーを防ぐことができます。

## <a name="syntax"></a>構文

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a>解説

前の構文では、 *単位名* を測定単位として定義しています。 省略可能な部分は、以前に定義した単位に基づいて新しいメジャーを定義するために使用されます。 たとえば、次の行では、メジャー `cm` (センチメートル) を定義しています。

```fsharp
[<Measure>] type cm
```

次の行では、メジャー `ml` (milliliter) を3次 () として定義して `cm^3` います。

```fsharp
[<Measure>] type ml = cm^3
```

前の構文では、 *measure* は単位を含む数式です。 単位が関係する数式では、整数の累乗がサポートされています (正と負)。単位間のスペースは、2つの単位の積、つまり `*` 単位の積を示すと同時に、 `/` 単位の商を示します。 逆数単位の場合は、負の整数の累乗を使用するか、または `/` 単位の数式の分子と分母を区別するを使用できます。 分母に複数の単位を指定する場合は、かっこで囲む必要があります。 の後のスペースで区切ら `/` れた単位は、分母の一部として解釈されますが、の後に続く単位 `*` は、分子の一部として解釈されます。

1つの単位式で1を使用すると、dimensionless の数量を示すことも、分子などの他の単位と組み合わせて使用することもできます。 たとえば、レートの単位はとして書き込ま `1/s` れます。ここで、は `s` 秒を示します。 かっこは、単位の数式では使用されません。 単位の数式で数値変換定数を指定することはできません。ただし、単位を個別に指定して変換定数を定義し、単位チェックされた計算で使用できます。

同じことを意味する単位の数式は、さまざまな方法で記述できます。 したがって、コンパイラは、単位の数式を一貫性のある形式に変換します。これにより、負の値が reciprocals に変換され、単位が1つの分子と分母にグループ化され、分子と分母の単位が alphabetizes されます。

たとえば、単位の数式 `kg m s^-2` と `m /s s * kg` は両方ともに変換され `kg m/s^2` ます。

浮動小数点式では測定単位を使用します。 浮動小数点数を関連する測定単位と共に使用すると、タイプセーフの別のレベルが追加され、弱く型指定された浮動小数点数を使用するときに、式で発生する可能性がある単位不一致エラーを回避するのに役立ちます。 単位を使用する浮動小数点式を記述する場合は、式の単位が一致している必要があります。

次の例に示すように、山かっこで囲まれた単位の数式でリテラルに注釈を付けることができます。

```fsharp
1.0<cm>
55.0<miles/hour>
```

数字と山かっこの間にスペースを入れないでください。ただし、次の例に示すように、などのリテラルサフィックスを含めることができ `f` ます。

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

このような注釈は、リテラルの型をプリミティブ型 (など) から `float` 次元型 (この場合はなど) に変更し `float<cm>` `float<miles/hour>` ます。 の単位注釈は `<1>` dimensionless quantity を示し、その型は、unit パラメーターを持たないプリミティブ型に相当します。

測定単位の型は、浮動小数点型または符号付き整数型であり、追加の単位注釈が角かっこで示されます。 したがって、変換の種類を `g` (グラム) から (キログラム) に記述する場合は、次のように `kg` 型を記述します。

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

測定単位は、コンパイル時の単位チェックに使用されますが、実行時環境には保存されません。 そのため、パフォーマンスには影響しません。

測定単位は、浮動小数点型だけでなく、任意の型に適用できます。ただし、浮動小数点型、符号付き整数型、および10進数型のみが次元の数量をサポートします。 したがって、プリミティブ型と、これらのプリミティブ型を含む集計では、測定単位を使用するのが理にかなっています。

次の例は、測定単位の使用方法を示しています。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

次のコード例は、dimensionless 浮動小数点数から次元浮動小数点値に変換する方法を示しています。 1.0 で乗算するだけで、1.0 にディメンションが適用されます。 これは、のような関数に要約でき `degreesFahrenheit` ます。

また、dimensionless 浮動小数点数を予期する関数に次元値を渡す場合は、演算子を使用して、その単位をキャンセルするか、にキャストする必要があり `float` `float` ます。 この例では、 `1.0<degC>` が `printf` dimensionless 数量を想定しているため、の引数としてをで除算し `printf` ます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

次のセッション例は、からの出力とこのコードへの入力を示しています。

```console
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a>汎用単位の使用

関連する測定単位を持つデータを操作するジェネリック関数を作成できます。 これを行うには、次のコード例に示すように、型パラメーターとしてジェネリック単位を使用して型を指定します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a>汎用単位を使用した集計型の作成

次のコードは、ジェネリックである単位を持つ個々の浮動小数点値で構成される集計型を作成する方法を示しています。 これにより、さまざまな単位で動作する1つの型を作成できます。 また、1つの単位セットを持つジェネリック型が、異なる単位のセットを持つ同じジェネリック型とは異なる型であることを保証することで、ジェネリックユニットはタイプセーフを保持します。 この手法の基礎は、属性を `Measure` 型パラメーターに適用できることです。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a>実行時の単位数

静的な型チェックには、測定単位が使用されます。 浮動小数点値をコンパイルすると、測定単位が削除されるため、実行時に単位が失われます。 したがって、実行時の単位のチェックに依存する機能を実装しようとすることはできません。 たとえば、 `ToString` 単位を出力する関数を実装することはできません。

## <a name="conversions"></a>コンバージョン

単位を持つ型 (など) を、単位の `float<'u>` ない型に変換するには、標準変換関数を使用します。 たとえば、 `float` 次のコードに示すように、を使用して、 `float` 単位を持たない値に変換することができます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

単位を含む値に単位なしの値を変換するには、適切な単位で注釈が付けられた1または1.0 の値を乗算します。 ただし、相互運用性レイヤーを記述する場合は、単位の値を単位の値に変換するために使用できる明示的な関数もいくつかあります。 これらは、 [Fsharp.core プリミティブ](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html) モジュールにあります。 たとえば、単位なしからに変換するには、 `float` `float<cm>` 次のコードに示すように、 [FloatWithMeasure](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html#FloatWithMeasure)を使用します。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a>F # コアライブラリの測定単位

名前空間では、ユニットライブラリを使用でき `FSharp.Data.UnitSystems.SI` ます。 この例では、副名前空間のシンボル形式 ( `m` メーターの場合) `UnitSymbols` と、 `meter` サブ名前空間のフルネーム (メーターのような) の両方に SI 単位が含まれてい `UnitNames` ます。

## <a name="see-also"></a>関連項目

- [F# 言語リファレンス](index.md)
