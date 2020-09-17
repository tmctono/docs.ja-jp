---
ms.openlocfilehash: 48d2f1b5fa2eced30d3c9fb65804268904f11ab8
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065066"
---
### <a name="unicode-category-changed-for-some-latin-1-characters"></a>一部の Latin-1 文字に対して変更された Unicode カテゴリ

<xref:System.Char> メソッドで、Latin-1 範囲の文字に対して正しい Unicode カテゴリが返されるようになりました。 そのカテゴリは、Unicode 標準のカテゴリと一致します。

#### <a name="change-description"></a>変更内容

以前のバージョンの .NET の <xref:System.Char> メソッドでは、Latin-1 範囲の文字に対して Unicode カテゴリの固定リストが使用されていました。 ただし、それらの API が実装された後に、Unicode 標準でこれらの文字の一部のカテゴリが変更されたため、不一致が発生していました。 また、<xref:System.Char> と、Unicode 標準に準拠する <xref:System.Globalization.CharUnicodeInfo> API の間でも一致していませんでした。 .NET 5.0 以降のバージョンの <xref:System.Char> メソッドでは、すべての文字について Unicode 標準に一致する Unicode カテゴリが使用され、返されます。

次の表では、.NET 5.0 で Unicode カテゴリが変更された文字を示します。

| 文字    | Unicode カテゴリ<br>以前の .NET バージョンの場合 | Unicode カテゴリ<br>.NET 5.0 以降のバージョンの場合 |
|:------------:|:---------------------------------------------:|:--------------------------------------------------:|
| § (\u00a7)   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| ª (\u00aa)   | `LowercaseLetter`                             | `OtherLetter`                                      |
| SHY (\u00ad) | `DashPunctuation`                             | `Format`                                           |
| ¶ (\u00b6)   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| º (\u00ba)   | `LowercaseLetter`                             | `OtherLetter`                                      |

#### <a name="version-introduced"></a>導入されたバージョン

.NET 5.0 RC1

#### <a name="recommended-action"></a>推奨アクション

<xref:System.Char> クラスを使用して Unicode 文字カテゴリを取得し、カテゴリが変更されないものと想定しているコードがある場合は、更新が必要になることがあります。

#### <a name="reason-for-change"></a>変更理由

この変更は、<xref:System.Char> 型によって返されるカテゴリを、Unicode 標準および <xref:System.Globalization.CharUnicodeInfo> 型の両方と一致させるために行われました。

#### <a name="category"></a>カテゴリ

- Core .NET ライブラリ
- グローバリゼーション

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName>
- <xref:System.Char.IsLetter%2A?displayProperty=fullName>
- <xref:System.Char.IsPunctuation%2A?displayProperty=fullName>
- <xref:System.Char.IsSymbol%2A?displayProperty=fullName>
- <xref:System.Char.IsLower%2A?displayProperty=fullName>

また、Unicode 文字カテゴリを取得するために <xref:System.Char> に依存するクラス (<xref:System.Text.RegularExpressions.Regex> など) も、この変更による影響を受けます。

<!--

#### Affected APIs

- `Overload:System.Char.GetUnicodeCategory`
- `Overload:System.Char.IsLetter`
- `Overload:System.Char.IsPunctuation`
- `Overload:System.Char.IsSymbol`
- `Overload:System.Char.IsLower`

-->
