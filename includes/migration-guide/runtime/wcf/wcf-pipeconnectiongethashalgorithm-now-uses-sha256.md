---
ms.openlocfilehash: 318609c15d2e0b9a7ee59b38463735b33ef87974
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857266"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="4051a-101">WCF PipeConnection.GetHashAlgorithm が SHA256 を使用するようになった</span><span class="sxs-lookup"><span data-stu-id="4051a-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4051a-102">説明</span><span class="sxs-lookup"><span data-stu-id="4051a-102">Details</span></span>|<span data-ttu-id="4051a-103">.NET Framework 4.7.1 以降の Windows Communication Foundation は、SHA256 ハッシュを使用して名前付きパイプ用のランダムな名前を生成します。</span><span class="sxs-lookup"><span data-stu-id="4051a-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="4051a-104">.NET Framework 4.7 以前のバージョンでは、SHA1 ハッシュを使っていました。</span><span class="sxs-lookup"><span data-stu-id="4051a-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>|
|<span data-ttu-id="4051a-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="4051a-105">Suggestion</span></span>|<span data-ttu-id="4051a-106">.NET Framework 4.7.1 以降でこの変更に関する互換性の問題が発生した場合は、次の行を app.config ファイルの <code>&lt;runtime&gt;</code> セクションに追加することで、変更を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="4051a-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="4051a-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="4051a-107">Scope</span></span>|<span data-ttu-id="4051a-108">Minor</span><span class="sxs-lookup"><span data-stu-id="4051a-108">Minor</span></span>|
|<span data-ttu-id="4051a-109">バージョン</span><span class="sxs-lookup"><span data-stu-id="4051a-109">Version</span></span>|<span data-ttu-id="4051a-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="4051a-110">4.7.1</span></span>|
|<span data-ttu-id="4051a-111">[種類]</span><span class="sxs-lookup"><span data-stu-id="4051a-111">Type</span></span>|<span data-ttu-id="4051a-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="4051a-112">Runtime</span></span>|
