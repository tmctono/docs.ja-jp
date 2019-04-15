---
ms.openlocfilehash: 735278848cb7399e414a128afc650a0a1f882337
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236021"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="e0b45-101">TextBlock コントロールの親の IsEnabled プロパティの変更がすべての子コントロールに影響する</span><span class="sxs-lookup"><span data-stu-id="e0b45-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e0b45-102">説明</span><span class="sxs-lookup"><span data-stu-id="e0b45-102">Details</span></span>|<span data-ttu-id="e0b45-103">.NET Framework 4.6.2、変更以降の<xref:System.Windows.UIElement.IsEnabled?displayProperty=name>の親のプロパティ、<xref:System.Windows.Controls.TextBlock?displayProperty=name>コントロール (ハイパーリンクやボタンなど) などの子コントロールに影響を与える、<xref:System.Windows.Controls.TextBlock?displayProperty=name>コントロール。 .NET Framework 4.6.1 以前のバージョンで、内部コントロール、<xref:System.Windows.Controls.TextBlock?displayProperty=name>の状態を常に反映されませんでした、<xref:System.Windows.UIElement.IsEnabled?displayProperty=name>のプロパティ、<xref:System.Windows.Controls.TextBlock?displayProperty=name>親。</span><span class="sxs-lookup"><span data-stu-id="e0b45-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=name> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=name> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=name> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=name> parent.</span></span>|
|<span data-ttu-id="e0b45-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="e0b45-104">Suggestion</span></span>|<span data-ttu-id="e0b45-105">なし。</span><span class="sxs-lookup"><span data-stu-id="e0b45-105">None.</span></span> <span data-ttu-id="e0b45-106">この変更は、<xref:System.Windows.Controls.TextBlock?displayProperty=name> コントロール内部のコントロールに期待される動作に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="e0b45-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=name> control.</span></span>|
|<span data-ttu-id="e0b45-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="e0b45-107">Scope</span></span>|<span data-ttu-id="e0b45-108">マイナー</span><span class="sxs-lookup"><span data-stu-id="e0b45-108">Minor</span></span>|
|<span data-ttu-id="e0b45-109">Version</span><span class="sxs-lookup"><span data-stu-id="e0b45-109">Version</span></span>|<span data-ttu-id="e0b45-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="e0b45-110">4.6.2</span></span>|
|<span data-ttu-id="e0b45-111">型</span><span class="sxs-lookup"><span data-stu-id="e0b45-111">Type</span></span>|<span data-ttu-id="e0b45-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="e0b45-112">Runtime</span></span>|
|<span data-ttu-id="e0b45-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e0b45-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
