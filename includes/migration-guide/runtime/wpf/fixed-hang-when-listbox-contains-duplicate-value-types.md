---
ms.openlocfilehash: 7637c2d96aef93b4cf8f2314c1dd1edba51d553c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496975"
---
### <a name="fixed-a-hang-when-listbox-contains-duplicate-value-types"></a>ListBox に重複する値型が含まれている場合のハングの修正

#### <a name="details"></a>説明

Items コレクションに重複する値型オブジェクトが含まれていると、<xref:System.Windows.Controls.ItemsControl> の仮想化がスクロール中にハングする場合がある問題を修正しました。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |Major|
|バージョン|4.8|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
