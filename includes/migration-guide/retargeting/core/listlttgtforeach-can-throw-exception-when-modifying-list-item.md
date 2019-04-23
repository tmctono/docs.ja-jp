---
ms.openlocfilehash: 4e81087431091dfa4d5432d5ea5e2b665be2b130
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774325"
---
### <a name="listtforeach-can-throw-exception-when-modifying-list-item"></a><span data-ttu-id="b3289-101">List\<T>.ForEach は、リスト項目を変更すると、例外をスローすることがあります。</span><span class="sxs-lookup"><span data-stu-id="b3289-101">List\<T>.ForEach can throw exception when modifying list item</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b3289-102">説明</span><span class="sxs-lookup"><span data-stu-id="b3289-102">Details</span></span>|<span data-ttu-id="b3289-103">.NET Framework 4.5 から、<xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> 列挙子は、呼び出し元のコレクション内の要素が変更された場合、<xref:System.InvalidOperationException?displayProperty=name> 例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="b3289-103">Beginning in .NET Framework 4.5, a <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> enumerator will throw an <xref:System.InvalidOperationException?displayProperty=name> exception if an element in the calling collection is modified.</span></span> <span data-ttu-id="b3289-104">以前は、この様な場合、例外はスローされませんでしたが、競合状態になることがありました。</span><span class="sxs-lookup"><span data-stu-id="b3289-104">Previously, this would not throw an exception but could lead to race conditions.</span></span>|
|<span data-ttu-id="b3289-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b3289-105">Suggestion</span></span>|<span data-ttu-id="b3289-106">理想的には、安全な操作ではないため、要素の列挙中にリストを変更しないようにコードを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3289-106">Ideally, code should be fixed to not modify lists while enumerating their elements because that is never a safe operation.</span></span> <span data-ttu-id="b3289-107">ただし、以前の動作に戻すには、アプリを .NET Framework 4.0 向けにできます。</span><span class="sxs-lookup"><span data-stu-id="b3289-107">To revert to the previous behavior, though, an app may target .NET Framework 4.0.</span></span>|
|<span data-ttu-id="b3289-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="b3289-108">Scope</span></span>|<span data-ttu-id="b3289-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="b3289-109">Edge</span></span>|
|<span data-ttu-id="b3289-110">Version</span><span class="sxs-lookup"><span data-stu-id="b3289-110">Version</span></span>|<span data-ttu-id="b3289-111">4.5</span><span class="sxs-lookup"><span data-stu-id="b3289-111">4.5</span></span>|
|<span data-ttu-id="b3289-112">型</span><span class="sxs-lookup"><span data-stu-id="b3289-112">Type</span></span>|<span data-ttu-id="b3289-113">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="b3289-113">Retargeting</span></span>|
|<span data-ttu-id="b3289-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="b3289-114">Affected APIs</span></span>|<ul><li><xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType></li></ul>|
