---
ms.openlocfilehash: c4a3d903894027a01d32ca132d1233da9d9c3ee5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497702"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a><span data-ttu-id="918e1-101">PreviewLostKeyboardFocus は、そのハンドラーが Windows フォーム メッセージ ボックスを表示する場合、繰り返し呼び出される</span><span class="sxs-lookup"><span data-stu-id="918e1-101">PreviewLostKeyboardFocus is called repeatedly if its handler shows a Windows Forms message box</span></span>

#### <a name="details"></a><span data-ttu-id="918e1-102">説明</span><span class="sxs-lookup"><span data-stu-id="918e1-102">Details</span></span>

<span data-ttu-id="918e1-103">.NET Framework 4.5 以降では、<xref:System.Windows.UIElement.PreviewLostKeyboardFocus> ハンドラーから <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> を呼び出すと、メッセージ ボックスが閉じられたとき、ハンドラーが再実行して、メッセージ ボックスの無限ループになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="918e1-103">Beginning in the .NET Framework 4.5, calling <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> from a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> handler will cause the handler to re-fire when the message box is closed, potentially resulting in an infinite loop of message boxes.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="918e1-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="918e1-104">Suggestion</span></span>

<span data-ttu-id="918e1-105">この問題を回避するには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="918e1-105">There are two options to work around this issue:</span></span><ol><li><span data-ttu-id="918e1-106"><xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> の代わりに <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> を呼び出すことによって回避できます。</span><span class="sxs-lookup"><span data-stu-id="918e1-106">It may be avoided by calling <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> instead of <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</span></span></li><li><span data-ttu-id="918e1-107"><xref:System.Windows.UIElement.LostKeyboardFocus> イベント ハンドラーから (<xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName> イベント ハンドラーではなく) メッセージ ボックスを表示することによって回避できます。</span><span class="sxs-lookup"><span data-stu-id="918e1-107">It may be avoided by showing the message box from a <xref:System.Windows.UIElement.LostKeyboardFocus> event handler (as opposed to a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName> event handler).</span></span></li></ol>

| <span data-ttu-id="918e1-108">名前</span><span class="sxs-lookup"><span data-stu-id="918e1-108">Name</span></span>    | <span data-ttu-id="918e1-109">[値]</span><span class="sxs-lookup"><span data-stu-id="918e1-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="918e1-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="918e1-110">Scope</span></span>   |<span data-ttu-id="918e1-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="918e1-111">Edge</span></span>|
|<span data-ttu-id="918e1-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="918e1-112">Version</span></span>|<span data-ttu-id="918e1-113">4.5</span><span class="sxs-lookup"><span data-stu-id="918e1-113">4.5</span></span>|
|<span data-ttu-id="918e1-114">種類</span><span class="sxs-lookup"><span data-stu-id="918e1-114">Type</span></span>|<span data-ttu-id="918e1-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="918e1-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="918e1-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="918e1-116">Affected APIs</span></span>

- <xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType>

<!--

#### Affected APIs

- `E:System.Windows.ContentElement.PreviewLostKeyboardFocus`
- `E:System.Windows.IInputElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement3D.PreviewLostKeyboardFocus`

-->
