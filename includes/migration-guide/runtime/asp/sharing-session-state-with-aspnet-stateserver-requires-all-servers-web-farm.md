---
ms.openlocfilehash: 0fe07ac21effacffc56d37ccb46a121f443acd20
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620175"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="fc3ba-101">Asp.Net StateServer とセッション状態を共有するには、Web ファーム内のすべてのサーバーが同じ .NET Framework バージョンを使用する必要があります</span><span class="sxs-lookup"><span data-stu-id="fc3ba-101">Sharing session state with Asp.Net StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="fc3ba-102">説明</span><span class="sxs-lookup"><span data-stu-id="fc3ba-102">Details</span></span>

<span data-ttu-id="fc3ba-103"><xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> セッション状態を有効にする場合、状態を正しく共有するには、指定の Web ファーム内のすべてのサーバーが同じバージョンの .NET Framework を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc3ba-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fc3ba-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="fc3ba-104">Suggestion</span></span>

<span data-ttu-id="fc3ba-105">同時に状態を共有する Web サーバー上で必ず .NET Framework バージョンのアップグレードを行います。</span><span class="sxs-lookup"><span data-stu-id="fc3ba-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>

| <span data-ttu-id="fc3ba-106">名前</span><span class="sxs-lookup"><span data-stu-id="fc3ba-106">Name</span></span>    | <span data-ttu-id="fc3ba-107">[値]</span><span class="sxs-lookup"><span data-stu-id="fc3ba-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fc3ba-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="fc3ba-108">Scope</span></span>   |<span data-ttu-id="fc3ba-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="fc3ba-109">Edge</span></span>|
|<span data-ttu-id="fc3ba-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="fc3ba-110">Version</span></span>|<span data-ttu-id="fc3ba-111">4.5</span><span class="sxs-lookup"><span data-stu-id="fc3ba-111">4.5</span></span>|
|<span data-ttu-id="fc3ba-112">種類</span><span class="sxs-lookup"><span data-stu-id="fc3ba-112">Type</span></span>|<span data-ttu-id="fc3ba-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="fc3ba-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fc3ba-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="fc3ba-114">Affected APIs</span></span>

-<xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
