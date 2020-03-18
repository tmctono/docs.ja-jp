---
ms.openlocfilehash: 9c3eedb7f7d4cd030a12c141b8630876c1ffdb4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859121"
---
### <a name="throttle-concurrent-requests-per-session"></a><span data-ttu-id="a49ab-101">セッションあたりの同時実行される要求のスロットル</span><span class="sxs-lookup"><span data-stu-id="a49ab-101">Throttle concurrent requests per session</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a49ab-102">説明</span><span class="sxs-lookup"><span data-stu-id="a49ab-102">Details</span></span>|<span data-ttu-id="a49ab-103">.NET Framework 4.6.2 以前の場合、ASP.NET は同じ Sessionid の要求を順番に実行します。ASP.NET は既定で常にクッキーを経由して Sessionid を発行します。</span><span class="sxs-lookup"><span data-stu-id="a49ab-103">In the .NET Framework 4.6.2 and earlier, ASP.NET executes requests with the same Sessionid sequentially, and ASP.NET always issues the Sessionid through cookies by default.</span></span> <span data-ttu-id="a49ab-104">ページの応答に長い時間がかかる場合、ブラウザーの F5 を押すと、サーバーのパフォーマンスが大幅に低下します。</span><span class="sxs-lookup"><span data-stu-id="a49ab-104">If a page takes a long time to respond, it will significantly degrade server performance just by pressing F5 on the browser.</span></span> <span data-ttu-id="a49ab-105">この修正プログラムでは、キューに置かれた要求を追跡し、特定の制限を超えたときに要求を終了するためのカウンターを追加しました。</span><span class="sxs-lookup"><span data-stu-id="a49ab-105">In the fix, we added a counter to track the queued requests and terminate the requests when they exceed a specified limit.</span></span> <span data-ttu-id="a49ab-106">既定値は 50 です。</span><span class="sxs-lookup"><span data-stu-id="a49ab-106">The default value is 50.</span></span> <span data-ttu-id="a49ab-107">制限に達すると、警告がイベント ログに記録され、HTTP 500 応答は IIS ログに記録される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a49ab-107">If the limit is reached, a warning will be logged in the event log, and an HTTP 500 response may be recorded in the IIS log.</span></span>|
|<span data-ttu-id="a49ab-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="a49ab-108">Suggestion</span></span>|<span data-ttu-id="a49ab-109">以前の動作を復元するには、次の設定を web.config ファイルに追加して、新しい動作を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="a49ab-109">To restore the old behavior, you can add the following setting to your web.config file to opt out of the new behavior.</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;aspnet:RequestQueueLimitPerSession&quot; value=&quot;2147483647&quot;/&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="a49ab-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="a49ab-110">Scope</span></span>|<span data-ttu-id="a49ab-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="a49ab-111">Edge</span></span>|
|<span data-ttu-id="a49ab-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="a49ab-112">Version</span></span>|<span data-ttu-id="a49ab-113">4.7</span><span class="sxs-lookup"><span data-stu-id="a49ab-113">4.7</span></span>|
|<span data-ttu-id="a49ab-114">[種類]</span><span class="sxs-lookup"><span data-stu-id="a49ab-114">Type</span></span>|<span data-ttu-id="a49ab-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="a49ab-115">Retargeting</span></span>|
