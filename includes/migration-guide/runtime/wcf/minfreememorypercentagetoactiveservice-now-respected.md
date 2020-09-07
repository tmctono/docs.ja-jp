---
ms.openlocfilehash: b23182ad1da8208a69b78fc7bc872780d386a59a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496442"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="2d51f-101">MinFreeMemoryPercentageToActiveService が順守されるようになった</span><span class="sxs-lookup"><span data-stu-id="2d51f-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

#### <a name="details"></a><span data-ttu-id="2d51f-102">説明</span><span class="sxs-lookup"><span data-stu-id="2d51f-102">Details</span></span>

<span data-ttu-id="2d51f-103">この設定は、WCF サービスをアクティブにするためにサーバー上で使用できなければならない最小メモリを設定します。</span><span class="sxs-lookup"><span data-stu-id="2d51f-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="2d51f-104"><xref:System.OutOfMemoryException?displayProperty=fullName> 例外が発生しないようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="2d51f-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=fullName> exceptions.</span></span> <span data-ttu-id="2d51f-105">.NET Framework 4.5 では、この設定には効果はありません。</span><span class="sxs-lookup"><span data-stu-id="2d51f-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="2d51f-106">.NET Framework 4.5.1 では、この設定が守られます。</span><span class="sxs-lookup"><span data-stu-id="2d51f-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2d51f-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="2d51f-107">Suggestion</span></span>

<span data-ttu-id="2d51f-108">Web サーバーで使用できる空きメモリが構成設定によって定義されたパーセンテージよりも小さい場合、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="2d51f-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="2d51f-109">制約されたメモリ環境で正常に開始し、実行された WCF サービスが今度は失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="2d51f-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>

| <span data-ttu-id="2d51f-110">名前</span><span class="sxs-lookup"><span data-stu-id="2d51f-110">Name</span></span>    | <span data-ttu-id="2d51f-111">[値]</span><span class="sxs-lookup"><span data-stu-id="2d51f-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2d51f-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="2d51f-112">Scope</span></span>   |<span data-ttu-id="2d51f-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="2d51f-113">Minor</span></span>|
|<span data-ttu-id="2d51f-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="2d51f-114">Version</span></span>|<span data-ttu-id="2d51f-115">4.5.1</span><span class="sxs-lookup"><span data-stu-id="2d51f-115">4.5.1</span></span>|
|<span data-ttu-id="2d51f-116">種類</span><span class="sxs-lookup"><span data-stu-id="2d51f-116">Type</span></span>|<span data-ttu-id="2d51f-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="2d51f-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2d51f-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="2d51f-118">Affected APIs</span></span>

<span data-ttu-id="2d51f-119">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="2d51f-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
