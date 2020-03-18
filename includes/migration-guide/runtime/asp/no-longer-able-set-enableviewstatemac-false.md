---
ms.openlocfilehash: dbe96abebdc61fae469f7727673e6fcb93cbc739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803189"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="74914-101">EnableViewStateMac を false に設定できなくなった</span><span class="sxs-lookup"><span data-stu-id="74914-101">No longer able to set EnableViewStateMac to false</span></span>

|   |   |
|---|---|
|<span data-ttu-id="74914-102">説明</span><span class="sxs-lookup"><span data-stu-id="74914-102">Details</span></span>|<span data-ttu-id="74914-103">ASP.NET では、開発者は <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> または <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code> を指定できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="74914-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="74914-104">ビュー ステートのメッセージ認証コード (MAC) は、ビュー ステートが埋め込まれたすべての要求に強制されています。</span><span class="sxs-lookup"><span data-stu-id="74914-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="74914-105">EnableViewStateMac プロパティを明示的に <code>false</code> に設定するアプリのみが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="74914-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>|
|<span data-ttu-id="74914-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="74914-106">Suggestion</span></span>|<span data-ttu-id="74914-107">EnableViewStateMac は true であると想定する必要があり、結果としての MAC エラーを解決する必要があります ([このガイダンス](https://support.microsoft.com/kb/2915218)で説明されているように、MAC エラーの原因の詳細によって複数の解決策があります)。</span><span class="sxs-lookup"><span data-stu-id="74914-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>|
|<span data-ttu-id="74914-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="74914-108">Scope</span></span>|<span data-ttu-id="74914-109">Major</span><span class="sxs-lookup"><span data-stu-id="74914-109">Major</span></span>|
|<span data-ttu-id="74914-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="74914-110">Version</span></span>|<span data-ttu-id="74914-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="74914-111">4.5.2</span></span>|
|<span data-ttu-id="74914-112">[種類]</span><span class="sxs-lookup"><span data-stu-id="74914-112">Type</span></span>|<span data-ttu-id="74914-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="74914-113">Runtime</span></span>|
