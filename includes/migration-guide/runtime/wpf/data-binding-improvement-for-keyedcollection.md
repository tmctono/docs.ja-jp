---
ms.openlocfilehash: a0dc2401155a162eaa5aa6b4d9e6af1ca1c2ccc8
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802573"
---
### <a name="data-binding-improvement-for-keyedcollection"></a><span data-ttu-id="00287-101">KeyedCollection のデータ バインディングの機能強化</span><span class="sxs-lookup"><span data-stu-id="00287-101">Data Binding improvement for KeyedCollection</span></span>

|   |   |
|---|---|
|<span data-ttu-id="00287-102">説明</span><span class="sxs-lookup"><span data-stu-id="00287-102">Details</span></span>|<span data-ttu-id="00287-103">ソース オブジェクトが同じシグネチャを持つカスタム インデクサーを宣言するときの<xref:System.Windows.Data.Binding>による IList インデクサーの不適切な使用を修正しました (例: KeyedCollection&lt;int,TItem&gt;)。</span><span class="sxs-lookup"><span data-stu-id="00287-103">Fixed <xref:System.Windows.Data.Binding> incorrect use of IList indexer when the source object declares a custom indexer with the same signature (e.g. KeyedCollection&lt;int,TItem&gt;).</span></span>|
|<span data-ttu-id="00287-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="00287-104">Suggestion</span></span>|<span data-ttu-id="00287-105">アプリケーションがこの変更の恩恵を受けるには、.NET Framework 4.7.2 以降上で実行する必要があります。また、次の [AppContext スイッチ](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element)をアプリ構成ファイルの <code>&lt;runtime&gt;</code> セクションに追加し、それを <code>false</code> に設定することで、変更を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00287-105">In order for the application to benefit from this change, it must run on the .NET Framework 4.7.2 or later, and it must opt in to the change by adding the following [AppContext switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the <code>&lt;runtime&gt;</code> section of the app config file and setting it to <code>false</code>:</span></span><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="00287-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="00287-106">Scope</span></span>|<span data-ttu-id="00287-107">Major</span><span class="sxs-lookup"><span data-stu-id="00287-107">Major</span></span>|
|<span data-ttu-id="00287-108">Version</span><span class="sxs-lookup"><span data-stu-id="00287-108">Version</span></span>|<span data-ttu-id="00287-109">4.8</span><span class="sxs-lookup"><span data-stu-id="00287-109">4.8</span></span>|
|<span data-ttu-id="00287-110">型</span><span class="sxs-lookup"><span data-stu-id="00287-110">Type</span></span>|<span data-ttu-id="00287-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="00287-111">Runtime</span></span>|

