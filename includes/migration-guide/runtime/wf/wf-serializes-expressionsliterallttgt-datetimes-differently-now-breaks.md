---
ms.openlocfilehash: 06424c4fa40343a881356c20003300f65e93efbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496398"
---
### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>WF による Expressions.Literal&lt;T&gt; DateTimes のシリアル化の方法が変わった (カスタム XAML パーサーが機能しなくなる)

#### <a name="details"></a>説明

関連する <xref:System.Windows.Markup.ValueSerializer> オブジェクトは、Second コンポーネントと <xref:System.DateTime.Millisecond?displayProperty=fullName> コンポーネントが非ゼロで (<xref:System.DateTime?displayProperty=fullName> 値の場合)、<xref:System.DateTime.Kind> プロパティが Unspecified ではない <xref:System.DateTime?displayProperty=fullName> オブジェクトまたは <xref:System.DateTimeOffset?displayProperty=fullName> オブジェクトを文字列ではなくプロパティ要素構文に変換します。 この変更により、<xref:System.DateTime?displayProperty=fullName> 値と <xref:System.DateTimeOffset?displayProperty=fullName> 値を往復させることができるようになります。 入力 XAML が属性構文であると想定するカスタム XAML パーサーは正しく機能しません。

#### <a name="suggestion"></a>提案される解決策

この変更により、<xref:System.DateTime?displayProperty=fullName> 値と <xref:System.DateTimeOffset?displayProperty=fullName> 値を往復させることができるようになります。 入力 XAML が属性構文であると想定するカスタム XAML パーサーは正しく機能しません。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.5|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
