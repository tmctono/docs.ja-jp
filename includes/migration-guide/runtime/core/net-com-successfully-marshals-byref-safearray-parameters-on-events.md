---
ms.openlocfilehash: 1907c9b82c9685899d328f67da8001c0fa4fb697
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497155"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM では、イベント時に ByRef SafeArray パラメーターを正常にマーシャリングします。

#### <a name="details"></a>説明

.NET Framework 4.7.2 以前のバージョンでは、COM イベントでの ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) パラメータ―は、ネイティブ コードに戻ってマーシャリングすることはできません。  この変更により、[SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) が正常にマーシャリングされるようになりました。<ul><li>[ x ] 後方互換</li></ul>

#### <a name="suggestion"></a>提案される解決策

COM イベント時に ByRef SafeArray パラメーターを正常にマーシャリングすると、実行が中断されてしまう場合は、アプリケーション構成に次の構成スイッチを追加して、このコードを無効にすることができます。<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |マイナー|
|バージョン|4.8|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
