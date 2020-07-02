---
ms.openlocfilehash: 395463225e3c1f1d168dd019ea75966ad54e5a8a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621260"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="a24d6-101">TextBlock コントロールの親の IsEnabled プロパティの変更がすべての子コントロールに影響する</span><span class="sxs-lookup"><span data-stu-id="a24d6-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

#### <a name="details"></a><span data-ttu-id="a24d6-102">説明</span><span class="sxs-lookup"><span data-stu-id="a24d6-102">Details</span></span>

<span data-ttu-id="a24d6-103">.NET Framework 4.6.2、変更以降の<xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName>の親のプロパティ、<xref:System.Windows.Controls.TextBlock?displayProperty=fullName>コントロール (ハイパーリンクやボタンなど) などの子コントロールに影響を与える、<xref:System.Windows.Controls.TextBlock?displayProperty=fullName>コントロール。 .NET Framework 4.6.1 以前のバージョンで、内部コントロール、<xref:System.Windows.Controls.TextBlock?displayProperty=fullName>の状態を常に反映されませんでした、<xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName>のプロパティ、<xref:System.Windows.Controls.TextBlock?displayProperty=fullName>親。</span><span class="sxs-lookup"><span data-stu-id="a24d6-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> parent.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a24d6-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="a24d6-104">Suggestion</span></span>

<span data-ttu-id="a24d6-105">[なし] :</span><span class="sxs-lookup"><span data-stu-id="a24d6-105">None.</span></span> <span data-ttu-id="a24d6-106">この変更は、<xref:System.Windows.Controls.TextBlock?displayProperty=fullName> コントロール内部のコントロールに期待される動作に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="a24d6-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.</span></span>

| <span data-ttu-id="a24d6-107">名前</span><span class="sxs-lookup"><span data-stu-id="a24d6-107">Name</span></span>    | <span data-ttu-id="a24d6-108">値</span><span class="sxs-lookup"><span data-stu-id="a24d6-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a24d6-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="a24d6-109">Scope</span></span>   |<span data-ttu-id="a24d6-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="a24d6-110">Minor</span></span>|
|<span data-ttu-id="a24d6-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="a24d6-111">Version</span></span>|<span data-ttu-id="a24d6-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="a24d6-112">4.6.2</span></span>|
|<span data-ttu-id="a24d6-113">種類</span><span class="sxs-lookup"><span data-stu-id="a24d6-113">Type</span></span>|<span data-ttu-id="a24d6-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="a24d6-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a24d6-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="a24d6-115">Affected APIs</span></span>

-<xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
