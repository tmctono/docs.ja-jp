---
ms.openlocfilehash: 99a7fa0fcfce6d490a182f85709b5dd0e0e8c86f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496505"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>EventSource.WriteEvent impls は、受け取ったのと同じパラメーター (と ID) を WriteEvent に渡す必要がある

#### <a name="details"></a>説明

ランタイムは次の内容を指定するコントラクトを強制するようになりました。ETW イベント メソッドを定義する <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> から派生するクラスは、ETW イベント メソッドが渡された同じ引数が続くイベント ID の基底クラス <code>EventSource.WriteEvent</code> メソッドを呼び出す必要があります。

#### <a name="suggestion"></a>提案される解決策

<xref:System.IndexOutOfRangeException?displayProperty=fullName> 例外は、<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> がこのコントラクトに違反するイベント ソースのプロセスの <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> データを読み取るときに、スローされます。

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
