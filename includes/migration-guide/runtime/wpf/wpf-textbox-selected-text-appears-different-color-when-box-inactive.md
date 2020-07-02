---
ms.openlocfilehash: cd59818fe674e10a206725bea8a74c4aceed99b1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620469"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="fc781-101">WPF TextBox で選択されているテキストが、テキスト ボックスがアクティブでないときに異なる色で表示される</span><span class="sxs-lookup"><span data-stu-id="fc781-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

#### <a name="details"></a><span data-ttu-id="fc781-102">説明</span><span class="sxs-lookup"><span data-stu-id="fc781-102">Details</span></span>

<span data-ttu-id="fc781-103">.NET Framework 4.5 では、WPF テキスト ボックス コントロールがアクティブでないとき (フォーカスがないとき)、ボックス内で選択されているテキストは、コントロールがアクティブなときとは別の色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc781-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fc781-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="fc781-104">Suggestion</span></span>

<span data-ttu-id="fc781-105"><xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> プロパティを <code>false</code> に設定することで、以前 (.NET Framework 4.0) の動作が復元される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fc781-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>

| <span data-ttu-id="fc781-106">名前</span><span class="sxs-lookup"><span data-stu-id="fc781-106">Name</span></span>    | <span data-ttu-id="fc781-107">[値]</span><span class="sxs-lookup"><span data-stu-id="fc781-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fc781-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="fc781-108">Scope</span></span>   |<span data-ttu-id="fc781-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="fc781-109">Edge</span></span>|
|<span data-ttu-id="fc781-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="fc781-110">Version</span></span>|<span data-ttu-id="fc781-111">4.5</span><span class="sxs-lookup"><span data-stu-id="fc781-111">4.5</span></span>|
|<span data-ttu-id="fc781-112">種類</span><span class="sxs-lookup"><span data-stu-id="fc781-112">Type</span></span>|<span data-ttu-id="fc781-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="fc781-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fc781-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="fc781-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
