---
ms.openlocfilehash: cecb7b2abd4f57fdaacb0ea373cc19dc3cd9b24a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620168"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="0cb04-101">EnableViewStateMac を false に設定できなくなった</span><span class="sxs-lookup"><span data-stu-id="0cb04-101">No longer able to set EnableViewStateMac to false</span></span>

#### <a name="details"></a><span data-ttu-id="0cb04-102">説明</span><span class="sxs-lookup"><span data-stu-id="0cb04-102">Details</span></span>

<span data-ttu-id="0cb04-103">ASP.NET では、開発者は <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> または <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code> を指定できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0cb04-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="0cb04-104">ビュー ステートのメッセージ認証コード (MAC) は、ビュー ステートが埋め込まれたすべての要求に強制されています。</span><span class="sxs-lookup"><span data-stu-id="0cb04-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="0cb04-105">EnableViewStateMac プロパティを明示的に <code>false</code> に設定するアプリのみが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="0cb04-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0cb04-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="0cb04-106">Suggestion</span></span>

<span data-ttu-id="0cb04-107">EnableViewStateMac は true であると想定する必要があり、結果としての MAC エラーを解決する必要があります ([このガイダンス](https://support.microsoft.com/kb/2915218)で説明されているように、MAC エラーの原因の詳細によって複数の解決策があります)。</span><span class="sxs-lookup"><span data-stu-id="0cb04-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>

| <span data-ttu-id="0cb04-108">名前</span><span class="sxs-lookup"><span data-stu-id="0cb04-108">Name</span></span>    | <span data-ttu-id="0cb04-109">[値]</span><span class="sxs-lookup"><span data-stu-id="0cb04-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0cb04-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="0cb04-110">Scope</span></span>   |<span data-ttu-id="0cb04-111">Major</span><span class="sxs-lookup"><span data-stu-id="0cb04-111">Major</span></span>|
|<span data-ttu-id="0cb04-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="0cb04-112">Version</span></span>|<span data-ttu-id="0cb04-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="0cb04-113">4.5.2</span></span>|
|<span data-ttu-id="0cb04-114">種類</span><span class="sxs-lookup"><span data-stu-id="0cb04-114">Type</span></span>|<span data-ttu-id="0cb04-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="0cb04-115">Runtime</span></span>|
