---
ms.openlocfilehash: 7140f6d4cac063088b3663ab98d292104218b542
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465515"
---
### <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a>現在、Cookie パスの処理は、RFC 6265 に準拠している

<xref:System.Net.Cookie> クラスと <xref:System.Net.CookieContainer> クラスについては、[RFC 6265](https://tools.ietf.org/html/rfc6265) に定義されているパス処理アルゴリズムが実装されました。

#### <a name="version-introduced"></a>導入されたバージョン

5.0

#### <a name="change-description"></a>変更の説明

- <xref:System.Net.Cookie.Path> プロパティは、要求パスのプレフィックスにする必要がなくなりました。
- RFC 6265 の[セクション 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) に定義されているように、<xref:System.Net.Cookie.Path> の既定値の計算とパス照合アルゴリズムが導入されました。

#### <a name="recommended-action"></a>推奨アクション

ほとんどの場合、お客様が何らかのアクションを実行する必要はありません。 ただし、コードが <xref:System.Net.Cookie.Path> 検証に依存していた場合、必要な検証をコードに実装する必要があります。 コードが <xref:System.Net.Cookie.Path> の既定値計算に依存している場合、既定値を使用せず、手動で <xref:System.Net.Cookie.Path> 値を指定することを検討してください。

#### <a name="category"></a>カテゴリ

ネットワーキング

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

-->
