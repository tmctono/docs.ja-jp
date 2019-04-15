---
ms.openlocfilehash: dbe96abebdc61fae469f7727673e6fcb93cbc739
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236645"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="6b3c2-101">EnableViewStateMac を false に設定できなくなった</span><span class="sxs-lookup"><span data-stu-id="6b3c2-101">No longer able to set EnableViewStateMac to false</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6b3c2-102">説明</span><span class="sxs-lookup"><span data-stu-id="6b3c2-102">Details</span></span>|<span data-ttu-id="6b3c2-103">ASP.NET では、開発者は <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> または <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code> を指定できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6b3c2-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="6b3c2-104">ビュー ステートのメッセージ認証コード (MAC) は、ビュー ステートが埋め込まれたすべての要求に強制されています。</span><span class="sxs-lookup"><span data-stu-id="6b3c2-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="6b3c2-105">EnableViewStateMac プロパティを明示的に <code>false</code> に設定するアプリのみが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="6b3c2-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>|
|<span data-ttu-id="6b3c2-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="6b3c2-106">Suggestion</span></span>|<span data-ttu-id="6b3c2-107">EnableViewStateMac は true であると想定する必要があり、結果としての MAC エラーを解決する必要があります ([このガイダンス](https://support.microsoft.com/kb/2915218)で説明されているように、MAC エラーの原因の詳細によって複数の解決策があります)。</span><span class="sxs-lookup"><span data-stu-id="6b3c2-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>|
|<span data-ttu-id="6b3c2-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="6b3c2-108">Scope</span></span>|<span data-ttu-id="6b3c2-109">Major</span><span class="sxs-lookup"><span data-stu-id="6b3c2-109">Major</span></span>|
|<span data-ttu-id="6b3c2-110">Version</span><span class="sxs-lookup"><span data-stu-id="6b3c2-110">Version</span></span>|<span data-ttu-id="6b3c2-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="6b3c2-111">4.5.2</span></span>|
|<span data-ttu-id="6b3c2-112">型</span><span class="sxs-lookup"><span data-stu-id="6b3c2-112">Type</span></span>|<span data-ttu-id="6b3c2-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="6b3c2-113">Runtime</span></span>|
