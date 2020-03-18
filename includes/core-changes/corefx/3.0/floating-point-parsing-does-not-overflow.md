---
ms.openlocfilehash: 30580b3fde5b8a99862896bb7d31c6c4024f97e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568085"
---
### <a name="floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception"></a><span data-ttu-id="f4e9f-101">浮動小数点の解析操作が失敗したり OverflowException がスローされたりすることがなくなった</span><span class="sxs-lookup"><span data-stu-id="f4e9f-101">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>

<span data-ttu-id="f4e9f-102">浮動小数点の解析メソッドが、<xref:System.OverflowException> または `false` 浮動小数点の型の範囲外の数値を持つ文字列を解析する場合に、<xref:System.Single> をスローしたり、<xref:System.Double> を返したりすることがなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f4e9f-102">The floating-point parsing methods no longer throw an <xref:System.OverflowException> or return `false` when they parse a string whose numeric value is outside the range of the <xref:System.Single> or <xref:System.Double> floating-point type.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f4e9f-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="f4e9f-103">Change description</span></span>

<span data-ttu-id="f4e9f-104">.NET Core 2.2 以前のバージョンでは、<xref:System.Double.Parse%2A?displayProperty=nameWithType> および <xref:System.Single.Parse%2A?displayProperty=nameWithType> メソッドは、それぞれの型の範囲外の値に対して、<xref:System.OverflowException> をスローします。</span><span class="sxs-lookup"><span data-stu-id="f4e9f-104">In .NET Core 2.2 and earlier versions, the <xref:System.Double.Parse%2A?displayProperty=nameWithType> and <xref:System.Single.Parse%2A?displayProperty=nameWithType> methods throw an <xref:System.OverflowException> for values that outside the range of their respective type.</span></span> <span data-ttu-id="f4e9f-105"><xref:System.Double.TryParse%2A?displayProperty=nameWithType> および <xref:System.Single.TryParse%2A?displayProperty=nameWithType> メソッドは、範囲外の数値を持つ文字列表現に対して `false` を返します。</span><span class="sxs-lookup"><span data-stu-id="f4e9f-105">The <xref:System.Double.TryParse%2A?displayProperty=nameWithType> and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> methods return `false` for the string representations of out-of-range numeric values.</span></span>

<span data-ttu-id="f4e9f-106">.NET Core 3.0 以降、範囲外の数値文字列を解析するときに、<xref:System.Double.Parse%2A?displayProperty=nameWithType>、<xref:System.Double.TryParse%2A?displayProperty=nameWithType>、<xref:System.Single.Parse%2A?displayProperty=nameWithType>、および <xref:System.Single.TryParse%2A?displayProperty=nameWithType> の各メソッドが失敗しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f4e9f-106">Starting with .NET Core 3.0, the <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType>, and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> methods no longer fail when parsing out-of-range numeric strings.</span></span> <span data-ttu-id="f4e9f-107">代わりに、<xref:System.Double> の解析メソッドが、<xref:System.Double.PositiveInfinity?displayProperty=nameWithType> を超過する値に対して <xref:System.Double.MaxValue?displayProperty=nameWithType> を返し、また <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> 未満の値に対して <xref:System.Double.MinValue?displayProperty=nameWithType> を返すようになりました。</span><span class="sxs-lookup"><span data-stu-id="f4e9f-107">Instead, the <xref:System.Double> parsing methods return <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> for values that exceed <xref:System.Double.MaxValue?displayProperty=nameWithType>, and they return <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> for values that are less than <xref:System.Double.MinValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f4e9f-108">同様に、<xref:System.Single> の解析メソッドが、<xref:System.Single.PositiveInfinity?displayProperty=nameWithType> を超過する値に対して <xref:System.Single.MaxValue?displayProperty=nameWithType> を返し、また <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> 未満の値に対して <xref:System.Single.MinValue?displayProperty=nameWithType> を返すようになりました。</span><span class="sxs-lookup"><span data-stu-id="f4e9f-108">Similarly, the <xref:System.Single> parsing methods return <xref:System.Single.PositiveInfinity?displayProperty=nameWithType> for values that exceed <xref:System.Single.MaxValue?displayProperty=nameWithType>, and they return <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> for values that are less than <xref:System.Single.MinValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="f4e9f-109">この変更は、IEEE 754:2008 に対する準拠の改善のために行われました。</span><span class="sxs-lookup"><span data-stu-id="f4e9f-109">This change was made for improved IEEE 754:2008 compliance.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f4e9f-110">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f4e9f-110">Version introduced</span></span>

<span data-ttu-id="f4e9f-111">3.0</span><span class="sxs-lookup"><span data-stu-id="f4e9f-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f4e9f-112">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="f4e9f-112">Recommended action</span></span>

<span data-ttu-id="f4e9f-113">この変更は、次の 2 つのいずれかの方法でコードに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4e9f-113">This change can affect your code in either of two ways:</span></span>

- <span data-ttu-id="f4e9f-114">コードは、オーバーフローが発生したときに実行される <xref:System.OverflowException> のハンドラーに依存します。</span><span class="sxs-lookup"><span data-stu-id="f4e9f-114">Your code depends on the handler for the <xref:System.OverflowException> to execute when an overflow occurs.</span></span> <span data-ttu-id="f4e9f-115">この場合、`catch` ステートメントを削除し、`If` または <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> が <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> であるかをテストする任意のコードを `true` ステートメントに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4e9f-115">In this case, you should remove the `catch` statement and place any necessary code in an `If` statement that tests whether <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> or <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> is `true`.</span></span>

- <span data-ttu-id="f4e9f-116">コードは、浮動小数点値が `Infinity` ではないことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="f4e9f-116">Your code assumes that floating-point values are not `Infinity`.</span></span> <span data-ttu-id="f4e9f-117">この場合は、必要な `PositiveInfinity` および `NegativeInfinity` の浮動小数点値を確認するコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4e9f-117">In this case, you should add the necessary code to check for floating-point values of `PositiveInfinity` and `NegativeInfinity`.</span></span>

#### <a name="category"></a><span data-ttu-id="f4e9f-118">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="f4e9f-118">Category</span></span>

<span data-ttu-id="f4e9f-119">CoreFx</span><span class="sxs-lookup"><span data-stu-id="f4e9f-119">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f4e9f-120">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="f4e9f-120">Affected APIs</span></span>

- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
