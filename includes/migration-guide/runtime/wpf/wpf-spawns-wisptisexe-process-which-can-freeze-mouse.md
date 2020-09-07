---
ms.openlocfilehash: c3114277445daaae988b41782721c443c1e780d1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497891"
---
### <a name="wpf-spawns-a-wisptisexe-process-which-can-freeze-the-mouse"></a>WPF が wisptis.exe プロセスを生成し、マウスがフリーズする可能性がある

#### <a name="details"></a>説明

この問題は 4.5.2 から発生するようになり、<code>wisptis.exe</code> が生成され、マウス入力がフリーズする可能性があります。

#### <a name="suggestion"></a>提案される解決策

この問題はサービス リリースの .NET Framework 4.5.2 (修正プログラム ロールアップ 3026376) で、あるいは .NET Framework 4.6 にアップグレードすることで解決できます。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |Major|
|バージョン|4.5.2|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
