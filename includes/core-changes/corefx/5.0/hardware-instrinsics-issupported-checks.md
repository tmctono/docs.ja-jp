---
ms.openlocfilehash: bba9659b92e5aabc276c585929c99898316036c5
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359137"
---
### <a name="hardware-intrinsic-issupported-checks-may-differ-for-nested-types"></a><span data-ttu-id="34854-101">ハードウェアに組み込みの IsSupported チェックは、入れ子にされた型によって異なる場合があります</span><span class="sxs-lookup"><span data-stu-id="34854-101">Hardware intrinsic IsSupported checks may differ for nested types</span></span>

<span data-ttu-id="34854-102">`<Isa>.X64.IsSupported` (`<Isa>` は <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> 名前空間のクラスを指す) をチェックすると、場合によっては、前のバージョンの .NET とは異なる結果が生成されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="34854-102">Checking `<Isa>.X64.IsSupported`, where `<Isa>` refers to the classes in the <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> namespace, may now produce a different result to previous versions of .NET.</span></span>

> [!TIP]
> <span data-ttu-id="34854-103">*ISA* は業界標準アーキテクチャの略です。</span><span class="sxs-lookup"><span data-stu-id="34854-103">*ISA* stands for industry standard architecture.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="34854-104">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="34854-104">Version introduced</span></span>

<span data-ttu-id="34854-105">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="34854-105">5.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="34854-106">変更内容</span><span class="sxs-lookup"><span data-stu-id="34854-106">Change description</span></span>

<span data-ttu-id="34854-107">.NET の前のバージョンでは、ハードウェアに組み込まれている型 <xref:System.Runtime.Intrinsics.X86> (たとえば、<xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType>) で、入れ子にされた `X64` クラスが公開されませんでした。</span><span class="sxs-lookup"><span data-stu-id="34854-107">In previous versions of .NET, some of the <xref:System.Runtime.Intrinsics.X86> hardware-intrinsic types, for example, <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType>, didn't expose a nested `X64` class.</span></span> <span data-ttu-id="34854-108">このような型の場合、`<Isa>.X64.IsSupported` を呼び出すと、`<Isa>` の親クラスの入れ子 `X64` クラスで `IsSupported` プロパティに解決されました。</span><span class="sxs-lookup"><span data-stu-id="34854-108">For these types, calling `<Isa>.X64.IsSupported` resolved to an `IsSupported` property on a nested `X64` class of a parent class of `<Isa>`.</span></span> <span data-ttu-id="34854-109">これは、`<Isa>.IsSupported` で `false` が返されるときでも、このプロパティで `true` が返される可能性を意味しました。</span><span class="sxs-lookup"><span data-stu-id="34854-109">This meant that the property could return `true` even when `<Isa>.IsSupported` returns `false`.</span></span>

<span data-ttu-id="34854-110">.NET 5.0 以降のバージョンでは、すべての <xref:System.Runtime.Intrinsics.X86> 型で、サポートを適宜報告する入れ子 `X64` クラスが公開されます。</span><span class="sxs-lookup"><span data-stu-id="34854-110">In .NET 5.0 and later versions, all of the <xref:System.Runtime.Intrinsics.X86> types expose a nested `X64` class that appropriately reports support.</span></span> <span data-ttu-id="34854-111">これにより、一般階層が正しく維持され、`<Isa>.X64.IsSupported` が `true` の場合、`<Isa>.IsSupported` も `true` になると想定できます。</span><span class="sxs-lookup"><span data-stu-id="34854-111">This ensures that the general hierarchy remains correct, and that if `<Isa>.X64.IsSupported` is `true`, then `<Isa>.IsSupported` can also be assumed to be `true`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="34854-112">変更理由</span><span class="sxs-lookup"><span data-stu-id="34854-112">Reason for change</span></span>

<span data-ttu-id="34854-113">`<Isa>.X64.IsSupported` が `true` の場合、`<Isa>.IsSupported` も暗黙的に `true` になることが意図されていました。</span><span class="sxs-lookup"><span data-stu-id="34854-113">It was intended that if `<Isa>.X64.IsSupported` is `true`, `<Isa>.IsSupported` is also implied to be `true`.</span></span> <span data-ttu-id="34854-114">しかしながら、C# におけるメンバー解決のしくみに起因し、入れ子 `X64` クラスが与えられていないクラスでは意図どおりになるとは限らず、ユーザー コードでバグが見つかる状況が発生しました。</span><span class="sxs-lookup"><span data-stu-id="34854-114">However, due to how member resolution works in C#, classes that didn't have a nested `X64` class exposed a situation where this wasn't always the case and led to bugs in user code.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="34854-115">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="34854-115">Recommended action</span></span>

<span data-ttu-id="34854-116">必要に応じて、該当する ISA がないか確認するよう、`IsSupported` をチェックするコードを調整します。</span><span class="sxs-lookup"><span data-stu-id="34854-116">If necessary, adjust code that checks `IsSupported` to check for the appropriate ISA.</span></span>

#### <a name="category"></a><span data-ttu-id="34854-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="34854-117">Category</span></span>

<span data-ttu-id="34854-118">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="34854-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="34854-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="34854-119">Affected APIs</span></span>

- <xref:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported`

-->
