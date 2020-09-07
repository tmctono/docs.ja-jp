---
ms.openlocfilehash: 346fb6ecd43f7f93529e45f169c79b7acacc9c1f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496603"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="71d7a-101">異なる 4.5 SQL 生成からより単純な 4.0 SQL 生成に戻す</span><span class="sxs-lookup"><span data-stu-id="71d7a-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

#### <a name="details"></a><span data-ttu-id="71d7a-102">説明</span><span class="sxs-lookup"><span data-stu-id="71d7a-102">Details</span></span>

<span data-ttu-id="71d7a-103">最初に OrderBy を使用せずに JOIN ステートメントを生成し、制限操作への呼び出しを含むクエリで、より単純な SQL が生成されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="71d7a-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="71d7a-104">.NET Framework 4.5 へのアップグレード後、これらのクエリは以前のバージョンよりも複雑な SQL を生成しました。</span><span class="sxs-lookup"><span data-stu-id="71d7a-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="71d7a-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="71d7a-105">Suggestion</span></span>

<span data-ttu-id="71d7a-106">既定では、この機能は無効です。</span><span class="sxs-lookup"><span data-stu-id="71d7a-106">This feature is disabled by default.</span></span> <span data-ttu-id="71d7a-107">Entity Framework がパフォーマンスを低下させる追加の JOIN ステートメントを生成する場合は、アプリケーション構成 (app.config) ファイルの <code>&lt;appSettings&gt;</code> セクションへ次のエントリを追加してこの機能を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="71d7a-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="71d7a-108">名前</span><span class="sxs-lookup"><span data-stu-id="71d7a-108">Name</span></span>    | <span data-ttu-id="71d7a-109">[値]</span><span class="sxs-lookup"><span data-stu-id="71d7a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="71d7a-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="71d7a-110">Scope</span></span>   |<span data-ttu-id="71d7a-111">透明</span><span class="sxs-lookup"><span data-stu-id="71d7a-111">Transparent</span></span>|
|<span data-ttu-id="71d7a-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="71d7a-112">Version</span></span>|<span data-ttu-id="71d7a-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="71d7a-113">4.5.2</span></span>|
|<span data-ttu-id="71d7a-114">種類</span><span class="sxs-lookup"><span data-stu-id="71d7a-114">Type</span></span>|<span data-ttu-id="71d7a-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="71d7a-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="71d7a-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="71d7a-116">Affected APIs</span></span>

<span data-ttu-id="71d7a-117">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="71d7a-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
