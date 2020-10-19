---
ms.openlocfilehash: 24b88b3ba1b6cfe9fb9fb1f6398a6daeb57596a9
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756112"
---
### <a name="order-of-tags-in-activitytags-is-reversed"></a><span data-ttu-id="e650a-101">Activity.Tags 内のタグの順序が逆になっている</span><span class="sxs-lookup"><span data-stu-id="e650a-101">Order of tags in Activity.Tags is reversed</span></span>

<span data-ttu-id="e650a-102"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> では、追加された順に項目がリストに格納されるようになりました。つまり、最初に追加された項目がリストの先頭になります。</span><span class="sxs-lookup"><span data-stu-id="e650a-102"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> now stores items in the list according to the order they are added, that is, the first item that's added is first in the list.</span></span> <span data-ttu-id="e650a-103">この変更は、[OpenTelemetry Attributes 仕様](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes)と一致させるために行われました。</span><span class="sxs-lookup"><span data-stu-id="e650a-103">This change was made to match the [OpenTelemetry Attributes specification](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).</span></span>

#### <a name="change-description"></a><span data-ttu-id="e650a-104">変更内容</span><span class="sxs-lookup"><span data-stu-id="e650a-104">Change description</span></span>

<span data-ttu-id="e650a-105">以前のバージョンの .NET では、<xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> により追加されたのと逆の順序で項目が格納されます。</span><span class="sxs-lookup"><span data-stu-id="e650a-105">In previous .NET versions, <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> stores items in the reverse order from which they're added.</span></span> <span data-ttu-id="e650a-106">つまり、最初に追加された項目がリストの末尾になります。</span><span class="sxs-lookup"><span data-stu-id="e650a-106">That is, the first item added is last in the list.</span></span> <span data-ttu-id="e650a-107">.NET 5.0 以降では、項目の順序は逆になり、最初に追加された項目が常にリストの先頭になります。</span><span class="sxs-lookup"><span data-stu-id="e650a-107">Starting in .NET 5.0, the order of the items is reversed, and the first item added is always first in the list.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e650a-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="e650a-108">Version introduced</span></span>

<span data-ttu-id="e650a-109">5.0</span><span class="sxs-lookup"><span data-stu-id="e650a-109">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e650a-110">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="e650a-110">Recommended action</span></span>

<span data-ttu-id="e650a-111">ご使用のアプリが <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> リストの順序に依存していて、.NET 5.0 以降にアップグレードする場合は、コードのこの部分を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e650a-111">If your app has a dependency on the <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> list order and you're upgrading to .NET 5.0 or later, you'll need to change this part of your code.</span></span>

#### <a name="category"></a><span data-ttu-id="e650a-112">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="e650a-112">Category</span></span>

<span data-ttu-id="e650a-113">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="e650a-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e650a-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e650a-114">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
