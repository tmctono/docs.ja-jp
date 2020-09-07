---
ms.openlocfilehash: 4d210eeedd2f228017634d29f11554deb6ed8079
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496842"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a>AllowCustomPaging が true に設定された GridView では、ビューの最終ページから他に移動するときに、PageIndexChanging イベントが発生する場合がある

#### <a name="details"></a>説明

.NET Framework 4.5 でのバグのため、<xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName> が有効になっている <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> に対して <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> が発生しないことがあります。

#### <a name="suggestion"></a>提案される解決策

この問題は .NET Framework 4.6 で修正されたため、このバージョンの .NET Framework にアップグレードすることによって対処できます。 回避策として、アプリでは、これらの条件 (<xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> が最終ページで、最後の <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> が <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> と異なる) を満たす <code>Page_Load</code> で明示的に BindGrid を行うことができます。 または、(カスタム ページングではなく) ページングを許可するようにアプリを変更することもできます。このシナリオでは問題は発生していません。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   |マイナー|
|バージョン|4.5|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.UI.WebControls.GridView.AllowCustomPaging`

-->
