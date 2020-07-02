---
ms.openlocfilehash: 0f87f9e9b87860da97ce96e18104b44ec4327c91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621231"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="f308f-101">WCF PipeConnection.GetHashAlgorithm が SHA256 を使用するようになった</span><span class="sxs-lookup"><span data-stu-id="f308f-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="f308f-102">説明</span><span class="sxs-lookup"><span data-stu-id="f308f-102">Details</span></span>

<span data-ttu-id="f308f-103">.NET Framework 4.7.1 以降の Windows Communication Foundation は、SHA256 ハッシュを使用して名前付きパイプ用のランダムな名前を生成します。</span><span class="sxs-lookup"><span data-stu-id="f308f-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="f308f-104">.NET Framework 4.7 以前のバージョンでは、SHA1 ハッシュを使っていました。</span><span class="sxs-lookup"><span data-stu-id="f308f-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f308f-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="f308f-105">Suggestion</span></span>

<span data-ttu-id="f308f-106">.NET Framework 4.7.1 以降でこの変更に関する互換性の問題が発生した場合は、次の行を app.config ファイルの <code>&lt;runtime&gt;</code> セクションに追加することで、変更を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="f308f-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="f308f-107">名前</span><span class="sxs-lookup"><span data-stu-id="f308f-107">Name</span></span>    | <span data-ttu-id="f308f-108">値</span><span class="sxs-lookup"><span data-stu-id="f308f-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f308f-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="f308f-109">Scope</span></span>   |<span data-ttu-id="f308f-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="f308f-110">Minor</span></span>|
|<span data-ttu-id="f308f-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="f308f-111">Version</span></span>|<span data-ttu-id="f308f-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="f308f-112">4.7.1</span></span>|
|<span data-ttu-id="f308f-113">種類</span><span class="sxs-lookup"><span data-stu-id="f308f-113">Type</span></span>|<span data-ttu-id="f308f-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="f308f-114">Runtime</span></span>|
