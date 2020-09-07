---
ms.openlocfilehash: 9d960774161fc44810f90ca30f56eb98f98de3ff
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496578"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="3692f-101">WPF TextBox は既定で元に戻す上限が 100 に設定される</span><span class="sxs-lookup"><span data-stu-id="3692f-101">WPF TextBox defaults to undo limit of 100</span></span>

#### <a name="details"></a><span data-ttu-id="3692f-102">説明</span><span class="sxs-lookup"><span data-stu-id="3692f-102">Details</span></span>

<span data-ttu-id="3692f-103">.NET Framework 4.5 では、WPF テキスト ボックスの既定の元に戻す上限は 100 です (.NET Framework 4.0 では無制限でした)。</span><span class="sxs-lookup"><span data-stu-id="3692f-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3692f-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="3692f-104">Suggestion</span></span>

<span data-ttu-id="3692f-105">元に戻す上限が 100 では低すぎる場合、<xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit> を使用して上限を明示的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="3692f-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>

| <span data-ttu-id="3692f-106">名前</span><span class="sxs-lookup"><span data-stu-id="3692f-106">Name</span></span>    | <span data-ttu-id="3692f-107">[値]</span><span class="sxs-lookup"><span data-stu-id="3692f-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3692f-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="3692f-108">Scope</span></span>   |<span data-ttu-id="3692f-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="3692f-109">Edge</span></span>|
|<span data-ttu-id="3692f-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="3692f-110">Version</span></span>|<span data-ttu-id="3692f-111">4.5</span><span class="sxs-lookup"><span data-stu-id="3692f-111">4.5</span></span>|
|<span data-ttu-id="3692f-112">種類</span><span class="sxs-lookup"><span data-stu-id="3692f-112">Type</span></span>|<span data-ttu-id="3692f-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="3692f-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="3692f-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="3692f-114">Affected APIs</span></span>

- <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.TextBox`

-->
