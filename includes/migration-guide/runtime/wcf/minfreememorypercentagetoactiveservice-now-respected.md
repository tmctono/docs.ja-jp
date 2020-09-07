---
ms.openlocfilehash: b23182ad1da8208a69b78fc7bc872780d386a59a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496442"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a>MinFreeMemoryPercentageToActiveService が順守されるようになった

#### <a name="details"></a>説明

この設定は、WCF サービスをアクティブにするためにサーバー上で使用できなければならない最小メモリを設定します。 <xref:System.OutOfMemoryException?displayProperty=fullName> 例外が発生しないようにデザインされています。 .NET Framework 4.5 では、この設定には効果はありません。 .NET Framework 4.5.1 では、この設定が守られます。

#### <a name="suggestion"></a>提案される解決策

Web サーバーで使用できる空きメモリが構成設定によって定義されたパーセンテージよりも小さい場合、例外が発生します。 制約されたメモリ環境で正常に開始し、実行された WCF サービスが今度は失敗することがあります。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |マイナー|
|バージョン|4.5.1|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
