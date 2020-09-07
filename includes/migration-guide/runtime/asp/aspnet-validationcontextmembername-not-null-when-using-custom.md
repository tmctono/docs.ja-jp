---
ms.openlocfilehash: 904a6abee2b4b2cf2f5727fb70e286c8a1a592c4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497831"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ASP.NET カスタムの DataAnnotations.ValidationAttribute を使用すると、ValidationContext.MemberName が NULL にならない

#### <a name="details"></a>説明

.NET Framework 4.7.2 以前のバージョンでは、カスタムの <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> を使用すると、<xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> プロパティで `null` が返されます。 October 2019 Update より前の .NET Framework 4.8 バージョンでは、メンバー名が返されます。 .NET Framework 4.8 の [.NET Framework October 2019 Preview の品質ロールアップ](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/)以降、既定では `null` が返されますが、代わりにメンバー名を返すように設定することもできます。

#### <a name="suggestion"></a>提案される解決策

.NET Framework 4.8 以降のバージョン用の [.NET Framework October 2019 Preview の品質ロールアップ](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/)で、メンバー名を返すプロパティに対して次の設定を *web.config* ファイルに追加します。<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>October 2019 Update より前の .NET Framework 4.8 バージョンでは、これを *web.config* ファイルに追加すると、以前の動作が復元され、プロパティで `null` が返されます。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |不明|
|バージョン|4.8|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ComponentModel.DataAnnotations.ValidationContext.MemberName`

-->
