---
ms.openlocfilehash: 4fc31f75e8f8cdd50abebd399d9749688e6faa5a
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065179"
---
### <a name="ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a><span data-ttu-id="b1142-101">CA2015: MemoryManager\<T> から派生した型にはファイナライザーを定義しません</span><span class="sxs-lookup"><span data-stu-id="b1142-101">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>

<span data-ttu-id="b1142-102">.NET コード アナライザー ルール [CA2015](/visualstudio/code-quality/ca2015) は、.NET 5.0 以降では既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b1142-102">.NET code analyzer rule [CA2015](/visualstudio/code-quality/ca2015) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="b1142-103">ファイナライザーを定義する <xref:System.Buffers.MemoryManager%601> から派生したすべての型に対して、ビルドの警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="b1142-103">It produces a build warning for any types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b1142-104">変更内容</span><span class="sxs-lookup"><span data-stu-id="b1142-104">Change description</span></span>

<span data-ttu-id="b1142-105">.NET 5.0 以降、.NET SDK には [.NET ソース コード アナライザー](../../../../docs/fundamentals/productivity/code-analysis.md)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1142-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="b1142-106">これらのルールのいくつかは、[CA2015](/visualstudio/code-quality/ca2015) を含め、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b1142-106">Several of these rules are enabled, by default, including [CA2015](/visualstudio/code-quality/ca2015).</span></span> <span data-ttu-id="b1142-107">このルールに違反し、警告をエラーとして扱うように構成されているコードがプロジェクトに含まれている場合、この変更によってビルドが破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b1142-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="b1142-108">ルール CA2015 によって、ファイナライザーを定義する <xref:System.Buffers.MemoryManager%601> から派生した型にフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="b1142-108">Rule CA2015 flags types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span> <span data-ttu-id="b1142-109"><xref:System.Buffers.MemoryManager%601> から派生した型にファイナライザーを追加すると、バグが示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b1142-109">Adding a finalizer to a type that derives from <xref:System.Buffers.MemoryManager%601> is likely an indication of a bug.</span></span> <span data-ttu-id="b1142-110"><xref:System.Span%601> で取得されたネイティブ リソースはクリーンアップされている可能性がありますが、<xref:System.Span%601> によって引き続き使用されている可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="b1142-110">It suggests that a native resource that could have been obtained in a <xref:System.Span%601> is getting cleaned up, potentially while it's still in use by the <xref:System.Span%601>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b1142-111">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b1142-111">Version introduced</span></span>

<span data-ttu-id="b1142-112">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="b1142-112">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b1142-113">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="b1142-113">Recommended action</span></span>

- <span data-ttu-id="b1142-114">ファイナライザーの定義を削除します。</span><span class="sxs-lookup"><span data-stu-id="b1142-114">Remove the finalizer definition.</span></span> <span data-ttu-id="b1142-115">詳細については、[CA2015](/visualstudio/code-quality/ca2015) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1142-115">For more information, see [CA2015](/visualstudio/code-quality/ca2015).</span></span>

- <span data-ttu-id="b1142-116">コード分析を完全に無効にするには、プロジェクト ファイルで `EnableNETAnalyzers` を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1142-116">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="b1142-117">詳細については、「[EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1142-117">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="b1142-118">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="b1142-118">Category</span></span>

<span data-ttu-id="b1142-119">コード分析</span><span class="sxs-lookup"><span data-stu-id="b1142-119">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b1142-120">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="b1142-120">Affected APIs</span></span>

<span data-ttu-id="b1142-121">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="b1142-121">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
