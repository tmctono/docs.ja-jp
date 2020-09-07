---
ms.openlocfilehash: a84d72813a46d6bb39f4710b35d2c9dc859e30ef
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497023"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a><span data-ttu-id="3edf7-101">Page.LoadComplete イベントによって、System.Web.UI.WebControls.EntityDataSource コントロールがデータ バインディングを呼び出さなくなりました</span><span class="sxs-lookup"><span data-stu-id="3edf7-101">Page.LoadComplete event no longer causes System.Web.UI.WebControls.EntityDataSource control to invoke data binding</span></span>

#### <a name="details"></a><span data-ttu-id="3edf7-102">説明</span><span class="sxs-lookup"><span data-stu-id="3edf7-102">Details</span></span>

<span data-ttu-id="3edf7-103"><xref:System.Web.UI.Page.LoadComplete> イベントが原因で、<xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> のコントロールがパラメーターの作成/更新/削除に変更を加えるためにデータ バインディングを呼び出すことがなくなりました。</span><span class="sxs-lookup"><span data-stu-id="3edf7-103">The <xref:System.Web.UI.Page.LoadComplete> event no longer causes the <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> control to invoke data binding for changes to create/update/delete parameters.</span></span> <span data-ttu-id="3edf7-104">この変更により、データベースへの不要なアクセスが排除され、コントロールの値がリセットされるのを防ぐことができるほか、<xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> や <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>などのように他のデータ コントロールと一貫性の取れた動作が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3edf7-104">This change eliminates an extraneous trip to the database, prevents the values of controls from being reset, and produces behavior that is consistent with other data controls, such as <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> and <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>.</span></span> <span data-ttu-id="3edf7-105">この変更により、アプリケーションが <xref:System.Web.UI.Page.LoadComplete> イベントのデータ バインディングの呼び出しに依存するような珍しい状況において、異なる動作が生成されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3edf7-105">This change produces different behavior in the unlikely event that applications rely on invoking data binding in the <xref:System.Web.UI.Page.LoadComplete> event.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3edf7-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="3edf7-106">Suggestion</span></span>

<span data-ttu-id="3edf7-107">データバインドの必要がある場合は、ポストバックの前半であるイベントでデータバインドを手動で呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3edf7-107">If there is a need for databinding, manually invoke databind in an event that is earlier in the post-back.</span></span>

| <span data-ttu-id="3edf7-108">名前</span><span class="sxs-lookup"><span data-stu-id="3edf7-108">Name</span></span>    | <span data-ttu-id="3edf7-109">[値]</span><span class="sxs-lookup"><span data-stu-id="3edf7-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3edf7-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="3edf7-110">Scope</span></span>   |<span data-ttu-id="3edf7-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="3edf7-111">Edge</span></span>|
|<span data-ttu-id="3edf7-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="3edf7-112">Version</span></span>|<span data-ttu-id="3edf7-113">4.5</span><span class="sxs-lookup"><span data-stu-id="3edf7-113">4.5</span></span>|
|<span data-ttu-id="3edf7-114">種類</span><span class="sxs-lookup"><span data-stu-id="3edf7-114">Type</span></span>|<span data-ttu-id="3edf7-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="3edf7-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="3edf7-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="3edf7-116">Affected APIs</span></span>

<span data-ttu-id="3edf7-117">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="3edf7-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
