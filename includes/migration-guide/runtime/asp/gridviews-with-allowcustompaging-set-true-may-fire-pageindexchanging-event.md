---
ms.openlocfilehash: 4d210eeedd2f228017634d29f11554deb6ed8079
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496842"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a><span data-ttu-id="20d7c-101">AllowCustomPaging が true に設定された GridView では、ビューの最終ページから他に移動するときに、PageIndexChanging イベントが発生する場合がある</span><span class="sxs-lookup"><span data-stu-id="20d7c-101">GridViews with AllowCustomPaging set to true may fire the PageIndexChanging event when leaving the final page of the view</span></span>

#### <a name="details"></a><span data-ttu-id="20d7c-102">説明</span><span class="sxs-lookup"><span data-stu-id="20d7c-102">Details</span></span>

<span data-ttu-id="20d7c-103">.NET Framework 4.5 でのバグのため、<xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName> が有効になっている <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> に対して <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> が発生しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="20d7c-103">A bug in the .NET Framework 4.5 causes <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> to sometimes not fire for <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>s that have enabled <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="20d7c-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="20d7c-104">Suggestion</span></span>

<span data-ttu-id="20d7c-105">この問題は .NET Framework 4.6 で修正されたため、このバージョンの .NET Framework にアップグレードすることによって対処できます。</span><span class="sxs-lookup"><span data-stu-id="20d7c-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span> <span data-ttu-id="20d7c-106">回避策として、アプリでは、これらの条件 (<xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> が最終ページで、最後の <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> が <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> と異なる) を満たす <code>Page_Load</code> で明示的に BindGrid を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="20d7c-106">As a work-around, the app can do an explicit BindGrid on any <code>Page_Load</code> that would hit these conditions (the <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> is on the last page and Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> is different from <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span></span> <span data-ttu-id="20d7c-107">または、(カスタム ページングではなく) ページングを許可するようにアプリを変更することもできます。このシナリオでは問題は発生していません。</span><span class="sxs-lookup"><span data-stu-id="20d7c-107">Alternatively, the app can be modified to allow paging (instead of custom paging), as that scenario does not demonstrate the problem.</span></span>

| <span data-ttu-id="20d7c-108">名前</span><span class="sxs-lookup"><span data-stu-id="20d7c-108">Name</span></span>    | <span data-ttu-id="20d7c-109">[値]</span><span class="sxs-lookup"><span data-stu-id="20d7c-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="20d7c-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="20d7c-110">Scope</span></span>   |<span data-ttu-id="20d7c-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="20d7c-111">Minor</span></span>|
|<span data-ttu-id="20d7c-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="20d7c-112">Version</span></span>|<span data-ttu-id="20d7c-113">4.5</span><span class="sxs-lookup"><span data-stu-id="20d7c-113">4.5</span></span>|
|<span data-ttu-id="20d7c-114">種類</span><span class="sxs-lookup"><span data-stu-id="20d7c-114">Type</span></span>|<span data-ttu-id="20d7c-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="20d7c-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="20d7c-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="20d7c-116">Affected APIs</span></span>

- <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.UI.WebControls.GridView.AllowCustomPaging`

-->
