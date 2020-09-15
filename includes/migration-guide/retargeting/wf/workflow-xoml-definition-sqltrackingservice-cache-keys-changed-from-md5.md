---
ms.openlocfilehash: 7a7ecf052276fe8e62463498b83230d466630c79
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616271"
---
### <a name="workflow-xoml-definition-and-sqltrackingservice-cache-keys-changed-from-md5-to-sha256"></a><span data-ttu-id="b51d6-101">ワークフロー XOML 定義および SqlTrackingService キャッシュ キーの MD5 から SHA256 への変更</span><span class="sxs-lookup"><span data-stu-id="b51d6-101">Workflow XOML definition and SqlTrackingService cache keys changed from MD5 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="b51d6-102">説明</span><span class="sxs-lookup"><span data-stu-id="b51d6-102">Details</span></span>

<span data-ttu-id="b51d6-103">ワークフロー ランタイムでは、XOML で定義されているワークフロー定義のキャッシュが保持されます。</span><span class="sxs-lookup"><span data-stu-id="b51d6-103">The Workflow Runtime in keeps a cache of workflow definitions defined in XOML.</span></span> <span data-ttu-id="b51d6-104">また、SqlTrackingService では、文字列によってキー指定されるキャッシュが保持されます。</span><span class="sxs-lookup"><span data-stu-id="b51d6-104">The SqlTrackingService also keeps a cache that is keyed by strings.</span></span> <span data-ttu-id="b51d6-105">これらのキャッシュは、チェックサム ハッシュ値を含む値によってキー指定されます。</span><span class="sxs-lookup"><span data-stu-id="b51d6-105">These caches are keyed by values that include checksum hash value.</span></span> <span data-ttu-id="b51d6-106">.NET Framework 4.7.2 以前のバージョンでは、このチェックサムのハッシュで MD5 アルゴリズムが使用され、FIPS 対応システムで問題が発生していました。</span><span class="sxs-lookup"><span data-stu-id="b51d6-106">In the .NET Framework 4.7.2 and earlier versions, this checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="b51d6-107">.NET Framework 4.8 以降では、SHA256 のアルゴリズムが使用されます。ワークフロー ランタイムと SqlTrackingService は開始されるたびに値が再計算されるため、この変更では互換性の問題は発生しないはずです。</span><span class="sxs-lookup"><span data-stu-id="b51d6-107">Starting with the .NET Framework 4.8, the algorithm used is SHA256.There shouldn't be a compatibility issue with this change because the values are recalculated each time the Workflow Runtime and SqlTrackingService is started.</span></span> <span data-ttu-id="b51d6-108">しかし、後方互換が提供されるため、お客様は必要に応じて、従来のハッシュ アルゴリズムの使用に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="b51d6-108">However, we have provided quirks to allow customers to revert back to usage of the legacy hashing algorithm, if necessary.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b51d6-109">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b51d6-109">Suggestion</span></span>

<span data-ttu-id="b51d6-110">この変更により、ワークフローの実行時に問題が生じる場合は、次のように、`AppContext` スイッチのいずれか、または両方を設定してみてください。</span><span class="sxs-lookup"><span data-stu-id="b51d6-110">If this change presents a problem when executing workflows, try setting one or both of the `AppContext` switches:</span></span>

- <span data-ttu-id="b51d6-111">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot; を true にする。</span><span class="sxs-lookup"><span data-stu-id="b51d6-111">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot; to true.</span></span>
- <span data-ttu-id="b51d6-112">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot; を true にする。</span><span class="sxs-lookup"><span data-stu-id="b51d6-112">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot; to true.</span></span>
<span data-ttu-id="b51d6-113">コード内で以下のように指定します。</span><span class="sxs-lookup"><span data-stu-id="b51d6-113">In code:</span></span>

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;, true);&#13;&#10;System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;, true);&#13;&#10;</code></pre>

<span data-ttu-id="b51d6-114">または、構成ファイルで次のようにします (<xref:System.Workflow.Runtime.WorkflowRuntime> オブジェクトを作成しているアプリケーションの構成ファイルで、このようにする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="b51d6-114">Or in the configuration file (this needs to be in the config file for the application that is creating the <xref:System.Workflow.Runtime.WorkflowRuntime> object):</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey=true&quot; /&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKeytrue&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="b51d6-115">名前</span><span class="sxs-lookup"><span data-stu-id="b51d6-115">Name</span></span>    | <span data-ttu-id="b51d6-116">値</span><span class="sxs-lookup"><span data-stu-id="b51d6-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b51d6-117">スコープ</span><span class="sxs-lookup"><span data-stu-id="b51d6-117">Scope</span></span>   | <span data-ttu-id="b51d6-118">マイナー</span><span class="sxs-lookup"><span data-stu-id="b51d6-118">Minor</span></span>       |
| <span data-ttu-id="b51d6-119">バージョン</span><span class="sxs-lookup"><span data-stu-id="b51d6-119">Version</span></span> | <span data-ttu-id="b51d6-120">4.8</span><span class="sxs-lookup"><span data-stu-id="b51d6-120">4.8</span></span>         |
| <span data-ttu-id="b51d6-121">種類</span><span class="sxs-lookup"><span data-stu-id="b51d6-121">Type</span></span>    | <span data-ttu-id="b51d6-122">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="b51d6-122">Retargeting</span></span> |
