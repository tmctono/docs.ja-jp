---
ms.openlocfilehash: 415eb1960c20fb662469e126560d6f366309eb0d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497852"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a>グリッド スター行領域の割り当てアルゴリズムの改善

#### <a name="details"></a>説明

.NET Framework 4.7 で導入された <xref:System.Windows.Controls.Grid> で[サイズを割り当てるためのアルゴリズム](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) のバグを修正しました。  空の行を含む <code>Height=&quot;Auto&quot;</code> のグリッドなど、場合によっては、行が正しくない位置に配置され、すべてグリッドの外側に示されることがありました。

#### <a name="suggestion"></a>提案される解決策

アプリケーションでこれらの変更を利用するには、.NET Framework 4.8 以降で実行する必要があります。

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
