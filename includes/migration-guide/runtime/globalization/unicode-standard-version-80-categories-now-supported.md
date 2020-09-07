---
ms.openlocfilehash: f389a9e9bcf4ac1777db66731a085d74889c4a98
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496570"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a>Unicode 標準バージョン 8.0 のカテゴリのサポート開始

#### <a name="details"></a>説明

.NET Framework 4.6.2 で、Unicode データが Unicode 標準バージョン 6.3 からバージョン 8.0 にアップグレードされました。  .NET Framework 4.6.2 で Unicode 文字カテゴリを要求すると、いくつかの結果が以前の .NET Framework バージョンの結果と一致しない可能性があります。  この変更は、主にチェロキーの音節、新タイ ロ文字の母音記号および声調記号に影響します。

#### <a name="suggestion"></a>提案される解決策

コードを確認し、ハードコーディングされた Unicode 文字カテゴリに依存するロジックを削除/変更します。

| 名前    | 値       |
|:--------|:------------|
| スコープ   |マイナー|
|バージョン|4.6.2|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Char.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)`

-->
