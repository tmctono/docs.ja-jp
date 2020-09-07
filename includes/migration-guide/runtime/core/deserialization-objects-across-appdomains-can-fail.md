---
ms.openlocfilehash: 3f82a4daac3b5d8981532f0c82e9a76f13c68b6e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496441"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a>アプリ ドメイン全体でのオブジェクトの逆シリアル化に失敗する可能性がある

#### <a name="details"></a>説明

場合によっては、アプリが異なるアプリケーション ベースを持つ複数のアプリ ドメインを使用すると、アプリ ドメイン間で論理呼び出しコンテキストのオブジェクトを逆シリアル化しようとして、例外がスローされます。

#### <a name="suggestion"></a>提案される解決策

「[軽減策:アプリ ドメイン全体でのオブジェクトの逆シリアル化](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)」を参照してください。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.5.1|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
