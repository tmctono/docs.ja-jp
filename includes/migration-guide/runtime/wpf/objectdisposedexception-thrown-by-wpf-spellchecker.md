---
ms.openlocfilehash: 3244913e06a744dafc4440f824ebe6bed25b8dd1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496645"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>ObjectDisposedException が WPF スペルチェックでスローされる

#### <a name="details"></a>説明

スペルチェックで <xref:System.ObjectDisposedException?displayProperty=fullName> がスローされ、WPF アプリケーションがシャットダウン時にクラッシュする場合があります。 これは .NET Framework 4.7 WPF で修正されます。例外は正しく処理されるため、アプリケーションが悪影響を受けることはなくなります。 ただし、デバッグ時に実行中のアプリケーションで初回例外が見られる場合があるので注意してください。

#### <a name="suggestion"></a>提案される解決策

.NET Framework 4.7 にアップグレードします

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.6.1|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
