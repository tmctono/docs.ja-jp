---
ms.openlocfilehash: 7bf5f7e8a49acc2918dd0d68a1c54a5c277091b0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496124"
---
### <a name="chained-popups-with-staysopenfalse"></a>StaysOpen=False でポップアップがチェーンされる

#### <a name="details"></a>説明

ポップアップの外側をクリックすると、StaysOpen=False のポップアップが閉じられることが想定されます。 このような 2 つ以上のポップアップがチェーンされている (つまり、1 つに別のものが含まれている) 場合、次のような、多くの問題が発生します。<ul><li>2 つのレベルを開き、P2 の外側と、P1 の内側をクリックします。  何も起こりません。</li><li>2 つのレベルを開き、P1 の外側をクリックします。  両方のポップアップが閉じます。</li><li>2 つのレベルを開いて閉じます。  次に、P2 をもう一度開いてみます。  何も起こりません。</li><li>3 つのレベルを開いてみます。  この操作を行うことはできません  (クリックする場所に応じて、何も起こらないか、最初の 2 つのレベルが閉じます)。このような場合 (および他のバリアント) は、予期したとおり動作します。</li></ul>

| 名前    | 値       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.7.1|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.Popup.StaysOpen`

-->
