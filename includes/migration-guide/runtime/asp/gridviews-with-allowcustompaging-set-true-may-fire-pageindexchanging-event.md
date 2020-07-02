---
ms.openlocfilehash: 3b329bf5ba2af4d3ab9c3e203e99daba8ca0d0c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620139"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a><span data-ttu-id="dbd46-101">AllowCustomPaging が true に設定された GridView では、ビューの最終ページから他に移動するときに、PageIndexChanging イベントが発生する場合がある</span><span class="sxs-lookup"><span data-stu-id="dbd46-101">GridViews with AllowCustomPaging set to true may fire the PageIndexChanging event when leaving the final page of the view</span></span>

#### <a name="details"></a><span data-ttu-id="dbd46-102">説明</span><span class="sxs-lookup"><span data-stu-id="dbd46-102">Details</span></span>

<span data-ttu-id="dbd46-103">.NET Framework 4.5 でのバグのため、<xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName> が有効になっている <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> に対して <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> が発生しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="dbd46-103">A bug in the .NET Framework 4.5 causes <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> to sometimes not fire for <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>s that have enabled <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dbd46-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="dbd46-104">Suggestion</span></span>

<span data-ttu-id="dbd46-105">この問題は .NET Framework 4.6 で修正されたため、このバージョンの .NET Framework にアップグレードすることによって対処できます。</span><span class="sxs-lookup"><span data-stu-id="dbd46-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span> <span data-ttu-id="dbd46-106">回避策として、アプリでは、これらの条件 (<xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> が最終ページで、最後の <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> が <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> と異なる) を満たす <code>Page_Load</code> で明示的に BindGrid を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dbd46-106">As a work-around, the app can do an explicit BindGrid on any <code>Page_Load</code> that would hit these conditions (the <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> is on the last page and Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> is different from <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span></span> <span data-ttu-id="dbd46-107">または、(カスタム ページングではなく) ページングを許可するようにアプリを変更することもできます。このシナリオでは問題は発生していません。</span><span class="sxs-lookup"><span data-stu-id="dbd46-107">Alternatively, the app can be modified to allow paging (instead of custom paging), as that scenario does not demonstrate the problem.</span></span>

| <span data-ttu-id="dbd46-108">名前</span><span class="sxs-lookup"><span data-stu-id="dbd46-108">Name</span></span>    | <span data-ttu-id="dbd46-109">[値]</span><span class="sxs-lookup"><span data-stu-id="dbd46-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dbd46-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="dbd46-110">Scope</span></span>   |<span data-ttu-id="dbd46-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="dbd46-111">Minor</span></span>|
|<span data-ttu-id="dbd46-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="dbd46-112">Version</span></span>|<span data-ttu-id="dbd46-113">4.5</span><span class="sxs-lookup"><span data-stu-id="dbd46-113">4.5</span></span>|
|<span data-ttu-id="dbd46-114">種類</span><span class="sxs-lookup"><span data-stu-id="dbd46-114">Type</span></span>|<span data-ttu-id="dbd46-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="dbd46-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dbd46-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="dbd46-116">Affected APIs</span></span>

-<xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType></li></ul>|
