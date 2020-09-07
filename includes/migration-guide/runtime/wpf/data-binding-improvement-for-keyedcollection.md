---
ms.openlocfilehash: 8964cd2f69e95e4078001997ad5a5d126ce42d7b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497553"
---
### <a name="data-binding-improvement-for-keyedcollection"></a><span data-ttu-id="eafcb-101">KeyedCollection のデータ バインディングの機能強化</span><span class="sxs-lookup"><span data-stu-id="eafcb-101">Data Binding improvement for KeyedCollection</span></span>

#### <a name="details"></a><span data-ttu-id="eafcb-102">説明</span><span class="sxs-lookup"><span data-stu-id="eafcb-102">Details</span></span>

<span data-ttu-id="eafcb-103">ソース オブジェクトが同じシグネチャを持つカスタム インデクサーを宣言するときの<xref:System.Windows.Data.Binding>による IList インデクサーの不適切な使用を修正しました (例: KeyedCollection&lt;int,TItem&gt;)。</span><span class="sxs-lookup"><span data-stu-id="eafcb-103">Fixed <xref:System.Windows.Data.Binding> incorrect use of IList indexer when the source object declares a custom indexer with the same signature (for example, KeyedCollection&lt;int,TItem&gt;).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="eafcb-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="eafcb-104">Suggestion</span></span>

<span data-ttu-id="eafcb-105">古いバージョンを対象とするアプリケーションがこの変更の恩恵を受けるには、.NET Framework 4.8 以降上で実行する必要があります。また、次の [AppContext スイッチ](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element)をアプリ構成ファイルの <code>&lt;runtime&gt;</code> セクションに追加し、それを <code>false</code> に設定することで、変更を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eafcb-105">In order for an application that targets an older version to benefit from this change, it must run on the .NET Framework 4.8 or later, and it must opt in to the change by adding the following [AppContext switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the <code>&lt;runtime&gt;</code> section of the app config file and setting it to <code>false</code>:</span></span><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="eafcb-106">名前</span><span class="sxs-lookup"><span data-stu-id="eafcb-106">Name</span></span>    | <span data-ttu-id="eafcb-107">[値]</span><span class="sxs-lookup"><span data-stu-id="eafcb-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="eafcb-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="eafcb-108">Scope</span></span>   |<span data-ttu-id="eafcb-109">Major</span><span class="sxs-lookup"><span data-stu-id="eafcb-109">Major</span></span>|
|<span data-ttu-id="eafcb-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="eafcb-110">Version</span></span>|<span data-ttu-id="eafcb-111">4.8</span><span class="sxs-lookup"><span data-stu-id="eafcb-111">4.8</span></span>|
|<span data-ttu-id="eafcb-112">種類</span><span class="sxs-lookup"><span data-stu-id="eafcb-112">Type</span></span>|<span data-ttu-id="eafcb-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="eafcb-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="eafcb-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="eafcb-114">Affected APIs</span></span>

<span data-ttu-id="eafcb-115">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="eafcb-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
