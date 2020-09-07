---
ms.openlocfilehash: c1793bb51f7da9169e912078fde202d0d62a4183
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497506"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="7ec1b-101">EnableViewStateMac を false に設定できなくなった</span><span class="sxs-lookup"><span data-stu-id="7ec1b-101">No longer able to set EnableViewStateMac to false</span></span>

#### <a name="details"></a><span data-ttu-id="7ec1b-102">説明</span><span class="sxs-lookup"><span data-stu-id="7ec1b-102">Details</span></span>

<span data-ttu-id="7ec1b-103">ASP.NET では、開発者は <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> または <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code> を指定できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7ec1b-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="7ec1b-104">ビュー ステートのメッセージ認証コード (MAC) は、ビュー ステートが埋め込まれたすべての要求に強制されています。</span><span class="sxs-lookup"><span data-stu-id="7ec1b-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="7ec1b-105">EnableViewStateMac プロパティを明示的に <code>false</code> に設定するアプリのみが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="7ec1b-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7ec1b-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="7ec1b-106">Suggestion</span></span>

<span data-ttu-id="7ec1b-107">EnableViewStateMac は true であると想定する必要があり、結果としての MAC エラーを解決する必要があります ([このガイダンス](https://support.microsoft.com/kb/2915218)で説明されているように、MAC エラーの原因の詳細によって複数の解決策があります)。</span><span class="sxs-lookup"><span data-stu-id="7ec1b-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>

| <span data-ttu-id="7ec1b-108">名前</span><span class="sxs-lookup"><span data-stu-id="7ec1b-108">Name</span></span>    | <span data-ttu-id="7ec1b-109">[値]</span><span class="sxs-lookup"><span data-stu-id="7ec1b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7ec1b-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="7ec1b-110">Scope</span></span>   |<span data-ttu-id="7ec1b-111">Major</span><span class="sxs-lookup"><span data-stu-id="7ec1b-111">Major</span></span>|
|<span data-ttu-id="7ec1b-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="7ec1b-112">Version</span></span>|<span data-ttu-id="7ec1b-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="7ec1b-113">4.5.2</span></span>|
|<span data-ttu-id="7ec1b-114">種類</span><span class="sxs-lookup"><span data-stu-id="7ec1b-114">Type</span></span>|<span data-ttu-id="7ec1b-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="7ec1b-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="7ec1b-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="7ec1b-116">Affected APIs</span></span>

<span data-ttu-id="7ec1b-117">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="7ec1b-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
