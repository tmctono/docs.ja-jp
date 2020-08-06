---
ms.openlocfilehash: 43ebb37124b8efe077b9f81fe5351bd7db2c72f7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302715"
---
### <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a><span data-ttu-id="80d93-101">Vector\<T> で、サポートされていない型に対して常に NotSupportedException がスローされる</span><span class="sxs-lookup"><span data-stu-id="80d93-101">Vector\<T> always throws NotSupportedException for unsupported types</span></span>

<span data-ttu-id="80d93-102"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> では、サポートされていない型パラメーターに対して常に <xref:System.NotSupportedException> がスローされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="80d93-102"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> now always throws a <xref:System.NotSupportedException> for unsupported type parameters.</span></span>

#### <a name="change-description"></a><span data-ttu-id="80d93-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="80d93-103">Change description</span></span>

<span data-ttu-id="80d93-104">以前の <xref:System.Numerics.Vector%601> のメンバーでは、`T` が [サポートされていない型](#unsupported-types)だった場合に、常に <xref:System.NotSupportedException> がスローされるとは限りませんでした。</span><span class="sxs-lookup"><span data-stu-id="80d93-104">Previously, members of <xref:System.Numerics.Vector%601> would not always throw a <xref:System.NotSupportedException> when `T` was an [unsupported type](#unsupported-types).</span></span> <span data-ttu-id="80d93-105">例外が常にスローされなかったのは、ハードウェアの高速化をサポートしていたコード パスが原因でした。</span><span class="sxs-lookup"><span data-stu-id="80d93-105">The exception wasn't always thrown because of code paths that supported hardware acceleration.</span></span> <span data-ttu-id="80d93-106">たとえば、ハードウェアの高速化がないプラットフォーム (ARM32 など) で `Vector<bool> + Vector<bool>` を使用すると、例外をスローするのではなく `default` が返されました。</span><span class="sxs-lookup"><span data-stu-id="80d93-106">For example, `Vector<bool> + Vector<bool>` returned `default` instead of throwing an exception on platforms that have no hardware acceleration, such as ARM32.</span></span> <span data-ttu-id="80d93-107">サポートされていない型について、<xref:System.Numerics.Vector%601> のメンバーが示す動作には、異なるプラットフォームやハードウェア構成にわたる一貫性がありませんでした。</span><span class="sxs-lookup"><span data-stu-id="80d93-107">For unsupported types, <xref:System.Numerics.Vector%601> members exhibited inconsistent behavior across different platforms and hardware configurations.</span></span>

<span data-ttu-id="80d93-108">.NET 5.0 以降、<xref:System.Numerics.Vector%601> のメンバーでは、`T` がサポートされていない型である場合に、すべてのハードウェア構成で常に <xref:System.NotSupportedException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="80d93-108">Starting in .NET 5.0, <xref:System.Numerics.Vector%601> members always throw a <xref:System.NotSupportedException> on all hardware configurations when `T` is not a supported type.</span></span>

##### <a name="unsupported-types"></a><span data-ttu-id="80d93-109">サポートされていない型</span><span class="sxs-lookup"><span data-stu-id="80d93-109">Unsupported types</span></span>

<span data-ttu-id="80d93-110"><xref:System.Numerics.Vector%601> の型パラメーターでサポートされている型は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="80d93-110">The supported types for the type parameter of <xref:System.Numerics.Vector%601> are:</span></span>

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

<span data-ttu-id="80d93-111">サポートされている型は変更されていませんが、将来変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80d93-111">The supported types have not changed, however, they may change in the future.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="80d93-112">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="80d93-112">Version introduced</span></span>

<span data-ttu-id="80d93-113">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="80d93-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="80d93-114">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="80d93-114">Recommended action</span></span>

<span data-ttu-id="80d93-115"><xref:System.Numerics.Vector%601> の型パラメーターにサポートされていない型を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="80d93-115">Don't use an unsupported type for the type parameter of <xref:System.Numerics.Vector%601>.</span></span>

#### <a name="category"></a><span data-ttu-id="80d93-116">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="80d93-116">Category</span></span>

<span data-ttu-id="80d93-117">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="80d93-117">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="80d93-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="80d93-118">Affected APIs</span></span>

- <span data-ttu-id="80d93-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> およびそのすべてのメンバー</span><span class="sxs-lookup"><span data-stu-id="80d93-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> and all its members</span></span>

<!--

#### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
