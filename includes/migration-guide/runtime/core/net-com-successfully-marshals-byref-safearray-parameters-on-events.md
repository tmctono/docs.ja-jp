---
ms.openlocfilehash: aadf5eb85c8736c29639d49bc8baf21545d2467c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606308"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM では、イベント時に ByRef SafeArray パラメーターを正常にマーシャリングします。

#### <a name="details"></a>説明

.NET Framework 4.7.2 以前のバージョンでは、COM イベントでの ByRef [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) パラメータ―は、ネイティブ コードに戻ってマーシャリングすることはできません。  この変更により、[SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) が正常にマーシャリングされるようになりました。<ul><li>[ x ] 後方互換</li></ul>

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
