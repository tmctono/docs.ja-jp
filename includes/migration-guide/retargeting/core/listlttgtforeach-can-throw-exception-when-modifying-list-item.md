---
ms.openlocfilehash: 3300a74b81fc9eeba670ee0ceb2c2615fd3925bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617220"
---
### <a name="listlttgtforeach-can-throw-exception-when-modifying-list-item"></a><span data-ttu-id="bd7fe-101">List&lt;T&gt;.ForEach は、リスト項目を変更すると、例外をスローすることがあります。</span><span class="sxs-lookup"><span data-stu-id="bd7fe-101">List&lt;T&gt;.ForEach can throw exception when modifying list item</span></span>

#### <a name="details"></a><span data-ttu-id="bd7fe-102">説明</span><span class="sxs-lookup"><span data-stu-id="bd7fe-102">Details</span></span>

<span data-ttu-id="bd7fe-103">.NET Framework 4.5 から、<xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> 列挙子は、呼び出し元のコレクション内の要素が変更された場合、<xref:System.InvalidOperationException?displayProperty=fullName> 例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="bd7fe-103">Beginning in .NET Framework 4.5, a <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> enumerator will throw an <xref:System.InvalidOperationException?displayProperty=fullName> exception if an element in the calling collection is modified.</span></span> <span data-ttu-id="bd7fe-104">以前は、この様な場合、例外はスローされませんでしたが、競合状態になることがありました。</span><span class="sxs-lookup"><span data-stu-id="bd7fe-104">Previously, this would not throw an exception but could lead to race conditions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bd7fe-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="bd7fe-105">Suggestion</span></span>

<span data-ttu-id="bd7fe-106">理想的には、安全な操作ではないため、要素の列挙中にリストを変更しないようにコードを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd7fe-106">Ideally, code should be fixed to not modify lists while enumerating their elements because that is never a safe operation.</span></span> <span data-ttu-id="bd7fe-107">ただし、以前の動作に戻すには、アプリを .NET Framework 4.0 向けにできます。</span><span class="sxs-lookup"><span data-stu-id="bd7fe-107">To revert to the previous behavior, though, an app may target .NET Framework 4.0.</span></span>

| <span data-ttu-id="bd7fe-108">名前</span><span class="sxs-lookup"><span data-stu-id="bd7fe-108">Name</span></span>    | <span data-ttu-id="bd7fe-109">[値]</span><span class="sxs-lookup"><span data-stu-id="bd7fe-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bd7fe-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="bd7fe-110">Scope</span></span>   | <span data-ttu-id="bd7fe-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="bd7fe-111">Edge</span></span>        |
| <span data-ttu-id="bd7fe-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="bd7fe-112">Version</span></span> | <span data-ttu-id="bd7fe-113">4.5</span><span class="sxs-lookup"><span data-stu-id="bd7fe-113">4.5</span></span>         |
| <span data-ttu-id="bd7fe-114">種類</span><span class="sxs-lookup"><span data-stu-id="bd7fe-114">Type</span></span>    | <span data-ttu-id="bd7fe-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="bd7fe-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="bd7fe-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="bd7fe-116">Affected APIs</span></span>

- <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType>
