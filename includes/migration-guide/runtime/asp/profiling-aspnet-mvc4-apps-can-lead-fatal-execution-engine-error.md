---
ms.openlocfilehash: c679cb2603d39f580203d9373d76481e904e6c1d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496790"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="0a37e-101">ASP.Net MVC4 アプリのプロファイリングにより、致命的な実行エンジン エラーが発生する可能性がある</span><span class="sxs-lookup"><span data-stu-id="0a37e-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

#### <a name="details"></a><span data-ttu-id="0a37e-102">説明</span><span class="sxs-lookup"><span data-stu-id="0a37e-102">Details</span></span>

<span data-ttu-id="0a37e-103">NGEN/プロファイル アセンブリを使用するプロファイラーにより、起動時にプロファイルされた ASP.NET MVC4 アプリケーションがクラッシュし、"致命的な実行エンジン例外" が示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0a37e-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0a37e-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="0a37e-104">Suggestion</span></span>

<span data-ttu-id="0a37e-105">この問題は、.NET Framework 4.5.2 で修正されます。</span><span class="sxs-lookup"><span data-stu-id="0a37e-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="0a37e-106">プロファイラーは、イベント マスクで <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> を指定することで、この問題を回避することもできます。</span><span class="sxs-lookup"><span data-stu-id="0a37e-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>

| <span data-ttu-id="0a37e-107">名前</span><span class="sxs-lookup"><span data-stu-id="0a37e-107">Name</span></span>    | <span data-ttu-id="0a37e-108">[値]</span><span class="sxs-lookup"><span data-stu-id="0a37e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0a37e-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="0a37e-109">Scope</span></span>   |<span data-ttu-id="0a37e-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="0a37e-110">Edge</span></span>|
|<span data-ttu-id="0a37e-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="0a37e-111">Version</span></span>|<span data-ttu-id="0a37e-112">4.5</span><span class="sxs-lookup"><span data-stu-id="0a37e-112">4.5</span></span>|
|<span data-ttu-id="0a37e-113">種類</span><span class="sxs-lookup"><span data-stu-id="0a37e-113">Type</span></span>|<span data-ttu-id="0a37e-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="0a37e-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0a37e-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="0a37e-115">Affected APIs</span></span>

<span data-ttu-id="0a37e-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="0a37e-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
