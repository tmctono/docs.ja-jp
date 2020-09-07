---
ms.openlocfilehash: 5c8ea3565fbe599dd53a71ba8bd339704f7d7f8a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497791"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a>SignedXml と EncryptedXml の互換性に影響する変更点

#### <a name="details"></a>説明

.NET Framework 4.6.2 では、<xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> および <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> のセキュリティ修正プログラムにより、実行時の動作が変わります。 次に例を示します。<ul><li>ドキュメントに <code>id</code> 属性が同じ値の複数の要素があり、署名でそれらの要素の 1 つが署名のルートとして指定されている場合、ドキュメントは無効と見なされるようになります。</li><li>参照で非正規 XPath 変換アルゴリズムを使っているドキュメントは、無効と見なされるようになります。</li><li>参照で非正規 XSLT 変換アルゴリズムを使っているドキュメントは、無効と見なされるようになります。</li><li>外部リソースのデタッチされた署名を利用しているプログラムは、利用できなくなります。</li></ul>

#### <a name="suggestion"></a>提案される解決策

ドキュメントの受信者が処理できない可能性があるため、開発者は <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> と <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> の使用、および <xref:System.Security.Cryptography.Xml.Transform> の派生型を確認することが必要な場合があります。

| 名前    | 値       |
|:--------|:------------|
| スコープ   |マイナー|
|バージョン|4.6.2|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.Xml.Transform`
- `T:System.Security.Cryptography.Xml.XmlDsigXPathTransform`
- `T:System.Security.Cryptography.Xml.XmlDsigXsltTransform`

-->
