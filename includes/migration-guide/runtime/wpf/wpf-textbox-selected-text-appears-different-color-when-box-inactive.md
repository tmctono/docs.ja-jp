---
ms.openlocfilehash: 74ce1bbc9a887aee3a33eaf05084e8c2000967c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235756"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="49507-101">WPF TextBox で選択されているテキストが、テキスト ボックスがアクティブでないときに異なる色で表示される</span><span class="sxs-lookup"><span data-stu-id="49507-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

|   |   |
|---|---|
|<span data-ttu-id="49507-102">説明</span><span class="sxs-lookup"><span data-stu-id="49507-102">Details</span></span>|<span data-ttu-id="49507-103">.NET Framework 4.5 では、WPF テキスト ボックス コントロールがアクティブでないとき (フォーカスがないとき)、ボックス内で選択されているテキストは、コントロールがアクティブなときとは別の色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="49507-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>|
|<span data-ttu-id="49507-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="49507-104">Suggestion</span></span>|<span data-ttu-id="49507-105"><xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> プロパティを <code>false</code> に設定することで、以前 (.NET Framework 4.0) の動作が復元される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="49507-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>|
|<span data-ttu-id="49507-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="49507-106">Scope</span></span>|<span data-ttu-id="49507-107">エッジ</span><span class="sxs-lookup"><span data-stu-id="49507-107">Edge</span></span>|
|<span data-ttu-id="49507-108">Version</span><span class="sxs-lookup"><span data-stu-id="49507-108">Version</span></span>|<span data-ttu-id="49507-109">4.5</span><span class="sxs-lookup"><span data-stu-id="49507-109">4.5</span></span>|
|<span data-ttu-id="49507-110">型</span><span class="sxs-lookup"><span data-stu-id="49507-110">Type</span></span>|<span data-ttu-id="49507-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="49507-111">Runtime</span></span>|
|<span data-ttu-id="49507-112">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="49507-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
