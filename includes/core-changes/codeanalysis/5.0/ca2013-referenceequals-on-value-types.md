---
ms.openlocfilehash: b01424c63d6e7956127bf889c53422b60ba2f219
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065207"
---
### <a name="ca2013-do-not-use-referenceequals-with-value-types"></a><span data-ttu-id="3ac09-101">CA2013: 値の型と共に ReferenceEquals を使用しないでください</span><span class="sxs-lookup"><span data-stu-id="3ac09-101">CA2013: Do not use ReferenceEquals with value types</span></span>

<span data-ttu-id="3ac09-102">.NET コード アナライザー ルール [CA2013](/visualstudio/code-quality/ca2013) は、.NET 5.0 以降では既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="3ac09-102">.NET code analyzer rule [CA2013](/visualstudio/code-quality/ca2013) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="3ac09-103"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> を使用して 1 つまたは複数の値の型の等価性を比較するコードについては、ビルド警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3ac09-103">It produces a build warning for any code where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3ac09-104">変更内容</span><span class="sxs-lookup"><span data-stu-id="3ac09-104">Change description</span></span>

<span data-ttu-id="3ac09-105">.NET 5.0 以降、.NET SDK には [.NET ソース コード アナライザー](../../../../docs/fundamentals/productivity/code-analysis.md)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ac09-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="3ac09-106">これらのルールのいくつかは、[CA2013](/visualstudio/code-quality/ca2013) を含め、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="3ac09-106">Several of these rules are enabled, by default, including [CA2013](/visualstudio/code-quality/ca2013).</span></span> <span data-ttu-id="3ac09-107">このルールに違反し、警告をエラーとして扱うように構成されているコードがプロジェクトに含まれている場合、この変更によってビルドが破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ac09-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="3ac09-108"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> を使用して 1 または複数の値の型の等価性を比較するインスタンスが、ルール CA2013 によって検出されます。</span><span class="sxs-lookup"><span data-stu-id="3ac09-108">Rule CA2013 finds instances where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span> <span data-ttu-id="3ac09-109">このように値の型の等価性を比較すると、値がボックス化されてから比較が行われるため、結果が不正確になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ac09-109">Comparing value types for equality in this way can lead to incorrect results, because the values are boxed before they're compared.</span></span> <span data-ttu-id="3ac09-110">比較した値が、同じ値の型のインスタンスを表す場合でも、<xref:System.Object.ReferenceEquals(System.Object,System.Object)> からは `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="3ac09-110"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> will return `false` even if the compared values represent the same instance of a value type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3ac09-111">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="3ac09-111">Version introduced</span></span>

<span data-ttu-id="3ac09-112">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="3ac09-112">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3ac09-113">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="3ac09-113">Recommended action</span></span>

- <span data-ttu-id="3ac09-114">適切な等値演算子 (`==` など) を使用するようにコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="3ac09-114">Change the code to use an appropriate equality operator, such as `==`.</span></span> <span data-ttu-id="3ac09-115">この警告を抑制しないでください。</span><span class="sxs-lookup"><span data-stu-id="3ac09-115">You should not suppress this warning.</span></span>

- <span data-ttu-id="3ac09-116">コード分析を完全に無効にするには、プロジェクト ファイルで `EnableNETAnalyzers` を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="3ac09-116">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="3ac09-117">詳細については、「[EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ac09-117">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="3ac09-118">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="3ac09-118">Category</span></span>

<span data-ttu-id="3ac09-119">コード分析</span><span class="sxs-lookup"><span data-stu-id="3ac09-119">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3ac09-120">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="3ac09-120">Affected APIs</span></span>

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

-->
