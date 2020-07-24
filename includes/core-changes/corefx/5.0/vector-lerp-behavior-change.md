---
ms.openlocfilehash: 4bc060f991501b81db0cb7c521e55996a2b5e91e
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281306"
---
### <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a><span data-ttu-id="76553-101">Vector2.Lerp と Vector4.Lerp の動作の変更</span><span class="sxs-lookup"><span data-stu-id="76553-101">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>

<span data-ttu-id="76553-102">浮動小数点の丸め誤差を正しく考慮するように <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> と <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> の実装が変更されました。</span><span class="sxs-lookup"><span data-stu-id="76553-102">The implementation of <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> changed to correctly account for a floating-point rounding error.</span></span>

#### <a name="change-description"></a><span data-ttu-id="76553-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="76553-103">Change description</span></span>

<span data-ttu-id="76553-104">以前は、<xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> と <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> は `value1 + (value2 - value1) * amount` として実装されていました。</span><span class="sxs-lookup"><span data-stu-id="76553-104">Previously, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> were implemented as `value1 + (value2 - value1) * amount`.</span></span> <span data-ttu-id="76553-105">ただし、浮動小数点の丸め誤差のため、`amount` が `1.0f` のとき、このアルゴリズムから `value2` が返されないことがありました。</span><span class="sxs-lookup"><span data-stu-id="76553-105">However, due to a floating-point rounding error, this algorithm doesn't always return `value2` when `amount` is `1.0f`.</span></span>

<span data-ttu-id="76553-106">.NET 5.0 以降では、この実装では、<xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType> と同じアルゴリズム、すなわち `(value1 * (1.0f - amount)) + (value2 * amount)` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="76553-106">In .NET 5.0 and later, the implementation uses the same algorithm as <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, which is `(value1 * (1.0f - amount)) + (value2 * amount)`.</span></span> <span data-ttu-id="76553-107">このアルゴリズムでは、丸め誤差が正しく考慮されます。</span><span class="sxs-lookup"><span data-stu-id="76553-107">This algorithm correctly accounts for the rounding error.</span></span> <span data-ttu-id="76553-108">これで、`amount` が `1.0f` のとき、結果は正確に `value2` となります。</span><span class="sxs-lookup"><span data-stu-id="76553-108">Now, when `amount` is `1.0f`, the result is precisely `value2`.</span></span> <span data-ttu-id="76553-109">更新後のアルゴリズムではまた、利用できるとき、<xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> を利用してアルゴリズムを自由に最適化できます。</span><span class="sxs-lookup"><span data-stu-id="76553-109">The updated algorithm also allows the algorithm to be freely optimized using <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> when it's available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="76553-110">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="76553-110">Version introduced</span></span>

<span data-ttu-id="76553-111">5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="76553-111">5.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="76553-112">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="76553-112">Recommended action</span></span>

<span data-ttu-id="76553-113">必要なアクションはありません。</span><span class="sxs-lookup"><span data-stu-id="76553-113">No action is necessary.</span></span> <span data-ttu-id="76553-114">ただし、以前の動作を保持する場合、`value1 + (value2 - value1) * amount` の前のアルゴリズムを使用する独自の `Lerp` 関数を実装できます。</span><span class="sxs-lookup"><span data-stu-id="76553-114">However, if you want to maintain the old behavior, you can implement your own `Lerp` function that uses the previous algorithm of `value1 + (value2 - value1) * amount`.</span></span>

#### <a name="category"></a><span data-ttu-id="76553-115">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="76553-115">Category</span></span>

<span data-ttu-id="76553-116">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="76553-116">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="76553-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="76553-117">Affected APIs</span></span>

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->
