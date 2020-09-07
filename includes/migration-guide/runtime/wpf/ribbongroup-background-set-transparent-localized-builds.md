---
ms.openlocfilehash: d6405573e476ce18513938b500041adefbeeef1b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496173"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>ローカライズされたビルドで RibbonGroup の背景が透明に設定される

#### <a name="details"></a>説明

ローカライズされたビルドの <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> の背景が常に透明のブラシで塗りつぶされており、UI の操作性が低下していました。 これは、.NET Framework 4.7 WPF 修正プログラムで修正されます。<xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> のローカライズされたリソースが更新され、正しいブラシが確実に選択されるようになります。

#### <a name="suggestion"></a>提案される解決策

.NET Framework 4.7 にアップグレードします

| 名前    | 値       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.6.2|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
