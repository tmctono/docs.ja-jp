---
ms.openlocfilehash: 8964cd2f69e95e4078001997ad5a5d126ce42d7b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497553"
---
### <a name="data-binding-improvement-for-keyedcollection"></a>KeyedCollection のデータ バインディングの機能強化

#### <a name="details"></a>説明

ソース オブジェクトが同じシグネチャを持つカスタム インデクサーを宣言するときの<xref:System.Windows.Data.Binding>による IList インデクサーの不適切な使用を修正しました (例: KeyedCollection&lt;int,TItem&gt;)。

#### <a name="suggestion"></a>提案される解決策

古いバージョンを対象とするアプリケーションがこの変更の恩恵を受けるには、.NET Framework 4.8 以降上で実行する必要があります。また、次の [AppContext スイッチ](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element)をアプリ構成ファイルの <code>&lt;runtime&gt;</code> セクションに追加し、それを <code>false</code> に設定することで、変更を選択する必要があります。<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

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
