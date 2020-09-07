---
ms.openlocfilehash: 12a26030a9a336d887ae9d53994a9daf13356618
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496544"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>TextBlock コントロールの親の IsEnabled プロパティの変更がすべての子コントロールに影響する

#### <a name="details"></a>説明

.NET Framework 4.6.2、変更以降の<xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName>の親のプロパティ、<xref:System.Windows.Controls.TextBlock?displayProperty=fullName>コントロール (ハイパーリンクやボタンなど) などの子コントロールに影響を与える、<xref:System.Windows.Controls.TextBlock?displayProperty=fullName>コントロール。 .NET Framework 4.6.1 以前のバージョンで、内部コントロール、<xref:System.Windows.Controls.TextBlock?displayProperty=fullName>の状態を常に反映されませんでした、<xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName>のプロパティ、<xref:System.Windows.Controls.TextBlock?displayProperty=fullName>親。

#### <a name="suggestion"></a>提案される解決策

[なし] : この変更は、<xref:System.Windows.Controls.TextBlock?displayProperty=fullName> コントロール内部のコントロールに期待される動作に準拠しています。

| 名前    | 値       |
|:--------|:------------|
| スコープ   |マイナー|
|バージョン|4.6.2|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.UIElement.IsEnabled`

-->
