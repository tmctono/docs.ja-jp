---
ms.openlocfilehash: 2b4f35fe15f806897e5e4d85ee774b2e4572d974
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497901"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a>終了時に WinRT ストリーム アダプターで FlushAsync が自動的に呼び出されなくなりました

#### <a name="details"></a>説明

Windows ストア アプリの Windows ランタイム ストリーム アダプターで、Dispose メソッドから FlushAsync メソッドが呼び出されなくなりました。

#### <a name="suggestion"></a>提案される解決策

この変更は透過的である必要があります。 開発者は次のようなコードを記述して以前の動作を復元できます。<pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |透明|
|バージョン|4.5.1|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
