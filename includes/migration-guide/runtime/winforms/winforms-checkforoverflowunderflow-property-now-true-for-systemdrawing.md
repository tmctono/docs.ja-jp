---
ms.openlocfilehash: 68b0c4bb032b9744ef585eaef3d68e31afebee24
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496122"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>WinForm の CheckForOverflowUnderflow プロパティが System.Drawing に対して true に設定されるようになった

#### <a name="details"></a>説明

System.Drawing.dll アセンブリの CheckForOverflowUnderflow プロパティが true に設定されます。

#### <a name="suggestion"></a>提案される解決策

これまではオーバーフローが発生すると、その結果は自動的に切り捨てられました。 現在では、<xref:System.OverflowException?displayProperty=fullName> 例外がスローされます。

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
