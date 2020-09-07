---
ms.openlocfilehash: e7001fcfdf88fd9e710fbb702f2ed39d63b1e080
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496678"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a>System.Uri エスケープで RFC 3986 がサポート対象に

#### <a name="details"></a>説明

URI エスケープは、.NET Framework 4.5 で、[RFC 3986](https://tools.ietf.org/html/rfc3986) をサポートするように変更されました。 具体的な変更内容:<ul><li><xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> は、予約されている文字を RFC 3986 に基づいてエスケープします。</li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> は、予約されている文字をエスケープしません。</li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> は、無効なエスケープ シーケンスが発生した場合に例外をスローしません。</li><li>予約されていないエスケープ文字はエスケープ解除されます。</li></ul>

#### <a name="suggestion"></a>提案される解決策

<ul><li>無効なエスケープ シーケンスの場合、<xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> のスローに依存しないように、アプリケーションを更新します。 このようなシーケンスは、直接削除する必要があります。</li><li>同様に、エスケープおよびエスケープ解除された URI とデータ文字列は、.NET Framework 4.0 と .NET Framework 4.5 で異なる場合があるため、.NET のバージョン間で直接比較しないでください。 代わりに、1 つの .NET バージョンで解析と正規化を行ってから比較してください。</li></ul>

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |マイナー|
|バージョン|4.5|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.EscapeDataString(System.String)`
- `M:System.Uri.EscapeUriString(System.String)`
- `M:System.Uri.UnescapeDataString(System.String)`

-->
