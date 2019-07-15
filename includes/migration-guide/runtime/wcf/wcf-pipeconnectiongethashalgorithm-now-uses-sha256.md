---
ms.openlocfilehash: 71f61f23a8b17459610d253766a99e594f09428e
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857266"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="37273-101">WCF PipeConnection.GetHashAlgorithm が SHA256 を使用するようになった</span><span class="sxs-lookup"><span data-stu-id="37273-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="37273-102">説明</span><span class="sxs-lookup"><span data-stu-id="37273-102">Details</span></span>|<span data-ttu-id="37273-103">.NET Framework 4.7.1 以降の Windows Communication Foundation は、SHA256 ハッシュを使用して名前付きパイプ用のランダムな名前を生成します。</span><span class="sxs-lookup"><span data-stu-id="37273-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="37273-104">.NET Framework 4.7 以前のバージョンでは、SHA1 ハッシュを使っていました。</span><span class="sxs-lookup"><span data-stu-id="37273-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>|
|<span data-ttu-id="37273-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="37273-105">Suggestion</span></span>|<span data-ttu-id="37273-106">.NET Framework 4.7.1 以降でこの変更に関する互換性の問題が発生した場合は、次の行を app.config ファイルの <code>&lt;runtime&gt;</code> セクションに追加することで、変更を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="37273-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="37273-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="37273-107">Scope</span></span>|<span data-ttu-id="37273-108">マイナー</span><span class="sxs-lookup"><span data-stu-id="37273-108">Minor</span></span>|
|<span data-ttu-id="37273-109">Version</span><span class="sxs-lookup"><span data-stu-id="37273-109">Version</span></span>|<span data-ttu-id="37273-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="37273-110">4.7.1</span></span>|
|<span data-ttu-id="37273-111">型</span><span class="sxs-lookup"><span data-stu-id="37273-111">Type</span></span>|<span data-ttu-id="37273-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="37273-112">Runtime</span></span>|

