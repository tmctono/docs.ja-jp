---
ms.openlocfilehash: 13d3799aeede86b01aa81ce1cd69b3c4c22311ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620481"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="c9fed-101">WPF TextBox は既定で元に戻す上限が 100 に設定される</span><span class="sxs-lookup"><span data-stu-id="c9fed-101">WPF TextBox defaults to undo limit of 100</span></span>

#### <a name="details"></a><span data-ttu-id="c9fed-102">説明</span><span class="sxs-lookup"><span data-stu-id="c9fed-102">Details</span></span>

<span data-ttu-id="c9fed-103">.NET Framework 4.5 では、WPF テキスト ボックスの既定の元に戻す上限は 100 です (.NET Framework 4.0 では無制限でした)。</span><span class="sxs-lookup"><span data-stu-id="c9fed-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c9fed-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c9fed-104">Suggestion</span></span>

<span data-ttu-id="c9fed-105">元に戻す上限が 100 では低すぎる場合、<xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit> を使用して上限を明示的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="c9fed-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>

| <span data-ttu-id="c9fed-106">名前</span><span class="sxs-lookup"><span data-stu-id="c9fed-106">Name</span></span>    | <span data-ttu-id="c9fed-107">[値]</span><span class="sxs-lookup"><span data-stu-id="c9fed-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c9fed-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="c9fed-108">Scope</span></span>   |<span data-ttu-id="c9fed-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="c9fed-109">Edge</span></span>|
|<span data-ttu-id="c9fed-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="c9fed-110">Version</span></span>|<span data-ttu-id="c9fed-111">4.5</span><span class="sxs-lookup"><span data-stu-id="c9fed-111">4.5</span></span>|
|<span data-ttu-id="c9fed-112">種類</span><span class="sxs-lookup"><span data-stu-id="c9fed-112">Type</span></span>|<span data-ttu-id="c9fed-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="c9fed-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c9fed-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c9fed-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
