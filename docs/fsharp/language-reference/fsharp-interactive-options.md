---
title: 対話形式のオプション
description: F# インタラクティブ、fsi.exe でサポートされているコマンドラインオプションについて説明します。
ms.date: 08/15/2020
ms.openlocfilehash: da2251c1d2e57090ed926e501cebf3c53ac58052
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558609"
---
# <a name="f-interactive-options"></a>F# インタラクティブオプション

この記事では F# インタラクティブでサポートされるコマンドラインオプションについて説明し `fsi.exe` ます。 F# インタラクティブは、F # コンパイラと同じコマンドラインオプションの多くを受け入れますが、いくつかの追加オプションも受け入れます。

## <a name="use-f-interactive-for-scripting"></a>スクリプトに F# インタラクティブを使用する

F# インタラクティブ、は `dotnet fsi` 対話形式で起動できます。また、コマンドラインから起動してスクリプトを実行することもできます。 コマンドラインの構文はです。

```dotnetcli
dotnet fsi [options] [ script-file [arguments] ]
```

F# スクリプト ファイルのファイル拡張子は `.fsx` です。

## <a name="table-of-f-interactive-options"></a>F# Interactive のオプションの表

次の表は、F# Interactive でサポートされるオプションの一覧です。 これらのオプションは、コマンドラインまたは Visual Studio IDE を使用して設定できます。 Visual Studio IDE でこれらのオプションを設定するには、[ **ツール** ] メニューを開き、[ **オプション**] を選択し、[ **F # ツール** ] ノードを展開して、[ **F# インタラクティブ**] を選択します。

F# Interactive オプションの引数でリストを指定する場合は、リストの要素をセミコロン (`;`) で区切ります。

|オプション|説明|
|------|-----------|
|**--**|残りの引数をコマンドライン引数として F # プログラムまたはスクリプトに F# インタラクティブように指示するために使用されます。これは、 **fsi.exe**リストを使用してコード内でアクセスできます。|
|**--checked**[ **+**&#124;**-** ]|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|
|**--codepage: &lt; int&gt;**|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|
|**--consolecolors**[ **+**&#124;**-** ]|警告およびエラーメッセージを色で出力します。|
|**--クロス最適化**[ **+**&#124;**-** ]|モジュール間の最適化を有効または無効にします。|
|**--debug**[ **+**&#124;**-** ]<br /><br />**--debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]<br /><br />**-g**[ **+**&#124;**-** ]<br /><br />**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|
|**--define: &lt; 文字列&gt;**|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|
|**--決定的**[ **+**&#124;**-** ]|決定的なアセンブリ (モジュールのバージョン GUID とタイムスタンプを含む) を生成します。|
|**--exec**|ファイルを読み込んだ後、またはコマンド ラインで指定したスクリプトを実行した後に F# Interactive を終了するように指示します。|
|**--fullpaths**|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|
|**--gui**[ **+**&#124;**-** ]|Windows フォーム イベントのループを有効または無効にします。 既定値は有効です。|
|**--help**<br /><br />**-?**|コマンドライン構文と各オプションの簡単な説明を表示するために使用します。|
|**--lib: &lt; フォルダー一覧&gt;**<br /><br />**-I: &lt; フォルダー一覧&gt;**|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|
|**--load: &lt; ファイル名&gt;**|指定したソース コードを起動時にコンパイルし、コンパイルされた F# の構成要素をセッションに読み込みます。|
|**--mlcompatibility**|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|
|**--noframework**|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラオプション](compiler-options.md)」を参照してください。|
|**--nologo**|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|
|**--nowarn: &lt; warning-list&gt;**|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|
|**--optimize**[ **+**&#124;**-** ]|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|
|**--preferreduilang: &lt; lang&gt;**| 優先する出力言語のカルチャ名を指定します (例: es、ja-jp)。 |
|**--quiet**|**Stdout**ストリームへの F# インタラクティブの出力を抑制します。|
|**--引用符-デバッグ**|追加のデバッグ情報が F# 引用符リテラルとリフレクション定義から派生した式に対して生成されるように指定します。 デバッグ情報は F# 式ツリー ノードのカスタム属性に追加されます。 「 [コード引用符](code-quotations.md) 」と「 [Expr. customattributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3)」を参照してください。|
|**--readline**[ **+**&#124;**-** ]|対話モードでのタブ補完を有効または無効にします。|
|**--reference: &lt; ファイル名&gt;**<br /><br />**-r: &lt; ファイル名&gt;**|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|
|**--tail**[ **+**&#124;**-** ]|tail IL 命令の使用を有効または無効にします。有効にすると、スタック フレームが tail 再帰関数で再利用されます。 このオプションは、既定で有効です。|
|**--targetprofile: &lt; 文字列&gt;**|このアセンブリのターゲットフレームワークプロファイルを指定します。 有効な値は、`mscorlib`、`netcore`、または `netstandard` です。 既定では、 `mscorlib`です。|
|**--使用: &lt; ファイル名&gt;**|指定したファイルを起動時に最初の入力として使用するよう、インタープリターに指示します。|
|**--utf8output**|fsc.exe コンパイラ オプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|
|**--warn: &lt; 警告レベル&gt;**|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|
|**--warnaserror**[ **+**&#124;**-** ]|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|
|**--warnaserror**[ **+**&#124;**-** ]:** &lt; int-list &gt; **|**fsc.exe**コンパイラオプションと同じです。 詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。|

## <a name="f-interactive-structured-printing"></a>構造化された印刷の F# インタラクティブ

F# インタラクティブ ( `dotnet fsi` ) では、構造化された [プレーンテキストの書式設定](plaintext-formatting.md) を使用して値を報告します。

1. プレーンテキスト形式のすべての機能がサポートされて `%A` おり、さらにカスタマイズも可能です。

2. 出力コンソールで色がサポートされている場合、印刷は色分けされます。

3. 文字列を明示的に評価しない限り、表示される文字列の長さに制限が適用されます。

4. ユーザー定義可能な一連の設定は、オブジェクトを介して使用でき `fsi` ます。

報告される値のプレーンテキスト印刷をカスタマイズするために使用できる設定は次のとおりです。

```fsharp
open System.Globalization

fsi.FormatProvider <- CultureInfo("de-DE")  // control the default culture for primitives

fsi.PrintWidth <- 120        // Control the width used for structured printing

fsi.PrintDepth <- 10         // Control the maximum depth of nested printing

fsi.PrintLength <- 10        // Control the length of lists and arrays

fsi.PrintSize <- 100         // Control the maximum overall object count

fsi.ShowProperties <- false  // Control whether properties of .NET objects are shown by default

fsi.ShowIEnumerable <- false // Control whether sequence values are expanded by default

fsi.ShowDeclarationValues <- false // Control whether values are shown for declaration outputs
```

### <a name="customize-with-addprinter-and-addprinttransformer"></a>およびを使用してカスタマイズする `AddPrinter``AddPrintTransformer`

およびを使用して F# インタラクティブ出力の印刷をカスタマイズでき `fsi.AddPrinter` `fsi.AddPrintTransformer` ます。
最初の関数は、オブジェクトの印刷を置き換えるテキストを提供します。 2番目の関数は、代わりに表示するサロゲートオブジェクトを返します。 たとえば、次の F # コードについて考えてみます。

```fsharp
open System

fsi.AddPrinter<DateTime>(fun dt -> dt.ToString("s"))

type DateAndLabel =
    { Date: DateTime
      Label: string  }

let newYearsDay1999 =
    { Date = DateTime(1999, 1, 1)
      Label = "New Year" }
```

F# インタラクティブで例を実行すると、書式設定オプションセットに基づいて出力されます。 この場合、日付と時刻の書式設定に影響します。

```console
type DateAndLabel =
  { Date: DateTime
    Label: string }
val newYearsDay1999 : DateAndLabel = { Date = 1999-01-01T00:00:00
                                       Label = "New Year" }
```

`fsi.AddPrintTransformer` を使用して、印刷する代理オブジェクトを指定できます。

```fsharp
type MyList(values: int list) =
    member _.Values = values

fsi.AddPrintTransformer(fun (x:MyList) -> box x.Values)

let x = MyList([1..10])
```

出力は次のとおりです。

```console
val x : MyList = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

に渡されたトランスフォーマー関数がを `fsi.AddPrintTransformer` 返す場合 `null` 、印刷トランスフォーマーは無視されます。
これは、型で始まる入力値をフィルター処理するために使用でき `obj` ます。  次に例を示します。

```fsharp
fsi.AddPrintTransformer(fun (x:obj) ->
    match x with
    | :? string as s when s = "beep" -> box ["quack"; "quack"; "quack"]
    | _ -> null)

let y = "beep"
```

出力は次のとおりです。

```console
val y : string = ["quack"; "quack"; "quack"]
```

## <a name="related-topics"></a>関連トピック

|Title|説明|
|-----|-----------|
|[コンパイラ オプション](compiler-options.md)|F # コンパイラ、 **fsc.exe**で使用できるコマンドラインオプションについて説明します。|
