---
ms.openlocfilehash: d32725b0d3063d3320b73e02039ff567090da932
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496102"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="f7985-101">WCF PipeConnection.GetHashAlgorithm が SHA256 を使用するようになった</span><span class="sxs-lookup"><span data-stu-id="f7985-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="f7985-102">説明</span><span class="sxs-lookup"><span data-stu-id="f7985-102">Details</span></span>

<span data-ttu-id="f7985-103">.NET Framework 4.7.1 以降の Windows Communication Foundation は、SHA256 ハッシュを使用して名前付きパイプ用のランダムな名前を生成します。</span><span class="sxs-lookup"><span data-stu-id="f7985-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="f7985-104">.NET Framework 4.7 以前のバージョンでは、SHA1 ハッシュを使っていました。</span><span class="sxs-lookup"><span data-stu-id="f7985-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f7985-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="f7985-105">Suggestion</span></span>

<span data-ttu-id="f7985-106">.NET Framework 4.7.1 以降でこの変更に関する互換性の問題が発生した場合は、次の行を app.config ファイルの <code>&lt;runtime&gt;</code> セクションに追加することで、変更を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="f7985-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="f7985-107">名前</span><span class="sxs-lookup"><span data-stu-id="f7985-107">Name</span></span>    | <span data-ttu-id="f7985-108">値</span><span class="sxs-lookup"><span data-stu-id="f7985-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f7985-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="f7985-109">Scope</span></span>   |<span data-ttu-id="f7985-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="f7985-110">Minor</span></span>|
|<span data-ttu-id="f7985-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="f7985-111">Version</span></span>|<span data-ttu-id="f7985-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="f7985-112">4.7.1</span></span>|
|<span data-ttu-id="f7985-113">種類</span><span class="sxs-lookup"><span data-stu-id="f7985-113">Type</span></span>|<span data-ttu-id="f7985-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="f7985-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f7985-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="f7985-115">Affected APIs</span></span>

<span data-ttu-id="f7985-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="f7985-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
