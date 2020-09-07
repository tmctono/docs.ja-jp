---
ms.openlocfilehash: 51ac10e6b4cc9c757cb7f68d7d665982bcb57d4e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496384"
---
### <a name="systemactivities-is-now-aptca"></a>System.Activities が APTCA に

#### <a name="details"></a>説明

アセンブリは <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> 属性でマークされています。

#### <a name="suggestion"></a>提案される解決策

派生クラスに <xref:System.Security.SecurityCriticalAttribute?displayProperty=fullName>のマークを付けることはできません。 以前は、派生型に <xref:System.Security.SecurityCriticalAttribute?displayProperty=fullName>マークを付ける必要がありました。 ただし、この変更によって生じる実質的な影響はないはずです。

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
