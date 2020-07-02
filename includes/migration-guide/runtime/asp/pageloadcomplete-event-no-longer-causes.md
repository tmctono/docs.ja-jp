---
ms.openlocfilehash: 39d609c955596354d1af28b4ed19d367dab0462b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620156"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a><span data-ttu-id="e2de4-101">Page.LoadComplete イベントによって、System.Web.UI.WebControls.EntityDataSource コントロールがデータ バインディングを呼び出さなくなりました</span><span class="sxs-lookup"><span data-stu-id="e2de4-101">Page.LoadComplete event no longer causes System.Web.UI.WebControls.EntityDataSource control to invoke data binding</span></span>

#### <a name="details"></a><span data-ttu-id="e2de4-102">説明</span><span class="sxs-lookup"><span data-stu-id="e2de4-102">Details</span></span>

<span data-ttu-id="e2de4-103"><xref:System.Web.UI.Page.LoadComplete> イベントが原因で、<xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> のコントロールがパラメーターの作成/更新/削除に変更を加えるためにデータ バインディングを呼び出すことがなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e2de4-103">The <xref:System.Web.UI.Page.LoadComplete> event no longer causes the <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> control to invoke data binding for changes to create/update/delete parameters.</span></span> <span data-ttu-id="e2de4-104">この変更により、データベースへの不要なアクセスが排除され、コントロールの値がリセットされるのを防ぐことができるほか、<xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> や <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>などのように他のデータ コントロールと一貫性の取れた動作が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e2de4-104">This change eliminates an extraneous trip to the database, prevents the values of controls from being reset, and produces behavior that is consistent with other data controls, such as <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> and <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>.</span></span> <span data-ttu-id="e2de4-105">この変更により、アプリケーションが <xref:System.Web.UI.Page.LoadComplete> イベントのデータ バインディングの呼び出しに依存するような珍しい状況において、異なる動作が生成されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e2de4-105">This change produces different behavior in the unlikely event that applications rely on invoking data binding in the <xref:System.Web.UI.Page.LoadComplete> event.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e2de4-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="e2de4-106">Suggestion</span></span>

<span data-ttu-id="e2de4-107">データバインドの必要がある場合は、ポストバックの前半であるイベントでデータバインドを手動で呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e2de4-107">If there is a need for databinding, manually invoke databind in an event that is earlier in the post-back.</span></span>

| <span data-ttu-id="e2de4-108">名前</span><span class="sxs-lookup"><span data-stu-id="e2de4-108">Name</span></span>    | <span data-ttu-id="e2de4-109">[値]</span><span class="sxs-lookup"><span data-stu-id="e2de4-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e2de4-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="e2de4-110">Scope</span></span>   |<span data-ttu-id="e2de4-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="e2de4-111">Edge</span></span>|
|<span data-ttu-id="e2de4-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="e2de4-112">Version</span></span>|<span data-ttu-id="e2de4-113">4.5</span><span class="sxs-lookup"><span data-stu-id="e2de4-113">4.5</span></span>|
|<span data-ttu-id="e2de4-114">種類</span><span class="sxs-lookup"><span data-stu-id="e2de4-114">Type</span></span>|<span data-ttu-id="e2de4-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="e2de4-115">Runtime</span></span>|
