---
ms.openlocfilehash: 3d29848e12d496d2d53c204e00ef8604831495e1
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024701"
---
### <a name="intptr-and-uintptr-implement-iformattable"></a><span data-ttu-id="a0d2b-101">IntPtr と UIntPtr の IFormattable 実装</span><span class="sxs-lookup"><span data-stu-id="a0d2b-101">IntPtr and UIntPtr implement IFormattable</span></span>

<span data-ttu-id="a0d2b-102"><xref:System.IntPtr> と <xref:System.UIntPtr> で <xref:System.IFormattable> が実装されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a0d2b-102"><xref:System.IntPtr> and <xref:System.UIntPtr> now implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="a0d2b-103">現在、<xref:System.IFormattable> サポートを確認する関数からは、これらの型に対して異なる結果が返されることがあります。書式指定子とカルチャで渡されることがあるためです。</span><span class="sxs-lookup"><span data-stu-id="a0d2b-103">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a0d2b-104">変更の説明</span><span class="sxs-lookup"><span data-stu-id="a0d2b-104">Change description</span></span>

<span data-ttu-id="a0d2b-105">以前のバージョンの .NET では、<xref:System.IntPtr> と <xref:System.UIntPtr> では <xref:System.IFormattable> が実装されません。</span><span class="sxs-lookup"><span data-stu-id="a0d2b-105">In previous versions of .NET, <xref:System.IntPtr> and <xref:System.UIntPtr> do not implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="a0d2b-106"><xref:System.IFormattable> を確認する関数はフォールバックし、<xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> または <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType> を呼び出すことがあります。つまり、書式指定子とカルチャは無視されます。</span><span class="sxs-lookup"><span data-stu-id="a0d2b-106">Functions that check for <xref:System.IFormattable> may fall back to just calling <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> or <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, which means that format specifiers and cultures are not respected.</span></span>

<span data-ttu-id="a0d2b-107">.NET 5.0 以降のバージョンでは、<xref:System.IntPtr> と <xref:System.UIntPtr> で <xref:System.IFormattable> が実装されます。</span><span class="sxs-lookup"><span data-stu-id="a0d2b-107">In .NET 5.0 and later versions, <xref:System.IntPtr> and <xref:System.UIntPtr> implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="a0d2b-108">現在、<xref:System.IFormattable> サポートを確認する関数からは、これらの型に対して異なる結果が返されることがあります。書式指定子とカルチャで渡されることがあるためです。</span><span class="sxs-lookup"><span data-stu-id="a0d2b-108">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

<span data-ttu-id="a0d2b-109">この変更は、補間された文字列や <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> などのシナリオに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="a0d2b-109">This change impacts scenarios like interpolated strings and <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, among others.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a0d2b-110">変更理由</span><span class="sxs-lookup"><span data-stu-id="a0d2b-110">Reason for change</span></span>

<span data-ttu-id="a0d2b-111"><xref:System.IntPtr> と <xref:System.UIntPtr> は、キーワードの `nint` と `nuint` を介して C# で言語サポートされます。</span><span class="sxs-lookup"><span data-stu-id="a0d2b-111"><xref:System.IntPtr> and <xref:System.UIntPtr> now have language support in C# through the `nint` and `nuint` keywords.</span></span> <span data-ttu-id="a0d2b-112">バッキング型は、<xref:System.Int32?displayProperty=nameWithType> など、他のプリミティブ型によって公開される機能により (可能であれば) ほぼ等しくなるように更新されました。</span><span class="sxs-lookup"><span data-stu-id="a0d2b-112">The backing types were updated to provide near parity (where possible) with functionality exposed by other primitive types, such as <xref:System.Int32?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a0d2b-113">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="a0d2b-113">Version introduced</span></span>

<span data-ttu-id="a0d2b-114">5.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="a0d2b-114">5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a0d2b-115">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="a0d2b-115">Recommended action</span></span>

<span data-ttu-id="a0d2b-116">これらの型の値を表示するとき、書式指定子またはカルチャを使用しない場合、`ToString()` のオーバーロードの <xref:System.IntPtr.ToString?displayProperty=nameWithType> と <xref:System.UIntPtr.ToString?displayProperty=nameWithType> を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a0d2b-116">If you don't want a format specifier or custom culture to be used when displaying values of these types, you can call the <xref:System.IntPtr.ToString?displayProperty=nameWithType> and <xref:System.UIntPtr.ToString?displayProperty=nameWithType> overloads of `ToString()`.</span></span>

#### <a name="category"></a><span data-ttu-id="a0d2b-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="a0d2b-117">Category</span></span>

<span data-ttu-id="a0d2b-118">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="a0d2b-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a0d2b-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="a0d2b-119">Affected APIs</span></span>

<span data-ttu-id="a0d2b-120">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="a0d2b-120">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
