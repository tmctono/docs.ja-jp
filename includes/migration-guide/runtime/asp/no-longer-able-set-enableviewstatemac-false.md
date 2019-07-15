---
ms.openlocfilehash: 78f4d533f1efdc8d43a9ab96508b84a77e3260bc
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803189"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="683d1-101">EnableViewStateMac を false に設定できなくなった</span><span class="sxs-lookup"><span data-stu-id="683d1-101">No longer able to set EnableViewStateMac to false</span></span>

|   |   |
|---|---|
|<span data-ttu-id="683d1-102">説明</span><span class="sxs-lookup"><span data-stu-id="683d1-102">Details</span></span>|<span data-ttu-id="683d1-103">ASP.NET では、開発者は <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> または <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code> を指定できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="683d1-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="683d1-104">ビュー ステートのメッセージ認証コード (MAC) は、ビュー ステートが埋め込まれたすべての要求に強制されています。</span><span class="sxs-lookup"><span data-stu-id="683d1-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="683d1-105">EnableViewStateMac プロパティを明示的に <code>false</code> に設定するアプリのみが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="683d1-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>|
|<span data-ttu-id="683d1-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="683d1-106">Suggestion</span></span>|<span data-ttu-id="683d1-107">EnableViewStateMac は true であると想定する必要があり、結果としての MAC エラーを解決する必要があります ([このガイダンス](https://support.microsoft.com/kb/2915218)で説明されているように、MAC エラーの原因の詳細によって複数の解決策があります)。</span><span class="sxs-lookup"><span data-stu-id="683d1-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>|
|<span data-ttu-id="683d1-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="683d1-108">Scope</span></span>|<span data-ttu-id="683d1-109">Major</span><span class="sxs-lookup"><span data-stu-id="683d1-109">Major</span></span>|
|<span data-ttu-id="683d1-110">Version</span><span class="sxs-lookup"><span data-stu-id="683d1-110">Version</span></span>|<span data-ttu-id="683d1-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="683d1-111">4.5.2</span></span>|
|<span data-ttu-id="683d1-112">型</span><span class="sxs-lookup"><span data-stu-id="683d1-112">Type</span></span>|<span data-ttu-id="683d1-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="683d1-113">Runtime</span></span>|

